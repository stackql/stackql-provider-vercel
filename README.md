# `vercel` provider for [`stackql`](https://github.com/stackql/stackql)

This repository is used to generate and document the `vercel` provider for StackQL, allowing you to query and manipulate Vercel resources using SQL-like syntax. The provider is built using the `@stackql/provider-utils` package, which provides tools for converting OpenAPI specifications into StackQL-compatible provider schemas.

## Prerequisites

To use the Vercel provider with StackQL, you'll need:

1. A Vercel account with appropriate API credentials
2. A Vercel API token with sufficient permissions for the resources you want to access
3. StackQL CLI installed on your system (see [StackQL](https://github.com/stackql/stackql))

## 1. Download the Open API Specification

First, download the Vercel API OpenAPI specification:

```bash
rm -rf provider-dev/downloaded/*
curl -L https://openapi.vercel.sh/openapi.yaml \
  -o provider-dev/downloaded/vercel-openapi.yaml

# Convert YAML to JSON if needed
python3 provider-dev/scripts/yaml_to_json.py \
  --input provider-dev/downloaded/vercel-openapi.yaml \
  --output provider-dev/downloaded/openapi.json
```

## 2. Split into Service Specs

Next, split the monolithic OpenAPI specification into service-specific files:

```bash
rm -rf provider-dev/source/*
npm run split -- \
  --provider-name vercel \
  --api-doc provider-dev/downloaded/openapi.json \
  --svc-discriminator tag \
  --output-dir provider-dev/source \
  --overwrite \
  --svc-name-overrides "$(cat <<EOF
{
  "deployments": "deployments",
  "projects": "projects",
  "domains": "domains",
  "teams": "teams",
  "users": "users",
  "authentication": "auth",
  "environments": "env",
  "edge-config": "edge_config",
  "edge-functions": "edge_functions",
  "webhooks": "webhooks"
}
EOF
)"
```

## 3. Generate Mappings

Generate the mapping configuration that connects OpenAPI operations to StackQL resources:

```bash
npm run generate-mappings -- \
  --provider-name vercel \
  --input-dir provider-dev/source \
  --output-dir provider-dev/config
```

Update the resultant `provider-dev/config/all_services.csv` to add the `stackql_resource_name`, `stackql_method_name`, `stackql_verb` values for each operation.

## 4. Generate Provider

This step transforms the split OpenAPI service specs into a fully-functional StackQL provider by applying the resource and method mappings defined in your CSV file.

```bash
rm -rf provider-dev/openapi/*
npm run generate-provider -- \
  --provider-name vercel \
  --input-dir provider-dev/source \
  --output-dir provider-dev/openapi/src/vercel \
  --config-path provider-dev/config/all_services.csv \
  --servers '[{"url": "https://api.vercel.com"}]' \
  --provider-config '{"auth": {"credentialsenvvar": "VERCEL_TOKEN", "type": "bearer"}}' \
  --overwrite
```

## 5. Test Provider

### Starting the StackQL Server

Before running tests, start a StackQL server with your provider:

```bash
PROVIDER_REGISTRY_ROOT_DIR="$(pwd)/provider-dev/openapi"
npm run start-server -- --provider vercel --registry $PROVIDER_REGISTRY_ROOT_DIR
```

### Test Meta Routes

Test all metadata routes (services, resources, methods) in the provider:

```bash
npm run test-meta-routes -- vercel --verbose
```

When you're done testing, stop the StackQL server:

```bash
npm run stop-server
```

Use this command to view the server status:

```bash
npm run server-status
```

### Run test queries

Run some test queries against the provider using the `stackql shell`:

```bash
PROVIDER_REGISTRY_ROOT_DIR="$(pwd)/provider-dev/openapi"
REG_STR='{"url": "file://'${PROVIDER_REGISTRY_ROOT_DIR}'", "localDocRoot": "'${PROVIDER_REGISTRY_ROOT_DIR}'", "verifyConfig": {"nopVerify": true}}'
./stackql shell --registry="${REG_STR}"
```

Example queries to try:

```sql
-- List all your Vercel projects
SELECT 
id,
name,
created_at,
updated_at,
framework,
public_source,
root_directory,
build_command,
dev_command,
install_command,
output_directory
FROM vercel.projects.projects;

-- Get all deployments
SELECT
id,
name,
url,
created_at,
state,
meta,
project_id,
target,
type,
creator_id,
team_id
FROM vercel.deployments.deployments;

-- List domains
SELECT
id,
name,
service_type,
verified,
nsVerified,
created_at,
expires_at,
cdn_enabled,
project_id
FROM vercel.domains.domains;

-- View team members
SELECT
uid,
role,
name,
email,
created_at
FROM vercel.teams.members
WHERE team_id = 'team_12345';

-- List environment variables for a project
SELECT
id,
key,
value,
target,
type,
created_at,
updated_at,
git_branch
FROM vercel.env.env_vars
WHERE project_id = 'prj_12345';

-- View Edge Config items
SELECT
key,
value,
edge_config_id
FROM vercel.edge_config.items
WHERE edge_config_id = 'ecfg_12345';
```

## 6. Publish the provider

To publish the provider push the `vercel` dir to `providers/src` in a feature branch of the [`stackql-provider-registry`](https://github.com/stackql/stackql-provider-registry). Follow the [registry release flow](https://github.com/stackql/stackql-provider-registry/blob/dev/docs/build-and-deployment.md).  

Launch the StackQL shell:

```bash
export DEV_REG="{ \"url\": \"https://registry-dev.stackql.app/providers\" }"
./stackql --registry="${DEV_REG}" shell
```

Pull the latest dev `vercel` provider:

```sql
registry pull vercel;
```

Run some test queries to verify the provider works as expected.

## 7. Generate web docs

Provider doc microsites are built using Docusaurus and published using GitHub Pages.  

a. Update `headerContent1.txt` and `headerContent2.txt` accordingly in `provider-dev/docgen/provider-data/`  

b. Update the following in `website/docusaurus.config.js`:  

```js
// Provider configuration - change these for different providers
const providerName = "vercel";
const providerTitle = "Vercel Provider";
```

c. Then generate docs using...

```bash
npm run generate-docs -- \
  --provider-name vercel \
  --provider-dir ./provider-dev/openapi/src/vercel/v00.00.00000 \
  --output-dir ./website \
  --provider-data-dir ./provider-dev/docgen/provider-data
```  

## 8. Test web docs locally

```bash
cd website
# test build
yarn build

# run local dev server
yarn start
```

## 9. Publish web docs to GitHub Pages

Under __Pages__ in the repository, in the __Build and deployment__ section select __GitHub Actions__ as the __Source__. In Netlify DNS create the following records:

| Source Domain | Record Type  | Target |
|---------------|--------------|--------|
| vercel-provider.stackql.io | CNAME | stackql.github.io. |

## License

MIT

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.