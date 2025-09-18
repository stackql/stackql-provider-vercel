--- 
title: edge_config
hide_title: false
hide_table_of_contents: false
keywords:
  - edge_config
  - edge_config
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

Creates, updates, deletes, gets or lists an <code>edge_config</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>edge_config</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.edge_config.edge_config" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_edge_config"
    values={[
        { label: 'get_edge_config', value: 'get_edge_config' },
        { label: 'get_edge_configs', value: 'get_edge_configs' }
    ]}
>
<TabItem value="get_edge_config">

The EdgeConfig.

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
    <td><CopyableCode code="id" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="digest" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="itemCount" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="ownerId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="sizeInBytes" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="slug" /></td>
    <td><code>string</code></td>
    <td>Name for the Edge Config Names are not unique. Must start with an alphabetic character and can contain only alphanumeric characters and underscores).</td>
</tr>
<tr>
    <td><CopyableCode code="transfer" /></td>
    <td><code>object</code></td>
    <td>Keeps track of the current state of the Edge Config while it gets transferred.</td>
</tr>
<tr>
    <td><CopyableCode code="updatedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="get_edge_configs">

List of all edge configs.

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
    <td><CopyableCode code="id" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="digest" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="itemCount" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="ownerId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="sizeInBytes" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="slug" /></td>
    <td><code>string</code></td>
    <td>Name for the Edge Config Names are not unique. Must start with an alphabetic character and can contain only alphanumeric characters and underscores).</td>
</tr>
<tr>
    <td><CopyableCode code="transfer" /></td>
    <td><code>object</code></td>
    <td>Keeps track of the current state of the Edge Config while it gets transferred.</td>
</tr>
<tr>
    <td><CopyableCode code="updatedAt" /></td>
    <td><code>number</code></td>
    <td></td>
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
    <td><a href="#get_edge_config"><CopyableCode code="get_edge_config" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Returns an Edge Config.</td>
</tr>
<tr>
    <td><a href="#get_edge_configs"><CopyableCode code="get_edge_configs" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Returns all Edge Configs.</td>
</tr>
<tr>
    <td><a href="#create_edge_config"><CopyableCode code="create_edge_config" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__slug"><code>data__slug</code></a></td>
    <td></td>
    <td>Creates an Edge Config.</td>
</tr>
<tr>
    <td><a href="#delete_edge_config"><CopyableCode code="delete_edge_config" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Delete an Edge Config by id.</td>
</tr>
<tr>
    <td><a href="#update_edge_config"><CopyableCode code="update_edge_config" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-slug"><code>slug</code></a></td>
    <td></td>
    <td>Updates an Edge Config.</td>
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
<tr id="parameter-edgeConfigId">
    <td><CopyableCode code="edgeConfigId" /></td>
    <td><code>string</code></td>
    <td>Edge config id.</td>
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
    defaultValue="get_edge_config"
    values={[
        { label: 'get_edge_config', value: 'get_edge_config' },
        { label: 'get_edge_configs', value: 'get_edge_configs' }
    ]}
>
<TabItem value="get_edge_config">

Returns an Edge Config.

```sql
SELECT
id,
createdAt,
digest,
itemCount,
ownerId,
sizeInBytes,
slug,
transfer,
updatedAt
FROM vercel.edge_config.edge_config
WHERE edgeConfigId = '{{ edgeConfigId }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
<TabItem value="get_edge_configs">

Returns all Edge Configs.

```sql
SELECT
id,
createdAt,
digest,
itemCount,
ownerId,
sizeInBytes,
slug,
transfer,
updatedAt
FROM vercel.edge_config.edge_config
WHERE teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_edge_config"
    values={[
        { label: 'create_edge_config', value: 'create_edge_config' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_edge_config">

Creates an Edge Config.

```sql
INSERT INTO vercel.edge_config.edge_config (
data__slug,
data__items,
teamId
)
SELECT 
'{{ slug }}' /* required */,
'{{ items }}',
'{{ teamId }}'
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: edge_config
  props:
    - name: teamId
      value: string
      description: Required parameter for the edge_config resource.
    - name: slug
      value: string
    - name: items
      value: object
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_edge_config"
    values={[
        { label: 'delete_edge_config', value: 'delete_edge_config' }
    ]}
>
<TabItem value="delete_edge_config">

Delete an Edge Config by id.

```sql
DELETE FROM vercel.edge_config.edge_config
WHERE edgeConfigId = '{{ edgeConfigId }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="update_edge_config"
    values={[
        { label: 'update_edge_config', value: 'update_edge_config' }
    ]}
>
<TabItem value="update_edge_config">

Updates an Edge Config.

```sql
EXEC vercel.edge_config.edge_config.update_edge_config 
@edgeConfigId='{{ edgeConfigId }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"slug": "{{ slug }}"
}'
;
```
</TabItem>
</Tabs>
