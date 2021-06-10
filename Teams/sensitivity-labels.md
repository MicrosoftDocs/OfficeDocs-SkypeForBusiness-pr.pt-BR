---
title: Rótulos de sensibilidade para Microsoft Teams
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
description: Saiba como usar rótulos de sensibilidade para proteger suas equipes Microsoft Teams.
ms.openlocfilehash: 461daf6e91f9ba276dceef1929601d1188563931
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593859"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="4e135-103">Rótulos de sensibilidade para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e135-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="4e135-104">[Os rótulos de](/microsoft-365/compliance/sensitivity-labels) sensibilidade Teams administradores para proteger e regular o acesso a conteúdo organizacional sensível criado durante a colaboração dentro das equipes.</span><span class="sxs-lookup"><span data-stu-id="4e135-104">[Sensitivity labels](/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="4e135-105">Depois de configurar rótulos de sensibilidade com suas políticas associadas no centro de conformidade da [Microsoft,](/microsoft-365/compliance/go-to-the-securitycompliance-center)esses rótulos podem ser aplicados às equipes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4e135-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="4e135-106">Atualmente, os rótulos de sensibilidade não têm suporte em equipes de classe para clientes que usam Teams Education SKUs.</span><span class="sxs-lookup"><span data-stu-id="4e135-106">Sensitivity labels are currently unsupported in class teams for customers using Teams Education SKUs.</span></span> <span data-ttu-id="4e135-107">Para saber mais sobre licenciamento, consulte [Microsoft Teams descrição do serviço.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="4e135-107">To learn more about licensing, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="4e135-108">Qual é a diferença entre rótulos de sensibilidade e rótulos Teams classificação?</span><span class="sxs-lookup"><span data-stu-id="4e135-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="4e135-109">Os rótulos de sensibilidade são diferentes dos rótulos de classificação, também conhecidos como classificação de grupo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e135-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="4e135-110">Rótulos de classificação são cadeias de caracteres de texto que podem ser associadas a um grupo Microsoft 365, mas não têm políticas reais associadas a eles.</span><span class="sxs-lookup"><span data-stu-id="4e135-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="4e135-111">Você usa rótulos de classificação como metadados e, em seguida, deve usar outros métodos, como ferramentas internas e scripts, para impor políticas.</span><span class="sxs-lookup"><span data-stu-id="4e135-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="4e135-112">O benefício de usar rótulos de sensibilidade é que suas políticas são impostas automaticamente de ponta a ponta por meio de uma combinação da plataforma Microsoft 365 Grupos, do centro de conformidade e dos serviços Teams.</span><span class="sxs-lookup"><span data-stu-id="4e135-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="4e135-113">Os rótulos de sensibilidade oferecem suporte de infraestrutura eficiente para proteger os dados confidenciais da sua organização e garantir a conformidade com suas políticas ou regulamentos internos.</span><span class="sxs-lookup"><span data-stu-id="4e135-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="4e135-114">Se você usa rótulos de classificação no momento, consulte a documentação a seguir para obter mais informações e instruções sobre como migrar para rótulos de sensibilidade: Classificação de grupo clássica do [Azure AD](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span><span class="sxs-lookup"><span data-stu-id="4e135-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="4e135-115">Cenários de exemplo para rótulos de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="4e135-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="4e135-116">Exemplos de cenários de como você pode usar rótulos de sensibilidade com Teams em sua organização:</span><span class="sxs-lookup"><span data-stu-id="4e135-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="4e135-117">Definir o nível de privacidade (público ou privado) para equipes</span><span class="sxs-lookup"><span data-stu-id="4e135-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="4e135-118">Controlar o acesso de convidados às equipes</span><span class="sxs-lookup"><span data-stu-id="4e135-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="4e135-119">Definir o nível de privacidade para equipes</span><span class="sxs-lookup"><span data-stu-id="4e135-119">Set the privacy level for teams</span></span>

<span data-ttu-id="4e135-120">Você pode criar e configurar um rótulo de sensibilidade que, quando aplicado durante a criação da equipe, permite que os usuários criem equipes com uma configuração de privacidade específica (pública ou privada).</span><span class="sxs-lookup"><span data-stu-id="4e135-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="4e135-121">Por exemplo, você cria e publica um rótulo de confidencialidade chamado "Confidencial" que tem a opção de privacidade de rótulo configurada como **Private**.</span><span class="sxs-lookup"><span data-stu-id="4e135-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="4e135-122">Como resultado, qualquer equipe criada com esse rótulo deve ser uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="4e135-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="4e135-123">Quando um usuário cria uma nova equipe e seleciona o rótulo **Confidencial,** a única opção de privacidade disponível para o usuário é **Private**.</span><span class="sxs-lookup"><span data-stu-id="4e135-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="4e135-124">Outras opções de privacidade, como Público e toda a organização, não estão disponíveis para o usuário selecionar:</span><span class="sxs-lookup"><span data-stu-id="4e135-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![Captura de tela do rótulo confidencial de confidencialidade](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="4e135-126">Da mesma forma, você cria e publica um rótulo de sensibilidade chamado "Geral" que tem a opção de privacidade de rótulo configurada como **Pública**.</span><span class="sxs-lookup"><span data-stu-id="4e135-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="4e135-127">Quando um usuário cria uma nova equipe, ele só pode criar equipes públicas ou em toda a organização quando seleciona esse rótulo:</span><span class="sxs-lookup"><span data-stu-id="4e135-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![Captura de tela do rótulo de sensibilidade geral](media/sensitivity-labels-general-example.png)

<span data-ttu-id="4e135-129">Quando a equipe é criada, o rótulo de sensibilidade fica visível no canto superior direito dos canais na equipe.</span><span class="sxs-lookup"><span data-stu-id="4e135-129">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span> 

> [!NOTE]
> <span data-ttu-id="4e135-130">Se você estiver usando rótulos pai-filho hierárquicos, como "Confidencial\Finanças", somente o rótulo pai será mostrado no header do canal.</span><span class="sxs-lookup"><span data-stu-id="4e135-130">If you are using hierarchical parent-child labels such as "Confidential\Finance", then only the parent label will be shown in the channel header.</span></span>

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-channel.png)

<span data-ttu-id="4e135-132">Um proprietário de equipe pode alterar o rótulo de sensibilidade e a configuração de privacidade da equipe a qualquer momento, indo para a equipe e clique em **Editar equipe**.</span><span class="sxs-lookup"><span data-stu-id="4e135-132">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![Captura de tela do rótulo de sensibilidade nas propriedades da equipe](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="4e135-134">Controlar o acesso de convidados às equipes</span><span class="sxs-lookup"><span data-stu-id="4e135-134">Control guest access to teams</span></span>

<span data-ttu-id="4e135-135">Você pode usar rótulos de sensibilidade para controlar o acesso de convidados às suas equipes.</span><span class="sxs-lookup"><span data-stu-id="4e135-135">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="4e135-136">Teams criado com um rótulo que não permite o acesso de convidados estão disponíveis apenas para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4e135-136">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="4e135-137">Pessoas de fora da sua organização não podem ser adicionadas à equipe.</span><span class="sxs-lookup"><span data-stu-id="4e135-137">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="4e135-138">Microsoft Teams de administração</span><span class="sxs-lookup"><span data-stu-id="4e135-138">Microsoft Teams admin center</span></span>

<span data-ttu-id="4e135-139">Você pode aplicar rótulos de sensibilidade ao criar ou editar uma equipe no Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="4e135-139">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="4e135-140">Os rótulos de sensibilidade também são  visíveis  nas propriedades da equipe e na coluna Classificação na página Gerenciar equipes do Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="4e135-140">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="4e135-141">Limitações</span><span class="sxs-lookup"><span data-stu-id="4e135-141">Limitations</span></span>

<span data-ttu-id="4e135-142">Antes de usar rótulos de sensibilidade para Teams, esteja ciente das seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="4e135-142">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="4e135-143">**Os nomes de rótulo pai não são exibidos para sub-rótulos**</span><span class="sxs-lookup"><span data-stu-id="4e135-143">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="4e135-144">Teams suporta sub-rótulos, mas não exibe o nome do rótulo pai.</span><span class="sxs-lookup"><span data-stu-id="4e135-144">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="4e135-145">Por exemplo, **Confidencial** \\ **Todos os Funcionários** é exibido como **Todos os Funcionários.**</span><span class="sxs-lookup"><span data-stu-id="4e135-145">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="4e135-146">**Os rótulos de sensibilidade não têm suporte Teams Graph APIs, cmdlets do PowerShell e modelos**</span><span class="sxs-lookup"><span data-stu-id="4e135-146">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="4e135-147">Os usuários não poderão especificar rótulos de sensibilidade ao criar equipes diretamente por meio de APIs Teams Graph, cmdlets Teams PowerShell e Teams modelos.</span><span class="sxs-lookup"><span data-stu-id="4e135-147">Users won't be able to specify sensitivity labels while creating teams directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span> <span data-ttu-id="4e135-148">No entanto, grupos modernos Graph APIs e cmdlets do PowerShell permitem a criação de grupos com rótulos.</span><span class="sxs-lookup"><span data-stu-id="4e135-148">However Modern Groups Graph APIs and PowerShell cmdlets do allow creation of groups with labels.</span></span> <span data-ttu-id="4e135-149">Para que os usuários possam primeiro criar Grupos com rótulos usando APIs Graph Grupos ou cmdlets do PowerShell e convertê-los em Teams.</span><span class="sxs-lookup"><span data-stu-id="4e135-149">So users can first create Groups with labels using Groups Graph APIs or PowerShell cmdlets and then convert these Groups in to Teams.</span></span>

- <span data-ttu-id="4e135-150">**Suporte para canais privados**</span><span class="sxs-lookup"><span data-stu-id="4e135-150">**Support for private channels**</span></span>
    
    <span data-ttu-id="4e135-151">Canais privados criados em uma equipe herdam o rótulo de sensibilidade aplicado em uma equipe.</span><span class="sxs-lookup"><span data-stu-id="4e135-151">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="4e135-152">O mesmo rótulo é aplicado automaticamente no conjunto SharePoint site do canal privado.</span><span class="sxs-lookup"><span data-stu-id="4e135-152">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="4e135-153">No entanto, se um usuário alterar diretamente o rótulo de sensibilidade em um site SharePoint para um canal privado, essa alteração de rótulo não se refletirá no cliente Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="4e135-153">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="4e135-154">Nesse cenário, os usuários continuam a ver o rótulo de sensibilidade original aplicado à equipe no header de canal privado.</span><span class="sxs-lookup"><span data-stu-id="4e135-154">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="4e135-155">Como criar e configurar rótulos de sensibilidade para Teams</span><span class="sxs-lookup"><span data-stu-id="4e135-155">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="4e135-156">Use as instruções da documentação Microsoft 365 para criar e configurar rótulos de sensibilidade para Teams:</span><span class="sxs-lookup"><span data-stu-id="4e135-156">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="4e135-157">[Use rótulos de sensibilidade para proteger o conteúdo em Microsoft Teams, Microsoft 365 grupos e SharePoint sites](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="4e135-157">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
