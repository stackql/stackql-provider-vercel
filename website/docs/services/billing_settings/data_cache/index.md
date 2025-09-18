--- 
title: data_cache
hide_title: false
hide_table_of_contents: false
keywords:
  - data_cache
  - billing_settings
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

Creates, updates, deletes, gets or lists a <code>data_cache</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>data_cache</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.billing_settings.data_cache" /></td></tr>
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
    <td><a href="#enable_excess_billing"><CopyableCode code="enable_excess_billing" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td></td>
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
</tbody>
</table>

## Lifecycle Methods

<Tabs
    defaultValue="enable_excess_billing"
    values={[
        { label: 'enable_excess_billing', value: 'enable_excess_billing' }
    ]}
>
<TabItem value="enable_excess_billing">

No description available.

```sql
EXEC vercel.billing_settings.data_cache.enable_excess_billing 
@@json=
'{
"excessBillingEnabled": {{ excessBillingEnabled }}
}'
;
```
</TabItem>
</Tabs>
