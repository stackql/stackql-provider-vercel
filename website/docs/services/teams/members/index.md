--- 
title: members
hide_title: false
hide_table_of_contents: false
keywords:
  - members
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

Creates, updates, deletes, gets or lists a <code>members</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>members</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.teams.members" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_team_members"
    values={[
        { label: 'get_team_members', value: 'get_team_members' }
    ]}
>
<TabItem value="get_team_members">

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
    <td>The name of this user. (example: Jane Doe)</td>
</tr>
<tr>
    <td><CopyableCode code="accessRequestedAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds for when this team member was accepted by an owner.</td>
</tr>
<tr>
    <td><CopyableCode code="avatar" /></td>
    <td><code>string</code></td>
    <td>ID of the file for the Avatar of this member. (example: 123a6c5209bc3778245d011443644c8d27dc2c50)</td>
</tr>
<tr>
    <td><CopyableCode code="bitbucket" /></td>
    <td><code>object</code></td>
    <td>Information about the Bitbucket account of this user.</td>
</tr>
<tr>
    <td><CopyableCode code="confirmed" /></td>
    <td><code>boolean</code></td>
    <td>Boolean that indicates if this member was confirmed by an owner.</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds when this member was added.</td>
</tr>
<tr>
    <td><CopyableCode code="email" /></td>
    <td><code>string</code></td>
    <td>The email of this member. (example: jane.doe@example.com)</td>
</tr>
<tr>
    <td><CopyableCode code="github" /></td>
    <td><code>object</code></td>
    <td>Information about the GitHub account for this user.</td>
</tr>
<tr>
    <td><CopyableCode code="gitlab" /></td>
    <td><code>object</code></td>
    <td>Information about the GitLab account of this user.</td>
</tr>
<tr>
    <td><CopyableCode code="joinedFrom" /></td>
    <td><code>object</code></td>
    <td>Map with information about the members origin if they joined by requesting access.</td>
</tr>
<tr>
    <td><CopyableCode code="projects" /></td>
    <td><code>array</code></td>
    <td>Array of project memberships</td>
</tr>
<tr>
    <td><CopyableCode code="role" /></td>
    <td><code>string</code></td>
    <td>Role of this user in the team. (example: OWNER)</td>
</tr>
<tr>
    <td><CopyableCode code="uid" /></td>
    <td><code>string</code></td>
    <td>The ID of this user. (example: zTuNVUXEAvvnNN3IaqinkyMw)</td>
</tr>
<tr>
    <td><CopyableCode code="username" /></td>
    <td><code>string</code></td>
    <td>The unique username of this user. (example: jane-doe)</td>
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
    <td><a href="#get_team_members"><CopyableCode code="get_team_members" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-search"><code>search</code></a>, <a href="#parameter-role"><code>role</code></a>, <a href="#parameter-excludeProject"><code>excludeProject</code></a>, <a href="#parameter-eligibleMembersForProjectId"><code>eligibleMembersForProjectId</code></a></td>
    <td>Get a paginated list of team members for the provided team.</td>
</tr>
<tr>
    <td><a href="#remove_team_member"><CopyableCode code="remove_team_member" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-uid"><code>uid</code></a></td>
    <td><a href="#parameter-newDefaultTeamId"><code>newDefaultTeamId</code></a></td>
    <td>Remove a Team Member from the Team, or dismiss a user that requested access, or leave a team.</td>
</tr>
<tr>
    <td><a href="#_get_team_members"><CopyableCode code="_get_team_members" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-search"><code>search</code></a>, <a href="#parameter-role"><code>role</code></a>, <a href="#parameter-excludeProject"><code>excludeProject</code></a>, <a href="#parameter-eligibleMembersForProjectId"><code>eligibleMembersForProjectId</code></a></td>
    <td>Get a paginated list of team members for the provided team.</td>
</tr>
<tr>
    <td><a href="#invite_user_to_team"><CopyableCode code="invite_user_to_team" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Invite a user to join the team specified in the URL. The authenticated user needs to be an `OWNER` in order to successfully invoke this endpoint. The user can be specified with an email or an ID. If both email and ID are provided, ID will take priority.</td>
</tr>
<tr>
    <td><a href="#update_team_member"><CopyableCode code="update_team_member" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-uid"><code>uid</code></a></td>
    <td></td>
    <td>Update the membership of a Team Member on the Team specified by `teamId`, such as changing the _role_ of the member, or confirming a request to join the Team for an unconfirmed member. The authenticated user must be an `OWNER` of the Team.</td>
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
<tr id="parameter-uid">
    <td><CopyableCode code="uid" /></td>
    <td><code>string</code></td>
    <td>The ID of the member.</td>
</tr>
<tr id="parameter-eligibleMembersForProjectId">
    <td><CopyableCode code="eligibleMembersForProjectId" /></td>
    <td><code>string</code></td>
    <td>Include team members who are eligible to be members of the specified project.</td>
</tr>
<tr id="parameter-excludeProject">
    <td><CopyableCode code="excludeProject" /></td>
    <td><code>string</code></td>
    <td>Exclude members who belong to the specified project.</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>number</code></td>
    <td>Limit how many teams should be returned</td>
</tr>
<tr id="parameter-newDefaultTeamId">
    <td><CopyableCode code="newDefaultTeamId" /></td>
    <td><code>string</code></td>
    <td>The ID of the team to set as the new default team for the Northstar user.</td>
</tr>
<tr id="parameter-role">
    <td><CopyableCode code="role" /></td>
    <td><code>string</code></td>
    <td>Only return members with the specified team role.</td>
</tr>
<tr id="parameter-search">
    <td><CopyableCode code="search" /></td>
    <td><code>string</code></td>
    <td>Search team members by their name, username, and email.</td>
</tr>
<tr id="parameter-since">
    <td><CopyableCode code="since" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds to only include members added since then.</td>
</tr>
<tr id="parameter-until">
    <td><CopyableCode code="until" /></td>
    <td><code>number</code></td>
    <td>Timestamp in milliseconds to only include members added until then.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_team_members"
    values={[
        { label: 'get_team_members', value: 'get_team_members' }
    ]}
>
<TabItem value="get_team_members">

Get a paginated list of team members for the provided team.

```sql
SELECT
name,
accessRequestedAt,
avatar,
bitbucket,
confirmed,
createdAt,
email,
github,
gitlab,
joinedFrom,
projects,
role,
uid,
username
FROM vercel.teams.members
WHERE teamId = '{{ teamId }}' -- required
AND limit = '{{ limit }}'
AND since = '{{ since }}'
AND until = '{{ until }}'
AND search = '{{ search }}'
AND role = '{{ role }}'
AND excludeProject = '{{ excludeProject }}'
AND eligibleMembersForProjectId = '{{ eligibleMembersForProjectId }}'
;
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="remove_team_member"
    values={[
        { label: 'remove_team_member', value: 'remove_team_member' }
    ]}
>
<TabItem value="remove_team_member">

Remove a Team Member from the Team, or dismiss a user that requested access, or leave a team.

```sql
DELETE FROM vercel.teams.members
WHERE teamId = '{{ teamId }}' --required
AND uid = '{{ uid }}' --required
AND newDefaultTeamId = '{{ newDefaultTeamId }}'
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_get_team_members"
    values={[
        { label: '_get_team_members', value: '_get_team_members' },
        { label: 'invite_user_to_team', value: 'invite_user_to_team' },
        { label: 'update_team_member', value: 'update_team_member' }
    ]}
>
<TabItem value="_get_team_members">

Get a paginated list of team members for the provided team.

```sql
EXEC vercel.teams.members._get_team_members 
@teamId='{{ teamId }}' --required, 
@limit='{{ limit }}', 
@since='{{ since }}', 
@until='{{ until }}', 
@search='{{ search }}', 
@role='{{ role }}', 
@excludeProject='{{ excludeProject }}', 
@eligibleMembersForProjectId='{{ eligibleMembersForProjectId }}'
;
```
</TabItem>
<TabItem value="invite_user_to_team">

Invite a user to join the team specified in the URL. The authenticated user needs to be an `OWNER` in order to successfully invoke this endpoint. The user can be specified with an email or an ID. If both email and ID are provided, ID will take priority.

```sql
EXEC vercel.teams.members.invite_user_to_team 
@teamId='{{ teamId }}' --required 
@@json=
'{
"uid": "{{ uid }}", 
"email": "{{ email }}", 
"role": "{{ role }}", 
"projects": "{{ projects }}"
}'
;
```
</TabItem>
<TabItem value="update_team_member">

Update the membership of a Team Member on the Team specified by `teamId`, such as changing the _role_ of the member, or confirming a request to join the Team for an unconfirmed member. The authenticated user must be an `OWNER` of the Team.

```sql
EXEC vercel.teams.members.update_team_member 
@teamId='{{ teamId }}' --required, 
@uid='{{ uid }}' --required 
@@json=
'{
"confirmed": {{ confirmed }}, 
"role": "{{ role }}", 
"projects": "{{ projects }}", 
"joinedFrom": "{{ joinedFrom }}"
}'
;
```
</TabItem>
</Tabs>
