--- 
title: certs
hide_title: false
hide_table_of_contents: false
keywords:
  - certs
  - certs
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

Creates, updates, deletes, gets or lists a <code>certs</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>certs</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.certs.certs" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_cert_by_id"
    values={[
        { label: 'get_cert_by_id', value: 'get_cert_by_id' }
    ]}
>
<TabItem value="get_cert_by_id">

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
    <td><CopyableCode code="autoRenew" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="cns" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="expiresAt" /></td>
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
    <td><a href="#get_cert_by_id"><CopyableCode code="get_cert_by_id" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Get cert by id</td>
</tr>
<tr>
    <td><a href="#remove_cert"><CopyableCode code="remove_cert" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Remove cert</td>
</tr>
<tr>
    <td><a href="#issue_cert"><CopyableCode code="issue_cert" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Issue a new cert</td>
</tr>
<tr>
    <td><a href="#upload_cert"><CopyableCode code="upload_cert" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-ca"><code>ca</code></a>, <a href="#parameter-key"><code>key</code></a>, <a href="#parameter-cert"><code>cert</code></a></td>
    <td></td>
    <td>Upload a cert</td>
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
    <td><code>string</code></td>
    <td>The cert id to remove</td>
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
    defaultValue="get_cert_by_id"
    values={[
        { label: 'get_cert_by_id', value: 'get_cert_by_id' }
    ]}
>
<TabItem value="get_cert_by_id">

Get cert by id

```sql
SELECT
id,
autoRenew,
cns,
createdAt,
expiresAt
FROM vercel.certs.certs
WHERE id = '{{ id }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="remove_cert"
    values={[
        { label: 'remove_cert', value: 'remove_cert' }
    ]}
>
<TabItem value="remove_cert">

Remove cert

```sql
DELETE FROM vercel.certs.certs
WHERE id = '{{ id }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="issue_cert"
    values={[
        { label: 'issue_cert', value: 'issue_cert' },
        { label: 'upload_cert', value: 'upload_cert' }
    ]}
>
<TabItem value="issue_cert">

Issue a new cert

```sql
EXEC vercel.certs.certs.issue_cert 
@teamId='{{ teamId }}' --required 
@@json=
'{
"cns": "{{ cns }}"
}'
;
```
</TabItem>
<TabItem value="upload_cert">

Upload a cert

```sql
EXEC vercel.certs.certs.upload_cert 
@teamId='{{ teamId }}' --required 
@@json=
'{
"ca": "{{ ca }}", 
"key": "{{ key }}", 
"cert": "{{ cert }}", 
"skipValidation": {{ skipValidation }}
}'
;
```
</TabItem>
</Tabs>
