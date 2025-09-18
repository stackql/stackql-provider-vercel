--- 
title: config
hide_title: false
hide_table_of_contents: false
keywords:
  - config
  - domains
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

Creates, updates, deletes, gets or lists a <code>config</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>config</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.domains.config" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_domain_config"
    values={[
        { label: 'get_domain_config', value: 'get_domain_config' }
    ]}
>
<TabItem value="get_domain_config">

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
    <td><CopyableCode code="acceptedChallenges" /></td>
    <td><code>array</code></td>
    <td>Which challenge types the domain can use for issuing certs.</td>
</tr>
<tr>
    <td><CopyableCode code="configuredBy" /></td>
    <td><code>string</code></td>
    <td>How we see the domain's configuration. - `CNAME`: Domain has a CNAME pointing to Vercel. - `A`: Domain's A record is resolving to Vercel. - `http`: Domain is resolving to Vercel but may be behind a Proxy. - `null`: Domain is not resolving to Vercel.</td>
</tr>
<tr>
    <td><CopyableCode code="misconfigured" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is configured AND we can automatically generate a TLS certificate.</td>
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
    <td><a href="#get_domain_config"><CopyableCode code="get_domain_config" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Get a Domain's configuration.</td>
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
<tr id="parameter-domain">
    <td><CopyableCode code="domain" /></td>
    <td><code>string</code></td>
    <td>The name of the domain.</td>
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
    defaultValue="get_domain_config"
    values={[
        { label: 'get_domain_config', value: 'get_domain_config' }
    ]}
>
<TabItem value="get_domain_config">

Get a Domain's configuration.

```sql
SELECT
acceptedChallenges,
configuredBy,
misconfigured
FROM vercel.domains.config
WHERE domain = '{{ domain }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
</Tabs>
