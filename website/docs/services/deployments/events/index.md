--- 
title: events
hide_title: false
hide_table_of_contents: false
keywords:
  - events
  - deployments
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

Creates, updates, deletes, gets or lists an <code>events</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>events</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.deployments.events" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_deployment_events"
    values={[
        { label: 'get_deployment_events', value: 'get_deployment_events' }
    ]}
>
<TabItem value="get_deployment_events">

A stream of jsonlines where each line is a deployment log item.<br />Array of deployment logs for the provided query.

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
    <td><a href="#get_deployment_events"><CopyableCode code="get_deployment_events" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-idOrUrl"><code>idOrUrl</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-direction"><code>direction</code></a>, <a href="#parameter-follow"><code>follow</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-name"><code>name</code></a>, <a href="#parameter-since"><code>since</code></a>, <a href="#parameter-until"><code>until</code></a>, <a href="#parameter-statusCode"><code>statusCode</code></a>, <a href="#parameter-delimiter"><code>delimiter</code></a>, <a href="#parameter-builds"><code>builds</code></a></td>
    <td>Get the build logs of a deployment by deployment ID and build ID. It can work as an infinite stream of logs or as a JSON endpoint depending on the input parameters.</td>
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
<tr id="parameter-idOrUrl">
    <td><CopyableCode code="idOrUrl" /></td>
    <td><code>string</code></td>
    <td>The unique identifier or hostname of the deployment.</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-builds">
    <td><CopyableCode code="builds" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr id="parameter-delimiter">
    <td><CopyableCode code="delimiter" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr id="parameter-direction">
    <td><CopyableCode code="direction" /></td>
    <td><code>string</code></td>
    <td>Order of the returned events based on the timestamp.</td>
</tr>
<tr id="parameter-follow">
    <td><CopyableCode code="follow" /></td>
    <td><code>number</code></td>
    <td>When enabled, this endpoint will return live events as they happen.</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>number</code></td>
    <td>Maximum number of events to return. Provide `-1` to return all available logs.</td>
</tr>
<tr id="parameter-name">
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td>Deployment build ID.</td>
</tr>
<tr id="parameter-since">
    <td><CopyableCode code="since" /></td>
    <td><code>number</code></td>
    <td>Timestamp for when build logs should be pulled from.</td>
</tr>
<tr id="parameter-statusCode">
    <td><CopyableCode code="statusCode" /></td>
    <td><code></code></td>
    <td>HTTP status code range to filter events by.</td>
</tr>
<tr id="parameter-until">
    <td><CopyableCode code="until" /></td>
    <td><code>number</code></td>
    <td>Timestamp for when the build logs should be pulled up until.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_deployment_events"
    values={[
        { label: 'get_deployment_events', value: 'get_deployment_events' }
    ]}
>
<TabItem value="get_deployment_events">

Get the build logs of a deployment by deployment ID and build ID. It can work as an infinite stream of logs or as a JSON endpoint depending on the input parameters.

```sql
SELECT
*
FROM vercel.deployments.events
WHERE idOrUrl = '{{ idOrUrl }}' -- required
AND teamId = '{{ teamId }}' -- required
AND direction = '{{ direction }}'
AND follow = '{{ follow }}'
AND limit = '{{ limit }}'
AND name = '{{ name }}'
AND since = '{{ since }}'
AND until = '{{ until }}'
AND statusCode = '{{ statusCode }}'
AND delimiter = '{{ delimiter }}'
AND builds = '{{ builds }}'
;
```
</TabItem>
</Tabs>
