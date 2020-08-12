---
title: Remover a política de reunião do RestrictedAnonymousAccess Teams dos usuários
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Saiba como remover a política de reunião do teams RestrictedAnonymousAccess dos usuários em sua organização.
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640967"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="9e759-103">Remover a política de reunião do RestrictedAnonymousAccess Teams dos usuários</span><span class="sxs-lookup"><span data-stu-id="9e759-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="9e759-104">[As políticas de reunião](meeting-policies-in-teams.md) no Microsoft Teams são usadas para controlar os recursos que estão disponíveis para os participantes da reunião em reuniões agendadas pelos usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9e759-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="9e759-105">O Teams inclui uma política interna chamada RestrictedAnonymousAccess, que contém configurações predefinidas que incluem a restrição de usuários anônimos de iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="9e759-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="9e759-106">(Usuários anônimos são usuários que não foram autenticados.) As configurações predefinidas na política da reunião não podem ser editadas nem alteradas por administradores.</span><span class="sxs-lookup"><span data-stu-id="9e759-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="9e759-107">Este artigo mostra como usar o PowerShell para remover a política de reunião do RestrictedAnonymousAccess dos usuários atribuídos a essa política.</span><span class="sxs-lookup"><span data-stu-id="9e759-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="9e759-108">Para saber mais sobre como gerenciar o Microsoft Teams usando o PowerShell, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9e759-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="9e759-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9e759-109">Before you start</span></span>

<span data-ttu-id="9e759-110">Instale e conecte-se ao [módulo do PowerShell do Skype for Business](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="9e759-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="9e759-111">Para obter orientação passo a passo, confira [instalar o Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="9e759-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="9e759-112">Obter as atribuições de política de reunião do teams para sua organização</span><span class="sxs-lookup"><span data-stu-id="9e759-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="9e759-113">Execute o seguinte para obter as atribuições de política de reunião do teams para sua organização.</span><span class="sxs-lookup"><span data-stu-id="9e759-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="9e759-114">Neste exemplo, a saída a seguir é retornada, o que mostra que dois usuários recebem a política de reunião do RestrictedAnonymousAccess.</span><span class="sxs-lookup"><span data-stu-id="9e759-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="9e759-115">Cancelar a atribuição da política de reunião do RestrictedAnonymous de usuários</span><span class="sxs-lookup"><span data-stu-id="9e759-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="9e759-116">Para remover a política de reunião do RestrictedAnonymous dos usuários, você pode usar o cmdlet [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) se tiver um pequeno número de usuários (por exemplo, menos de 100 usuários).</span><span class="sxs-lookup"><span data-stu-id="9e759-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="9e759-117">Se você tiver um grande número de usuários (por exemplo, mais de 100 usuários), é mais eficiente usar o cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) para enviar uma operação em lotes.</span><span class="sxs-lookup"><span data-stu-id="9e759-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="9e759-118">Usar o cmdlet da política Grant-CsTeamsMeeting</span><span class="sxs-lookup"><span data-stu-id="9e759-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="9e759-119">Execute o seguinte para remover a política de reunião do RestrictedAnonymous dos usuários.</span><span class="sxs-lookup"><span data-stu-id="9e759-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="9e759-120">Usar o cmdlet New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="9e759-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="9e759-121">Com a [atribuição de política em lotes](assign-policies.md#assign-a-policy-to-a-batch-of-users), o número máximo de usuários para os quais você pode remover ou atualizar políticas é de 5.000 de cada vez.</span><span class="sxs-lookup"><span data-stu-id="9e759-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="9e759-122">Por exemplo, se você tiver mais de 5.000 usuários, será necessário enviar vários lotes.</span><span class="sxs-lookup"><span data-stu-id="9e759-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="9e759-123">Para obter melhores resultados, não envie vários lotes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="9e759-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="9e759-124">Permitir que os lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="9e759-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="9e759-125">O cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) está no módulo do PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="9e759-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="9e759-126">Antes de seguir estas etapas, instale e conecte-se ao [módulo do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="9e759-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="9e759-127">Para obter orientação passo a passo, confira [instalar o Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="9e759-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="9e759-128">Execute os comandos a seguir para remover a política de reunião do RestrictedAnonymousAccess de um lote de usuários.</span><span class="sxs-lookup"><span data-stu-id="9e759-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="9e759-129">Obter o status da atribuição em lotes</span><span class="sxs-lookup"><span data-stu-id="9e759-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="9e759-130">Cada atribuição de lote retorna uma ID de operação, que você pode usar para acompanhar o andamento e o status das tarefas e identificar quaisquer falhas que possam ocorrer.</span><span class="sxs-lookup"><span data-stu-id="9e759-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="9e759-131">Por exemplo, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9e759-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="9e759-132">Verifique se o **ErrorCount** é **0** (zero) e se **OverallStatus** está **concluído**.</span><span class="sxs-lookup"><span data-stu-id="9e759-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9e759-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9e759-133">Related topics</span></span>

- [<span data-ttu-id="9e759-134">Gerenciar políticas de reunião no Teams</span><span class="sxs-lookup"><span data-stu-id="9e759-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="9e759-135">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="9e759-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="9e759-136">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="9e759-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
