--- 
title: artifacts
hide_title: false
hide_table_of_contents: false
keywords:
  - artifacts
  - artifacts
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

Creates, updates, deletes, gets or lists an <code>artifacts</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>artifacts</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.artifacts.artifacts" /></td></tr>
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
    <td><a href="#record_events"><CopyableCode code="record_events" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-x-artifact-client-ci"><code>x-artifact-client-ci</code></a>, <a href="#parameter-x-artifact-client-interactive"><code>x-artifact-client-interactive</code></a></td>
    <td>Records an artifacts cache usage event. The body of this request is an array of cache usage events. The supported event types are `HIT` and `MISS`. The source is either `LOCAL` the cache event was on the users filesystem cache or `REMOTE` if the cache event is for a remote cache. When the event is a `HIT` the request also accepts a number `duration` which is the time taken to generate the artifact in the cache.</td>
</tr>
<tr>
    <td><a href="#status"><CopyableCode code="status" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Check the status of Remote Caching for this principal. Returns a JSON-encoded status indicating if Remote Caching is enabled, disabled, or disabled due to usage limits.</td>
</tr>
<tr>
    <td><a href="#upload_artifact"><CopyableCode code="upload_artifact" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-Content-Length"><code>Content-Length</code></a>, <a href="#parameter-hash"><code>hash</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-x-artifact-duration"><code>x-artifact-duration</code></a>, <a href="#parameter-x-artifact-client-ci"><code>x-artifact-client-ci</code></a>, <a href="#parameter-x-artifact-client-interactive"><code>x-artifact-client-interactive</code></a>, <a href="#parameter-x-artifact-tag"><code>x-artifact-tag</code></a></td>
    <td>Uploads a cache artifact identified by the `hash` specified on the path. The cache artifact can then be downloaded with the provided `hash`.</td>
</tr>
<tr>
    <td><a href="#download_artifact"><CopyableCode code="download_artifact" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-hash"><code>hash</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-x-artifact-client-ci"><code>x-artifact-client-ci</code></a>, <a href="#parameter-x-artifact-client-interactive"><code>x-artifact-client-interactive</code></a></td>
    <td>Downloads a cache artifact indentified by its `hash` specified on the request path. The artifact is downloaded as an octet-stream. The client should verify the content-length header and response body.</td>
</tr>
<tr>
    <td><a href="#artifact_exists"><CopyableCode code="artifact_exists" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-hash"><code>hash</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Check that a cache artifact with the given `hash` exists. This request returns response headers only and is equivalent to a `GET` request to this endpoint where the response contains no body.</td>
</tr>
<tr>
    <td><a href="#artifact_query"><CopyableCode code="artifact_query" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-hashes"><code>hashes</code></a></td>
    <td></td>
    <td>Query information about an array of artifacts.</td>
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
<tr id="parameter-Content-Length">
    <td><CopyableCode code="Content-Length" /></td>
    <td><code>number</code></td>
    <td>The artifact size in bytes</td>
</tr>
<tr id="parameter-hash">
    <td><CopyableCode code="hash" /></td>
    <td><code>string</code></td>
    <td>The artifact hash</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-x-artifact-client-ci">
    <td><CopyableCode code="x-artifact-client-ci" /></td>
    <td><code>string</code></td>
    <td>The continuous integration or delivery environment where this artifact is downloaded.</td>
</tr>
<tr id="parameter-x-artifact-client-interactive">
    <td><CopyableCode code="x-artifact-client-interactive" /></td>
    <td><code>integer</code></td>
    <td>1 if the client is an interactive shell. Otherwise 0</td>
</tr>
<tr id="parameter-x-artifact-duration">
    <td><CopyableCode code="x-artifact-duration" /></td>
    <td><code>number</code></td>
    <td>The time taken to generate the uploaded artifact in milliseconds.</td>
</tr>
<tr id="parameter-x-artifact-tag">
    <td><CopyableCode code="x-artifact-tag" /></td>
    <td><code>string</code></td>
    <td>The base64 encoded tag for this artifact. The value is sent back to clients when the artifact is downloaded as the header `x-artifact-tag`</td>
</tr>
</tbody>
</table>

## Lifecycle Methods

<Tabs
    defaultValue="record_events"
    values={[
        { label: 'record_events', value: 'record_events' },
        { label: 'status', value: 'status' },
        { label: 'upload_artifact', value: 'upload_artifact' },
        { label: 'download_artifact', value: 'download_artifact' },
        { label: 'artifact_exists', value: 'artifact_exists' },
        { label: 'artifact_query', value: 'artifact_query' }
    ]}
>
<TabItem value="record_events">

Records an artifacts cache usage event. The body of this request is an array of cache usage events. The supported event types are `HIT` and `MISS`. The source is either `LOCAL` the cache event was on the users filesystem cache or `REMOTE` if the cache event is for a remote cache. When the event is a `HIT` the request also accepts a number `duration` which is the time taken to generate the artifact in the cache.

```sql
EXEC vercel.artifacts.artifacts.record_events 
@teamId='{{ teamId }}' --required, 
@x-artifact-client-ci='{{ x-artifact-client-ci }}', 
@x-artifact-client-interactive='{{ x-artifact-client-interactive }}'
;
```
</TabItem>
<TabItem value="status">

Check the status of Remote Caching for this principal. Returns a JSON-encoded status indicating if Remote Caching is enabled, disabled, or disabled due to usage limits.

```sql
EXEC vercel.artifacts.artifacts.status 
@teamId='{{ teamId }}' --required
;
```
</TabItem>
<TabItem value="upload_artifact">

Uploads a cache artifact identified by the `hash` specified on the path. The cache artifact can then be downloaded with the provided `hash`.

```sql
EXEC vercel.artifacts.artifacts.upload_artifact 
@Content-Length='{{ Content-Length }}' --required, 
@hash='{{ hash }}' --required, 
@teamId='{{ teamId }}' --required, 
@x-artifact-duration='{{ x-artifact-duration }}', 
@x-artifact-client-ci='{{ x-artifact-client-ci }}', 
@x-artifact-client-interactive='{{ x-artifact-client-interactive }}', 
@x-artifact-tag='{{ x-artifact-tag }}'
;
```
</TabItem>
<TabItem value="download_artifact">

Downloads a cache artifact indentified by its `hash` specified on the request path. The artifact is downloaded as an octet-stream. The client should verify the content-length header and response body.

```sql
EXEC vercel.artifacts.artifacts.download_artifact 
@hash='{{ hash }}' --required, 
@teamId='{{ teamId }}' --required, 
@x-artifact-client-ci='{{ x-artifact-client-ci }}', 
@x-artifact-client-interactive='{{ x-artifact-client-interactive }}'
;
```
</TabItem>
<TabItem value="artifact_exists">

Check that a cache artifact with the given `hash` exists. This request returns response headers only and is equivalent to a `GET` request to this endpoint where the response contains no body.

```sql
EXEC vercel.artifacts.artifacts.artifact_exists 
@hash='{{ hash }}' --required, 
@teamId='{{ teamId }}' --required
;
```
</TabItem>
<TabItem value="artifact_query">

Query information about an array of artifacts.

```sql
EXEC vercel.artifacts.artifacts.artifact_query 
@teamId='{{ teamId }}' --required 
@@json=
'{
"hashes": "{{ hashes }}"
}'
;
```
</TabItem>
</Tabs>
