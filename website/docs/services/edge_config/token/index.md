--- 
title: token
hide_title: false
hide_table_of_contents: false
keywords:
  - token
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

Creates, updates, deletes, gets or lists a <code>token</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>token</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.edge_config.token" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_edge_config_token"
    values={[
        { label: 'get_edge_config_token', value: 'get_edge_config_token' }
    ]}
>
<TabItem value="get_edge_config_token">

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
    <td><a href="#get_edge_config_token"><CopyableCode code="get_edge_config_token" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-token"><code>token</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Return meta data about an Edge Config token.</td>
</tr>
<tr>
    <td><a href="#create_edge_config_token"><CopyableCode code="create_edge_config_token" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__label"><code>data__label</code></a></td>
    <td></td>
    <td>Adds a token to an existing Edge Config.</td>
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
<tr id="parameter-token">
    <td><CopyableCode code="token" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_edge_config_token"
    values={[
        { label: 'get_edge_config_token', value: 'get_edge_config_token' }
    ]}
>
<TabItem value="get_edge_config_token">

Return meta data about an Edge Config token.

```sql
SELECT
id,
createdAt,
edgeConfigId,
label,
token
FROM vercel.edge_config.token
WHERE edgeConfigId = '{{ edgeConfigId }}' -- required
AND token = '{{ token }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_edge_config_token"
    values={[
        { label: 'create_edge_config_token', value: 'create_edge_config_token' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_edge_config_token">

Adds a token to an existing Edge Config.

```sql
INSERT INTO vercel.edge_config.token (
data__label,
edgeConfigId,
teamId
)
SELECT 
'{{ label }}' /* required */,
'{{ edgeConfigId }}',
'{{ teamId }}'
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: token
  props:
    - name: edgeConfigId
      value: string
      description: Required parameter for the token resource.
    - name: teamId
      value: string
      description: Required parameter for the token resource.
    - name: label
      value: string
```
</TabItem>
</Tabs>
