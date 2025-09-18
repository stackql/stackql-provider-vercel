--- 
title: item
hide_title: false
hide_table_of_contents: false
keywords:
  - item
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

Creates, updates, deletes, gets or lists an <code>item</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>item</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.edge_config.item" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_edge_config_item"
    values={[
        { label: 'get_edge_config_item', value: 'get_edge_config_item' }
    ]}
>
<TabItem value="get_edge_config_item">

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
    <td><a href="#get_edge_config_item"><CopyableCode code="get_edge_config_item" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-edgeConfigItemKey"><code>edgeConfigItemKey</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Returns a specific Edge Config Item.</td>
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
<tr id="parameter-edgeConfigItemKey">
    <td><CopyableCode code="edgeConfigItemKey" /></td>
    <td><code>string</code></td>
    <td>Edge config id item key.</td>
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
    defaultValue="get_edge_config_item"
    values={[
        { label: 'get_edge_config_item', value: 'get_edge_config_item' }
    ]}
>
<TabItem value="get_edge_config_item">

Returns a specific Edge Config Item.

```sql
SELECT
createdAt,
edgeConfigId,
key,
updatedAt,
value
FROM vercel.edge_config.item
WHERE edgeConfigId = '{{ edgeConfigId }}' -- required
AND edgeConfigItemKey = '{{ edgeConfigItemKey }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>
