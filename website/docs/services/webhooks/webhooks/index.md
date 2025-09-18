--- 
title: webhooks
hide_title: false
hide_table_of_contents: false
keywords:
  - webhooks
  - webhooks
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

Creates, updates, deletes, gets or lists a <code>webhooks</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>webhooks</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.webhooks.webhooks" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_webhook"
    values={[
        { label: 'get_webhook', value: 'get_webhook' },
        { label: 'get_webhooks', value: 'get_webhooks' }
    ]}
>
<TabItem value="get_webhook">

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
    <td>The webhook id (example: account_hook_GflD6EYyo7F4ViYS)</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>A number containing the date when the webhook was created in in milliseconds</td>
</tr>
<tr>
    <td><CopyableCode code="events" /></td>
    <td><code>array</code></td>
    <td>The webhooks events (example: deployment.created)</td>
</tr>
<tr>
    <td><CopyableCode code="ownerId" /></td>
    <td><code>string</code></td>
    <td>The unique ID of the team the webhook belongs to (example: ZspSRT4ljIEEmMHgoDwKWDei)</td>
</tr>
<tr>
    <td><CopyableCode code="projectIds" /></td>
    <td><code>array</code></td>
    <td>The ID of the projects the webhook is associated with</td>
</tr>
<tr>
    <td><CopyableCode code="updatedAt" /></td>
    <td><code>number</code></td>
    <td>A number containing the date when the webhook was updated in in milliseconds</td>
</tr>
<tr>
    <td><CopyableCode code="url" /></td>
    <td><code>string</code></td>
    <td>A string with the URL of the webhook (example: https://my-webhook.com)</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="get_webhooks">

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
    <td><a href="#get_webhook"><CopyableCode code="get_webhook" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Get a webhook</td>
</tr>
<tr>
    <td><a href="#get_webhooks"><CopyableCode code="get_webhooks" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-projectId"><code>projectId</code></a></td>
    <td>Get a list of webhooks</td>
</tr>
<tr>
    <td><a href="#create_webhook"><CopyableCode code="create_webhook" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__url"><code>data__url</code></a>, <a href="#parameter-data__events"><code>data__events</code></a></td>
    <td></td>
    <td>Creates a webhook</td>
</tr>
<tr>
    <td><a href="#delete_webhook"><CopyableCode code="delete_webhook" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Deletes a webhook</td>
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
    <td></td>
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
    defaultValue="get_webhook"
    values={[
        { label: 'get_webhook', value: 'get_webhook' },
        { label: 'get_webhooks', value: 'get_webhooks' }
    ]}
>
<TabItem value="get_webhook">

Get a webhook

```sql
SELECT
id,
createdAt,
events,
ownerId,
projectIds,
updatedAt,
url
FROM vercel.webhooks.webhooks
WHERE id = '{{ id }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
<TabItem value="get_webhooks">

Get a list of webhooks

```sql
SELECT
*
FROM vercel.webhooks.webhooks
WHERE teamId = '{{ teamId }}' -- required
AND projectId = '{{ projectId }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_webhook"
    values={[
        { label: 'create_webhook', value: 'create_webhook' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_webhook">

Creates a webhook

```sql
INSERT INTO vercel.webhooks.webhooks (
data__url,
data__events,
data__projectIds,
teamId
)
SELECT 
'{{ url }}' /* required */,
'{{ events }}' /* required */,
'{{ projectIds }}',
'{{ teamId }}'
RETURNING
id,
createdAt,
events,
ownerId,
projectIds,
secret,
updatedAt,
url
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: webhooks
  props:
    - name: teamId
      value: string
      description: Required parameter for the webhooks resource.
    - name: url
      value: string
    - name: events
      value: array
    - name: projectIds
      value: array
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_webhook"
    values={[
        { label: 'delete_webhook', value: 'delete_webhook' }
    ]}
>
<TabItem value="delete_webhook">

Deletes a webhook

```sql
DELETE FROM vercel.webhooks.webhooks
WHERE id = '{{ id }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>
