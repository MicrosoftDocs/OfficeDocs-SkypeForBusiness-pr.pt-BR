---
title: Rótulos de sensibilidade do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como definir e usar rótulos de sensibilidade no Microsoft Teams.
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653557"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="21e0a-103">Rótulos de sensibilidade do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="21e0a-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="21e0a-104">Os [Rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permitem que os administradores de equipe regulam o acesso a conteúdo organizacional confidencial criado durante a colaboração dentro do teams.</span><span class="sxs-lookup"><span data-stu-id="21e0a-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="21e0a-105">Você pode definir rótulos de sensibilidade e suas políticas associadas no [centro de conformidade de & de segurança](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="21e0a-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="21e0a-106">Esses rótulos e políticas são automaticamente aplicados ao Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="21e0a-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="21e0a-107">Qual é a diferença entre rótulos de sensibilidade e rótulos de classificação de equipes?</span><span class="sxs-lookup"><span data-stu-id="21e0a-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="21e0a-108">Rótulos de sensibilidade são diferentes dos rótulos de classificação que exigem que você os crie usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21e0a-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="21e0a-109">Os rótulos de classificação são cadeias de caracteres de texto que podem ser associadas a um grupo, mas não têm políticas reais associadas a eles.</span><span class="sxs-lookup"><span data-stu-id="21e0a-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="21e0a-110">Você usa rótulos de classificação como metadados para impor políticas manualmente por meio de ferramentas e scripts internos.</span><span class="sxs-lookup"><span data-stu-id="21e0a-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="21e0a-111">Por outro lado, as etiquetas de sensibilidade e suas políticas são automaticamente impostas de ponta a ponta por meio de uma combinação da plataforma de grupos, do centro de conformidade & do centro de conformidade e dos serviços do teams.</span><span class="sxs-lookup"><span data-stu-id="21e0a-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="21e0a-112">Os rótulos de sensibilidade fornecem suporte avançado à infraestrutura para proteger os dados confidenciais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="21e0a-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="21e0a-113">Criar e publicar rótulos de sensibilidade para equipes</span><span class="sxs-lookup"><span data-stu-id="21e0a-113">Create and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="21e0a-114">Para saber como habilitar, criar e publicar rótulos de sensibilidade para equipes, consulte [usar rótulos de sensibilidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="21e0a-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="21e0a-115">Usar rótulos de sensibilidade com o Teams</span><span class="sxs-lookup"><span data-stu-id="21e0a-115">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="21e0a-116">Aqui estão alguns exemplos de cenários de como você pode usar rótulos de sensibilidade com o Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="21e0a-116">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="21e0a-117">Configuração de privacidade do teams</span><span class="sxs-lookup"><span data-stu-id="21e0a-117">Privacy setting of teams</span></span>

<span data-ttu-id="21e0a-118">Você pode criar um rótulo de sensibilidade que, quando aplicado durante a criação da equipe, permite que os usuários criem equipes com uma configuração específica de privacidade (pública ou particular).</span><span class="sxs-lookup"><span data-stu-id="21e0a-118">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="21e0a-119">Por exemplo, você pode criar um rótulo chamado "confidencial" no centro de conformidade do & de segurança e configurar o Microsoft Teams para que qualquer equipe criada com esse rótulo deve ser uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="21e0a-119">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="21e0a-120">Quando um usuário cria uma nova equipe e seleciona o rótulo **confidencial** , a única opção de privacidade que está disponível para o usuário é **particular**.</span><span class="sxs-lookup"><span data-stu-id="21e0a-120">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="21e0a-121">Outras opções de privacidade, como público e toda a organização, são desabilitadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="21e0a-121">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Captura de tela de rótulo confidencial de confidencialidade](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="21e0a-123">Da mesma forma, se o usuário selecionar **geral** quando criar uma nova equipe, ele só poderá criar equipes públicas ou de toda a organização.</span><span class="sxs-lookup"><span data-stu-id="21e0a-123">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Captura de tela do rótulo de sensibilidade geral](media/sensitivity-labels-general-example.png)

<span data-ttu-id="21e0a-125">Quando a equipe é criada, o rótulo de sensibilidade fica visível no canto superior direito dos canais da equipe.</span><span class="sxs-lookup"><span data-stu-id="21e0a-125">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-channel.png)

<span data-ttu-id="21e0a-127">Um proprietário de equipe pode alterar o rótulo de sensibilidade e a configuração de privacidade da equipe a qualquer momento, acessando a equipe e, em seguida, clicando em **Editar equipe**.</span><span class="sxs-lookup"><span data-stu-id="21e0a-127">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="21e0a-129">Acesso de convidado a equipes</span><span class="sxs-lookup"><span data-stu-id="21e0a-129">Guest access to teams</span></span>

<span data-ttu-id="21e0a-130">Você pode especificar se uma equipe criada com um rótulo específico permite acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="21e0a-130">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="21e0a-131">As equipes criadas com um rótulo que não permite acesso de convidado só estão disponíveis para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="21e0a-131">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="21e0a-132">Pessoas de fora da sua organização não podem ser adicionadas à equipe.</span><span class="sxs-lookup"><span data-stu-id="21e0a-132">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="21e0a-133">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="21e0a-133">Known issues</span></span>

<span data-ttu-id="21e0a-134">**Suporte para rótulos de sensibilidade no centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="21e0a-134">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="21e0a-135">No momento, não há suporte para rótulos de sensibilidade no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="21e0a-135">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="21e0a-136">Se você usar rótulos de sensibilidade, não poderá definir rótulos de sensibilidade ao criar ou editar uma equipe.</span><span class="sxs-lookup"><span data-stu-id="21e0a-136">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="21e0a-137">Os rótulos de sensibilidade também não ficam visíveis nas propriedades da equipe e não ficarão visíveis na coluna **classificação** no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="21e0a-137">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="21e0a-138">**Suporte para rótulos de sensibilidade em APIs de gráficos do Teams, cmdlets e modelos do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="21e0a-138">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="21e0a-139">Atualmente, os usuários não poderão aplicar rótulos de sensibilidade em equipes criadas diretamente por meio de APIs de gráfico, cmdlets e modelos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21e0a-139">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="21e0a-140">**Edição de rótulos de sensibilidade diretamente em um conjunto de sites do SharePoint para canais privados**</span><span class="sxs-lookup"><span data-stu-id="21e0a-140">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="21e0a-141">Os canais privados criados em uma equipe herdam o rótulo de sensibilidade que foi aplicado a uma equipe.</span><span class="sxs-lookup"><span data-stu-id="21e0a-141">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="21e0a-142">Além disso, o mesmo rótulo é aplicado automaticamente no conjunto de sites do SharePoint para o canal privado.</span><span class="sxs-lookup"><span data-stu-id="21e0a-142">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="21e0a-143">Se um usuário atualizar diretamente o rótulo de sensibilidade em um conjunto de sites do SharePoint para um canal privado, esse rótulo não será atualizado no cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="21e0a-143">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="21e0a-144">Nesse cenário, os usuários continuarão a ver o rótulo de sensibilidade aplicado a uma equipe no cabeçalho do canal privado.</span><span class="sxs-lookup"><span data-stu-id="21e0a-144">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="21e0a-145">**Tempo de propagação de alterações aplicadas a rótulos de sensibilidade fora do aplicativo Teams**</span><span class="sxs-lookup"><span data-stu-id="21e0a-145">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="21e0a-146">As alterações feitas em rótulos de sensibilidade fora do aplicativo Teams podem levar até 24 horas para refletir no aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="21e0a-146">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="21e0a-147">Isso se aplica a qualquer alteração feita para habilitar ou desabilitar rótulos de um locatário, alterações em nomes de rótulo, configurações e políticas.</span><span class="sxs-lookup"><span data-stu-id="21e0a-147">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="21e0a-148">Além disso, qualquer alteração em um rótulo feito diretamente em um grupo ou conjunto de sites do SharePoint que faz backup da equipe pode levar até 24 horas para se propagar para o aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="21e0a-148">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>