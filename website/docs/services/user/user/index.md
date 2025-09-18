--- 
title: user
hide_title: false
hide_table_of_contents: false
keywords:
  - user
  - user
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

Creates, updates, deletes, gets or lists a <code>user</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>user</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.user.user" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_auth_user"
    values={[
        { label: 'get_auth_user', value: 'get_auth_user' }
    ]}
>
<TabItem value="get_auth_user">

Successful response.

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
    <td><a href="#get_auth_user"><CopyableCode code="get_auth_user" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td></td>
    <td></td>
    <td>Retrieves information related to the currently authenticated User.</td>
</tr>
<tr>
    <td><a href="#request_delete"><CopyableCode code="request_delete" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td></td>
    <td></td>
    <td>Initiates the deletion process for the currently authenticated User, by sending a deletion confirmation email. The email contains a link that the user needs to visit in order to proceed with the deletion process.</td>
</tr>
<tr>
    <td><a href="#_get_auth_user"><CopyableCode code="_get_auth_user" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td></td>
    <td></td>
    <td>Retrieves information related to the currently authenticated User.</td>
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
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_auth_user"
    values={[
        { label: 'get_auth_user', value: 'get_auth_user' }
    ]}
>
<TabItem value="get_auth_user">

Retrieves information related to the currently authenticated User.

```sql
SELECT
*
FROM vercel.user.user
;
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="request_delete"
    values={[
        { label: 'request_delete', value: 'request_delete' }
    ]}
>
<TabItem value="request_delete">

Initiates the deletion process for the currently authenticated User, by sending a deletion confirmation email. The email contains a link that the user needs to visit in order to proceed with the deletion process.

```sql
DELETE FROM vercel.user.user
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_get_auth_user"
    values={[
        { label: '_get_auth_user', value: '_get_auth_user' }
    ]}
>
<TabItem value="_get_auth_user">

Retrieves information related to the currently authenticated User.

```sql
EXEC vercel.user.user._get_auth_user 

;
```
</TabItem>
</Tabs>
