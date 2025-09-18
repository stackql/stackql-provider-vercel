--- 
title: teams
hide_title: false
hide_table_of_contents: false
keywords:
  - teams
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

Creates, updates, deletes, gets or lists a <code>teams</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>teams</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.teams.teams" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_team"
    values={[
        { label: 'get_team', value: 'get_team' },
        { label: 'get_teams', value: 'get_teams' }
    ]}
>
<TabItem value="get_team">

The requested team

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
    <td>The Team's unique identifier. (example: team_nllPyCtREAqxxdyFKbbMDlxd)</td>
</tr>
<tr>
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td>Name associated with the Team account, or `null` if none has been provided. (example: My Team)</td>
</tr>
<tr>
    <td><CopyableCode code="avatar" /></td>
    <td><code>string</code></td>
    <td>The ID of the file used as avatar for this Team. (example: 6eb07268bcfadd309905ffb1579354084c24655c)</td>
</tr>
<tr>
    <td><CopyableCode code="slug" /></td>
    <td><code>string</code></td>
    <td>The Team's slug, which is unique across the Vercel platform. (example: my-team)</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="get_teams">

A paginated list of teams.

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
    <td><a href="#get_team"><CopyableCode code="get_team" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-slug"><code>slug</code></a></td>
    <td>Get information for the Team specified by the `teamId` parameter.</td>
</tr>
<tr>
    <td><a href="#get_teams"><CopyableCode code="get_teams" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td></td>
    <td><a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a></td>
    <td>Get a paginated list of all the Teams the authenticated User is a member of.</td>
</tr>
<tr>
    <td><a href="#create_team"><CopyableCode code="create_team" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-data__slug"><code>data__slug</code></a></td>
    <td></td>
    <td>Create a new Team under your account. You need to send a POST request with the desired Team slug, and optionally the Team name.</td>
</tr>
<tr>
    <td><a href="#delete_team"><CopyableCode code="delete_team" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-newDefaultTeamId"><code>newDefaultTeamId</code></a></td>
    <td>Delete a team under your account. You need to send a `DELETE` request with the desired team `id`. An optional array of reasons for deletion may also be sent.</td>
</tr>
<tr>
    <td><a href="#join_team"><CopyableCode code="join_team" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Join a team with a provided invite code or team ID.</td>
</tr>
<tr>
    <td><a href="#patch_team"><CopyableCode code="patch_team" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Update the information of a Team specified by the `teamId` parameter. The request body should contain the information that will be updated on the Team.</td>
</tr>
<tr>
    <td><a href="#_get_teams"><CopyableCode code="_get_teams" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td></td>
    <td><a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a></td>
    <td>Get a paginated list of all the Teams the authenticated User is a member of.</td>
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
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>number</code></td>
    <td>Maximum number of Teams which may be returned.</td>
</tr>
<tr id="parameter-newDefaultTeamId">
    <td><CopyableCode code="newDefaultTeamId" /></td>
    <td><code>string</code></td>
    <td>Id of the team to be set as the new default team</td>
</tr>
<tr id="parameter-since">
    <td><CopyableCode code="since" /></td>
    <td><code>number</code></td>
    <td>Timestamp (in milliseconds) to only include Teams created since then.</td>
</tr>
<tr id="parameter-slug">
    <td><CopyableCode code="slug" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr id="parameter-until">
    <td><CopyableCode code="until" /></td>
    <td><code>number</code></td>
    <td>Timestamp (in milliseconds) to only include Teams created until then.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_team"
    values={[
        { label: 'get_team', value: 'get_team' },
        { label: 'get_teams', value: 'get_teams' }
    ]}
>
<TabItem value="get_team">

Get information for the Team specified by the `teamId` parameter.

```sql
SELECT
id,
name,
avatar,
slug
FROM vercel.teams.teams
WHERE teamId = '{{ teamId }}' -- required
AND slug = '{{ slug }}'
;
```
</TabItem>
<TabItem value="get_teams">

Get a paginated list of all the Teams the authenticated User is a member of.

```sql
SELECT
*
FROM vercel.teams.teams
WHERE limit = '{{ limit }}'
AND since = '{{ since }}'
AND until = '{{ until }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_team"
    values={[
        { label: 'create_team', value: 'create_team' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_team">

Create a new Team under your account. You need to send a POST request with the desired Team slug, and optionally the Team name.

```sql
INSERT INTO vercel.teams.teams (
data__slug,
data__name
)
SELECT 
'{{ slug }}' /* required */,
'{{ name }}'
RETURNING
id,
billing,
slug
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: teams
  props:
    - name: slug
      value: string
      description: |
        The desired slug for the Team
    - name: name
      value: string
      description: |
        The desired name for the Team. It will be generated from the provided slug if nothing is provided
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_team"
    values={[
        { label: 'delete_team', value: 'delete_team' }
    ]}
>
<TabItem value="delete_team">

Delete a team under your account. You need to send a `DELETE` request with the desired team `id`. An optional array of reasons for deletion may also be sent.

```sql
DELETE FROM vercel.teams.teams
WHERE teamId = '{{ teamId }}' --required
AND newDefaultTeamId = '{{ newDefaultTeamId }}'
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="join_team"
    values={[
        { label: 'join_team', value: 'join_team' },
        { label: 'patch_team', value: 'patch_team' },
        { label: '_get_teams', value: '_get_teams' }
    ]}
>
<TabItem value="join_team">

Join a team with a provided invite code or team ID.

```sql
EXEC vercel.teams.teams.join_team 
@teamId='{{ teamId }}' --required 
@@json=
'{
"inviteCode": "{{ inviteCode }}", 
"teamId": "{{ teamId }}"
}'
;
```
</TabItem>
<TabItem value="patch_team">

Update the information of a Team specified by the `teamId` parameter. The request body should contain the information that will be updated on the Team.

```sql
EXEC vercel.teams.teams.patch_team 
@teamId='{{ teamId }}' --required 
@@json=
'{
"avatar": "{{ avatar }}", 
"description": "{{ description }}", 
"emailDomain": "{{ emailDomain }}", 
"name": "{{ name }}", 
"previewDeploymentSuffix": "{{ previewDeploymentSuffix }}", 
"regenerateInviteCode": {{ regenerateInviteCode }}, 
"saml": "{{ saml }}", 
"slug": "{{ slug }}", 
"enablePreviewFeedback": "{{ enablePreviewFeedback }}", 
"sensitiveEnvironmentVariablePolicy": "{{ sensitiveEnvironmentVariablePolicy }}", 
"migrateExistingEnvVariablesToSensitive": {{ migrateExistingEnvVariablesToSensitive }}, 
"remoteCaching": "{{ remoteCaching }}", 
"hideIpAddresses": {{ hideIpAddresses }}
}'
;
```
</TabItem>
<TabItem value="_get_teams">

Get a paginated list of all the Teams the authenticated User is a member of.

```sql
EXEC vercel.teams.teams._get_teams 
@limit='{{ limit }}', 
@since='{{ since }}', 
@until='{{ until }}'
;
```
</TabItem>
</Tabs>
