---
title: Exemplo de script do PowerShell – criar & atribuir política de mensagens
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Use este script do PowerShell para criar uma política de mensagens no Teams e atribuí-la a usuários em sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 318a430f6f59cbb28ffeda4336c36ae07533615b
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533736"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="43181-103">Exemplo de script do PowerShell, criar e atribuir uma política de mensagens</span><span class="sxs-lookup"><span data-stu-id="43181-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="43181-104">Use este script do PowerShell para criar uma política de mensagens no Microsoft Teams e atribuí-la a usuários.</span><span class="sxs-lookup"><span data-stu-id="43181-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="43181-105">Para obter mais informações sobre como usar esse script do PowerShell, consulte [início rápido-equipes de educação](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="43181-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="43181-106">Esse script usa o cmdlet [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) que está no módulo do PowerShell do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="43181-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="43181-107">Consulte [visão geral do teams PowerShell](../teams-powershell-overview.md) para saber mais sobre como gerenciar o Microsoft Teams usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43181-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="43181-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="43181-108">Before you start</span></span>

<span data-ttu-id="43181-109">Baixe e instale o [módulo do PowerShell do Skype for Business online](https://www.microsoft.com/download/details.aspx?id=39366)e, em seguida, reinicie o computador, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="43181-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="43181-110">Para obter mais informações, consulte [gerenciar o Skype for Business online com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="43181-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="43181-111">Script de exemplo</span><span class="sxs-lookup"><span data-stu-id="43181-111">Sample script</span></span>

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
> <span data-ttu-id="43181-112">Você também pode atribuir uma política de mensagens diretamente aos usuários em escala por meio de uma atribuição de política em lotes ou a um grupo do qual os usuários são membros.</span><span class="sxs-lookup"><span data-stu-id="43181-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="43181-113">Para obter mais informações, consulte [atribuir políticas a grandes conjuntos de usuários na sua escola](../batch-group-policy-assignment-edu.md) e [atribuir políticas a seus usuários no Microsoft Teams](../assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="43181-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
