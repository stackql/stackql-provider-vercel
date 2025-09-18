--- 
title: search_repo
hide_title: false
hide_table_of_contents: false
keywords:
  - search_repo
  - integrations
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

Creates, updates, deletes, gets or lists a <code>search_repo</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>search_repo</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.integrations.search_repo" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="git_namespaces"
    values={[
        { label: 'git_namespaces', value: 'git_namespaces' }
    ]}
>
<TabItem value="git_namespaces">

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
    <td><CopyableCode code="gitAccount" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="repos" /></td>
    <td><code>array</code></td>
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
    <td><a href="#git_namespaces"><CopyableCode code="git_namespaces" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-query"><code>query</code></a>, <a href="#parameter-namespaceId"><code>namespaceId</code></a>, <a href="#parameter-provider"><code>provider</code></a>, <a href="#parameter-installationId"><code>installationId</code></a>, <a href="#parameter-host"><code>host</code></a></td>
    <td>Lists git repositories linked to a namespace `id` for a supported provider. A specific namespace `id` can be obtained via the `git-namespaces`  endpoint. Supported providers are `github`, `gitlab` and `bitbucket`. If the provider or namespace is not provided, it will try to obtain it from the user that authenticated the request.</td>
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
<tr id="parameter-host">
    <td><CopyableCode code="host" /></td>
    <td><code>string</code></td>
    <td>The custom Git host if using a custom Git provider, like GitHub Enterprise Server</td>
</tr>
<tr id="parameter-installationId">
    <td><CopyableCode code="installationId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr id="parameter-namespaceId">
    <td><CopyableCode code="namespaceId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr id="parameter-provider">
    <td><CopyableCode code="provider" /></td>
    <td><code></code></td>
    <td></td>
</tr>
<tr id="parameter-query">
    <td><CopyableCode code="query" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="git_namespaces"
    values={[
        { label: 'git_namespaces', value: 'git_namespaces' }
    ]}
>
<TabItem value="git_namespaces">

Lists git repositories linked to a namespace `id` for a supported provider. A specific namespace `id` can be obtained via the `git-namespaces`  endpoint. Supported providers are `github`, `gitlab` and `bitbucket`. If the provider or namespace is not provided, it will try to obtain it from the user that authenticated the request.

```sql
SELECT
gitAccount,
repos
FROM vercel.integrations.search_repo
WHERE teamId = '{{ teamId }}' -- required
AND query = '{{ query }}'
AND namespaceId = '{{ namespaceId }}'
AND provider = '{{ provider }}'
AND installationId = '{{ installationId }}'
AND host = '{{ host }}'
;
```
</TabItem>
</Tabs>
