--- 
title: domains
hide_title: false
hide_table_of_contents: false
keywords:
  - domains
  - projects
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
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.projects.domains" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_project_domain"
    values={[
        { label: 'get_project_domain', value: 'get_project_domain' },
        { label: 'get_project_domains', value: 'get_project_domains' }
    ]}
>
<TabItem value="get_project_domain">

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
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="apexName" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="gitBranch" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="redirect" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="redirectStatusCode" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="updatedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="verification" /></td>
    <td><code>array</code></td>
    <td>A list of verification challenges, one of which must be completed to verify the domain for use on the project. After the challenge is complete `POST /projects/:idOrName/domains/:domain/verify` to verify the domain. Possible challenges: - If `verification.type = TXT` the `verification.domain` will be checked for a TXT record matching `verification.value`.</td>
</tr>
<tr>
    <td><CopyableCode code="verified" /></td>
    <td><code>boolean</code></td>
    <td>`true` if the domain is verified for use with the project. If `false` it will not be used as an alias on this project until the challenge in `verification` is completed.</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="get_project_domains">

Successful response retrieving a list of domains

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
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="apexName" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="gitBranch" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="redirect" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="redirectStatusCode" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="updatedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="verification" /></td>
    <td><code>array</code></td>
    <td>A list of verification challenges, one of which must be completed to verify the domain for use on the project. After the challenge is complete `POST /projects/:idOrName/domains/:domain/verify` to verify the domain. Possible challenges: - If `verification.type = TXT` the `verification.domain` will be checked for a TXT record matching `verification.value`.</td>
</tr>
<tr>
    <td><CopyableCode code="verified" /></td>
    <td><code>boolean</code></td>
    <td>`true` if the domain is verified for use with the project. If `false` it will not be used as an alias on this project until the challenge in `verification` is completed.</td>
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
    <td><a href="#get_project_domain"><CopyableCode code="get_project_domain" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Get project domain by project id/name and domain name.</td>
</tr>
<tr>
    <td><a href="#get_project_domains"><CopyableCode code="get_project_domains" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-production"><code>production</code></a>, <a href="#parameter-gitBranch"><code>gitBranch</code></a>, <a href="#parameter-redirects"><code>redirects</code></a>, <a href="#parameter-redirect"><code>redirect</code></a>, <a href="#parameter-verified"><code>verified</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-order"><code>order</code></a></td>
    <td>Retrieve the domains associated with a given project by passing either the project `id` or `name` in the URL.</td>
</tr>
<tr>
    <td><a href="#remove_project_domain"><CopyableCode code="remove_project_domain" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Remove a domain from a project by passing the domain name and by specifying the project by either passing the project `id` or `name` in the URL.</td>
</tr>
<tr>
    <td><a href="#_get_project_domains"><CopyableCode code="_get_project_domains" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-production"><code>production</code></a>, <a href="#parameter-gitBranch"><code>gitBranch</code></a>, <a href="#parameter-redirects"><code>redirects</code></a>, <a href="#parameter-redirect"><code>redirect</code></a>, <a href="#parameter-verified"><code>verified</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-order"><code>order</code></a></td>
    <td>Retrieve the domains associated with a given project by passing either the project `id` or `name` in the URL.</td>
</tr>
<tr>
    <td><a href="#update_project_domain"><CopyableCode code="update_project_domain" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Update a project domain's configuration, including the name, git branch and redirect of the domain.</td>
</tr>
<tr>
    <td><a href="#add_project_domain"><CopyableCode code="add_project_domain" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-name"><code>name</code></a></td>
    <td></td>
    <td>Add a domain to the project by passing its domain name and by specifying the project by either passing the project `id` or `name` in the URL. If the domain is not yet verified to be used on this project, the request will return `verified = false`, and the domain will need to be verified according to the `verification` challenge via `POST /projects/:idOrName/domains/:domain/verify`. If the domain already exists on the project, the request will fail with a `400` status code.</td>
</tr>
<tr>
    <td><a href="#verify_project_domain"><CopyableCode code="verify_project_domain" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Attempts to verify a project domain with `verified = false` by checking the correctness of the project domain's `verification` challenge.</td>
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
    <td>The domain name you want to verify</td>
</tr>
<tr id="parameter-idOrName">
    <td><CopyableCode code="idOrName" /></td>
    <td><code>string</code></td>
    <td>The unique project identifier or the project name</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-gitBranch">
    <td><CopyableCode code="gitBranch" /></td>
    <td><code>string</code></td>
    <td>Filters domains based on specific branch.</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>number</code></td>
    <td>Maximum number of domains to list from a request (max 100).</td>
</tr>
<tr id="parameter-order">
    <td><CopyableCode code="order" /></td>
    <td><code></code></td>
    <td>Domains sort order by createdAt</td>
</tr>
<tr id="parameter-production">
    <td><CopyableCode code="production" /></td>
    <td><code></code></td>
    <td>Filters only production domains when set to `true`.</td>
</tr>
<tr id="parameter-redirect">
    <td><CopyableCode code="redirect" /></td>
    <td><code>string</code></td>
    <td>Filters domains based on their redirect target.</td>
</tr>
<tr id="parameter-redirects">
    <td><CopyableCode code="redirects" /></td>
    <td><code></code></td>
    <td>Excludes redirect project domains when \"false\". Includes redirect project domains when \"true\" (default).</td>
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
<tr id="parameter-verified">
    <td><CopyableCode code="verified" /></td>
    <td><code></code></td>
    <td>Filters domains based on their verification status.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_project_domain"
    values={[
        { label: 'get_project_domain', value: 'get_project_domain' },
        { label: 'get_project_domains', value: 'get_project_domains' }
    ]}
>
<TabItem value="get_project_domain">

Get project domain by project id/name and domain name.

```sql
SELECT
name,
apexName,
createdAt,
gitBranch,
projectId,
redirect,
redirectStatusCode,
updatedAt,
verification,
verified
FROM vercel.projects.domains
WHERE idOrName = '{{ idOrName }}' -- required
AND domain = '{{ domain }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
<TabItem value="get_project_domains">

Retrieve the domains associated with a given project by passing either the project `id` or `name` in the URL.

```sql
SELECT
name,
apexName,
createdAt,
gitBranch,
projectId,
redirect,
redirectStatusCode,
updatedAt,
verification,
verified
FROM vercel.projects.domains
WHERE idOrName = '{{ idOrName }}' -- required
AND teamId = '{{ teamId }}' -- required
AND production = '{{ production }}'
AND gitBranch = '{{ gitBranch }}'
AND redirects = '{{ redirects }}'
AND redirect = '{{ redirect }}'
AND verified = '{{ verified }}'
AND limit = '{{ limit }}'
AND since = '{{ since }}'
AND until = '{{ until }}'
AND order = '{{ order }}'
;
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="remove_project_domain"
    values={[
        { label: 'remove_project_domain', value: 'remove_project_domain' }
    ]}
>
<TabItem value="remove_project_domain">

Remove a domain from a project by passing the domain name and by specifying the project by either passing the project `id` or `name` in the URL.

```sql
DELETE FROM vercel.projects.domains
WHERE idOrName = '{{ idOrName }}' --required
AND domain = '{{ domain }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_get_project_domains"
    values={[
        { label: '_get_project_domains', value: '_get_project_domains' },
        { label: 'update_project_domain', value: 'update_project_domain' },
        { label: 'add_project_domain', value: 'add_project_domain' },
        { label: 'verify_project_domain', value: 'verify_project_domain' }
    ]}
>
<TabItem value="_get_project_domains">

Retrieve the domains associated with a given project by passing either the project `id` or `name` in the URL.

```sql
EXEC vercel.projects.domains._get_project_domains 
@idOrName='{{ idOrName }}' --required, 
@teamId='{{ teamId }}' --required, 
@production='{{ production }}', 
@gitBranch='{{ gitBranch }}', 
@redirects='{{ redirects }}', 
@redirect='{{ redirect }}', 
@verified='{{ verified }}', 
@limit='{{ limit }}', 
@since='{{ since }}', 
@until='{{ until }}', 
@order='{{ order }}'
;
```
</TabItem>
<TabItem value="update_project_domain">

Update a project domain's configuration, including the name, git branch and redirect of the domain.

```sql
EXEC vercel.projects.domains.update_project_domain 
@idOrName='{{ idOrName }}' --required, 
@domain='{{ domain }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"gitBranch": "{{ gitBranch }}", 
"redirect": "{{ redirect }}", 
"redirectStatusCode": {{ redirectStatusCode }}
}'
;
```
</TabItem>
<TabItem value="add_project_domain">

Add a domain to the project by passing its domain name and by specifying the project by either passing the project `id` or `name` in the URL. If the domain is not yet verified to be used on this project, the request will return `verified = false`, and the domain will need to be verified according to the `verification` challenge via `POST /projects/:idOrName/domains/:domain/verify`. If the domain already exists on the project, the request will fail with a `400` status code.

```sql
EXEC vercel.projects.domains.add_project_domain 
@idOrName='{{ idOrName }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"name": "{{ name }}", 
"gitBranch": "{{ gitBranch }}", 
"redirect": "{{ redirect }}", 
"redirectStatusCode": {{ redirectStatusCode }}
}'
;
```
</TabItem>
<TabItem value="verify_project_domain">

Attempts to verify a project domain with `verified = false` by checking the correctness of the project domain's `verification` challenge.

```sql
EXEC vercel.projects.domains.verify_project_domain 
@idOrName='{{ idOrName }}' --required, 
@domain='{{ domain }}' --required, 
@teamId='{{ teamId }}' --required
;
```
</TabItem>
</Tabs>
