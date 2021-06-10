---
title: Exemplo de script do PowerShell - Criar & de mensagens de atribuição
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
ms.openlocfilehash: c665b96c0c44c2ea763c343bb2857d4c2b9dbb26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117269"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="d6659-103">Exemplo de script do PowerShell, criar e atribuir uma política de mensagens</span><span class="sxs-lookup"><span data-stu-id="d6659-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="d6659-104">Use este script do PowerShell para criar uma política de mensagens no Microsoft Teams e atribuí-la aos usuários.</span><span class="sxs-lookup"><span data-stu-id="d6659-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="d6659-105">Para obter mais informações sobre como usar esse script do PowerShell, consulte [Início rápido - Teams para Educação](../teams-quick-start-edu.yml).</span><span class="sxs-lookup"><span data-stu-id="d6659-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](../teams-quick-start-edu.yml).</span></span>

<span data-ttu-id="d6659-106">Este script usa o cmdlet [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) que está no módulo Skype for Business PowerShell Online.</span><span class="sxs-lookup"><span data-stu-id="d6659-106">This script uses the [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="d6659-107">Consulte [Teams visão geral do PowerShell](../teams-powershell-overview.md) para saber mais sobre como gerenciar Teams usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6659-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="d6659-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d6659-108">Before you start</span></span>

<span data-ttu-id="d6659-109">Baixe e instale o [módulo Skype for Business PowerShell Online](https://www.microsoft.com/download/details.aspx?id=39366)e reinicie o computador, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="d6659-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="d6659-110">Para se inclinar mais, consulte [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="d6659-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="d6659-111">Script de exemplo</span><span class="sxs-lookup"><span data-stu-id="d6659-111">Sample script</span></span>

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
> <span data-ttu-id="d6659-112">Você também pode atribuir uma política de mensagens diretamente aos usuários em escala por meio de uma atribuição de política em lote ou a um grupo de que os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="d6659-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="d6659-113">Para obter mais informações, consulte Atribuir políticas a [grandes conjuntos](../batch-group-policy-assignment-edu.md) de usuários em sua escola e Atribuir políticas aos seus usuários em [Teams](../assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d6659-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>