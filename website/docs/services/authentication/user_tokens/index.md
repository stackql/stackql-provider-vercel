--- 
title: user_tokens
hide_title: false
hide_table_of_contents: false
keywords:
  - user_tokens
  - authentication
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

Creates, updates, deletes, gets or lists a <code>user_tokens</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>user_tokens</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.authentication.user_tokens" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_auth_token"
    values={[
        { label: 'get_auth_token', value: 'get_auth_token' },
        { label: 'list_auth_tokens', value: 'list_auth_tokens' }
    ]}
>
<TabItem value="get_auth_token">

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
<tr>
    <td><CopyableCode code="token" /></td>
    <td><code>object</code></td>
    <td>Authentication token metadata.</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="list_auth_tokens">

Authentication token metadata.

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
    <td>The unique identifier of the token. (example: 5d9f2ebd38ddca62e5d51e9c1704c72530bdc8bfdd41e782a6687c48399e8391)</td>
</tr>
<tr>
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td>The human-readable name of the token.</td>
</tr>
<tr>
    <td><CopyableCode code="activeAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp (in milliseconds) of when the token was most recently used.</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp (in milliseconds) of when the token was created.</td>
</tr>
<tr>
    <td><CopyableCode code="expiresAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp (in milliseconds) of when the token expires.</td>
</tr>
<tr>
    <td><CopyableCode code="origin" /></td>
    <td><code>string</code></td>
    <td>The origin of how the token was created. (example: github)</td>
</tr>
<tr>
    <td><CopyableCode code="scopes" /></td>
    <td><code>array</code></td>
    <td>The access scopes granted to the token.</td>
</tr>
<tr>
    <td><CopyableCode code="type" /></td>
    <td><code>string</code></td>
    <td>The type of the token. (example: oauth2-token)</td>
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
    <td><a href="#get_auth_token"><CopyableCode code="get_auth_token" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-tokenId"><code>tokenId</code></a></td>
    <td></td>
    <td>Retrieve metadata about an authentication token belonging to the currently authenticated User.</td>
</tr>
<tr>
    <td><a href="#list_auth_tokens"><CopyableCode code="list_auth_tokens" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td></td>
    <td></td>
    <td>Retrieve a list of the current User's authentication tokens.</td>
</tr>
<tr>
    <td><a href="#create_auth_token"><CopyableCode code="create_auth_token" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__name"><code>data__name</code></a></td>
    <td></td>
    <td>Creates and returns a new authentication token for the currently authenticated User. The `bearerToken` property is only provided once, in the response body, so be sure to save it on the client for use with API requests.</td>
</tr>
<tr>
    <td><a href="#delete_auth_token"><CopyableCode code="delete_auth_token" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-tokenId"><code>tokenId</code></a></td>
    <td></td>
    <td>Invalidate an authentication token, such that it will no longer be valid for future HTTP requests.</td>
</tr>
<tr>
    <td><a href="#_list_auth_tokens"><CopyableCode code="_list_auth_tokens" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td></td>
    <td></td>
    <td>Retrieve a list of the current User's authentication tokens.</td>
</tr>
<tr>
    <td><a href="#verify_token"><CopyableCode code="verify_token" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-token"><code>token</code></a></td>
    <td><a href="#parameter-email"><code>email</code></a>, <a href="#parameter-tokenName"><code>tokenName</code></a>, <a href="#parameter-ssoUserId"><code>ssoUserId</code></a>, <a href="#parameter-teamName"><code>teamName</code></a>, <a href="#parameter-teamSlug"><code>teamSlug</code></a>, <a href="#parameter-teamPlan"><code>teamPlan</code></a></td>
    <td>Verify the user accepted the login request and get a authentication token. The user email address and the token received after requesting the login must be added to the URL as a query string with the names `email` and `token`.</td>
</tr>
<tr>
    <td><a href="#email_login"><CopyableCode code="email_login" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-email"><code>email</code></a></td>
    <td></td>
    <td>Request a new login for a user to get a token. This will respond with a verification token and send an email to confirm the request. Once confirmed you can use the verification token to get an authentication token.</td>
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
<tr id="parameter-token">
    <td><CopyableCode code="token" /></td>
    <td><code>string</code></td>
    <td>The token returned when the login was requested.</td>
</tr>
<tr id="parameter-tokenId">
    <td><CopyableCode code="tokenId" /></td>
    <td><code>string</code></td>
    <td>The identifier of the token to invalidate. The special value \"current\" may be supplied, which invalidates the token that the HTTP request was authenticated with.</td>
</tr>
<tr id="parameter-email">
    <td><CopyableCode code="email" /></td>
    <td><code>string</code></td>
    <td>Email to verify the login.</td>
</tr>
<tr id="parameter-ssoUserId">
    <td><CopyableCode code="ssoUserId" /></td>
    <td><code>string</code></td>
    <td>The SAML Profile ID, when connecting a SAML Profile to a Team member for the first time.</td>
</tr>
<tr id="parameter-teamName">
    <td><CopyableCode code="teamName" /></td>
    <td><code>string</code></td>
    <td>The name of this user's team.</td>
</tr>
<tr id="parameter-teamPlan">
    <td><CopyableCode code="teamPlan" /></td>
    <td><code>string</code></td>
    <td>The plan for this user's team (pro or hobby).</td>
</tr>
<tr id="parameter-teamSlug">
    <td><CopyableCode code="teamSlug" /></td>
    <td><code>string</code></td>
    <td>The slug for this user's team.</td>
</tr>
<tr id="parameter-tokenName">
    <td><CopyableCode code="tokenName" /></td>
    <td><code>string</code></td>
    <td>The desired name for the token. It will be displayed on the user account details.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_auth_token"
    values={[
        { label: 'get_auth_token', value: 'get_auth_token' },
        { label: 'list_auth_tokens', value: 'list_auth_tokens' }
    ]}
>
<TabItem value="get_auth_token">

Retrieve metadata about an authentication token belonging to the currently authenticated User.

```sql
SELECT
token
FROM vercel.authentication.user_tokens
WHERE tokenId = '{{ tokenId }}' -- required
;
```
</TabItem>
<TabItem value="list_auth_tokens">

Retrieve a list of the current User's authentication tokens.

```sql
SELECT
id,
name,
activeAt,
createdAt,
expiresAt,
origin,
scopes,
type
FROM vercel.authentication.user_tokens
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_auth_token"
    values={[
        { label: 'create_auth_token', value: 'create_auth_token' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_auth_token">

Creates and returns a new authentication token for the currently authenticated User. The `bearerToken` property is only provided once, in the response body, so be sure to save it on the client for use with API requests.

```sql
INSERT INTO vercel.authentication.user_tokens (
data__name,
data__expiresAt,
teamId
)
SELECT 
'{{ name }}' /* required */,
{{ expiresAt }},
'{{ teamId }}'
RETURNING
bearerToken,
token
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: user_tokens
  props:
    - name: teamId
      value: string
      description: Required parameter for the user_tokens resource.
    - name: name
      value: string
    - name: expiresAt
      value: number
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_auth_token"
    values={[
        { label: 'delete_auth_token', value: 'delete_auth_token' }
    ]}
>
<TabItem value="delete_auth_token">

Invalidate an authentication token, such that it will no longer be valid for future HTTP requests.

```sql
DELETE FROM vercel.authentication.user_tokens
WHERE tokenId = '{{ tokenId }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_list_auth_tokens"
    values={[
        { label: '_list_auth_tokens', value: '_list_auth_tokens' },
        { label: 'verify_token', value: 'verify_token' },
        { label: 'email_login', value: 'email_login' }
    ]}
>
<TabItem value="_list_auth_tokens">

Retrieve a list of the current User's authentication tokens.

```sql
EXEC vercel.authentication.user_tokens._list_auth_tokens 

;
```
</TabItem>
<TabItem value="verify_token">

Verify the user accepted the login request and get a authentication token. The user email address and the token received after requesting the login must be added to the URL as a query string with the names `email` and `token`.

```sql
EXEC vercel.authentication.user_tokens.verify_token 
@token='{{ token }}' --required, 
@email='{{ email }}', 
@tokenName='{{ tokenName }}', 
@ssoUserId='{{ ssoUserId }}', 
@teamName='{{ teamName }}', 
@teamSlug='{{ teamSlug }}', 
@teamPlan='{{ teamPlan }}'
;
```
</TabItem>
<TabItem value="email_login">

Request a new login for a user to get a token. This will respond with a verification token and send an email to confirm the request. Once confirmed you can use the verification token to get an authentication token.

```sql
EXEC vercel.authentication.user_tokens.email_login 
@@json=
'{
"email": "{{ email }}", 
"tokenName": "{{ tokenName }}"
}'
;
```
</TabItem>
</Tabs>
