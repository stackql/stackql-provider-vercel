--- 
title: tokens
hide_title: false
hide_table_of_contents: false
keywords:
  - tokens
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

Creates, updates, deletes, gets or lists a <code>tokens</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>tokens</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.edge_config.tokens" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_edge_config_tokens"
    values={[
        { label: 'get_edge_config_tokens', value: 'get_edge_config_tokens' }
    ]}
>
<TabItem value="get_edge_config_tokens">

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
    <td>This is not the token itself, but rather an id to identify the token by</td>
</tr>
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
    <td><CopyableCode code="label" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="token" /></td>
    <td><code>string</code></td>
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
    <td><a href="#get_edge_config_tokens"><CopyableCode code="get_edge_config_tokens" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Returns all tokens of an Edge Config.</td>
</tr>
<tr>
    <td><a href="#delete_edge_config_tokens"><CopyableCode code="delete_edge_config_tokens" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Deletes one or more tokens of an existing Edge Config.</td>
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
    defaultValue="get_edge_config_tokens"
    values={[
        { label: 'get_edge_config_tokens', value: 'get_edge_config_tokens' }
    ]}
>
<TabItem value="get_edge_config_tokens">

Returns all tokens of an Edge Config.

```sql
SELECT
id,
createdAt,
edgeConfigId,
label,
token
FROM vercel.edge_config.tokens
WHERE edgeConfigId = '{{ edgeConfigId }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_edge_config_tokens"
    values={[
        { label: 'delete_edge_config_tokens', value: 'delete_edge_config_tokens' }
    ]}
>
<TabItem value="delete_edge_config_tokens">

Deletes one or more tokens of an existing Edge Config.

```sql
DELETE FROM vercel.edge_config.tokens
WHERE edgeConfigId = '{{ edgeConfigId }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>
