--- 
title: deployments
hide_title: false
hide_table_of_contents: false
keywords:
  - deployments
  - checks
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

Creates, updates, deletes, gets or lists a <code>deployments</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>deployments</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.checks.deployments" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_check"
    values={[
        { label: 'get_check', value: 'get_check' },
        { label: 'get_all_checks', value: 'get_all_checks' }
    ]}
>
<TabItem value="get_check">

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
    <td><CopyableCode code="blocking" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="completedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="conclusion" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="deploymentId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="detailsUrl" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="externalId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="integrationId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="output" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="path" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="rerequestable" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="startedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="updatedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="get_all_checks">

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
    <td><CopyableCode code="completedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="conclusion" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="detailsUrl" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="integrationId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="output" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="path" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="rerequestable" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="startedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="updatedAt" /></td>
    <td><code>number</code></td>
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
    <td><a href="#get_check"><CopyableCode code="get_check" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-deploymentId"><code>deploymentId</code></a>, <a href="#parameter-checkId"><code>checkId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Return a detailed response for a single check.</td>
</tr>
<tr>
    <td><a href="#get_all_checks"><CopyableCode code="get_all_checks" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-deploymentId"><code>deploymentId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>List all of the checks created for a deployment.</td>
</tr>
<tr>
    <td><a href="#create_check"><CopyableCode code="create_check" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-deploymentId"><code>deploymentId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__name"><code>data__name</code></a>, <a href="#parameter-data__blocking"><code>data__blocking</code></a></td>
    <td></td>
    <td>Creates a new check. This endpoint must be called with an OAuth2 or it will produce a 400 error.</td>
</tr>
<tr>
    <td><a href="#_get_all_checks"><CopyableCode code="_get_all_checks" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-deploymentId"><code>deploymentId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>List all of the checks created for a deployment.</td>
</tr>
<tr>
    <td><a href="#update_check"><CopyableCode code="update_check" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-deploymentId"><code>deploymentId</code></a>, <a href="#parameter-checkId"><code>checkId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Update an existing check. This endpoint must be called with an OAuth2 or it will produce a 400 error.</td>
</tr>
<tr>
    <td><a href="#rerequest_check"><CopyableCode code="rerequest_check" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-deploymentId"><code>deploymentId</code></a>, <a href="#parameter-checkId"><code>checkId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Rerequest a selected check that has failed.</td>
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
<tr id="parameter-checkId">
    <td><CopyableCode code="checkId" /></td>
    <td><code>string</code></td>
    <td>The check to rerun</td>
</tr>
<tr id="parameter-deploymentId">
    <td><CopyableCode code="deploymentId" /></td>
    <td><code>string</code></td>
    <td>The deployment to rerun the check for.</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_check"
    values={[
        { label: 'get_check', value: 'get_check' },
        { label: 'get_all_checks', value: 'get_all_checks' }
    ]}
>
<TabItem value="get_check">

Return a detailed response for a single check.

```sql
SELECT
id,
name,
blocking,
completedAt,
conclusion,
createdAt,
deploymentId,
detailsUrl,
externalId,
integrationId,
output,
path,
rerequestable,
startedAt,
status,
updatedAt
FROM vercel.checks.deployments
WHERE deploymentId = '{{ deploymentId }}' -- required
AND checkId = '{{ checkId }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
<TabItem value="get_all_checks">

List all of the checks created for a deployment.

```sql
SELECT
id,
name,
completedAt,
conclusion,
createdAt,
detailsUrl,
integrationId,
output,
path,
rerequestable,
startedAt,
status,
updatedAt
FROM vercel.checks.deployments
WHERE deploymentId = '{{ deploymentId }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_check"
    values={[
        { label: 'create_check', value: 'create_check' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_check">

Creates a new check. This endpoint must be called with an OAuth2 or it will produce a 400 error.

```sql
INSERT INTO vercel.checks.deployments (
data__name,
data__path,
data__blocking,
data__detailsUrl,
data__externalId,
data__rerequestable,
deploymentId,
teamId
)
SELECT 
'{{ name }}' /* required */,
'{{ path }}',
{{ blocking }} /* required */,
'{{ detailsUrl }}',
'{{ externalId }}',
{{ rerequestable }},
'{{ deploymentId }}',
'{{ teamId }}'
RETURNING
id,
name,
blocking,
completedAt,
conclusion,
createdAt,
deploymentId,
detailsUrl,
externalId,
integrationId,
output,
path,
rerequestable,
startedAt,
status,
updatedAt
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: deployments
  props:
    - name: deploymentId
      value: string
      description: Required parameter for the deployments resource.
    - name: teamId
      value: string
      description: Required parameter for the deployments resource.
    - name: name
      value: string
      description: |
        The name of the check being created
    - name: path
      value: string
      description: |
        Path of the page that is being checked
    - name: blocking
      value: boolean
      description: |
        Whether the check should block a deployment from succeeding
    - name: detailsUrl
      value: string
      description: |
        URL to display for further details
    - name: externalId
      value: string
      description: |
        An identifier that can be used as an external reference
    - name: rerequestable
      value: boolean
      description: |
        Whether a user should be able to request for the check to be rerun if it fails
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_get_all_checks"
    values={[
        { label: '_get_all_checks', value: '_get_all_checks' },
        { label: 'update_check', value: 'update_check' },
        { label: 'rerequest_check', value: 'rerequest_check' }
    ]}
>
<TabItem value="_get_all_checks">

List all of the checks created for a deployment.

```sql
EXEC vercel.checks.deployments._get_all_checks 
@deploymentId='{{ deploymentId }}' --required, 
@teamId='{{ teamId }}' --required
;
```
</TabItem>
<TabItem value="update_check">

Update an existing check. This endpoint must be called with an OAuth2 or it will produce a 400 error.

```sql
EXEC vercel.checks.deployments.update_check 
@deploymentId='{{ deploymentId }}' --required, 
@checkId='{{ checkId }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"name": "{{ name }}", 
"path": "{{ path }}", 
"status": "{{ status }}", 
"conclusion": "{{ conclusion }}", 
"detailsUrl": "{{ detailsUrl }}", 
"output": "{{ output }}", 
"externalId": "{{ externalId }}"
}'
;
```
</TabItem>
<TabItem value="rerequest_check">

Rerequest a selected check that has failed.

```sql
EXEC vercel.checks.deployments.rerequest_check 
@deploymentId='{{ deploymentId }}' --required, 
@checkId='{{ checkId }}' --required, 
@teamId='{{ teamId }}' --required
;
```
</TabItem>
</Tabs>
