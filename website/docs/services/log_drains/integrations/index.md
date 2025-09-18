--- 
title: integrations
hide_title: false
hide_table_of_contents: false
keywords:
  - integrations
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

Creates, updates, deletes, gets or lists an <code>integrations</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>integrations</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.log_drains.integrations" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_integration_log_drains"
    values={[
        { label: 'get_integration_log_drains', value: 'get_integration_log_drains' }
    ]}
>
<TabItem value="get_integration_log_drains">

A list of log drains

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
    <td>The unique identifier of the log drain. Always prefixed with `ld_` (example: ld_nBuA7zCID8g4QZ8g)</td>
</tr>
<tr>
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td>The name of the log drain (example: My first log drain)</td>
</tr>
<tr>
    <td><CopyableCode code="branch" /></td>
    <td><code>string</code></td>
    <td>The branch regexp of log drain (example: feature/*)</td>
</tr>
<tr>
    <td><CopyableCode code="clientId" /></td>
    <td><code>string</code></td>
    <td>The oauth2 client application id that created this log drain (example: oac_xRhY4LAB7yLhUADD69EvV7ct)</td>
</tr>
<tr>
    <td><CopyableCode code="configurationId" /></td>
    <td><code>string</code></td>
    <td>The client configuration this log drain was created with (example: icfg_cuwj0AdCdH3BwWT4LPijCC7t)</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>A timestamp that tells you when the log drain was created</td>
</tr>
<tr>
    <td><CopyableCode code="createdFrom" /></td>
    <td><code>string</code></td>
    <td>Whether the log drain was created by an integration or by a user (example: integration)</td>
</tr>
<tr>
    <td><CopyableCode code="deliveryFormat" /></td>
    <td><code>string</code></td>
    <td>The delivery log format (example: json)</td>
</tr>
<tr>
    <td><CopyableCode code="environment" /></td>
    <td><code>string</code></td>
    <td>The environment of log drain (example: production)</td>
</tr>
<tr>
    <td><CopyableCode code="headers" /></td>
    <td><code>object</code></td>
    <td>The headers to send with the request (example: &#123;"Authorization": "Bearer 123"&#125;)</td>
</tr>
<tr>
    <td><CopyableCode code="ownerId" /></td>
    <td><code>string</code></td>
    <td>The identifier of the team or user whose events will trigger the log drain (example: kr1PsOIzqEL5Xg6M4VZcZosf)</td>
</tr>
<tr>
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td> (example: AbCgVkqoxXeXCDWehVir51LHGrrcWL4mkYm14W6UBPWQeb)</td>
</tr>
<tr>
    <td><CopyableCode code="projectIds" /></td>
    <td><code>array</code></td>
    <td>The identifier of the projects this log drain is associated with (example: AbCgVkqoxXeXCDWehVir51LHGrrcWL4mkYm14W6UBPWQeb)</td>
</tr>
<tr>
    <td><CopyableCode code="sources" /></td>
    <td><code>array</code></td>
    <td>The sources from which logs are currently being delivered to this log drain.</td>
</tr>
<tr>
    <td><CopyableCode code="url" /></td>
    <td><code>string</code></td>
    <td>The URL to call when logs are generated (example: https://example.com/log-drain)</td>
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
    <td><a href="#get_integration_log_drains"><CopyableCode code="get_integration_log_drains" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Retrieves a list of all Integration log drains that are defined for the authenticated user or team. When using an OAuth2 token, the list is limited to log drains created by the authenticated integration.</td>
</tr>
<tr>
    <td><a href="#create_log_drain"><CopyableCode code="create_log_drain" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__name"><code>data__name</code></a>, <a href="#parameter-data__url"><code>data__url</code></a></td>
    <td></td>
    <td>Creates an Integration log drain. This endpoint must be called with an OAuth2 client (integration), since log drains are tied to integrations. If it is called with a different token type it will produce a 400 error.</td>
</tr>
<tr>
    <td><a href="#delete_integration_log_drain"><CopyableCode code="delete_integration_log_drain" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-updateFlow"><code>updateFlow</code></a></td>
    <td>Deletes the Integration log drain with the provided `id`. When using an OAuth2 Token, the log drain can be deleted only if the integration owns it.</td>
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
    <td>ID of the log drain to be deleted</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-updateFlow">
    <td><CopyableCode code="updateFlow" /></td>
    <td><code>boolean</code></td>
    <td>If this API is being called as part of an update flow, this should be set to true</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_integration_log_drains"
    values={[
        { label: 'get_integration_log_drains', value: 'get_integration_log_drains' }
    ]}
>
<TabItem value="get_integration_log_drains">

Retrieves a list of all Integration log drains that are defined for the authenticated user or team. When using an OAuth2 token, the list is limited to log drains created by the authenticated integration.

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
environment,
headers,
ownerId,
projectId,
projectIds,
sources,
url
FROM vercel.log_drains.integrations
WHERE teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_log_drain"
    values={[
        { label: 'create_log_drain', value: 'create_log_drain' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_log_drain">

Creates an Integration log drain. This endpoint must be called with an OAuth2 client (integration), since log drains are tied to integrations. If it is called with a different token type it will produce a 400 error.

```sql
INSERT INTO vercel.log_drains.integrations (
data__name,
data__projectIds,
data__secret,
data__deliveryFormat,
data__url,
data__sources,
data__headers,
data__environment,
data__branch,
data__previousLogDrainId,
teamId
)
SELECT 
'{{ name }}' /* required */,
'{{ projectIds }}',
'{{ secret }}',
'{{ deliveryFormat }}',
'{{ url }}' /* required */,
'{{ sources }}',
'{{ headers }}',
'{{ environment }}',
'{{ branch }}',
'{{ previousLogDrainId }}',
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
environment,
headers,
ownerId,
projectId,
projectIds,
sources,
url
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: integrations
  props:
    - name: teamId
      value: string
      description: Required parameter for the integrations resource.
    - name: name
      value: string
      description: |
        The name of the log drain
    - name: projectIds
      value: array
    - name: secret
      value: string
      description: |
        A secret to sign log drain notification headers so a consumer can verify their authenticity
    - name: deliveryFormat
      value: string
      description: |
        The delivery log format
      valid_values: ['json', 'ndjson', 'syslog']
    - name: url
      value: string
      description: |
        The url where you will receive logs. The protocol must be `https://` or `http://` when type is `json` and `ndjson`, and `syslog+tls:` or `syslog:` when the type is `syslog`.
    - name: sources
      value: array
    - name: headers
      value: object
      description: |
        Headers to be sent together with the request
    - name: environment
      value: string
      description: |
        The environment of log drain
      valid_values: ['preview', 'production']
    - name: branch
      value: string
      description: |
        The branch regexp of log drain
    - name: previousLogDrainId
      value: string
      description: |
        The id of the log drain that was previously created and deleted
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_integration_log_drain"
    values={[
        { label: 'delete_integration_log_drain', value: 'delete_integration_log_drain' }
    ]}
>
<TabItem value="delete_integration_log_drain">

Deletes the Integration log drain with the provided `id`. When using an OAuth2 Token, the log drain can be deleted only if the integration owns it.

```sql
DELETE FROM vercel.log_drains.integrations
WHERE id = '{{ id }}' --required
AND teamId = '{{ teamId }}' --required
AND updateFlow = '{{ updateFlow }}'
;
```
</TabItem>
</Tabs>
