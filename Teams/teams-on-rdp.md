---
title: Usar o Teams com serviços de área de trabalho remota
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o Microsoft Teams com serviços de área de trabalho remota.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ac88778fca7034446d0ec42a0a4a65d7c76f979
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278879"
---
# <a name="teams-in-remote-desktop-services"></a><span data-ttu-id="b68d6-103">Teams nos Serviços de Área de Trabalho Remota</span><span class="sxs-lookup"><span data-stu-id="b68d6-103">Teams in Remote Desktop Services</span></span>

<span data-ttu-id="b68d6-104">Este artigo descreve os requisitos e limitações para usar o Microsoft Teams em um ambiente de serviços de área de trabalho remota (RDS).</span><span class="sxs-lookup"><span data-stu-id="b68d6-104">This article describes the requirements and limitations for using Microsoft Teams in a remote desktop services (RDS) environment.</span></span>

## <a name="what-is-rds"></a><span data-ttu-id="b68d6-105">O que é RDS?</span><span class="sxs-lookup"><span data-stu-id="b68d6-105">What is RDS?</span></span>

<span data-ttu-id="b68d6-106">O RDS (Remote Desktop Services) é a plataforma escolhida para criar soluções de virtualização para todas as necessidades do cliente final.</span><span class="sxs-lookup"><span data-stu-id="b68d6-106">Remote Desktop Services (RDS) is the platform of choice for building virtualization solutions for every end customer need.</span></span> <span data-ttu-id="b68d6-107">O RDS permite que você forneça aplicativos virtualizados individuais, forneça acesso seguro à área de trabalho móvel e remota e forneça aos usuários finais a capacidade de executar seus aplicativos e áreas de trabalho na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b68d6-107">RDS lets you deliver individual virtualized applications, provide secure mobile and remote desktop access, and provide end users the ability to run their applications and desktops from the cloud.</span></span>

<span data-ttu-id="b68d6-108">O RDS oferece flexibilidade de implantação, eficiência de custo e extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="b68d6-108">RDS offers deployment flexibility, cost efficiency, and extensibility.</span></span> <span data-ttu-id="b68d6-109">O RDS é entregue por meio de várias opções de implantação, incluindo o Windows Server 2016 para implantações locais, o Microsoft Azure para implantações na nuvem e uma ampla variedade de soluções de parceiros.</span><span class="sxs-lookup"><span data-stu-id="b68d6-109">RDS is delivered through a variety of deployment options, including Windows Server 2016 for on-premises deployments, Microsoft Azure for cloud deployments, and a robust array of partner solutions.</span></span>
<span data-ttu-id="b68d6-110">Dependendo do ambiente e das preferências, você pode configurar a solução de RDS para virtualização baseada em sessão, como uma infraestrutura de área de trabalho virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="b68d6-110">Depending on your environment and preferences, you can set up the RDS solution for session-based virtualization, as a virtual desktop infrastructure (VDI)</span></span>

<span data-ttu-id="b68d6-111">Atualmente, o Teams em um ambiente de serviços de área de trabalho remoto está disponível com suporte para a funcionalidade de colaboração e chat.</span><span class="sxs-lookup"><span data-stu-id="b68d6-111">Currently, Teams in a remote desktop services environment is available with support for collaboration and chat functionality.</span></span> <span data-ttu-id="b68d6-112">Para garantir uma experiência ideal para o usuário, siga as orientações neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b68d6-112">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="b68d6-113">Teams no VDI com chat e colaboração</span><span class="sxs-lookup"><span data-stu-id="b68d6-113">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="b68d6-114">Se sua organização quiser usar apenas recursos de chat e colaboração no Teams, você pode definir políticas no nível do usuário para desativar a funcionalidade de chamada e reunião no Teams.</span><span class="sxs-lookup"><span data-stu-id="b68d6-114">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="b68d6-115">Definir políticas para desativar a funcionalidade de chamada e reunião</span><span class="sxs-lookup"><span data-stu-id="b68d6-115">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="b68d6-116">Você pode definir políticas usando o Centro de administração do Microsoft Teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b68d6-116">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="b68d6-117">Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem.</span><span class="sxs-lookup"><span data-stu-id="b68d6-117">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="b68d6-118">Se você não vir as alterações de uma determinada conta imediatamente, tente novamente em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="b68d6-118">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="b68d6-119">[**Chamadas de políticas:**](teams-calling-policy.md)o Teams inclui a política interna de chamada Desallowing, na qual todos os recursos de chamada estão desligados.</span><span class="sxs-lookup"><span data-stu-id="b68d6-119">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="b68d6-120">Atribua a política DesallowCalling a todos os usuários em sua organização que usam o Teams em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="b68d6-120">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="b68d6-121">[**Políticas de**](meeting-policies-in-teams.md)reunião: o Teams inclui a política de reunião AllOff interna, na qual todos os recursos da reunião estão desligados.</span><span class="sxs-lookup"><span data-stu-id="b68d6-121">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="b68d6-122">Atribua a política AllOff a todos os usuários em sua organização que usam o Teams em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="b68d6-122">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b68d6-123">Atribuir políticas usando o Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b68d6-123">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b68d6-124">Para atribuir a política de chamada DesallowCalling e a política de reunião AllOff a um usuário:</span><span class="sxs-lookup"><span data-stu-id="b68d6-124">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="b68d6-125">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **Usuários.**</span><span class="sxs-lookup"><span data-stu-id="b68d6-125">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="b68d6-126">Selecione o usuário selecionando à esquerda do nome de usuário e, em seguida, selecione **Editar configurações.**</span><span class="sxs-lookup"><span data-stu-id="b68d6-126">Select the user by selecting to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="b68d6-127">Faça as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b68d6-127">Do the following steps:</span></span>

    <span data-ttu-id="b68d6-128">a.</span><span class="sxs-lookup"><span data-stu-id="b68d6-128">a.</span></span>  <span data-ttu-id="b68d6-129">Em **Política de Chamada,** selecione **DesallowCalling.**</span><span class="sxs-lookup"><span data-stu-id="b68d6-129">Under **Calling policy**, select **DisallowCalling**.</span></span>

    <span data-ttu-id="b68d6-130">b.</span><span class="sxs-lookup"><span data-stu-id="b68d6-130">b.</span></span>  <span data-ttu-id="b68d6-131">Em **Política de Reunião,** selecione **AllOff.**</span><span class="sxs-lookup"><span data-stu-id="b68d6-131">Under **Meeting policy**, select **AllOff**.</span></span>

4. <span data-ttu-id="b68d6-132">Selecione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="b68d6-132">Select **Apply**.</span></span>

<span data-ttu-id="b68d6-133">Para atribuir uma política a vários usuários por vez:</span><span class="sxs-lookup"><span data-stu-id="b68d6-133">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="b68d6-134">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.</span><span class="sxs-lookup"><span data-stu-id="b68d6-134">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="b68d6-135">Na coluna **&#x2713;** (marca de seleção), selecione os usuários.</span><span class="sxs-lookup"><span data-stu-id="b68d6-135">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b68d6-136">Para selecionar todos os usuários, selecione o &#x2713; (marca de seleção) na parte superior da tabela.</span><span class="sxs-lookup"><span data-stu-id="b68d6-136">To select all users, select the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="b68d6-137">Selecione **Editar configurações,** faça as alterações que você deseja e selecione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="b68d6-137">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="b68d6-138">Ou você também pode fazer as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b68d6-138">Or, you can also do the following steps:</span></span>

1. <span data-ttu-id="b68d6-139">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a política que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="b68d6-139">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="b68d6-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b68d6-140">For example:</span></span>

    - <span data-ttu-id="b68d6-141">Vá para **as políticas**  >  **de Chamada** de Voz e selecione **DesallowCalling.**</span><span class="sxs-lookup"><span data-stu-id="b68d6-141">Go to **Voice** > **Calling policies**, and then select **DisallowCalling**.</span></span>
    - <span data-ttu-id="b68d6-142">Vá para **as políticas de**  >  **Reunião** de Reuniões e selecione **AllOff.**</span><span class="sxs-lookup"><span data-stu-id="b68d6-142">Go to **Meetings** > **Meeting policies**, and then select **AllOff**.</span></span>

2. <span data-ttu-id="b68d6-143">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="b68d6-143">Select **Manage users**.</span></span>
3. <span data-ttu-id="b68d6-144">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b68d6-144">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b68d6-145">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="b68d6-145">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b68d6-146">Quando terminar de adicionar usuários, selecione **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="b68d6-146">When you're finished adding users, select **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="b68d6-147">Atribuir políticas usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b68d6-147">Assign policies using PowerShell</span></span>

<span data-ttu-id="b68d6-148">O exemplo a seguir mostra como usar [o Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada DesallowCalling a um usuário.</span><span class="sxs-lookup"><span data-stu-id="b68d6-148">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="b68d6-149">Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamadas, consulte [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="b68d6-149">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="b68d6-150">O exemplo a seguir mostra como usar [o Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião AllOff a um usuário.</span><span class="sxs-lookup"><span data-stu-id="b68d6-150">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="b68d6-151">Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="b68d6-151">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>
