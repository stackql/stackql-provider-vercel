--- 
title: items
hide_title: false
hide_table_of_contents: false
keywords:
  - items
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

Creates, updates, deletes, gets or lists an <code>items</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>items</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.edge_config.items" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_edge_config_items"
    values={[
        { label: 'get_edge_config_items', value: 'get_edge_config_items' }
    ]}
>
<TabItem value="get_edge_config_items">

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
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="edgeConfigId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="key" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="updatedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="value" /></td>
    <td><code></code></td>
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
    <td><a href="#get_edge_config_items"><CopyableCode code="get_edge_config_items" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Returns all items of an Edge Config.</td>
</tr>
<tr>
    <td><a href="#patcht_edge_config_items"><CopyableCode code="patcht_edge_config_items" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-items"><code>items</code></a></td>
    <td></td>
    <td>Update multiple Edge Config Items in batch.</td>
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
    defaultValue="get_edge_config_items"
    values={[
        { label: 'get_edge_config_items', value: 'get_edge_config_items' }
    ]}
>
<TabItem value="get_edge_config_items">

Returns all items of an Edge Config.

```sql
SELECT
createdAt,
edgeConfigId,
key,
updatedAt,
value
FROM vercel.edge_config.items
WHERE edgeConfigId = '{{ edgeConfigId }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="patcht_edge_config_items"
    values={[
        { label: 'patcht_edge_config_items', value: 'patcht_edge_config_items' }
    ]}
>
<TabItem value="patcht_edge_config_items">

Update multiple Edge Config Items in batch.

```sql
EXEC vercel.edge_config.items.patcht_edge_config_items 
@edgeConfigId='{{ edgeConfigId }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"items": "{{ items }}"
}'
;
```
</TabItem>
</Tabs>
