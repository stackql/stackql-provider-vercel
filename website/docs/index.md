---
title: vercel
hide_title: false
hide_table_of_contents: false
keywords:
  - vercel
  - stackql
  - infrastructure-as-code
  - configuration-as-data
  - cloud inventory
description: Query, deploy, and manage Vercel resources using SQL
custom_edit_url: null
image: /img/stackql-vercel-provider-featured-image.png
id: 'provider-intro'
---

import CopyableCode from '@site/src/components/CopyableCode/CopyableCode';

Cloud platform for serverless deployment and hosting of web applications. 

:::info[Provider Summary] 

total services: __19__  
total resources: __59__  

:::

See also:   
[[` SHOW `]](https://stackql.io/docs/language-spec/show) [[` DESCRIBE `]](https://stackql.io/docs/language-spec/describe)  [[` REGISTRY `]](https://stackql.io/docs/language-spec/registry)
* * * 

## Installation

To pull the latest version of the `vercel` provider, run the following command:  

```bash
REGISTRY PULL vercel;
```
> To view previous provider versions or to pull a specific provider version, see [here](https://stackql.io/docs/language-spec/registry).  

## Authentication

The following system environment variables are used for authentication by default:  

- <CopyableCode code="VERCEL_API_TOKEN" /> - Vercel API Token (see <a href="https://vercel.com/account/tokens">Creating a Vercel API Token</a>)
  
These variables are sourced at runtime (from the local machine or as CI variables/secrets).  

<details>

<summary>Using different environment variables</summary>

To use different environment variables (instead of the defaults), use the `--auth` flag of the `stackql` program.  For example:  

```bash

AUTH='{ "vercel": { "type": "bearer", "credentialsenvvar": "YOUR_VERCEL_API_TOKEN_VAR" }}'
stackql shell --auth="${AUTH}"

```
or using PowerShell:  

```powershell

$Auth = "{ 'vercel': { 'type': 'bearer', 'credentialsenvvar': 'YOUR_VERCEL_API_TOKEN_VAR' }}"
stackql.exe shell --auth=$Auth

```
</details>

## Services
<div class="row">
<div class="providerDocColumn">
<a href="/services/aliases/">aliases</a><br />
<a href="/services/artifacts/">artifacts</a><br />
<a href="/services/authentication/">authentication</a><br />
<a href="/services/billing_settings/">billing_settings</a><br />
<a href="/services/cache/">cache</a><br />
<a href="/services/certs/">certs</a><br />
<a href="/services/checks/">checks</a><br />
<a href="/services/deployments/">deployments</a><br />
<a href="/services/dns/">dns</a><br />
<a href="/services/domains/">domains</a><br />
</div>
<div class="providerDocColumn">
<a href="/services/edge_config/">edge_config</a><br />
<a href="/services/integrations/">integrations</a><br />
<a href="/services/log_drains/">log_drains</a><br />
<a href="/services/project_members/">project_members</a><br />
<a href="/services/projects/">projects</a><br />
<a href="/services/secrets/">secrets</a><br />
<a href="/services/teams/">teams</a><br />
<a href="/services/user/">user</a><br />
<a href="/services/webhooks/">webhooks</a><br />
</div>
</div>
