--- 
title: data_cache_purge_all
hide_title: false
hide_table_of_contents: false
keywords:
  - data_cache_purge_all
  - cache
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

Creates, updates, deletes, gets or lists a <code>data_cache_purge_all</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>data_cache_purge_all</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.cache.data_cache_purge_all" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

`SELECT` not supported for this resource, use `SHOW METHODS` to view available operations for the resource.


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
    <td><a href="#purge_all"><CopyableCode code="purge_all" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-projectIdOrName"><code>projectIdOrName</code></a></td>
    <td></td>
    <td></td>
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
<tr id="parameter-projectIdOrName">
    <td><CopyableCode code="projectIdOrName" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
</tbody>
</table>

## Lifecycle Methods

<Tabs
    defaultValue="purge_all"
    values={[
        { label: 'purge_all', value: 'purge_all' }
    ]}
>
<TabItem value="purge_all">

No description available.

```sql
EXEC vercel.cache.data_cache_purge_all.purge_all 
@projectIdOrName='{{ projectIdOrName }}' --required
;
```
</TabItem>
</Tabs>
