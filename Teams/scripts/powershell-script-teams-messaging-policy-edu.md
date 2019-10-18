---
title: Exemplo de script do PowerShell, criar e atribuir uma política de mensagens
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Use este script do PowerShell para criar uma política de mensagens no Teams e atribuí-la a usuários em sua organização.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c8f58e4fbfa7629f9e5c59c41e0100263c29d4e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573443"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="b9f54-103">Exemplo de script do PowerShell, criar e atribuir uma política de mensagens</span><span class="sxs-lookup"><span data-stu-id="b9f54-103">PowerShell script sample - Create and assign a messaging policy</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="b9f54-104">Use este script do PowerShell para criar uma política de mensagens no Microsoft Teams e atribuí-la a usuários.</span><span class="sxs-lookup"><span data-stu-id="b9f54-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="b9f54-105">Para obter mais informações sobre como usar esse script do PowerShell, consulte [início rápido-equipes de educação](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="b9f54-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="b9f54-106">Se você é novato no PowerShell e precisa de ajuda para começar, consulte [Visão geral do Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span><span class="sxs-lookup"><span data-stu-id="b9f54-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="b9f54-107">Script de exemplo</span><span class="sxs-lookup"><span data-stu-id="b9f54-107">Sample script</span></span>

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


