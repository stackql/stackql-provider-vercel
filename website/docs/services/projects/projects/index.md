--- 
title: projects
hide_title: false
hide_table_of_contents: false
keywords:
  - projects
  - projects
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

Creates, updates, deletes, gets or lists a <code>projects</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>projects</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="vercel.projects.projects" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_project"
    values={[
        { label: 'get_project', value: 'get_project' },
        { label: 'get_projects', value: 'get_projects' }
    ]}
>
<TabItem value="get_project">

The project information

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
    <td><CopyableCode code="accountId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="analytics" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="autoAssignCustomDomains" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="autoAssignCustomDomainsUpdatedBy" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="autoExposeSystemEnvs" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="buildCommand" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="commandForIgnoringBuildStep" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="connectBuildsEnabled" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="connectConfigurationId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="crons" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="customerSupportCodeVisibility" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="dataCache" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="devCommand" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="directoryListing" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="enablePreviewFeedback" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="env" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="framework" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="gitComments" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="gitForkProtection" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="gitLFS" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="hasActiveBranches" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="hasFloatingAliases" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="installCommand" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="lastAliasRequest" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="lastRollbackTarget" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="latestDeployments" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="link" /></td>
    <td><code></code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="live" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="nodeVersion" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="outputDirectory" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="passwordProtection" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="paused" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="permissions" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="productionDeploymentsFastLane" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="protectionBypass" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="publicSource" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="rootDirectory" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="serverlessFunctionRegion" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="skipGitConnectDuringLink" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="sourceFilesOutsideRootDirectory" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="ssoProtection" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="targets" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="transferCompletedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="transferStartedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="transferToAccountId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="transferredFromAccountId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="trustedIps" /></td>
    <td><code></code></td>
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
<TabItem value="get_projects">

The paginated list of projects

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
    <td><CopyableCode code="accountId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="analytics" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="autoAssignCustomDomains" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="autoAssignCustomDomainsUpdatedBy" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="autoExposeSystemEnvs" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="buildCommand" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="commandForIgnoringBuildStep" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="connectBuildsEnabled" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="connectConfigurationId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="crons" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="customerSupportCodeVisibility" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="dataCache" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="devCommand" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="directoryListing" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="enablePreviewFeedback" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="env" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="framework" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="gitComments" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="gitForkProtection" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="gitLFS" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="hasActiveBranches" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="hasFloatingAliases" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="installCommand" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="lastAliasRequest" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="lastRollbackTarget" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="latestDeployments" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="link" /></td>
    <td><code></code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="live" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="nodeVersion" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="outputDirectory" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="passwordProtection" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="paused" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="permissions" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="productionDeploymentsFastLane" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="protectionBypass" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="publicSource" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="rootDirectory" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="serverlessFunctionRegion" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="skipGitConnectDuringLink" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="sourceFilesOutsideRootDirectory" /></td>
    <td><code>boolean</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="ssoProtection" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="targets" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="transferCompletedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="transferStartedAt" /></td>
    <td><code>number</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="transferToAccountId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="transferredFromAccountId" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="trustedIps" /></td>
    <td><code></code></td>
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
    <td><a href="#get_project"><CopyableCode code="get_project" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Get the information for a specific project by passing either the project `id` or `name` in the URL.</td>
</tr>
<tr>
    <td><a href="#get_projects"><CopyableCode code="get_projects" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-from"><code>from</code></a>, <a href="#parameter-gitForkProtection"><code>gitForkProtection</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-search"><code>search</code></a>, <a href="#parameter-repo"><code>repo</code></a>, <a href="#parameter-repoId"><code>repoId</code></a>, <a href="#parameter-repoUrl"><code>repoUrl</code></a>, <a href="#parameter-excludeRepos"><code>excludeRepos</code></a>, <a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-edgeConfigTokenId"><code>edgeConfigTokenId</code></a></td>
    <td>Allows to retrieve the list of projects of the authenticated user or team. The list will be paginated and the provided query parameters allow filtering the returned projects.</td>
</tr>
<tr>
    <td><a href="#create_project"><CopyableCode code="create_project" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a>, <a href="#parameter-data__name"><code>data__name</code></a></td>
    <td></td>
    <td>Allows to create a new project with the provided configuration. It only requires the project `name` but more configuration can be provided to override the defaults.</td>
</tr>
<tr>
    <td><a href="#delete_project"><CopyableCode code="delete_project" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Delete a specific project by passing either the project `id` or `name` in the URL.</td>
</tr>
<tr>
    <td><a href="#update_project_data_cache"><CopyableCode code="update_project_data_cache" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-projectId"><code>projectId</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Update the data cache feature on a project.</td>
</tr>
<tr>
    <td><a href="#_get_projects"><CopyableCode code="_get_projects" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-teamId"><code>teamId</code></a></td>
    <td><a href="#parameter-from"><code>from</code></a>, <a href="#parameter-gitForkProtection"><code>gitForkProtection</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-search"><code>search</code></a>, <a href="#parameter-repo"><code>repo</code></a>, <a href="#parameter-repoId"><code>repoId</code></a>, <a href="#parameter-repoUrl"><code>repoUrl</code></a>, <a href="#parameter-excludeRepos"><code>excludeRepos</code></a>, <a href="#parameter-edgeConfigId"><code>edgeConfigId</code></a>, <a href="#parameter-edgeConfigTokenId"><code>edgeConfigTokenId</code></a></td>
    <td>Allows to retrieve the list of projects of the authenticated user or team. The list will be paginated and the provided query parameters allow filtering the returned projects.</td>
</tr>
<tr>
    <td><a href="#update_project"><CopyableCode code="update_project" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-idOrName"><code>idOrName</code></a>, <a href="#parameter-teamId"><code>teamId</code></a></td>
    <td></td>
    <td>Update the fields of a project using either its `name` or `id`.</td>
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
<tr id="parameter-idOrName">
    <td><CopyableCode code="idOrName" /></td>
    <td><code>string</code></td>
    <td>The unique project identifier or the project name</td>
</tr>
<tr id="parameter-projectId">
    <td><CopyableCode code="projectId" /></td>
    <td><code>string</code></td>
    <td>The unique project identifier</td>
</tr>
<tr id="parameter-teamId">
    <td><CopyableCode code="teamId" /></td>
    <td><code>string</code></td>
    <td>The Team identifier or slug to perform the request on behalf of.</td>
</tr>
<tr id="parameter-edgeConfigId">
    <td><CopyableCode code="edgeConfigId" /></td>
    <td><code>string</code></td>
    <td>Filter results by connected Edge Config ID</td>
</tr>
<tr id="parameter-edgeConfigTokenId">
    <td><CopyableCode code="edgeConfigTokenId" /></td>
    <td><code>string</code></td>
    <td>Filter results by connected Edge Config Token ID</td>
</tr>
<tr id="parameter-excludeRepos">
    <td><CopyableCode code="excludeRepos" /></td>
    <td><code>string</code></td>
    <td>Filter results by excluding those projects that belong to a repo</td>
</tr>
<tr id="parameter-from">
    <td><CopyableCode code="from" /></td>
    <td><code>string</code></td>
    <td>Query only projects updated after the given timestamp</td>
</tr>
<tr id="parameter-gitForkProtection">
    <td><CopyableCode code="gitForkProtection" /></td>
    <td><code>string</code></td>
    <td>Specifies whether PRs from Git forks should require a team member's authorization before it can be deployed</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>string</code></td>
    <td>Limit the number of projects returned</td>
</tr>
<tr id="parameter-repo">
    <td><CopyableCode code="repo" /></td>
    <td><code>string</code></td>
    <td>Filter results by repo. Also used for project count</td>
</tr>
<tr id="parameter-repoId">
    <td><CopyableCode code="repoId" /></td>
    <td><code>string</code></td>
    <td>Filter results by Repository ID.</td>
</tr>
<tr id="parameter-repoUrl">
    <td><CopyableCode code="repoUrl" /></td>
    <td><code>string</code></td>
    <td>Filter results by Repository URL.</td>
</tr>
<tr id="parameter-search">
    <td><CopyableCode code="search" /></td>
    <td><code>string</code></td>
    <td>Search projects by the name field</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_project"
    values={[
        { label: 'get_project', value: 'get_project' },
        { label: 'get_projects', value: 'get_projects' }
    ]}
>
<TabItem value="get_project">

Get the information for a specific project by passing either the project `id` or `name` in the URL.

```sql
SELECT
id,
name,
accountId,
analytics,
autoAssignCustomDomains,
autoAssignCustomDomainsUpdatedBy,
autoExposeSystemEnvs,
buildCommand,
commandForIgnoringBuildStep,
connectBuildsEnabled,
connectConfigurationId,
createdAt,
crons,
customerSupportCodeVisibility,
dataCache,
devCommand,
directoryListing,
enablePreviewFeedback,
env,
framework,
gitComments,
gitForkProtection,
gitLFS,
hasActiveBranches,
hasFloatingAliases,
installCommand,
lastAliasRequest,
lastRollbackTarget,
latestDeployments,
link,
live,
nodeVersion,
outputDirectory,
passwordProtection,
paused,
permissions,
productionDeploymentsFastLane,
protectionBypass,
publicSource,
rootDirectory,
serverlessFunctionRegion,
skipGitConnectDuringLink,
sourceFilesOutsideRootDirectory,
ssoProtection,
targets,
transferCompletedAt,
transferStartedAt,
transferToAccountId,
transferredFromAccountId,
trustedIps,
updatedAt
FROM vercel.projects.projects
WHERE idOrName = '{{ idOrName }}' -- required
AND teamId = '{{ teamId }}' -- required
;
```
</TabItem>
<TabItem value="get_projects">

Allows to retrieve the list of projects of the authenticated user or team. The list will be paginated and the provided query parameters allow filtering the returned projects.

```sql
SELECT
id,
name,
accountId,
analytics,
autoAssignCustomDomains,
autoAssignCustomDomainsUpdatedBy,
autoExposeSystemEnvs,
buildCommand,
commandForIgnoringBuildStep,
connectBuildsEnabled,
connectConfigurationId,
createdAt,
crons,
customerSupportCodeVisibility,
dataCache,
devCommand,
directoryListing,
enablePreviewFeedback,
env,
framework,
gitComments,
gitForkProtection,
gitLFS,
hasActiveBranches,
hasFloatingAliases,
installCommand,
lastAliasRequest,
lastRollbackTarget,
latestDeployments,
link,
live,
nodeVersion,
outputDirectory,
passwordProtection,
paused,
permissions,
productionDeploymentsFastLane,
protectionBypass,
publicSource,
rootDirectory,
serverlessFunctionRegion,
skipGitConnectDuringLink,
sourceFilesOutsideRootDirectory,
ssoProtection,
targets,
transferCompletedAt,
transferStartedAt,
transferToAccountId,
transferredFromAccountId,
trustedIps,
updatedAt
FROM vercel.projects.projects
WHERE teamId = '{{ teamId }}' -- required
AND from = '{{ from }}'
AND gitForkProtection = '{{ gitForkProtection }}'
AND limit = '{{ limit }}'
AND search = '{{ search }}'
AND repo = '{{ repo }}'
AND repoId = '{{ repoId }}'
AND repoUrl = '{{ repoUrl }}'
AND excludeRepos = '{{ excludeRepos }}'
AND edgeConfigId = '{{ edgeConfigId }}'
AND edgeConfigTokenId = '{{ edgeConfigTokenId }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_project"
    values={[
        { label: 'create_project', value: 'create_project' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_project">

Allows to create a new project with the provided configuration. It only requires the project `name` but more configuration can be provided to override the defaults.

```sql
INSERT INTO vercel.projects.projects (
data__buildCommand,
data__commandForIgnoringBuildStep,
data__devCommand,
data__environmentVariables,
data__framework,
data__gitRepository,
data__installCommand,
data__name,
data__skipGitConnectDuringLink,
data__outputDirectory,
data__publicSource,
data__rootDirectory,
data__serverlessFunctionRegion,
teamId
)
SELECT 
'{{ buildCommand }}',
'{{ commandForIgnoringBuildStep }}',
'{{ devCommand }}',
'{{ environmentVariables }}',
'{{ framework }}',
'{{ gitRepository }}',
'{{ installCommand }}',
'{{ name }}' /* required */,
{{ skipGitConnectDuringLink }},
'{{ outputDirectory }}',
{{ publicSource }},
'{{ rootDirectory }}',
'{{ serverlessFunctionRegion }}',
'{{ teamId }}'
RETURNING
id,
name,
accountId,
analytics,
autoAssignCustomDomains,
autoAssignCustomDomainsUpdatedBy,
autoExposeSystemEnvs,
buildCommand,
commandForIgnoringBuildStep,
connectBuildsEnabled,
connectConfigurationId,
createdAt,
crons,
customerSupportCodeVisibility,
dataCache,
devCommand,
directoryListing,
enablePreviewFeedback,
env,
framework,
gitComments,
gitForkProtection,
gitLFS,
hasActiveBranches,
hasFloatingAliases,
installCommand,
lastAliasRequest,
lastRollbackTarget,
latestDeployments,
link,
live,
nodeVersion,
outputDirectory,
passwordProtection,
paused,
permissions,
productionDeploymentsFastLane,
protectionBypass,
publicSource,
rootDirectory,
serverlessFunctionRegion,
skipGitConnectDuringLink,
sourceFilesOutsideRootDirectory,
ssoProtection,
targets,
transferCompletedAt,
transferStartedAt,
transferToAccountId,
transferredFromAccountId,
trustedIps,
updatedAt
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: projects
  props:
    - name: teamId
      value: string
      description: Required parameter for the projects resource.
    - name: buildCommand
      value: string
      description: |
        The build command for this project. When `null` is used this value will be automatically detected
    - name: commandForIgnoringBuildStep
      value: string
    - name: devCommand
      value: string
      description: |
        The dev command for this project. When `null` is used this value will be automatically detected
    - name: environmentVariables
      value: array
      description: |
        Collection of ENV Variables the Project will use
    - name: framework
      value: string
      description: |
        The framework that is being used for this project. When `null` is used no framework is selected
      valid_values: ['', 'blitzjs', 'nextjs', 'gatsby', 'remix', 'astro', 'hexo', 'eleventy', 'docusaurus-2', 'docusaurus', 'preact', 'solidstart', 'dojo', 'ember', 'vue', 'scully', 'ionic-angular', 'angular', 'polymer', 'svelte', 'sveltekit', 'sveltekit-1', 'ionic-react', 'create-react-app', 'gridsome', 'umijs', 'sapper', 'saber', 'stencil', 'nuxtjs', 'redwoodjs', 'hugo', 'jekyll', 'brunch', 'middleman', 'zola', 'hydrogen', 'vite', 'vitepress', 'vuepress', 'parcel', 'sanity', 'storybook']
    - name: gitRepository
      value: object
      description: |
        The Git Repository that will be connected to the project. When this is defined, any pushes to the specified connected Git Repository will be automatically deployed
    - name: installCommand
      value: string
      description: |
        The install command for this project. When `null` is used this value will be automatically detected
    - name: name
      value: string
      description: |
        The desired name for the project
    - name: skipGitConnectDuringLink
      value: boolean
      description: |
        Opts-out of the message prompting a CLI user to connect a Git repository in `vercel link`.
    - name: outputDirectory
      value: string
      description: |
        The output directory of the project. When `null` is used this value will be automatically detected
    - name: publicSource
      value: boolean
      description: |
        Specifies whether the source code and logs of the deployments for this project should be public or not
    - name: rootDirectory
      value: string
      description: |
        The name of a directory or relative path to the source code of your project. When `null` is used it will default to the project root
    - name: serverlessFunctionRegion
      value: string
      description: |
        The region to deploy Serverless Functions in this project
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="delete_project"
    values={[
        { label: 'delete_project', value: 'delete_project' }
    ]}
>
<TabItem value="delete_project">

Delete a specific project by passing either the project `id` or `name` in the URL.

```sql
DELETE FROM vercel.projects.projects
WHERE idOrName = '{{ idOrName }}' --required
AND teamId = '{{ teamId }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="update_project_data_cache"
    values={[
        { label: 'update_project_data_cache', value: 'update_project_data_cache' },
        { label: '_get_projects', value: '_get_projects' },
        { label: 'update_project', value: 'update_project' }
    ]}
>
<TabItem value="update_project_data_cache">

Update the data cache feature on a project.

```sql
EXEC vercel.projects.projects.update_project_data_cache 
@projectId='{{ projectId }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"disabled": {{ disabled }}
}'
;
```
</TabItem>
<TabItem value="_get_projects">

Allows to retrieve the list of projects of the authenticated user or team. The list will be paginated and the provided query parameters allow filtering the returned projects.

```sql
EXEC vercel.projects.projects._get_projects 
@teamId='{{ teamId }}' --required, 
@from='{{ from }}', 
@gitForkProtection='{{ gitForkProtection }}', 
@limit='{{ limit }}', 
@search='{{ search }}', 
@repo='{{ repo }}', 
@repoId='{{ repoId }}', 
@repoUrl='{{ repoUrl }}', 
@excludeRepos='{{ excludeRepos }}', 
@edgeConfigId='{{ edgeConfigId }}', 
@edgeConfigTokenId='{{ edgeConfigTokenId }}'
;
```
</TabItem>
<TabItem value="update_project">

Update the fields of a project using either its `name` or `id`.

```sql
EXEC vercel.projects.projects.update_project 
@idOrName='{{ idOrName }}' --required, 
@teamId='{{ teamId }}' --required 
@@json=
'{
"autoExposeSystemEnvs": {{ autoExposeSystemEnvs }}, 
"autoAssignCustomDomains": {{ autoAssignCustomDomains }}, 
"autoAssignCustomDomainsUpdatedBy": "{{ autoAssignCustomDomainsUpdatedBy }}", 
"buildCommand": "{{ buildCommand }}", 
"commandForIgnoringBuildStep": "{{ commandForIgnoringBuildStep }}", 
"customerSupportCodeVisibility": {{ customerSupportCodeVisibility }}, 
"devCommand": "{{ devCommand }}", 
"directoryListing": {{ directoryListing }}, 
"framework": "{{ framework }}", 
"gitForkProtection": {{ gitForkProtection }}, 
"gitLFS": {{ gitLFS }}, 
"installCommand": "{{ installCommand }}", 
"name": "{{ name }}", 
"nodeVersion": "{{ nodeVersion }}", 
"outputDirectory": "{{ outputDirectory }}", 
"passwordProtection": "{{ passwordProtection }}", 
"publicSource": {{ publicSource }}, 
"rootDirectory": "{{ rootDirectory }}", 
"serverlessFunctionRegion": "{{ serverlessFunctionRegion }}", 
"skipGitConnectDuringLink": {{ skipGitConnectDuringLink }}, 
"sourceFilesOutsideRootDirectory": {{ sourceFilesOutsideRootDirectory }}, 
"ssoProtection": "{{ ssoProtection }}", 
"trustedIps": "{{ trustedIps }}", 
"enablePreviewFeedback": {{ enablePreviewFeedback }}
}'
;
```
</TabItem>
</Tabs>
