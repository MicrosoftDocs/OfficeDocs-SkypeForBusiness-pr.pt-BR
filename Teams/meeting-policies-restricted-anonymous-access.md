---
title: Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários
author: cichur
ms.author: v-cichur
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
description: Saiba como remover a política de reunião RestrictedAnonymousAccess Teams dos usuários em sua organização.
ms.openlocfilehash: 55385cdd47f6b6c9882f8d4e8dcadc848f13755d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806251"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="4804f-103">Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários</span><span class="sxs-lookup"><span data-stu-id="4804f-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="4804f-104">[As políticas de](meeting-policies-in-teams.md) reunião no Microsoft Teams são usadas para controlar os recursos que estão disponíveis para os participantes da reunião para reuniões agendadas pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4804f-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="4804f-105">O Teams inclui uma política interna chamada RestrictedAnonymousAccess, que contém configurações pré-definidas que incluem a restrição de usuários anônimos de iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="4804f-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="4804f-106">(Usuários anônimos são usuários que não foram autenticados.) As configurações predefinidos na política de reunião não podem ser editadas ou alteradas pelos administradores.</span><span class="sxs-lookup"><span data-stu-id="4804f-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="4804f-107">Este artigo mostra como usar o PowerShell para remover a política de reunião RestrictedAnonymousAccess de usuários que estão atribuídos a essa política.</span><span class="sxs-lookup"><span data-stu-id="4804f-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="4804f-108">Para saber mais sobre como gerenciar o Teams usando o PowerShell, confira a visão geral do [PowerShell do Teams.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4804f-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="4804f-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4804f-109">Before you start</span></span>

<span data-ttu-id="4804f-110">Instale e conecte-se ao [módulo do PowerShell do Skype for Business.](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="4804f-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="4804f-111">Para obter orientações passo a passo, consulte [Instalar o Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="4804f-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="4804f-112">Obter as atribuições de política de reunião do Teams para sua organização</span><span class="sxs-lookup"><span data-stu-id="4804f-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="4804f-113">Execute o seguinte para obter as atribuições de política de reunião do Teams para sua organização.</span><span class="sxs-lookup"><span data-stu-id="4804f-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="4804f-114">Neste exemplo, a saída a seguir é retornada, o que mostra que dois usuários são atribuídos à política de reunião RestrictedAnonymousAccess.</span><span class="sxs-lookup"><span data-stu-id="4804f-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="4804f-115">Desa designe a política de reunião RestrictedAnonymous dos usuários</span><span class="sxs-lookup"><span data-stu-id="4804f-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="4804f-116">Para remover a política de reunião RestrictedAnonymous dos usuários, você pode usar o cmdlet [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) se tiver um pequeno número de usuários (por exemplo, menos de 100 usuários).</span><span class="sxs-lookup"><span data-stu-id="4804f-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="4804f-117">Se você tiver um grande número de usuários (por exemplo, mais de 100 usuários), será mais eficiente usar o cmdlet  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) para enviar uma operação em lotes.</span><span class="sxs-lookup"><span data-stu-id="4804f-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="4804f-118">Usar o cmdlet Grant-CsTeamsMeeting Política de Grant-CsTeamsMeeting</span><span class="sxs-lookup"><span data-stu-id="4804f-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="4804f-119">Execute o seguinte para remover a política de reunião RestrictedAnonymous dos usuários.</span><span class="sxs-lookup"><span data-stu-id="4804f-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="4804f-120">Usar o New-CsBatchPolicyAssignmentOperation cmdlet</span><span class="sxs-lookup"><span data-stu-id="4804f-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="4804f-121">Com [a atribuição de política](assign-policies.md#assign-a-policy-to-a-batch-of-users)em lote, o número máximo de usuários para os quais você pode remover ou atualizar políticas é 5.000 por vez.</span><span class="sxs-lookup"><span data-stu-id="4804f-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="4804f-122">Por exemplo, se você tiver mais de 5.000 usuários, precisará enviar vários lotes.</span><span class="sxs-lookup"><span data-stu-id="4804f-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="4804f-123">Para melhores resultados, não envie vários lotes por vez.</span><span class="sxs-lookup"><span data-stu-id="4804f-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="4804f-124">Permitir que lotes concluam o processamento antes de enviar mais lotes.</span><span class="sxs-lookup"><span data-stu-id="4804f-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="4804f-125">O cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) está no módulo PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="4804f-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="4804f-126">Antes de seguir essas etapas, instale e conecte-se ao módulo [powerShell do Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="4804f-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="4804f-127">Para obter orientações passo a passo, consulte [Instalar o Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="4804f-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="4804f-128">Execute os seguintes comandos para remover a política de reunião RestrictedAnonymousAccess de um lote de usuários.</span><span class="sxs-lookup"><span data-stu-id="4804f-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="4804f-129">Obter o status da atribuição de lote</span><span class="sxs-lookup"><span data-stu-id="4804f-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="4804f-130">Cada atribuição em lote retorna uma ID de operação, que você pode usar para controlar o progresso e o status das atribuições e identificar quaisquer falhas que possam ocorrer.</span><span class="sxs-lookup"><span data-stu-id="4804f-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="4804f-131">Por exemplo, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4804f-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="4804f-132">Certifique-se **de que ErrorCount** seja **0** (zero) e **OverallStatus** seja **Concluído.**</span><span class="sxs-lookup"><span data-stu-id="4804f-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4804f-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4804f-133">Related topics</span></span>

- [<span data-ttu-id="4804f-134">Gerenciar políticas de reunião no Teams</span><span class="sxs-lookup"><span data-stu-id="4804f-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="4804f-135">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="4804f-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="4804f-136">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4804f-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
