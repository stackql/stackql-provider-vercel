--- 
title: deployments
hide_title: false
hide_table_of_contents: false
keywords:
  - deployments
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

Creates, updates, deletes, gets or lists a <code>deployments</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>deployments</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.aliases.deployments" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="list_deployment_aliases"
    values={[
        { label: 'list_deployment_aliases', value: 'list_deployment_aliases' }
    ]}
>
<TabItem value="list_deployment_aliases">

The list of aliases assigned to the deployment

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
    <td><CopyableCode code="uid" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the alias (example: 2WjyKQmM8ZnGcJsPWMrHRHrE)</td>
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
    <td><a href="#list_deployment_aliases"><CopyableCode code="list_deployment_aliases" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Retrieves all Aliases for the Deployment with the given ID. The authenticated user or team must own the deployment.</td>
</tr>
<tr>
    <td><a href="#_list_deployment_aliases"><CopyableCode code="_list_deployment_aliases" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Retrieves all Aliases for the Deployment with the given ID. The authenticated user or team must own the deployment.</td>
</tr>
<tr>
    <td><a href="#assign_alias"><CopyableCode code="assign_alias" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Creates a new alias for the deployment with the given deployment ID. The authenticated user or team must own this deployment. If the desired alias is already assigned to another deployment, then it will be removed from the old deployment and assigned to the new one.</td>
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
    <td><code></code></td>
    <td>The ID of the deployment the aliases should be listed for</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="list_deployment_aliases"
    values={[
        { label: 'list_deployment_aliases', value: 'list_deployment_aliases' }
    ]}
>
<TabItem value="list_deployment_aliases">

Retrieves all Aliases for the Deployment with the given ID. The authenticated user or team must own the deployment.

```sql
SELECT
alias,
created,
protectionBypass,
redirect,
uid
FROM vercel.aliases.deployments
WHERE id = '{{ id }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_list_deployment_aliases"
    values={[
        { label: '_list_deployment_aliases', value: '_list_deployment_aliases' },
        { label: 'assign_alias', value: 'assign_alias' }
    ]}
>
<TabItem value="_list_deployment_aliases">

Retrieves all Aliases for the Deployment with the given ID. The authenticated user or team must own the deployment.

```sql
EXEC vercel.aliases.deployments._list_deployment_aliases 
@id='{{ id }}' --required, 
@teamId='{{ teamId }}' --required
;
```
</TabItem>
<TabItem value="assign_alias">

Creates a new alias for the deployment with the given deployment ID. The authenticated user or team must own this deployment. If the desired alias is already assigned to another deployment, then it will be removed from the old deployment and assigned to the new one.

```sql
EXEC vercel.aliases.deployments.assign_alias 
@id='{{ id }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"alias": "{{ alias }}", 
"redirect": "{{ redirect }}"
}'
;
```
</TabItem>
</Tabs>
