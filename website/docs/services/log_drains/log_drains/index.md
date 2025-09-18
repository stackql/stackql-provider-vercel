--- 
title: log_drains
hide_title: false
hide_table_of_contents: false
keywords:
  - log_drains
  - log_drains
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

Creates, updates, deletes, gets or lists a <code>log_drains</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>log_drains</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.log_drains.log_drains" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_configurable_log_drain"
    values={[
        { label: 'get_configurable_log_drain', value: 'get_configurable_log_drain' },
        { label: 'get_configurable_log_drains', value: 'get_configurable_log_drains' }
    ]}
>
<TabItem value="get_configurable_log_drain">

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
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="branch" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="clientId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="configurationId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdFrom" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="deliveryFormat" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="disabledAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="disabledBy" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="disabledReason" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="environment" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="firstErrorTimestamp" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="headers" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="ownerId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="projectIds" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="secret" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="sources" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="url" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="get_configurable_log_drains">

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
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="branch" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="clientId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="configurationId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdFrom" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="deliveryFormat" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="disabledAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="disabledBy" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="disabledReason" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="environment" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="firstErrorTimestamp" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="headers" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="ownerId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="projectIds" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="secret" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="sources" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="url" /></td>
    <td><code>string</code></td>
    <td></td>
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
    <td><a href="#get_configurable_log_drain"><CopyableCode code="get_configurable_log_drain" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Retrieves a Configurable Log Drain. This endpoint must be called with a team AccessToken (integration OAuth2 clients are not allowed). Only log drains owned by the authenticated team can be accessed.</td>
</tr>
<tr>
    <td><a href="#get_configurable_log_drains"><CopyableCode code="get_configurable_log_drains" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-projectId"><code>projectId</code></a></td>
    <td>Retrieves a list of Configurable Log Drains. This endpoint must be called with a team AccessToken (integration OAuth2 clients are not allowed). Only log drains owned by the authenticated team can be accessed.</td>
</tr>
<tr>
    <td><a href="#create_configurable_log_drain"><CopyableCode code="create_configurable_log_drain" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__deliveryFormat"><code>data__deliveryFormat</code></a>, <a href="#parameter-data__url"><code>data__url</code></a>, <a href="#parameter-data__sources"><code>data__sources</code></a></td>
    <td></td>
    <td>Creates a configurable log drain. This endpoint must be called with a team AccessToken (integration OAuth2 clients are not allowed)</td>
</tr>
<tr>
    <td><a href="#delete_configurable_log_drain"><CopyableCode code="delete_configurable_log_drain" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Deletes a Configurable Log Drain. This endpoint must be called with a team AccessToken (integration OAuth2 clients are not allowed). Only log drains owned by the authenticated team can be deleted.</td>
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
<tr id="parameter-id">
    <td><CopyableCode code="id" /></td>
    <td><code>string</code></td>
    <td>ID of the log drain to be deleted.</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-projectId">
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_configurable_log_drain"
    values={[
        { label: 'get_configurable_log_drain', value: 'get_configurable_log_drain' },
        { label: 'get_configurable_log_drains', value: 'get_configurable_log_drains' }
    ]}
>
<TabItem value="get_configurable_log_drain">

Retrieves a Configurable Log Drain. This endpoint must be called with a team AccessToken (integration OAuth2 clients are not allowed). Only log drains owned by the authenticated team can be accessed.

```sql
SELECT
id,
name,
branch,
clientId,
configurationId,
createdAt,
createdFrom,
deliveryFormat,
disabledAt,
disabledBy,
disabledReason,
environment,
firstErrorTimestamp,
headers,
ownerId,
projectIds,
secret,
sources,
status,
teamId,
url
FROM vercel.log_drains.log_drains
WHERE id = '{{ id }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
<TabItem value="get_configurable_log_drains">

Retrieves a list of Configurable Log Drains. This endpoint must be called with a team AccessToken (integration OAuth2 clients are not allowed). Only log drains owned by the authenticated team can be accessed.

```sql
SELECT
id,
name,
branch,
clientId,
configurationId,
createdAt,
createdFrom,
deliveryFormat,
disabledAt,
disabledBy,
disabledReason,
environment,
firstErrorTimestamp,
headers,
ownerId,
projectIds,
secret,
sources,
status,
teamId,
url
FROM vercel.log_drains.log_drains
WHERE teamId = '{{ teamId }}' -- required
AND projectId = '{{ projectId }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_configurable_log_drain"
    values={[
        { label: 'create_configurable_log_drain', value: 'create_configurable_log_drain' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_configurable_log_drain">

Creates a configurable log drain. This endpoint must be called with a team AccessToken (integration OAuth2 clients are not allowed)

```sql
INSERT INTO vercel.log_drains.log_drains (
data__deliveryFormat,
data__url,
data__headers,
data__projectIds,
data__sources,
data__environment,
data__branch,
data__secret,
teamId
)
SELECT 
'{{ deliveryFormat }}' /* required */,
'{{ url }}' /* required */,
'{{ headers }}',
'{{ projectIds }}',
'{{ sources }}' /* required */,
'{{ environment }}',
'{{ branch }}',
'{{ secret }}',
'{{ teamId }}'
RETURNING
id,
name,
branch,
clientId,
configurationId,
createdAt,
createdFrom,
deliveryFormat,
disabledAt,
disabledBy,
disabledReason,
environment,
firstErrorTimestamp,
headers,
ownerId,
projectIds,
secret,
sources,
status,
teamId,
url
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: log_drains
  props:
    - name: teamId
      value: string
      description: Required parameter for the log_drains resource.
    - name: deliveryFormat
      value: string
      description: |
        The delivery log format
      valid_values: ['json', 'ndjson']
    - name: url
      value: string
      description: |
        The log drain url
    - name: headers
      value: object
      description: |
        Headers to be sent together with the request
    - name: projectIds
      value: array
    - name: sources
      value: array
    - name: environment
      value: string
      description: |
        The environment of log drain
      valid_values: ['preview', 'production']
    - name: branch
      value: string
      description: |
        The branch regexp of log drain
    - name: secret
      value: string
      description: |
        Custom secret of log drain
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_configurable_log_drain"
    values={[
        { label: 'delete_configurable_log_drain', value: 'delete_configurable_log_drain' }
    ]}
>
<TabItem value="delete_configurable_log_drain">

Deletes a Configurable Log Drain. This endpoint must be called with a team AccessToken (integration OAuth2 clients are not allowed). Only log drains owned by the authenticated team can be deleted.

```sql
DELETE FROM vercel.log_drains.log_drains
WHERE id = '{{ id }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>
