--- 
title: projects_members
hide_title: false
hide_table_of_contents: false
keywords:
  - projects_members
  - project_members
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

Creates, updates, deletes, gets or lists a <code>projects_members</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>projects_members</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.project_members.projects_members" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_project_members"
    values={[
        { label: 'get_project_members', value: 'get_project_members' }
    ]}
>
<TabItem value="get_project_members">

Paginated list of members for the project.

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
    <td><a href="#get_project_members"><CopyableCode code="get_project_members" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-search"><code>search</code></a></td>
    <td>Lists all members of a project.</td>
</tr>
<tr>
    <td><a href="#remove_project_member"><CopyableCode code="remove_project_member" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-uid"><code>uid</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Remove a member from a specific project</td>
</tr>
<tr>
    <td><a href="#_get_project_members"><CopyableCode code="_get_project_members" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-search"><code>search</code></a></td>
    <td>Lists all members of a project.</td>
</tr>
<tr>
    <td><a href="#add_project_member"><CopyableCode code="add_project_member" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-uid"><code>uid</code></a></td>
    <td></td>
    <td>Adds a new member to the project.</td>
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
<tr id="parameter-idOrName">
    <td><CopyableCode code="idOrName" /></td>
    <td><code>string</code></td>
    <td>The ID or name of the Project.</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-uid">
    <td><CopyableCode code="uid" /></td>
    <td><code>string</code></td>
    <td>The user ID of the member.</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>integer</code></td>
    <td>Limit how many project members should be returned</td>
</tr>
<tr id="parameter-search">
    <td><CopyableCode code="search" /></td>
    <td><code>string</code></td>
    <td>Search project members by their name, username, and email.</td>
</tr>
<tr id="parameter-since">
    <td><CopyableCode code="since" /></td>
    <td><code>integer</code></td>
    <td>Timestamp in milliseconds to only include members added since then.</td>
</tr>
<tr id="parameter-until">
    <td><CopyableCode code="until" /></td>
    <td><code>integer</code></td>
    <td>Timestamp in milliseconds to only include members added until then.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_project_members"
    values={[
        { label: 'get_project_members', value: 'get_project_members' }
    ]}
>
<TabItem value="get_project_members">

Lists all members of a project.

```sql
SELECT
*
FROM vercel.project_members.projects_members
WHERE idOrName = '{{ idOrName }}' -- required
AND teamId = '{{ teamId }}' -- required
AND limit = '{{ limit }}'
AND since = '{{ since }}'
AND until = '{{ until }}'
AND search = '{{ search }}'
;
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="remove_project_member"
    values={[
        { label: 'remove_project_member', value: 'remove_project_member' }
    ]}
>
<TabItem value="remove_project_member">

Remove a member from a specific project

```sql
DELETE FROM vercel.project_members.projects_members
WHERE idOrName = '{{ idOrName }}' --required
AND uid = '{{ uid }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_get_project_members"
    values={[
        { label: '_get_project_members', value: '_get_project_members' },
        { label: 'add_project_member', value: 'add_project_member' }
    ]}
>
<TabItem value="_get_project_members">

Lists all members of a project.

```sql
EXEC vercel.project_members.projects_members._get_project_members 
@idOrName='{{ idOrName }}' --required, 
@teamId='{{ teamId }}' --required, 
@limit='{{ limit }}', 
@since='{{ since }}', 
@until='{{ until }}', 
@search='{{ search }}'
;
```
</TabItem>
<TabItem value="add_project_member">

Adds a new member to the project.

```sql
EXEC vercel.project_members.projects_members.add_project_member 
@idOrName='{{ idOrName }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"uid": "{{ uid }}", 
"username": "{{ username }}", 
"email": "{{ email }}", 
"role": "{{ role }}"
}'
;
```
</TabItem>
</Tabs>
