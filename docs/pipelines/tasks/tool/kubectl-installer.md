---
title: Kubectl installer task
titleSuffix: Azure Pipelines & TFS
description: Install kubectl on an agent machine
ms.topic: reference
ms.assetid: 2773400c-3701-48b7-b56a-a5b612719687
ms.author: atulmal
author: azooinmyluggage
ms.date: 04/17/2019
monikerRange: 'azure-devops'
---

# Kubectl installer task

[!INCLUDE [version-eq-azure-devops](../../../includes/version-eq-azure-devops.md)]

This task can be used for installing a specific version of kubectl binary on agents.

::: moniker range="> tfs-2018"

## YAML snippet

[!INCLUDE [temp](../includes/yaml/KubectlInstallerV0.md)]

::: moniker-end

## Task inputs

<table>
  <thead>
    <tr>
      <th>Parameters</th>
      <th>Description</th>
    </tr>
  </thead>
  <tr>
    <td><code>kubectlVersion</code><br/>Kubectl version spec</td>
    <td>(Optional) The version of kubectl to be installed on the agent. Acceptable values are <code>latest</code> or any semantic version string like <code>1.15.0</code><br/>Default value: <code>latest</code></td>
  </tr>
</table>

The following YAML example showcases the installation of latest version of kubectl binary on the agent - 

```YAML
- task: KubectlInstaller@0
  displayName: Kubectl installer
  inputs: 
    kubectlVersion: latest
```

The following YAML example demonstrates the use of an explicit version string rather than installing the latest version available at the time of task execution - 

```YAML
- task: KubectlInstaller@0
  displayName: Kubectl installer
  inputs: 
    kubectlVersion: 1.15.0
```

## Open source

This task is open source [on GitHub](https://github.com/Microsoft/azure-pipelines-tasks/tree/master/Tasks/KubectlInstallerV0). Feedback and contributions are welcome.