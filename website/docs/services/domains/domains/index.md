--- 
title: domains
hide_title: false
hide_table_of_contents: false
keywords:
  - domains
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

Creates, updates, deletes, gets or lists a <code>domains</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>domains</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.domains.domains" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_domain"
    values={[
        { label: 'get_domain', value: 'get_domain' },
        { label: 'get_domains', value: 'get_domains' }
    ]}
>
<TabItem value="get_domain">

Successful response retrieving an information for a specific domains.

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
    <td>The unique identifier of the domain. (example: EmTbe5CEJyTk2yVAHBUWy4A3sRusca3GCwRjTC1bpeVnt1)</td>
</tr>
<tr>
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td>The domain name. (example: example.com)</td>
</tr>
<tr>
    <td><CopyableCode code="boughtAt" /></td>
    <td><code>number</code></td>
    <td>If it was purchased through Vercel, the timestamp in milliseconds when it was purchased.</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds when the domain was created in the registry.</td>
</tr>
<tr>
    <td><CopyableCode code="creator" /></td>
    <td><code>object</code></td>
    <td>An object containing information of the domain creator, including the user's id, username, and email.</td>
</tr>
<tr>
    <td><CopyableCode code="customNameservers" /></td>
    <td><code>array</code></td>
    <td>A list of custom nameservers for the domain to point to. Only applies to domains purchased with Vercel.</td>
</tr>
<tr>
    <td><CopyableCode code="expiresAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds at which the domain is set to expire. `null` if not bought with Vercel.</td>
</tr>
<tr>
    <td><CopyableCode code="intendedNameservers" /></td>
    <td><code>array</code></td>
    <td>A list of the intended nameservers for the domain to point to Vercel DNS.</td>
</tr>
<tr>
    <td><CopyableCode code="nameservers" /></td>
    <td><code>array</code></td>
    <td>A list of the current nameservers of the domain.</td>
</tr>
<tr>
    <td><CopyableCode code="orderedAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds at which the domain was ordered.</td>
</tr>
<tr>
    <td><CopyableCode code="renew" /></td>
    <td><code>boolean</code></td>
    <td>Indicates whether the domain is set to automatically renew.</td>
</tr>
<tr>
    <td><CopyableCode code="serviceType" /></td>
    <td><code>string</code></td>
    <td>The type of service the domain is handled by. `external` if the DNS is externally handled, `zeit.world` if handled with Vercel, or `na` if the service is not available. (example: zeit.world)</td>
</tr>
<tr>
    <td><CopyableCode code="suffix" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="transferStartedAt" /></td>
    <td><code>number</code></td>
    <td>If transferred into Vercel, timestamp in milliseconds when the domain transfer was initiated.</td>
</tr>
<tr>
    <td><CopyableCode code="transferredAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds at which the domain was successfully transferred into Vercel. `null` if the transfer is still processing or was never transferred in.</td>
</tr>
<tr>
    <td><CopyableCode code="verified" /></td>
    <td><code>boolean</code></td>
    <td>If the domain has the ownership verified.</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="get_domains">

Successful response retrieving a list of domains.

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
    <td>The unique identifier of the domain. (example: EmTbe5CEJyTk2yVAHBUWy4A3sRusca3GCwRjTC1bpeVnt1)</td>
</tr>
<tr>
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td>The domain name. (example: example.com)</td>
</tr>
<tr>
    <td><CopyableCode code="boughtAt" /></td>
    <td><code>number</code></td>
    <td>If it was purchased through Vercel, the timestamp in milliseconds when it was purchased.</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds when the domain was created in the registry.</td>
</tr>
<tr>
    <td><CopyableCode code="creator" /></td>
    <td><code>object</code></td>
    <td>An object containing information of the domain creator, including the user's id, username, and email.</td>
</tr>
<tr>
    <td><CopyableCode code="customNameservers" /></td>
    <td><code>array</code></td>
    <td>A list of custom nameservers for the domain to point to. Only applies to domains purchased with Vercel.</td>
</tr>
<tr>
    <td><CopyableCode code="expiresAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds at which the domain is set to expire. `null` if not bought with Vercel.</td>
</tr>
<tr>
    <td><CopyableCode code="intendedNameservers" /></td>
    <td><code>array</code></td>
    <td>A list of the intended nameservers for the domain to point to Vercel DNS.</td>
</tr>
<tr>
    <td><CopyableCode code="nameservers" /></td>
    <td><code>array</code></td>
    <td>A list of the current nameservers of the domain.</td>
</tr>
<tr>
    <td><CopyableCode code="orderedAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds at which the domain was ordered.</td>
</tr>
<tr>
    <td><CopyableCode code="renew" /></td>
    <td><code>boolean</code></td>
    <td>Indicates whether the domain is set to automatically renew.</td>
</tr>
<tr>
    <td><CopyableCode code="serviceType" /></td>
    <td><code>string</code></td>
    <td>The type of service the domain is handled by. `external` if the DNS is externally handled, `zeit.world` if handled with Vercel, or `na` if the service is not available. (example: zeit.world)</td>
</tr>
<tr>
    <td><CopyableCode code="transferStartedAt" /></td>
    <td><code>number</code></td>
    <td>If transferred into Vercel, timestamp in milliseconds when the domain transfer was initiated.</td>
</tr>
<tr>
    <td><CopyableCode code="transferredAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds at which the domain was successfully transferred into Vercel. `null` if the transfer is still processing or was never transferred in.</td>
</tr>
<tr>
    <td><CopyableCode code="verified" /></td>
    <td><code>boolean</code></td>
    <td>If the domain has the ownership verified.</td>
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
    <td><a href="#get_domain"><CopyableCode code="get_domain" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Get information for a single domain in an account or team.</td>
</tr>
<tr>
    <td><a href="#get_domains"><CopyableCode code="get_domains" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a></td>
    <td>Retrieves a list of domains registered for the authenticated user or team. By default it returns the last 20 domains if no limit is provided.</td>
</tr>
<tr>
    <td><a href="#create_or_transfer_domain"><CopyableCode code="create_or_transfer_domain" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__name"><code>data__name</code></a></td>
    <td></td>
    <td>This endpoint is used for adding a new apex domain name with Vercel for the authenticating user. Can also be used for initiating a domain transfer request from an external Registrar to Vercel.</td>
</tr>
<tr>
    <td><a href="#delete_domain"><CopyableCode code="delete_domain" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Delete a previously registered domain name from Vercel. Deleting a domain will automatically remove any associated aliases.</td>
</tr>
<tr>
    <td><a href="#buy_domain"><CopyableCode code="buy_domain" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-name"><code>name</code></a></td>
    <td></td>
    <td>Allows to purchase the specified domain.</td>
</tr>
<tr>
    <td><a href="#_get_domain"><CopyableCode code="_get_domain" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Get information for a single domain in an account or team.</td>
</tr>
<tr>
    <td><a href="#_get_domains"><CopyableCode code="_get_domains" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a></td>
    <td>Retrieves a list of domains registered for the authenticated user or team. By default it returns the last 20 domains if no limit is provided.</td>
</tr>
<tr>
    <td><a href="#patch_domain"><CopyableCode code="patch_domain" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Update or move apex domain.</td>
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
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>number</code></td>
    <td>Maximum number of domains to list from a request.</td>
</tr>
<tr id="parameter-since">
    <td><CopyableCode code="since" /></td>
    <td><code>number</code></td>
    <td>Get domains created after this JavaScript timestamp.</td>
</tr>
<tr id="parameter-until">
    <td><CopyableCode code="until" /></td>
    <td><code>number</code></td>
    <td>Get domains created before this JavaScript timestamp.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_domain"
    values={[
        { label: 'get_domain', value: 'get_domain' },
        { label: 'get_domains', value: 'get_domains' }
    ]}
>
<TabItem value="get_domain">

Get information for a single domain in an account or team.

```sql
SELECT
id,
name,
boughtAt,
createdAt,
creator,
customNameservers,
expiresAt,
intendedNameservers,
nameservers,
orderedAt,
renew,
serviceType,
suffix,
transferStartedAt,
transferredAt,
verified
FROM vercel.domains.domains
WHERE domain = '{{ domain }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
<TabItem value="get_domains">

Retrieves a list of domains registered for the authenticated user or team. By default it returns the last 20 domains if no limit is provided.

```sql
SELECT
id,
name,
boughtAt,
createdAt,
creator,
customNameservers,
expiresAt,
intendedNameservers,
nameservers,
orderedAt,
renew,
serviceType,
transferStartedAt,
transferredAt,
verified
FROM vercel.domains.domains
WHERE teamId = '{{ teamId }}' -- required
AND limit = '{{ limit }}'
AND since = '{{ since }}'
AND until = '{{ until }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_or_transfer_domain"
    values={[
        { label: 'create_or_transfer_domain', value: 'create_or_transfer_domain' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_or_transfer_domain">

This endpoint is used for adding a new apex domain name with Vercel for the authenticating user. Can also be used for initiating a domain transfer request from an external Registrar to Vercel.

```sql
INSERT INTO vercel.domains.domains (
data__name,
data__cdnEnabled,
data__zone,
data__method,
teamId
)
SELECT 
'{{ name }}' /* required */,
{{ cdnEnabled }},
{{ zone }},
'{{ method }}',
'{{ teamId }}'
RETURNING
domain
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: domains
  props:
    - name: teamId
      value: string
      description: Required parameter for the domains resource.
    - name: name
      value: string
      description: |
        The domain name you want to add.
    - name: cdnEnabled
      value: boolean
      description: |
        Whether the domain has the Vercel Edge Network enabled or not.
    - name: zone
      value: boolean
    - name: method
      value: string
      description: |
        The domain operation to perform.
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_domain"
    values={[
        { label: 'delete_domain', value: 'delete_domain' }
    ]}
>
<TabItem value="delete_domain">

Delete a previously registered domain name from Vercel. Deleting a domain will automatically remove any associated aliases.

```sql
DELETE FROM vercel.domains.domains
WHERE domain = '{{ domain }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="buy_domain"
    values={[
        { label: 'buy_domain', value: 'buy_domain' },
        { label: '_get_domain', value: '_get_domain' },
        { label: '_get_domains', value: '_get_domains' },
        { label: 'patch_domain', value: 'patch_domain' }
    ]}
>
<TabItem value="buy_domain">

Allows to purchase the specified domain.

```sql
EXEC vercel.domains.domains.buy_domain 
@teamId='{{ teamId }}' --required 
@@json=
'{
"name": "{{ name }}", 
"expectedPrice": {{ expectedPrice }}, 
"renew": {{ renew }}
}'
;
```
</TabItem>
<TabItem value="_get_domain">

Get information for a single domain in an account or team.

```sql
EXEC vercel.domains.domains._get_domain 
@domain='{{ domain }}' --required, 
@teamId='{{ teamId }}' --required
;
```
</TabItem>
<TabItem value="_get_domains">

Retrieves a list of domains registered for the authenticated user or team. By default it returns the last 20 domains if no limit is provided.

```sql
EXEC vercel.domains.domains._get_domains 
@teamId='{{ teamId }}' --required, 
@limit='{{ limit }}', 
@since='{{ since }}', 
@until='{{ until }}'
;
```
</TabItem>
<TabItem value="patch_domain">

Update or move apex domain.

```sql
EXEC vercel.domains.domains.patch_domain 
@domain='{{ domain }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"op": "{{ op }}", 
"renew": {{ renew }}, 
"customNameservers": "{{ customNameservers }}", 
"zone": {{ zone }}
}'
;
```
</TabItem>
</Tabs>
