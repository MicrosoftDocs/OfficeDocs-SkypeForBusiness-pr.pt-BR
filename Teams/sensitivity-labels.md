---
title: Rótulos de sensibilidade do Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar rótulos de sensibilidade para proteger suas equipes no Microsoft Teams.
ms.openlocfilehash: 3b994bd7f1aa8fbc1fde13aaf49b195a1698695a
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937523"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="3260b-103">Rótulos de sensibilidade do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3260b-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="3260b-104">[Os rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permitem que os administradores do Teams protejam e regulam o acesso a conteúdo organizacional sensível criado durante a colaboração dentro das equipes.</span><span class="sxs-lookup"><span data-stu-id="3260b-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="3260b-105">Depois de configurar rótulos de sensibilidade com suas políticas associadas no centro de conformidade da [Microsoft,](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)esses rótulos podem ser aplicados às equipes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3260b-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="3260b-106">No momento, os rótulos de sensibilidade não têm suporte para clientes que usam SKUs do Teams Education.</span><span class="sxs-lookup"><span data-stu-id="3260b-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="3260b-107">Para saber mais sobre licenciamento, consulte a descrição [do serviço microsoft teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="3260b-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="3260b-108">Qual é a diferença entre rótulos de sensibilidade e rótulos de classificação do Teams?</span><span class="sxs-lookup"><span data-stu-id="3260b-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="3260b-109">Os rótulos de sensibilidade são diferentes dos rótulos de classificação, também conhecidos como classificação de grupo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3260b-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="3260b-110">Os rótulos de classificação são cadeias de texto que podem ser associadas a um grupo do Microsoft 365, mas que não têm políticas reais associadas a eles.</span><span class="sxs-lookup"><span data-stu-id="3260b-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="3260b-111">Você usa rótulos de classificação como metadados e deve usar outros métodos, como ferramentas internas e scripts, para impor políticas.</span><span class="sxs-lookup"><span data-stu-id="3260b-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="3260b-112">A vantagem de usar rótulos de sensibilidade é que suas políticas são impostas automaticamente de ponta a ponta por meio de uma combinação da plataforma Grupos do Microsoft 365, do centro de conformidade e dos serviços do Teams.</span><span class="sxs-lookup"><span data-stu-id="3260b-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="3260b-113">Os rótulos de sensibilidade oferecem suporte poderoso à infraestrutura para proteger os dados confidenciais da sua organização e garantir a conformidade com suas políticas ou regulamentos internos.</span><span class="sxs-lookup"><span data-stu-id="3260b-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="3260b-114">Se você usa rótulos de classificação no momento, confira a documentação a seguir para obter mais informações e instruções sobre como migrá-los para rótulos de sensibilidade: classificação de grupo clássico [do Azure AD.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)</span><span class="sxs-lookup"><span data-stu-id="3260b-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="3260b-115">Cenários de exemplo para rótulos de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="3260b-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="3260b-116">Cenários de exemplo de como você pode usar rótulos de sensibilidade com o Teams em sua organização:</span><span class="sxs-lookup"><span data-stu-id="3260b-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="3260b-117">Definir o nível de privacidade (público ou privado) das equipes</span><span class="sxs-lookup"><span data-stu-id="3260b-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="3260b-118">Controlar o acesso de convidados às equipes</span><span class="sxs-lookup"><span data-stu-id="3260b-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="3260b-119">Definir o nível de privacidade das equipes</span><span class="sxs-lookup"><span data-stu-id="3260b-119">Set the privacy level for teams</span></span>

<span data-ttu-id="3260b-120">Você pode criar e configurar um rótulo de sensibilidade que, quando aplicado durante a criação da equipe, permite que os usuários criem equipes com uma configuração específica de privacidade (pública ou privada).</span><span class="sxs-lookup"><span data-stu-id="3260b-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="3260b-121">Por exemplo, você cria e publica um rótulo de confidencialidade chamado "Confidencial" que tem a opção de privacidade do rótulo configurada como **Particular.**</span><span class="sxs-lookup"><span data-stu-id="3260b-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="3260b-122">Como resultado, qualquer equipe criada com esse rótulo deve ser uma equipe particular.</span><span class="sxs-lookup"><span data-stu-id="3260b-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="3260b-123">Quando um usuário cria uma nova  equipe e seleciona o rótulo Confidencial, a única opção de privacidade disponível para o usuário é **Particular.**</span><span class="sxs-lookup"><span data-stu-id="3260b-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="3260b-124">Outras opções de privacidade, como Público e toda a organização, não estão disponíveis para o usuário selecionar:</span><span class="sxs-lookup"><span data-stu-id="3260b-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![Captura de tela do rótulo confidencial de confidencialidade](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="3260b-126">Da mesma forma, você cria e publica um rótulo de sensibilidade chamado "Geral" que tem a opção de privacidade do rótulo configurada como **Público.**</span><span class="sxs-lookup"><span data-stu-id="3260b-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="3260b-127">Quando um usuário cria uma nova equipe, ele só pode criar equipes públicas ou de toda a organização quando seleciona esse rótulo:</span><span class="sxs-lookup"><span data-stu-id="3260b-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![Captura de tela do rótulo de sensibilidade geral](media/sensitivity-labels-general-example.png)

<span data-ttu-id="3260b-129">Quando uma equipe é criada, o rótulo de sensibilidade fica visível no canto superior direito dos canais da equipe.</span><span class="sxs-lookup"><span data-stu-id="3260b-129">When a team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-channel.png)

<span data-ttu-id="3260b-131">Um proprietário de equipe pode alterar o rótulo de sensibilidade e a configuração de privacidade da equipe a qualquer momento, indo até a equipe e, em seguida, clique em **Editar equipe.**</span><span class="sxs-lookup"><span data-stu-id="3260b-131">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![Captura de tela do rótulo de sensibilidade nas propriedades da equipe](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="3260b-133">Controlar o acesso de convidados às equipes</span><span class="sxs-lookup"><span data-stu-id="3260b-133">Control guest access to teams</span></span>

<span data-ttu-id="3260b-134">Você pode usar rótulos de sensibilidade para controlar o acesso de convidados às suas equipes.</span><span class="sxs-lookup"><span data-stu-id="3260b-134">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="3260b-135">As equipes criadas com um rótulo que não permite o acesso de convidados só estão disponíveis para os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3260b-135">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="3260b-136">Pessoas de fora da sua organização não podem ser adicionadas à equipe.</span><span class="sxs-lookup"><span data-stu-id="3260b-136">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="3260b-137">Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3260b-137">Microsoft Teams admin center</span></span>

<span data-ttu-id="3260b-138">Você pode aplicar rótulos de sensibilidade ao criar ou editar uma equipe no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3260b-138">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="3260b-139">Os rótulos de sensibilidade também são  visíveis  nas propriedades da equipe e na coluna Classificação na página Gerenciar equipes do Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3260b-139">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="3260b-140">Limitações</span><span class="sxs-lookup"><span data-stu-id="3260b-140">Limitations</span></span>

<span data-ttu-id="3260b-141">Antes de usar rótulos de sensibilidade para o Teams, esteja ciente das seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="3260b-141">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="3260b-142">**Os nomes dos rótulos pai não são exibidos para sublabeles**</span><span class="sxs-lookup"><span data-stu-id="3260b-142">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="3260b-143">O Teams dá suporte a sublabeles, mas não exibe o nome do rótulo pai.</span><span class="sxs-lookup"><span data-stu-id="3260b-143">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="3260b-144">Por exemplo, **Confidencial** \\ **Todos os Funcionários** é exibido como **Todos os Funcionários.**</span><span class="sxs-lookup"><span data-stu-id="3260b-144">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="3260b-145">**Os rótulos de sensibilidade não são suportados por APIs do Teams Graph, cmdlets do PowerShell e modelos**</span><span class="sxs-lookup"><span data-stu-id="3260b-145">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="3260b-146">Os usuários não poderão aplicar rótulos de sensibilidade em equipes criadas diretamente por meio de APIs do Teams Graph, cmdlets do PowerShell e modelos do Teams.</span><span class="sxs-lookup"><span data-stu-id="3260b-146">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="3260b-147">**Suporte para canais privados**</span><span class="sxs-lookup"><span data-stu-id="3260b-147">**Support for private channels**</span></span>
    
    <span data-ttu-id="3260b-148">Canais privados criados em uma equipe herdam o rótulo de sensibilidade aplicado em uma equipe.</span><span class="sxs-lookup"><span data-stu-id="3260b-148">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="3260b-149">O mesmo rótulo é aplicado automaticamente no conjunto de sites do SharePoint para o canal privado.</span><span class="sxs-lookup"><span data-stu-id="3260b-149">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="3260b-150">No entanto, se um usuário alterar diretamente o rótulo de sensibilidade em um site do SharePoint para um canal privado, essa alteração de rótulo não será refletida no cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="3260b-150">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="3260b-151">Nesse cenário, os usuários continuam a ver o rótulo de sensibilidade original aplicado na equipe no título do canal privado.</span><span class="sxs-lookup"><span data-stu-id="3260b-151">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="3260b-152">Como criar e configurar rótulos de sensibilidade para o Teams</span><span class="sxs-lookup"><span data-stu-id="3260b-152">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="3260b-153">Use as instruções da documentação do Microsoft 365 para criar e configurar rótulos de sensibilidade para o Teams:</span><span class="sxs-lookup"><span data-stu-id="3260b-153">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="3260b-154">[Use rótulos de sensibilidade para proteger conteúdo no Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="3260b-154">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
