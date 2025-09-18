--- 
title: aliases
hide_title: false
hide_table_of_contents: false
keywords:
  - aliases
  - aliases
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

Creates, updates, deletes, gets or lists an <code>aliases</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>aliases</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.aliases.aliases" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_alias"
    values={[
        { label: 'get_alias', value: 'get_alias' },
        { label: 'list_aliases', value: 'list_aliases' }
    ]}
>
<TabItem value="get_alias">

The alias information

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
    <td><CopyableCode code="alias" /></td>
    <td><code>string</code></td>
    <td>The alias name, it could be a `.vercel.app` subdomain or a custom domain (example: my-alias.vercel.app)</td>
</tr>
<tr>
    <td><CopyableCode code="created" /></td>
    <td><code>string (date-time)</code></td>
    <td>The date when the alias was created (example: 2017-04-26T23:00:34.232Z)</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>The date when the alias was created in milliseconds since the UNIX epoch</td>
</tr>
<tr>
    <td><CopyableCode code="creator" /></td>
    <td><code>object</code></td>
    <td>Information of the user who created the alias</td>
</tr>
<tr>
    <td><CopyableCode code="deletedAt" /></td>
    <td><code>number</code></td>
    <td>The date when the alias was deleted in milliseconds since the UNIX epoch</td>
</tr>
<tr>
    <td><CopyableCode code="deployment" /></td>
    <td><code>object</code></td>
    <td>A map with the deployment ID, URL and metadata</td>
</tr>
<tr>
    <td><CopyableCode code="deploymentId" /></td>
    <td><code>string</code></td>
    <td>The deployment ID (example: dpl_5m8CQaRBm3FnWRW1od3wKTpaECPx)</td>
</tr>
<tr>
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the project (example: prj_12HKQaOmR5t5Uy6vdcQsNIiZgHGB)</td>
</tr>
<tr>
    <td><CopyableCode code="protectionBypass" /></td>
    <td><code>object</code></td>
    <td>The protection bypass for the alias</td>
</tr>
<tr>
    <td><CopyableCode code="redirect" /></td>
    <td><code>string</code></td>
    <td>Target destination domain for redirect when the alias is a redirect</td>
</tr>
<tr>
    <td><CopyableCode code="redirectStatusCode" /></td>
    <td><code>number</code></td>
    <td>Status code to be used on redirect</td>
</tr>
<tr>
    <td><CopyableCode code="uid" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the alias</td>
</tr>
<tr>
    <td><CopyableCode code="updatedAt" /></td>
    <td><code>number</code></td>
    <td>The date when the alias was updated in milliseconds since the UNIX epoch</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="list_aliases">

The paginated list of aliases

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
    <td><CopyableCode code="alias" /></td>
    <td><code>string</code></td>
    <td>The alias name, it could be a `.vercel.app` subdomain or a custom domain (example: my-alias.vercel.app)</td>
</tr>
<tr>
    <td><CopyableCode code="created" /></td>
    <td><code>string (date-time)</code></td>
    <td>The date when the alias was created (example: 2017-04-26T23:00:34.232Z)</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>The date when the alias was created in milliseconds since the UNIX epoch</td>
</tr>
<tr>
    <td><CopyableCode code="creator" /></td>
    <td><code>object</code></td>
    <td>Information of the user who created the alias</td>
</tr>
<tr>
    <td><CopyableCode code="deletedAt" /></td>
    <td><code>number</code></td>
    <td>The date when the alias was deleted in milliseconds since the UNIX epoch</td>
</tr>
<tr>
    <td><CopyableCode code="deployment" /></td>
    <td><code>object</code></td>
    <td>A map with the deployment ID, URL and metadata</td>
</tr>
<tr>
    <td><CopyableCode code="deploymentId" /></td>
    <td><code>string</code></td>
    <td>The deployment ID (example: dpl_5m8CQaRBm3FnWRW1od3wKTpaECPx)</td>
</tr>
<tr>
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the project (example: prj_12HKQaOmR5t5Uy6vdcQsNIiZgHGB)</td>
</tr>
<tr>
    <td><CopyableCode code="protectionBypass" /></td>
    <td><code>object</code></td>
    <td>The protection bypass for the alias</td>
</tr>
<tr>
    <td><CopyableCode code="redirect" /></td>
    <td><code>string</code></td>
    <td>Target destination domain for redirect when the alias is a redirect</td>
</tr>
<tr>
    <td><CopyableCode code="redirectStatusCode" /></td>
    <td><code>number</code></td>
    <td>Status code to be used on redirect</td>
</tr>
<tr>
    <td><CopyableCode code="uid" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the alias</td>
</tr>
<tr>
    <td><CopyableCode code="updatedAt" /></td>
    <td><code>number</code></td>
    <td>The date when the alias was updated in milliseconds since the UNIX epoch</td>
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
    <td><a href="#get_alias"><CopyableCode code="get_alias" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-idOrAlias"><code>idOrAlias</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-from"><code>from</code></a>, <a href="#parameter-projectId"><code>projectId</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a></td>
    <td>Retrieves an Alias for the given host name or alias ID.</td>
</tr>
<tr>
    <td><a href="#list_aliases"><CopyableCode code="list_aliases" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-from"><code>from</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-projectId"><code>projectId</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-rollbackDeploymentId"><code>rollbackDeploymentId</code></a></td>
    <td>Retrieves a list of aliases for the authenticated User or Team. When `domain` is provided, only aliases for that domain will be returned. When `projectId` is provided, it will only return the given project aliases.</td>
</tr>
<tr>
    <td><a href="#delete_alias"><CopyableCode code="delete_alias" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-aliasId"><code>aliasId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Delete an Alias with the specified ID.</td>
</tr>
<tr>
    <td><a href="#_list_aliases"><CopyableCode code="_list_aliases" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-from"><code>from</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-projectId"><code>projectId</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-rollbackDeploymentId"><code>rollbackDeploymentId</code></a></td>
    <td>Retrieves a list of aliases for the authenticated User or Team. When `domain` is provided, only aliases for that domain will be returned. When `projectId` is provided, it will only return the given project aliases.</td>
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
<tr id="parameter-aliasId">
    <td><CopyableCode code="aliasId" /></td>
    <td><code></code></td>
    <td>The ID or alias that will be removed</td>
</tr>
<tr id="parameter-idOrAlias">
    <td><CopyableCode code="idOrAlias" /></td>
    <td><code>string</code></td>
    <td>The alias or alias ID to be retrieved</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-domain">
    <td><CopyableCode code="domain" /></td>
    <td><code></code></td>
    <td>Get only aliases of the given domain name</td>
</tr>
<tr id="parameter-from">
    <td><CopyableCode code="from" /></td>
    <td><code>number</code></td>
    <td>Get only aliases created after the provided timestamp</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>number</code></td>
    <td>Maximum number of aliases to list from a request</td>
</tr>
<tr id="parameter-projectId">
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td>Filter aliases from the given `projectId`</td>
</tr>
<tr id="parameter-rollbackDeploymentId">
    <td><CopyableCode code="rollbackDeploymentId" /></td>
    <td><code>string</code></td>
    <td>Get aliases that would be rolled back for the given deployment</td>
</tr>
<tr id="parameter-since">
    <td><CopyableCode code="since" /></td>
    <td><code>number</code></td>
    <td>Get aliases created after this JavaScript timestamp</td>
</tr>
<tr id="parameter-until">
    <td><CopyableCode code="until" /></td>
    <td><code>number</code></td>
    <td>Get aliases created before this JavaScript timestamp</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_alias"
    values={[
        { label: 'get_alias', value: 'get_alias' },
        { label: 'list_aliases', value: 'list_aliases' }
    ]}
>
<TabItem value="get_alias">

Retrieves an Alias for the given host name or alias ID.

```sql
SELECT
alias,
created,
createdAt,
creator,
deletedAt,
deployment,
deploymentId,
projectId,
protectionBypass,
redirect,
redirectStatusCode,
uid,
updatedAt
FROM vercel.aliases.aliases
WHERE idOrAlias = '{{ idOrAlias }}' -- required
AND teamId = '{{ teamId }}' -- required
AND from = '{{ from }}'
AND projectId = '{{ projectId }}'
AND since = '{{ since }}'
AND until = '{{ until }}'
;
```
</TabItem>
<TabItem value="list_aliases">

Retrieves a list of aliases for the authenticated User or Team. When `domain` is provided, only aliases for that domain will be returned. When `projectId` is provided, it will only return the given project aliases.

```sql
SELECT
alias,
created,
createdAt,
creator,
deletedAt,
deployment,
deploymentId,
projectId,
protectionBypass,
redirect,
redirectStatusCode,
uid,
updatedAt
FROM vercel.aliases.aliases
WHERE teamId = '{{ teamId }}' -- required
AND domain = '{{ domain }}'
AND from = '{{ from }}'
AND limit = '{{ limit }}'
AND projectId = '{{ projectId }}'
AND since = '{{ since }}'
AND until = '{{ until }}'
AND rollbackDeploymentId = '{{ rollbackDeploymentId }}'
;
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_alias"
    values={[
        { label: 'delete_alias', value: 'delete_alias' }
    ]}
>
<TabItem value="delete_alias">

Delete an Alias with the specified ID.

```sql
DELETE FROM vercel.aliases.aliases
WHERE aliasId = '{{ aliasId }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_list_aliases"
    values={[
        { label: '_list_aliases', value: '_list_aliases' }
    ]}
>
<TabItem value="_list_aliases">

Retrieves a list of aliases for the authenticated User or Team. When `domain` is provided, only aliases for that domain will be returned. When `projectId` is provided, it will only return the given project aliases.

```sql
EXEC vercel.aliases.aliases._list_aliases 
@teamId='{{ teamId }}' --required, 
@domain='{{ domain }}', 
@from='{{ from }}', 
@limit='{{ limit }}', 
@projectId='{{ projectId }}', 
@since='{{ since }}', 
@until='{{ until }}', 
@rollbackDeploymentId='{{ rollbackDeploymentId }}'
;
```
</TabItem>
</Tabs>
