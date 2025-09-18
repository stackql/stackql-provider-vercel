--- 
title: domain_registry
hide_title: false
hide_table_of_contents: false
keywords:
  - domain_registry
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

Creates, updates, deletes, gets or lists a <code>domain_registry</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>domain_registry</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.domains.domain_registry" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_domain_transfer"
    values={[
        { label: 'get_domain_transfer', value: 'get_domain_transfer' }
    ]}
>
<TabItem value="get_domain_transfer">

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
    <td><CopyableCode code="reason" /></td>
    <td><code>string</code></td>
    <td>Description associated with transferable state.</td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td>The current state of an ongoing transfer. `pending_owner`: Awaiting approval by domain's admin contact (every transfer begins with this status). If approval is not given within five days, the transfer is cancelled. `pending_admin`: Waiting for approval by Vercel Registrar admin. `pending_registry`: Awaiting registry approval (the transfer completes after 7 days unless it is declined by the current registrar). `completed`: The transfer completed successfully. `cancelled`: The transfer was cancelled. `undef`: No transfer exists for this domain. `unknown`: This TLD is not supported by Vercel's Registrar.</td>
</tr>
<tr>
    <td><CopyableCode code="transferPolicy" /></td>
    <td><code>string</code></td>
    <td>The domain's transfer policy (depends on TLD requirements). `charge-and-renew`: transfer will charge for renewal and will renew the existing domain's registration. `no-charge-no-change`: transfer will have no change to registration period and does not require charge. `no-change`: transfer charge is required, but no change in registration period. `new-term`: transfer charge is required and a new registry term is set based on the transfer date. `not-supported`: transfers are not supported for this domain or TLD. `null`: This TLD is not supported by Vercel's Registrar.</td>
</tr>
<tr>
    <td><CopyableCode code="transferable" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is transferable</td>
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
    <td><a href="#get_domain_transfer"><CopyableCode code="get_domain_transfer" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Fetch domain transfer availability or transfer status if a transfer is in progress.</td>
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
<tr id="parameter-domain">
    <td><CopyableCode code="domain" /></td>
    <td><code>string</code></td>
    <td>The name of the domain.</td>
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
    defaultValue="get_domain_transfer"
    values={[
        { label: 'get_domain_transfer', value: 'get_domain_transfer' }
    ]}
>
<TabItem value="get_domain_transfer">

Fetch domain transfer availability or transfer status if a transfer is in progress.

```sql
SELECT
reason,
status,
transferPolicy,
transferable
FROM vercel.domains.domain_registry
WHERE domain = '{{ domain }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>
