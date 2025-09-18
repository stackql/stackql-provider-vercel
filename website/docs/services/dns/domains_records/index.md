--- 
title: domains_records
hide_title: false
hide_table_of_contents: false
keywords:
  - domains_records
  - dns
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

Creates, updates, deletes, gets or lists a <code>domains_records</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>domains_records</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.dns.domains_records" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_records"
    values={[
        { label: 'get_records', value: 'get_records' }
    ]}
>
<TabItem value="get_records">

Successful response retrieving a list of paginated DNS records.

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
    <td><a href="#get_records"><CopyableCode code="get_records" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a></td>
    <td>Retrieves a list of DNS records created for a domain name. By default it returns 20 records if no limit is provided. The rest can be retrieved using the pagination options.</td>
</tr>
<tr>
    <td><a href="#create_record"><CopyableCode code="create_record" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__type"><code>data__type</code></a>, <a href="#parameter-data__value"><code>data__value</code></a>, <a href="#parameter-data__name"><code>data__name</code></a></td>
    <td></td>
    <td>Creates a DNS record for a domain.</td>
</tr>
<tr>
    <td><a href="#remove_record"><CopyableCode code="remove_record" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-recordId"><code>recordId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Removes an existing DNS record from a domain name.</td>
</tr>
<tr>
    <td><a href="#_get_records"><CopyableCode code="_get_records" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a></td>
    <td>Retrieves a list of DNS records created for a domain name. By default it returns 20 records if no limit is provided. The rest can be retrieved using the pagination options.</td>
</tr>
<tr>
    <td><a href="#update_record"><CopyableCode code="update_record" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-recordId"><code>recordId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Updates an existing DNS record for a domain name.</td>
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
    <td></td>
</tr>
<tr id="parameter-recordId">
    <td><CopyableCode code="recordId" /></td>
    <td><code>string</code></td>
    <td>The id of the DNS record</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>string</code></td>
    <td>Maximum number of records to list from a request.</td>
</tr>
<tr id="parameter-since">
    <td><CopyableCode code="since" /></td>
    <td><code>string</code></td>
    <td>Get records created after this JavaScript timestamp.</td>
</tr>
<tr id="parameter-until">
    <td><CopyableCode code="until" /></td>
    <td><code>string</code></td>
    <td>Get records created before this JavaScript timestamp.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_records"
    values={[
        { label: 'get_records', value: 'get_records' }
    ]}
>
<TabItem value="get_records">

Retrieves a list of DNS records created for a domain name. By default it returns 20 records if no limit is provided. The rest can be retrieved using the pagination options.

```sql
SELECT
*
FROM vercel.dns.domains_records
WHERE domain = '{{ domain }}' -- required
AND teamId = '{{ teamId }}' -- required
AND limit = '{{ limit }}'
AND since = '{{ since }}'
AND until = '{{ until }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_record"
    values={[
        { label: 'create_record', value: 'create_record' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_record">

Creates a DNS record for a domain.

```sql
INSERT INTO vercel.dns.domains_records (
data__name,
data__type,
data__ttl,
data__value,
data__comment,
domain,
teamId
)
SELECT 
'{{ name }}' /* required */,
'{{ type }}' /* required */,
{{ ttl }},
'{{ value }}' /* required */,
'{{ comment }}',
'{{ domain }}',
'{{ teamId }}'
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: domains_records
  props:
    - name: domain
      value: string
      description: Required parameter for the domains_records resource.
    - name: teamId
      value: string
      description: Required parameter for the domains_records resource.
    - name: name
      value: string
      description: |
        A subdomain name or an empty string for the root domain.
    - name: type
      value: string
      description: |
        Must be of type `A`.
      valid_values: ['A']
    - name: ttl
      value: number
      description: |
        The TTL value. Must be a number between 60 and 2147483647. Default value is 60.
    - name: value
      value: string
      description: |
        The record value must be a valid IPv4 address.
    - name: comment
      value: string
      description: |
        A comment to add context on what this DNS record is for
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="remove_record"
    values={[
        { label: 'remove_record', value: 'remove_record' }
    ]}
>
<TabItem value="remove_record">

Removes an existing DNS record from a domain name.

```sql
DELETE FROM vercel.dns.domains_records
WHERE domain = '{{ domain }}' --required
AND recordId = '{{ recordId }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_get_records"
    values={[
        { label: '_get_records', value: '_get_records' },
        { label: 'update_record', value: 'update_record' }
    ]}
>
<TabItem value="_get_records">

Retrieves a list of DNS records created for a domain name. By default it returns 20 records if no limit is provided. The rest can be retrieved using the pagination options.

```sql
EXEC vercel.dns.domains_records._get_records 
@domain='{{ domain }}' --required, 
@teamId='{{ teamId }}' --required, 
@limit='{{ limit }}', 
@since='{{ since }}', 
@until='{{ until }}'
;
```
</TabItem>
<TabItem value="update_record">

Updates an existing DNS record for a domain name.

```sql
EXEC vercel.dns.domains_records.update_record 
@recordId='{{ recordId }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"name": "{{ name }}", 
"value": "{{ value }}", 
"type": "{{ type }}", 
"ttl": {{ ttl }}, 
"mxPriority": {{ mxPriority }}, 
"srv": "{{ srv }}", 
"comment": "{{ comment }}"
}'
;
```
</TabItem>
</Tabs>
