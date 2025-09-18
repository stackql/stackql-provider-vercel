--- 
title: invites
hide_title: false
hide_table_of_contents: false
keywords:
  - invites
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

Creates, updates, deletes, gets or lists an <code>invites</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>invites</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.teams.invites" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

`SELECT` not supported for this resource, use `SHOW METHODS` to view available operations for the resource.


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
    <td><a href="#delete_team_invite_code"><CopyableCode code="delete_team_invite_code" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-inviteId"><code>inviteId</code></a></td>
    <td></td>
    <td>Delete an active Team invite code.</td>
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
<tr id="parameter-inviteId">
    <td><CopyableCode code="inviteId" /></td>
    <td><code>string</code></td>
    <td>The Team invite code ID.</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
</tbody>
</table>

## `DELETE` examples

<Tabs
    defaultValue="delete_team_invite_code"
    values={[
        { label: 'delete_team_invite_code', value: 'delete_team_invite_code' }
    ]}
>
<TabItem value="delete_team_invite_code">

Delete an active Team invite code.

```sql
DELETE FROM vercel.teams.invites
WHERE teamId = '{{ teamId }}' --required
AND inviteId = '{{ inviteId }}' --required
;
```
</TabItem>
</Tabs>
