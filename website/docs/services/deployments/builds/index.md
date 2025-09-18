--- 
title: builds
hide_title: false
hide_table_of_contents: false
keywords:
  - builds
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

Creates, updates, deletes, gets or lists a <code>builds</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>builds</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.deployments.builds" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_builds_for_deployment"
    values={[
        { label: 'get_builds_for_deployment', value: 'get_builds_for_deployment' }
    ]}
>
<TabItem value="get_builds_for_deployment">

An object representing a Build on Vercel

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
    <td>The unique identifier of the Build</td>
</tr>
<tr>
    <td><CopyableCode code="config" /></td>
    <td><code>object</code></td>
    <td>An object that contains the Build's configuration</td>
</tr>
<tr>
    <td><CopyableCode code="copiedFrom" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td>The time at which the Build was created</td>
</tr>
<tr>
    <td><CopyableCode code="createdIn" /></td>
    <td><code>string</code></td>
    <td>The region where the Build was first created</td>
</tr>
<tr>
    <td><CopyableCode code="deployedAt" /></td>
    <td><code>number</code></td>
    <td>The time at which the Build was deployed</td>
</tr>
<tr>
    <td><CopyableCode code="deploymentId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the deployment</td>
</tr>
<tr>
    <td><CopyableCode code="entrypoint" /></td>
    <td><code>string</code></td>
    <td>The entrypoint of the deployment</td>
</tr>
<tr>
    <td><CopyableCode code="fingerprint" /></td>
    <td><code>string</code></td>
    <td>If the Build uses the `@vercel/static` Runtime, it contains a hashed string of all outputs</td>
</tr>
<tr>
    <td><CopyableCode code="output" /></td>
    <td><code>array</code></td>
    <td>A list of outputs for the Build that can be either Serverless Functions or static files</td>
</tr>
<tr>
    <td><CopyableCode code="readyState" /></td>
    <td><code>string</code></td>
    <td>The state of the deployment depending on the process of deploying, or if it is ready or in an error state</td>
</tr>
<tr>
    <td><CopyableCode code="readyStateAt" /></td>
    <td><code>number</code></td>
    <td>The time at which the Build state was last modified</td>
</tr>
<tr>
    <td><CopyableCode code="scheduledAt" /></td>
    <td><code>number</code></td>
    <td>The time at which the Build was scheduled to be built</td>
</tr>
<tr>
    <td><CopyableCode code="use" /></td>
    <td><code>string</code></td>
    <td>The Runtime the Build used to generate the output</td>
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
    <td><a href="#get_builds_for_deployment"><CopyableCode code="get_builds_for_deployment" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-deploymentId"><code>deploymentId</code></a></td>
    <td></td>
    <td>Retrieves the list of builds given their deployment's unique identifier. No longer listed as public API as of May 2023.</td>
</tr>
<tr>
    <td><a href="#_get_builds_for_deployment"><CopyableCode code="_get_builds_for_deployment" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-deploymentId"><code>deploymentId</code></a></td>
    <td></td>
    <td>Retrieves the list of builds given their deployment's unique identifier. No longer listed as public API as of May 2023.</td>
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
<tr id="parameter-deploymentId">
    <td><CopyableCode code="deploymentId" /></td>
    <td><code>string</code></td>
    <td>The deployment unique identifier</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_builds_for_deployment"
    values={[
        { label: 'get_builds_for_deployment', value: 'get_builds_for_deployment' }
    ]}
>
<TabItem value="get_builds_for_deployment">

Retrieves the list of builds given their deployment's unique identifier. No longer listed as public API as of May 2023.

```sql
SELECT
id,
config,
copiedFrom,
createdAt,
createdIn,
deployedAt,
deploymentId,
entrypoint,
fingerprint,
output,
readyState,
readyStateAt,
scheduledAt,
use
FROM vercel.deployments.builds
WHERE deploymentId = '{{ deploymentId }}' -- required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_get_builds_for_deployment"
    values={[
        { label: '_get_builds_for_deployment', value: '_get_builds_for_deployment' }
    ]}
>
<TabItem value="_get_builds_for_deployment">

Retrieves the list of builds given their deployment's unique identifier. No longer listed as public API as of May 2023.

```sql
EXEC vercel.deployments.builds._get_builds_for_deployment 
@deploymentId='{{ deploymentId }}' --required
;
```
</TabItem>
</Tabs>
