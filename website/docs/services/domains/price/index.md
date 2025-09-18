--- 
title: price
hide_title: false
hide_table_of_contents: false
keywords:
  - price
  - domains
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

Creates, updates, deletes, gets or lists a <code>price</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>price</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.domains.price" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="check_domain_price"
    values={[
        { label: 'check_domain_price', value: 'check_domain_price' }
    ]}
>
<TabItem value="check_domain_price">

Successful response which returns the price of the domain and the period.

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
    <td><CopyableCode code="period" /></td>
    <td><code>number</code></td>
    <td>The number of years the domain could be held before paying again.</td>
</tr>
<tr>
    <td><CopyableCode code="price" /></td>
    <td><code>number</code></td>
    <td>The domain price in USD.</td>
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
    <td><a href="#check_domain_price"><CopyableCode code="check_domain_price" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-name"><code>name</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-type"><code>type</code></a></td>
    <td>Check the price to purchase a domain and how long a single purchase period is.</td>
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
<tr id="parameter-name">
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td>The name of the domain for which the price needs to be checked.</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-type">
    <td><CopyableCode code="type" /></td>
    <td><code>string</code></td>
    <td>In which status of the domain the price needs to be checked.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="check_domain_price"
    values={[
        { label: 'check_domain_price', value: 'check_domain_price' }
    ]}
>
<TabItem value="check_domain_price">

Check the price to purchase a domain and how long a single purchase period is.

```sql
SELECT
period,
price
FROM vercel.domains.price
WHERE name = '{{ name }}' -- required
AND teamId = '{{ teamId }}' -- required
AND type = '{{ type }}'
;
```
</TabItem>
</Tabs>
