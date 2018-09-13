---
title: Exemplo de script do PowerShell - criar e atribuir uma política de mensagens
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
description: Use esse script do PowerShell para criar uma política de mensagens em equipes e atribuí-lo aos usuários em sua organização.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 399cc6cf20554cd8ab23e6d75b66b2d6251e46de
ms.sourcegitcommit: 31918f51e8220950af6437a16d8beeb637fba2b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2018
ms.locfileid: "23961888"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Exemplo de script do PowerShell - criar e atribuir uma política de mensagens
-------------------------------------------------------------------------

Use esse script do PowerShell para criar uma política de mensagens no Microsoft Teams e atribuí-lo aos usuários. 

Para obter mais informações sobre como usar esse script do PowerShell, consulte [Quick start - Teams educacional](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

Se você é novato no PowerShell e precisa de ajuda para começar, consulte [Visão geral do Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="sample-script"></a>Script de exemplo

````powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId
   
 }

````


