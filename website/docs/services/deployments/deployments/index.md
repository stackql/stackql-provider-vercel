--- 
title: deployments
hide_title: false
hide_table_of_contents: false
keywords:
  - deployments
  - deployments
  - vercel
  - infrastructure-as-code
  - configuration-as-data
  - cloud inventory
description: Query, deploy and manage vercel resources using SQL
custom_edit_url: null
image: /img/stackql-vercel-provider-featured-image.png
---

import CopyableCode from '@site/src/components/CopyableCode/CopyableCode';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Creates, updates, deletes, gets or lists a <code>deployments</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>deployments</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.deployments.deployments" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_deployment"
    values={[
        { label: 'get_deployment', value: 'get_deployment' },
        { label: 'get_deployments', value: 'get_deployments' }
    ]}
>
<TabItem value="get_deployment">

The deployment including only public information<br />The deployment including both public and private information

<table>
<thead>
    <tr>
    <th>Name</th>
    <th>Datatype</th>
    <th>Description</th>
    </tr>
</thead>
<tbody>
</tbody>
</table>
</TabItem>
<TabItem value="get_deployments">

<table>
<thead>
    <tr>
    <th>Name</th>
    <th>Datatype</th>
    <th>Description</th>
    </tr>
</thead>
<tbody>
<tr>
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td>The name of the deployment. (example: docs)</td>
</tr>
<tr>
    <td><CopyableCode code="aliasAssigned" /></td>
    <td><code></code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="aliasError" /></td>
    <td><code>object</code></td>
    <td>An error object in case aliasing of the deployment failed.</td>
</tr>
<tr>
    <td><CopyableCode code="buildingAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp of when the deployment started building at.</td>
</tr>
<tr>
    <td><CopyableCode code="checksConclusion" /></td>
    <td><code>string</code></td>
    <td>Conclusion for checks</td>
</tr>
<tr>
    <td><CopyableCode code="checksState" /></td>
    <td><code>string</code></td>
    <td>State of all registered checks</td>
</tr>
<tr>
    <td><CopyableCode code="connectBuildsEnabled" /></td>
    <td><code>boolean</code></td>
    <td>The flag saying if Vercel Connect configuration is used for builds</td>
</tr>
<tr>
    <td><CopyableCode code="connectConfigurationId" /></td>
    <td><code>string</code></td>
    <td>The ID of Vercel Connect configuration used for this deployment</td>
</tr>
<tr>
    <td><CopyableCode code="created" /></td>
    <td><code>number</code></td>
    <td>Timestamp of when the deployment got created.</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp of when the deployment got created.</td>
</tr>
<tr>
    <td><CopyableCode code="creator" /></td>
    <td><code>object</code></td>
    <td>Metadata information of the user who created the deployment.</td>
</tr>
<tr>
    <td><CopyableCode code="inspectorUrl" /></td>
    <td><code>string</code></td>
    <td>Vercel URL to inspect the deployment. (example: https://vercel.com/acme/nextjs/J1hXN00qjUeoYfpEEf7dnDtpSiVq)</td>
</tr>
<tr>
    <td><CopyableCode code="isRollbackCandidate" /></td>
    <td><code>boolean</code></td>
    <td>Deployment can be used for instant rollback</td>
</tr>
<tr>
    <td><CopyableCode code="meta" /></td>
    <td><code>object</code></td>
    <td>Metadata information from the Git provider.</td>
</tr>
<tr>
    <td><CopyableCode code="projectSettings" /></td>
    <td><code>object</code></td>
    <td>The project settings which was used for this deployment</td>
</tr>
<tr>
    <td><CopyableCode code="ready" /></td>
    <td><code>number</code></td>
    <td>Timestamp of when the deployment got ready.</td>
</tr>
<tr>
    <td><CopyableCode code="readyState" /></td>
    <td><code>string</code></td>
    <td>In which state is the deployment. (example: READY)</td>
</tr>
<tr>
    <td><CopyableCode code="readySubstate" /></td>
    <td><code>string</code></td>
    <td>Since June 2023 Substate of deployment when readyState is 'READY' Tracks whether or not deployment has seen production traffic: - STAGED: never seen production traffic - PROMOTED: has seen production traffic</td>
</tr>
<tr>
    <td><CopyableCode code="source" /></td>
    <td><code>string</code></td>
    <td>The source of the deployment. (example: cli)</td>
</tr>
<tr>
    <td><CopyableCode code="state" /></td>
    <td><code>string</code></td>
    <td>In which state is the deployment. (example: READY)</td>
</tr>
<tr>
    <td><CopyableCode code="target" /></td>
    <td><code>string</code></td>
    <td>On which environment has the deployment been deployed to. (example: production)</td>
</tr>
<tr>
    <td><CopyableCode code="type" /></td>
    <td><code>string</code></td>
    <td>The type of the deployment. (example: LAMBDAS)</td>
</tr>
<tr>
    <td><CopyableCode code="uid" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the deployment. (example: dpl_2euZBFqxYdDMDG1jTrHFnNZ2eUVa)</td>
</tr>
<tr>
    <td><CopyableCode code="url" /></td>
    <td><code>string</code></td>
    <td>The URL of the deployment. (example: docs-9jaeg38me.vercel.app)</td>
</tr>
</tbody>
</table>
</TabItem>
</Tabs>

## Methods

The following methods are available for this resource:

<table>
<thead>
    <tr>
    <th>Name</th>
    <th>Accessible by</th>
    <th>Required Params</th>
    <th>Optional Params</th>
    <th>Description</th>
    </tr>
</thead>
<tbody>
<tr>
    <td><a href="#get_deployment"><CopyableCode code="get_deployment" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-idOrUrl"><code>idOrUrl</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-withGitRepoInfo"><code>withGitRepoInfo</code></a></td>
    <td>Retrieves information for a deployment either by supplying its ID (`id` property) or Hostname (`url` property). Additional details will be included when the authenticated user or team is an owner of the deployment.</td>
</tr>
<tr>
    <td><a href="#get_deployments"><CopyableCode code="get_deployments" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-app"><code>app</code></a>, <a href="#parameter-from"><code>from</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-projectId"><code>projectId</code></a>, <a href="#parameter-target"><code>target</code></a>, <a href="#parameter-to"><code>to</code></a>, <a href="#parameter-users"><code>users</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-state"><code>state</code></a>, <a href="#parameter-rollbackCandidate"><code>rollbackCandidate</code></a></td>
    <td>List deployments under the authenticated user or team. If a deployment hasn't finished uploading (is incomplete), the `url` property will have a value of `null`.</td>
</tr>
<tr>
    <td><a href="#create_deployment"><CopyableCode code="create_deployment" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__name"><code>data__name</code></a>, <a href="#parameter-data__project"><code>data__project</code></a>, <a href="#parameter-data__connection_uris"><code>data__connection_uris</code></a>, <a href="#parameter-data__roles"><code>data__roles</code></a>, <a href="#parameter-data__databases"><code>data__databases</code></a>, <a href="#parameter-data__branch"><code>data__branch</code></a>, <a href="#parameter-data__endpoints"><code>data__endpoints</code></a>, <a href="#parameter-data__endpoint"><code>data__endpoint</code></a>, <a href="#parameter-data__database"><code>data__database</code></a>, <a href="#parameter-data__role"><code>data__role</code></a>, <a href="#parameter-data__password"><code>data__password</code></a>, <a href="#parameter-data__projects"><code>data__projects</code></a>, <a href="#parameter-data__pagination"><code>data__pagination</code></a></td>
    <td><a href="#parameter-forceNew"><code>forceNew</code></a>, <a href="#parameter-skipAutoDetectionConfirmation"><code>skipAutoDetectionConfirmation</code></a></td>
    <td>Create a new deployment with all the required and intended data. If the deployment is not a git deployment, all files must be provided with the request, either referenced or inlined. Additionally, a deployment id can be specified to redeploy a previous deployment.</td>
</tr>
<tr>
    <td><a href="#delete_deployment"><CopyableCode code="delete_deployment" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-url"><code>url</code></a></td>
    <td>This API allows you to delete a deployment, either by supplying its `id` in the URL or the `url` of the deployment as a query parameter. You can obtain the ID, for example, by listing all deployments.</td>
</tr>
<tr>
    <td><a href="#cancel_deployment"><CopyableCode code="cancel_deployment" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>This endpoint allows you to cancel a deployment which is currently building, by supplying its `id` in the URL.</td>
</tr>
<tr>
    <td><a href="#_get_deployments"><CopyableCode code="_get_deployments" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-app"><code>app</code></a>, <a href="#parameter-from"><code>from</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-projectId"><code>projectId</code></a>, <a href="#parameter-target"><code>target</code></a>, <a href="#parameter-to"><code>to</code></a>, <a href="#parameter-users"><code>users</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-state"><code>state</code></a>, <a href="#parameter-rollbackCandidate"><code>rollbackCandidate</code></a></td>
    <td>List deployments under the authenticated user or team. If a deployment hasn't finished uploading (is incomplete), the `url` property will have a value of `null`.</td>
</tr>
</tbody>
</table>

## Parameters

Parameters can be passed in the `WHERE` clause of a query. Check the [Methods](#methods) section to see which parameters are required or optional for each operation.

<table>
<thead>
    <tr>
    <th>Name</th>
    <th>Datatype</th>
    <th>Description</th>
    </tr>
</thead>
<tbody>
<tr id="parameter-id">
    <td><CopyableCode code="id" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the deployment.</td>
</tr>
<tr id="parameter-idOrUrl">
    <td><CopyableCode code="idOrUrl" /></td>
    <td><code>string</code></td>
    <td>The unique identifier or hostname of the deployment.</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-app">
    <td><CopyableCode code="app" /></td>
    <td><code>string</code></td>
    <td>Name of the deployment.</td>
</tr>
<tr id="parameter-forceNew">
    <td><CopyableCode code="forceNew" /></td>
    <td><code></code></td>
    <td>Forces a new deployment even if there is a previous similar deployment</td>
</tr>
<tr id="parameter-from">
    <td><CopyableCode code="from" /></td>
    <td><code>number</code></td>
    <td>Gets the deployment created after this Date timestamp. (default: current time)</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>number</code></td>
    <td>Maximum number of deployments to list from a request.</td>
</tr>
<tr id="parameter-projectId">
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td>Filter deployments from the given `projectId`.</td>
</tr>
<tr id="parameter-rollbackCandidate">
    <td><CopyableCode code="rollbackCandidate" /></td>
    <td><code>boolean</code></td>
    <td>Filter deployments based on their rollback candidacy</td>
</tr>
<tr id="parameter-since">
    <td><CopyableCode code="since" /></td>
    <td><code>number</code></td>
    <td>Get Deployments created after this JavaScript timestamp.</td>
</tr>
<tr id="parameter-skipAutoDetectionConfirmation">
    <td><CopyableCode code="skipAutoDetectionConfirmation" /></td>
    <td><code></code></td>
    <td>Allows to skip framework detection so the API would not fail to ask for confirmation</td>
</tr>
<tr id="parameter-state">
    <td><CopyableCode code="state" /></td>
    <td><code>string</code></td>
    <td>Filter deployments based on their state (`BUILDING`, `ERROR`, `INITIALIZING`, `QUEUED`, `READY`, `CANCELED`)</td>
</tr>
<tr id="parameter-target">
    <td><CopyableCode code="target" /></td>
    <td><code>string</code></td>
    <td>Filter deployments based on the environment.</td>
</tr>
<tr id="parameter-to">
    <td><CopyableCode code="to" /></td>
    <td><code>number</code></td>
    <td>Gets the deployment created before this Date timestamp. (default: current time)</td>
</tr>
<tr id="parameter-until">
    <td><CopyableCode code="until" /></td>
    <td><code>number</code></td>
    <td>Get Deployments created before this JavaScript timestamp.</td>
</tr>
<tr id="parameter-url">
    <td><CopyableCode code="url" /></td>
    <td><code>string</code></td>
    <td>A Deployment or Alias URL. In case it is passed, the ID will be ignored</td>
</tr>
<tr id="parameter-users">
    <td><CopyableCode code="users" /></td>
    <td><code>string</code></td>
    <td>Filter out deployments based on users who have created the deployment.</td>
</tr>
<tr id="parameter-withGitRepoInfo">
    <td><CopyableCode code="withGitRepoInfo" /></td>
    <td><code>string</code></td>
    <td>Whether to add in gitRepo information.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_deployment"
    values={[
        { label: 'get_deployment', value: 'get_deployment' },
        { label: 'get_deployments', value: 'get_deployments' }
    ]}
>
<TabItem value="get_deployment">

Retrieves information for a deployment either by supplying its ID (`id` property) or Hostname (`url` property). Additional details will be included when the authenticated user or team is an owner of the deployment.

```sql
SELECT
*
FROM vercel.deployments.deployments
WHERE idOrUrl = '{{ idOrUrl }}' -- required
AND teamId = '{{ teamId }}' -- required
AND withGitRepoInfo = '{{ withGitRepoInfo }}'
;
```
</TabItem>
<TabItem value="get_deployments">

List deployments under the authenticated user or team. If a deployment hasn't finished uploading (is incomplete), the `url` property will have a value of `null`.

```sql
SELECT
name,
aliasAssigned,
aliasError,
buildingAt,
checksConclusion,
checksState,
connectBuildsEnabled,
connectConfigurationId,
created,
createdAt,
creator,
inspectorUrl,
isRollbackCandidate,
meta,
projectSettings,
ready,
readyState,
readySubstate,
source,
state,
target,
type,
uid,
url
FROM vercel.deployments.deployments
WHERE teamId = '{{ teamId }}' -- required
AND app = '{{ app }}'
AND from = '{{ from }}'
AND limit = '{{ limit }}'
AND projectId = '{{ projectId }}'
AND target = '{{ target }}'
AND to = '{{ to }}'
AND users = '{{ users }}'
AND since = '{{ since }}'
AND until = '{{ until }}'
AND state = '{{ state }}'
AND rollbackCandidate = '{{ rollbackCandidate }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_deployment"
    values={[
        { label: 'create_deployment', value: 'create_deployment' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_deployment">

Create a new deployment with all the required and intended data. If the deployment is not a git deployment, all files must be provided with the request, either referenced or inlined. Additionally, a deployment id can be specified to redeploy a previous deployment.

```sql
INSERT INTO vercel.deployments.deployments (
data__$schema,
data__alias,
data__build,
data__builds,
data__cleanUrls,
data__env,
data__functions,
data__git,
data__headers,
data__images,
data__name,
data__public,
data__redirects,
data__regions,
data__rewrites,
data__routes,
data__trailingSlash,
data__buildCommand,
data__ignoreCommand,
data__devCommand,
data__framework,
data__installCommand,
data__outputDirectory,
data__crons,
data__deploymentId,
data__files,
data__gitMetadata,
data__gitSource,
data__meta,
data__monorepoManager,
data__project,
data__projectSettings,
data__target,
data__withLatestCommit,
data__connection_uris,
data__roles,
data__databases,
data__branch,
data__endpoints,
data__endpoint,
data__database,
data__role,
data__password,
data__projects,
data__pagination,
teamId,
forceNew,
skipAutoDetectionConfirmation
)
SELECT 
'{{ $schema }}',
'{{ alias }}',
'{{ build }}',
'{{ builds }}',
{{ cleanUrls }},
'{{ env }}',
'{{ functions }}',
'{{ git }}',
'{{ headers }}',
'{{ images }}',
'{{ name }}' /* required */,
{{ public }},
'{{ redirects }}',
'{{ regions }}',
'{{ rewrites }}',
'{{ routes }}',
{{ trailingSlash }},
'{{ buildCommand }}',
'{{ ignoreCommand }}',
'{{ devCommand }}',
'{{ framework }}',
'{{ installCommand }}',
'{{ outputDirectory }}',
'{{ crons }}',
'{{ deploymentId }}',
'{{ files }}',
'{{ gitMetadata }}',
'{{ gitSource }}',
'{{ meta }}',
'{{ monorepoManager }}',
'{{ project }}' /* required */,
'{{ projectSettings }}',
'{{ target }}',
{{ withLatestCommit }},
'{{ connection_uris }}' /* required */,
'{{ roles }}' /* required */,
'{{ databases }}' /* required */,
'{{ branch }}' /* required */,
'{{ endpoints }}' /* required */,
'{{ endpoint }}' /* required */,
'{{ database }}' /* required */,
'{{ role }}' /* required */,
'{{ password }}' /* required */,
'{{ projects }}' /* required */,
'{{ pagination }}' /* required */,
'{{ teamId }}',
'{{ forceNew }}',
'{{ skipAutoDetectionConfirmation }}'
RETURNING
id,
name,
alias,
aliasAssigned,
aliasAssignedAt,
aliasError,
aliasFinal,
aliasWarning,
autoAssignCustomDomains,
automaticAliases,
bootedAt,
build,
buildErrorAt,
buildingAt,
builds,
canceledAt,
checksConclusion,
checksState,
connectBuildsEnabled,
connectConfigurationId,
createdAt,
createdIn,
creator,
env,
errorCode,
errorLink,
errorMessage,
errorStep,
functions,
gitRepo,
gitSource,
inspectorUrl,
isInConcurrentBuildsQueue,
lambdas,
meta,
monorepoManager,
ownerId,
plan,
previewCommentsEnabled,
projectId,
public,
readyState,
readySubstate,
regions,
routes,
source,
target,
team,
type,
url,
userAliases,
version
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: deployments
  props:
    - name: teamId
      value: string
      description: Required parameter for the deployments resource.
    - name: $schema
      value: string
      description: |
        Ignored. Can be set to get completions, validations and documentation in some editors.
    - name: alias
      value: array
      description: |
        Aliases that will get assigned when the deployment is `READY` and the target is `production`. The client needs to make a `GET` request to its API to ensure the assignment
    - name: build
      value: object
      description: |
        An object containing another object with information to be passed to the Build Process
    - name: builds
      value: array
      description: |
        A list of build descriptions whose src references valid source files.
    - name: cleanUrls
      value: boolean
      description: |
        When set to `true`, all HTML files and Serverless Functions will have their extension removed. When visiting a path that ends with the extension, a 308 response will redirect the client to the extensionless path.
    - name: env
      value: object
      description: |
        An object containing the deployment's environment variable names and values. Secrets can be referenced by prefixing the value with `@`
    - name: functions
      value: object
      description: |
        An object describing custom options for your Serverless Functions. Each key must be glob pattern that matches the paths of the Serverless Functions you would like to customize (like `api/*.js` or `api/test.js`).
    - name: git
      value: object
    - name: headers
      value: array
      description: |
        A list of header definitions.
    - name: images
      value: object
    - name: name
      value: string
      description: |
        A string with the project name used in the deployment URL
    - name: public
      value: boolean
      description: |
        Whether a deployment's source and logs are available publicly
    - name: redirects
      value: array
      description: |
        A list of redirect definitions.
    - name: regions
      value: array
      description: |
        An array of the regions the deployment's Serverless Functions should be deployed to
    - name: rewrites
      value: array
      description: |
        A list of rewrite definitions.
    - name: routes
      value: array
      description: |
        A list of routes objects used to rewrite paths to point towards other internal or external paths
    - name: trailingSlash
      value: boolean
      description: |
        When `false`, visiting a path that ends with a forward slash will respond with a `308` status code and redirect to the path without the trailing slash.
    - name: buildCommand
      value: string
      description: |
        The build command for this project. When `null` is used this value will be automatically detected
    - name: ignoreCommand
      value: string
    - name: devCommand
      value: string
      description: |
        The dev command for this project. When `null` is used this value will be automatically detected
    - name: framework
      value: string
      description: |
        The framework that is being used for this project. When `null` is used no framework is selected
      valid_values: ['', 'blitzjs', 'nextjs', 'gatsby', 'remix', 'astro', 'hexo', 'eleventy', 'docusaurus-2', 'docusaurus', 'preact', 'solidstart', 'dojo', 'ember', 'vue', 'scully', 'ionic-angular', 'angular', 'polymer', 'svelte', 'sveltekit', 'sveltekit-1', 'ionic-react', 'create-react-app', 'gridsome', 'umijs', 'sapper', 'saber', 'stencil', 'nuxtjs', 'redwoodjs', 'hugo', 'jekyll', 'brunch', 'middleman', 'zola', 'hydrogen', 'vite', 'vitepress', 'vuepress', 'parcel', 'sanity', 'storybook']
    - name: installCommand
      value: string
      description: |
        The install command for this project. When `null` is used this value will be automatically detected
    - name: outputDirectory
      value: string
      description: |
        The output directory of the project. When `null` is used this value will be automatically detected
    - name: crons
      value: array
      description: |
        An array of cron jobs that should be created for production Deployments.
    - name: deploymentId
      value: string
      description: |
        An deployment id for an existing deployment to redeploy
    - name: files
      value: array
      description: |
        A list of objects with the files to be deployed
    - name: gitMetadata
      value: object
      description: |
        Populates initial git metadata for different git providers.
    - name: gitSource
      value: string
      description: |
        Defines the Git Repository source to be deployed. This property can not be used in combination with `files`.
    - name: meta
      value: object
      description: |
        An object containing the deployment's metadata. Multiple key-value pairs can be attached to a deployment
    - name: monorepoManager
      value: string
      description: |
        The monorepo manager that is being used for this deployment. When `null` is used no monorepo manager is selected
    - name: project
      value: object
    - name: projectSettings
      value: object
      description: |
        Project settings that will be applied to the deployment. It is required for the first deployment of a project and will be saved for any following deployments
    - name: target
      value: string
      description: |
        Either not defined, `staging`, or `production`. If `staging`, a staging alias in the format `<project>-<team>.vercel.app` will be assigned. If `production`, any aliases defined in `alias` will be assigned. If omitted, the target will be `preview`
      valid_values: ['staging', 'production']
    - name: withLatestCommit
      value: boolean
      description: |
        When `true` and `deploymentId` is passed in, the sha from the previous deployment's `gitSource` is removed forcing the latest commit to be used.
    - name: connection_uris
      value: array
    - name: roles
      value: array
    - name: databases
      value: array
    - name: branch
      value: object
    - name: endpoints
      value: array
    - name: endpoint
      value: object
    - name: database
      value: object
    - name: role
      value: object
    - name: password
      value: string
    - name: projects
      value: array
    - name: pagination
      value: object
    - name: forceNew
      value: string
      description: Forces a new deployment even if there is a previous similar deployment
    - name: skipAutoDetectionConfirmation
      value: string
      description: Allows to skip framework detection so the API would not fail to ask for confirmation
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_deployment"
    values={[
        { label: 'delete_deployment', value: 'delete_deployment' }
    ]}
>
<TabItem value="delete_deployment">

This API allows you to delete a deployment, either by supplying its `id` in the URL or the `url` of the deployment as a query parameter. You can obtain the ID, for example, by listing all deployments.

```sql
DELETE FROM vercel.deployments.deployments
WHERE id = '{{ id }}' --required
AND teamId = '{{ teamId }}' --required
AND url = '{{ url }}'
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="cancel_deployment"
    values={[
        { label: 'cancel_deployment', value: 'cancel_deployment' },
        { label: '_get_deployments', value: '_get_deployments' }
    ]}
>
<TabItem value="cancel_deployment">

This endpoint allows you to cancel a deployment which is currently building, by supplying its `id` in the URL.

```sql
EXEC vercel.deployments.deployments.cancel_deployment 
@id='{{ id }}' --required, 
@teamId='{{ teamId }}' --required
;
```
</TabItem>
<TabItem value="_get_deployments">

List deployments under the authenticated user or team. If a deployment hasn't finished uploading (is incomplete), the `url` property will have a value of `null`.

```sql
EXEC vercel.deployments.deployments._get_deployments 
@teamId='{{ teamId }}' --required, 
@app='{{ app }}', 
@from='{{ from }}', 
@limit='{{ limit }}', 
@projectId='{{ projectId }}', 
@target='{{ target }}', 
@to='{{ to }}', 
@users='{{ users }}', 
@since='{{ since }}', 
@until='{{ until }}', 
@state='{{ state }}', 
@rollbackCandidate={{ rollbackCandidate }}
;
```
</TabItem>
</Tabs>
