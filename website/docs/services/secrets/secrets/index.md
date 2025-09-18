--- 
title: secrets
hide_title: false
hide_table_of_contents: false
keywords:
  - secrets
  - secrets
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

Creates, updates, deletes, gets or lists a <code>secrets</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>secrets</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.secrets.secrets" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_secret"
    values={[
        { label: 'get_secret', value: 'get_secret' },
        { label: 'get_secrets', value: 'get_secrets' }
    ]}
>
<TabItem value="get_secret">

Successful response retrieving a secret.

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
    <td>The name of the secret. (example: my-api-key)</td>
</tr>
<tr>
    <td><CopyableCode code="created" /></td>
    <td><code>string (date-time)</code></td>
    <td>The date when the secret was created. (example: 2021-02-10T13:11:49.180Z)</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp for when the secret was created.</td>
</tr>
<tr>
    <td><CopyableCode code="decryptable" /></td>
    <td><code>boolean</code></td>
    <td>Indicates whether the secret value can be decrypted after it has been created.</td>
</tr>
<tr>
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the project which the secret belongs to. (example: prj_2WjyKQmM8ZnGcJsPWMrHRHrE)</td>
</tr>
<tr>
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the team the secret was created for. (example: team_LLHUOMOoDlqOp8wPE4kFo9pE)</td>
</tr>
<tr>
    <td><CopyableCode code="uid" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the secret. (example: sec_XCG7t7AIHuO2SBA8667zNUiM)</td>
</tr>
<tr>
    <td><CopyableCode code="userId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the user who created the secret. (example: 2qDDuGFTWXBLDNnqZfWPDp1A)</td>
</tr>
<tr>
    <td><CopyableCode code="value" /></td>
    <td><code>string</code></td>
    <td>The value of the secret.</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="get_secrets">

Successful response retrieving a list of secrets.

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
    <td>The name of the secret. (example: my-api-key)</td>
</tr>
<tr>
    <td><CopyableCode code="created" /></td>
    <td><code>string (date-time)</code></td>
    <td>The date when the secret was created. (example: 2021-02-10T13:11:49.180Z)</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>Timestamp for when the secret was created.</td>
</tr>
<tr>
    <td><CopyableCode code="decryptable" /></td>
    <td><code>boolean</code></td>
    <td>Indicates whether the secret value can be decrypted after it has been created.</td>
</tr>
<tr>
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the project which the secret belongs to. (example: prj_2WjyKQmM8ZnGcJsPWMrHRHrE)</td>
</tr>
<tr>
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the team the secret was created for. (example: team_LLHUOMOoDlqOp8wPE4kFo9pE)</td>
</tr>
<tr>
    <td><CopyableCode code="uid" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the secret. (example: sec_XCG7t7AIHuO2SBA8667zNUiM)</td>
</tr>
<tr>
    <td><CopyableCode code="userId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the user who created the secret. (example: 2qDDuGFTWXBLDNnqZfWPDp1A)</td>
</tr>
<tr>
    <td><CopyableCode code="value" /></td>
    <td><code>string</code></td>
    <td>The value of the secret.</td>
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
    <td><a href="#get_secret"><CopyableCode code="get_secret" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-decrypt"><code>decrypt</code></a></td>
    <td>Retrieves the information for a specific secret by passing either the secret id or name in the URL.</td>
</tr>
<tr>
    <td><a href="#get_secrets"><CopyableCode code="get_secrets" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-projectId"><code>projectId</code></a></td>
    <td>Retrieves the active Vercel secrets for the authenticated user or team. By default it returns 20 secrets. The rest can be retrieved using the pagination options. The body will contain an entry for each secret.</td>
</tr>
<tr>
    <td><a href="#create_secret"><CopyableCode code="create_secret" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-name"><code>name</code></a>, <a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__name"><code>data__name</code></a>, <a href="#parameter-data__value"><code>data__value</code></a></td>
    <td></td>
    <td>Allows to create a new secret.</td>
</tr>
<tr>
    <td><a href="#delete_secret"><CopyableCode code="delete_secret" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>This deletes the user or team’s secret defined in the URL.</td>
</tr>
<tr>
    <td><a href="#_get_secrets"><CopyableCode code="_get_secrets" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-projectId"><code>projectId</code></a></td>
    <td>Retrieves the active Vercel secrets for the authenticated user or team. By default it returns 20 secrets. The rest can be retrieved using the pagination options. The body will contain an entry for each secret.</td>
</tr>
<tr>
    <td><a href="#rename_secret"><CopyableCode code="rename_secret" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-name"><code>name</code></a>, <a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-name"><code>name</code></a></td>
    <td></td>
    <td>Enables to edit the name of a secret. The name has to be unique to the user or team’s secrets.</td>
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
    <td>The name or the unique identifier to which the secret belongs to.</td>
</tr>
<tr id="parameter-name">
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td>The name of the secret.</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-decrypt">
    <td><CopyableCode code="decrypt" /></td>
    <td><code>string</code></td>
    <td>Whether to try to decrypt the value of the secret. Only works if `decryptable` has been set to `true` when the secret was created.</td>
</tr>
<tr id="parameter-id">
    <td><CopyableCode code="id" /></td>
    <td><code>string</code></td>
    <td>Filter out secrets based on comma separated secret ids.</td>
</tr>
<tr id="parameter-projectId">
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td>Filter out secrets that belong to a project.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_secret"
    values={[
        { label: 'get_secret', value: 'get_secret' },
        { label: 'get_secrets', value: 'get_secrets' }
    ]}
>
<TabItem value="get_secret">

Retrieves the information for a specific secret by passing either the secret id or name in the URL.

```sql
SELECT
name,
created,
createdAt,
decryptable,
projectId,
teamId,
uid,
userId,
value
FROM vercel.secrets.secrets
WHERE idOrName = '{{ idOrName }}' -- required
AND teamId = '{{ teamId }}' -- required
AND decrypt = '{{ decrypt }}'
;
```
</TabItem>
<TabItem value="get_secrets">

Retrieves the active Vercel secrets for the authenticated user or team. By default it returns 20 secrets. The rest can be retrieved using the pagination options. The body will contain an entry for each secret.

```sql
SELECT
name,
created,
createdAt,
decryptable,
projectId,
teamId,
uid,
userId,
value
FROM vercel.secrets.secrets
WHERE teamId = '{{ teamId }}' -- required
AND id = '{{ id }}'
AND projectId = '{{ projectId }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_secret"
    values={[
        { label: 'create_secret', value: 'create_secret' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_secret">

Allows to create a new secret.

```sql
INSERT INTO vercel.secrets.secrets (
data__name,
data__value,
data__decryptable,
data__projectId,
name,
teamId
)
SELECT 
'{{ name }}' /* required */,
'{{ value }}' /* required */,
{{ decryptable }},
'{{ projectId }}',
'{{ name }}',
'{{ teamId }}'
RETURNING
name,
created,
createdAt,
decryptable,
projectId,
teamId,
uid,
userId,
value
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: secrets
  props:
    - name: name
      value: string
      description: Required parameter for the secrets resource.
    - name: teamId
      value: string
      description: Required parameter for the secrets resource.
    - name: name
      value: string
      description: |
        The name of the secret (max 100 characters).
    - name: value
      value: string
      description: |
        The value of the new secret.
    - name: decryptable
      value: boolean
      description: |
        Whether the secret value can be decrypted after it has been created.
    - name: projectId
      value: string
      description: |
        Associate a secret to a project.
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_secret"
    values={[
        { label: 'delete_secret', value: 'delete_secret' }
    ]}
>
<TabItem value="delete_secret">

This deletes the user or team’s secret defined in the URL.

```sql
DELETE FROM vercel.secrets.secrets
WHERE idOrName = '{{ idOrName }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_get_secrets"
    values={[
        { label: '_get_secrets', value: '_get_secrets' },
        { label: 'rename_secret', value: 'rename_secret' }
    ]}
>
<TabItem value="_get_secrets">

Retrieves the active Vercel secrets for the authenticated user or team. By default it returns 20 secrets. The rest can be retrieved using the pagination options. The body will contain an entry for each secret.

```sql
EXEC vercel.secrets.secrets._get_secrets 
@teamId='{{ teamId }}' --required, 
@id='{{ id }}', 
@projectId='{{ projectId }}'
;
```
</TabItem>
<TabItem value="rename_secret">

Enables to edit the name of a secret. The name has to be unique to the user or team’s secrets.

```sql
EXEC vercel.secrets.secrets.rename_secret 
@name='{{ name }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"name": "{{ name }}"
}'
;
```
</TabItem>
</Tabs>
