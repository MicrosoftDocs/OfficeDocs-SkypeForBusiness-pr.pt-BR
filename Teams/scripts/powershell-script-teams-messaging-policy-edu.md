---
title: Exemplo de script do PowerShell - Criar & atribuir política de mensagens
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Use este script do PowerShell para criar uma política de mensagens no Teams e atribuí-la aos usuários em sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d1fa3ebe45785c088852c518ac5490263fa6aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804651"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="5ce81-103">Exemplo de script do PowerShell, criar e atribuir uma política de mensagens</span><span class="sxs-lookup"><span data-stu-id="5ce81-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="5ce81-104">Use este script do PowerShell para criar uma política de mensagens no Microsoft Teams e atribuí-la aos usuários.</span><span class="sxs-lookup"><span data-stu-id="5ce81-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="5ce81-105">Para obter mais informações sobre como usar este script do PowerShell, consulte [Início rápido – Teams for Education.](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)</span><span class="sxs-lookup"><span data-stu-id="5ce81-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="5ce81-106">Este script usa o cmdlet [Grant-CsTeamsMessagingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) que está no módulo PowerShell do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="5ce81-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="5ce81-107">Confira [a visão geral do Teams PowerShell](../teams-powershell-overview.md) para saber mais sobre como gerenciar o Teams usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ce81-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="5ce81-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5ce81-108">Before you start</span></span>

<span data-ttu-id="5ce81-109">Baixe e instale o módulo [do PowerShell](https://www.microsoft.com/download/details.aspx?id=39366)do Skype for Business Online e reinicie o computador, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="5ce81-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="5ce81-110">Para se inclinar mais, [consulte Gerenciar o Skype for Business Online com o PowerShell do Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="5ce81-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="5ce81-111">Script de exemplo</span><span class="sxs-lookup"><span data-stu-id="5ce81-111">Sample script</span></span>

```powershell
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
```

> [!NOTE]
> <span data-ttu-id="5ce81-112">Você também pode atribuir uma política de mensagens diretamente aos usuários em escala por meio de uma atribuição de política em lote ou a um grupo do que os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="5ce81-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="5ce81-113">Para saber mais, [confira Atribuir políticas a grandes conjuntos](../batch-group-policy-assignment-edu.md) de usuários em sua escola e Atribuir políticas aos usuários no [Teams.](../assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5ce81-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
