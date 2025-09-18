--- 
title: files
hide_title: false
hide_table_of_contents: false
keywords:
  - files
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

Creates, updates, deletes, gets or lists a <code>files</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>files</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.deployments.files" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="list_deployment_files"
    values={[
        { label: 'list_deployment_files', value: 'list_deployment_files' }
    ]}
>
<TabItem value="list_deployment_files">

Retrieved the file tree successfully

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
    <td>The name of the file tree entry (example: my-file.json)</td>
</tr>
<tr>
    <td><CopyableCode code="children" /></td>
    <td><code>array</code></td>
    <td>The list of children files of the directory (only valid for the `directory` type)</td>
</tr>
<tr>
    <td><CopyableCode code="contentType" /></td>
    <td><code>string</code></td>
    <td>The content-type of the file (only valid for the `file` type) (example: application/json)</td>
</tr>
<tr>
    <td><CopyableCode code="mode" /></td>
    <td><code>number</code></td>
    <td>The file "mode" indicating file type and permissions.</td>
</tr>
<tr>
    <td><CopyableCode code="symlink" /></td>
    <td><code>string</code></td>
    <td>Not currently used. See `file-list-to-tree.ts`.</td>
</tr>
<tr>
    <td><CopyableCode code="type" /></td>
    <td><code>string</code></td>
    <td>String indicating the type of file tree entry. (example: file)</td>
</tr>
<tr>
    <td><CopyableCode code="uid" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the file (only valid for the `file` type) (example: 2d4aad419917f15b1146e9e03ddc9bb31747e4d0)</td>
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
    <td><a href="#list_deployment_files"><CopyableCode code="list_deployment_files" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Allows to retrieve the file structure of a deployment by supplying the deployment unique identifier.</td>
</tr>
<tr>
    <td><a href="#upload_file"><CopyableCode code="upload_file" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-Content-Length"><code>Content-Length</code></a>, <a href="#parameter-x-vercel-digest"><code>x-vercel-digest</code></a>, <a href="#parameter-x-now-digest"><code>x-now-digest</code></a>, <a href="#parameter-x-now-size"><code>x-now-size</code></a></td>
    <td>Before you create a deployment you need to upload the required files for that deployment. To do it, you need to first upload each file to this endpoint. Once that's completed, you can create a new deployment with the uploaded files. The file content must be placed inside the body of the request. In the case of a successful response you'll receive a status code 200 with an empty body.</td>
</tr>
<tr>
    <td><a href="#get_deployment_file_contents"><CopyableCode code="get_deployment_file_contents" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-id"><code>id</code></a>, <a href="#parameter-fileId"><code>fileId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-path"><code>path</code></a></td>
    <td>Allows to retrieve the content of a file by supplying the file identifier and the deployment unique identifier. The response body will contain the raw content of the file.</td>
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
<tr id="parameter-fileId">
    <td><CopyableCode code="fileId" /></td>
    <td><code>string</code></td>
    <td>The unique file identifier</td>
</tr>
<tr id="parameter-id">
    <td><CopyableCode code="id" /></td>
    <td><code>string</code></td>
    <td>The unique deployment identifier</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-Content-Length">
    <td><CopyableCode code="Content-Length" /></td>
    <td><code>number</code></td>
    <td>The file size in bytes</td>
</tr>
<tr id="parameter-path">
    <td><CopyableCode code="path" /></td>
    <td><code>string</code></td>
    <td>Path to the file to fetch (only for Git deployments)</td>
</tr>
<tr id="parameter-x-now-digest">
    <td><CopyableCode code="x-now-digest" /></td>
    <td><code>string</code></td>
    <td>The file SHA1 used to check the integrity</td>
</tr>
<tr id="parameter-x-now-size">
    <td><CopyableCode code="x-now-size" /></td>
    <td><code>number</code></td>
    <td>The file size as an alternative to `Content-Length`</td>
</tr>
<tr id="parameter-x-vercel-digest">
    <td><CopyableCode code="x-vercel-digest" /></td>
    <td><code>string</code></td>
    <td>The file SHA1 used to check the integrity</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="list_deployment_files"
    values={[
        { label: 'list_deployment_files', value: 'list_deployment_files' }
    ]}
>
<TabItem value="list_deployment_files">

Allows to retrieve the file structure of a deployment by supplying the deployment unique identifier.

```sql
SELECT
name,
children,
contentType,
mode,
symlink,
type,
uid
FROM vercel.deployments.files
WHERE id = '{{ id }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="upload_file"
    values={[
        { label: 'upload_file', value: 'upload_file' },
        { label: 'get_deployment_file_contents', value: 'get_deployment_file_contents' }
    ]}
>
<TabItem value="upload_file">

Before you create a deployment you need to upload the required files for that deployment. To do it, you need to first upload each file to this endpoint. Once that's completed, you can create a new deployment with the uploaded files. The file content must be placed inside the body of the request. In the case of a successful response you'll receive a status code 200 with an empty body.

```sql
EXEC vercel.deployments.files.upload_file 
@teamId='{{ teamId }}' --required, 
@Content-Length='{{ Content-Length }}', 
@x-vercel-digest='{{ x-vercel-digest }}', 
@x-now-digest='{{ x-now-digest }}', 
@x-now-size='{{ x-now-size }}'
;
```
</TabItem>
<TabItem value="get_deployment_file_contents">

Allows to retrieve the content of a file by supplying the file identifier and the deployment unique identifier. The response body will contain the raw content of the file.

```sql
EXEC vercel.deployments.files.get_deployment_file_contents 
@id='{{ id }}' --required, 
@fileId='{{ fileId }}' --required, 
@teamId='{{ teamId }}' --required, 
@path='{{ path }}'
;
```
</TabItem>
</Tabs>
