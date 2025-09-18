--- 
title: request
hide_title: false
hide_table_of_contents: false
keywords:
  - request
  - teams
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

Creates, updates, deletes, gets or lists a <code>request</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>request</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.teams.request" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_team_access_request"
    values={[
        { label: 'get_team_access_request', value: 'get_team_access_request' }
    ]}
>
<TabItem value="get_team_access_request">

Successfully

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
    <td><CopyableCode code="accessRequestedAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds when the user requested access to the team.</td>
</tr>
<tr>
    <td><CopyableCode code="bitbucket" /></td>
    <td><code>object</code></td>
    <td>Map of the connected Bitbucket account.</td>
</tr>
<tr>
    <td><CopyableCode code="confirmed" /></td>
    <td><code>boolean</code></td>
    <td>Current status of the membership. Will be `true` if confirmed, if pending it'll be `false`.</td>
</tr>
<tr>
    <td><CopyableCode code="github" /></td>
    <td><code>object</code></td>
    <td>Map of the connected GitHub account.</td>
</tr>
<tr>
    <td><CopyableCode code="gitlab" /></td>
    <td><code>object</code></td>
    <td>Map of the connected GitLab account.</td>
</tr>
<tr>
    <td><CopyableCode code="joinedFrom" /></td>
    <td><code>object</code></td>
    <td>A map that describes the origin from where the user joined.</td>
</tr>
<tr>
    <td><CopyableCode code="teamName" /></td>
    <td><code>string</code></td>
    <td>The name of the team. (example: My Team)</td>
</tr>
<tr>
    <td><CopyableCode code="teamSlug" /></td>
    <td><code>string</code></td>
    <td>The slug of the team. (example: my-team)</td>
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
    <td><a href="#get_team_access_request"><CopyableCode code="get_team_access_request" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-userId"><code>userId</code></a></td>
    <td></td>
    <td>Check the status of a join request. It'll respond with a 404 if the request has been declined. If no `userId` path segment was provided, this endpoint will instead return the status of the authenticated user.</td>
</tr>
<tr>
    <td><a href="#request_access_to_team"><CopyableCode code="request_access_to_team" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-joinedFrom"><code>joinedFrom</code></a></td>
    <td></td>
    <td>Request access to a team as a member. An owner has to approve the request. Only 10 users can request access to a team at the same time.</td>
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
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>ID of the Team.</td>
</tr>
<tr id="parameter-userId">
    <td><CopyableCode code="userId" /></td>
    <td><code>string</code></td>
    <td>User ID.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_team_access_request"
    values={[
        { label: 'get_team_access_request', value: 'get_team_access_request' }
    ]}
>
<TabItem value="get_team_access_request">

Check the status of a join request. It'll respond with a 404 if the request has been declined. If no `userId` path segment was provided, this endpoint will instead return the status of the authenticated user.

```sql
SELECT
accessRequestedAt,
bitbucket,
confirmed,
github,
gitlab,
joinedFrom,
teamName,
teamSlug
FROM vercel.teams.request
WHERE teamId = '{{ teamId }}' -- required
AND userId = '{{ userId }}' -- required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="request_access_to_team"
    values={[
        { label: 'request_access_to_team', value: 'request_access_to_team' }
    ]}
>
<TabItem value="request_access_to_team">

Request access to a team as a member. An owner has to approve the request. Only 10 users can request access to a team at the same time.

```sql
EXEC vercel.teams.request.request_access_to_team 
@teamId='{{ teamId }}' --required 
@@json=
'{
"joinedFrom": "{{ joinedFrom }}"
}'
;
```
</TabItem>
</Tabs>
