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
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="815b2-103">Rótulos de sensibilidade do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="815b2-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="815b2-104">Os [Rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permitem que os administradores de equipe protejam e regulassem o acesso a conteúdos organizacionais confidenciais criados durante a colaboração no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="815b2-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="815b2-105">Depois de configurar os rótulos de sensibilidade com suas políticas associadas no [centro de conformidade da Microsoft](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), esses rótulos podem ser aplicados às equipes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="815b2-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="815b2-106">No momento, os rótulos de sensibilidade não são aceitos para clientes que usam SKUs de educação do teams.</span><span class="sxs-lookup"><span data-stu-id="815b2-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="815b2-107">Para saber mais sobre licenciamento, consulte [Descrição do serviço Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="815b2-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="815b2-108">Qual é a diferença entre rótulos de sensibilidade e rótulos de classificação de equipes?</span><span class="sxs-lookup"><span data-stu-id="815b2-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="815b2-109">Rótulos de sensibilidade são diferentes dos rótulos de classificação, também conhecidos como classificação do Azure AD Group.</span><span class="sxs-lookup"><span data-stu-id="815b2-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="815b2-110">Os rótulos de classificação são cadeias de caracteres de texto que podem ser associadas a um grupo do Microsoft 365, mas não têm políticas reais associadas a eles.</span><span class="sxs-lookup"><span data-stu-id="815b2-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="815b2-111">Você usa rótulos de classificação como metadados e deve usar outros métodos, como ferramentas internas e scripts, para impor políticas.</span><span class="sxs-lookup"><span data-stu-id="815b2-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="815b2-112">A vantagem de usar rótulos de sensibilidade é que suas políticas sejam automaticamente impostas de ponta a ponta por meio de uma combinação da plataforma de grupos do Microsoft 365, do centro de conformidade e dos serviços do teams.</span><span class="sxs-lookup"><span data-stu-id="815b2-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="815b2-113">Os rótulos de sensibilidade fornecem suporte avançado à infra-estrutura para proteger os dados confidenciais da sua organização e garantir a conformidade com suas políticas internas ou normas.</span><span class="sxs-lookup"><span data-stu-id="815b2-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="815b2-114">Se você usa rótulos de classificação no momento, confira a documentação a seguir para obter mais informações e instruções sobre como migrá-los para rótulos de sensibilidade: [classificação clássica do Azure ad Group](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span><span class="sxs-lookup"><span data-stu-id="815b2-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="815b2-115">Cenários de exemplo para rótulos de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="815b2-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="815b2-116">Exemplos de cenários sobre como você pode usar rótulos de sensibilidade com o Teams em sua organização:</span><span class="sxs-lookup"><span data-stu-id="815b2-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="815b2-117">Definir o nível de privacidade (público ou particular) para o Teams</span><span class="sxs-lookup"><span data-stu-id="815b2-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="815b2-118">Controlar o acesso de convidados às equipes</span><span class="sxs-lookup"><span data-stu-id="815b2-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="815b2-119">Definir o nível de privacidade para Teams</span><span class="sxs-lookup"><span data-stu-id="815b2-119">Set the privacy level for teams</span></span>

<span data-ttu-id="815b2-120">Você pode criar e configurar um rótulo de sensibilidade que, quando aplicado durante a criação da equipe, permite aos usuários criar equipes com uma configuração específica de privacidade (pública ou particular).</span><span class="sxs-lookup"><span data-stu-id="815b2-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="815b2-121">Por exemplo, você cria e publica um rótulo de sensibilidade chamado "confidencial" que tem a opção de privacidade de rótulo configurada como **particular**.</span><span class="sxs-lookup"><span data-stu-id="815b2-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="815b2-122">Como resultado, qualquer equipe criada com esse rótulo deve ser uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="815b2-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="815b2-123">Quando um usuário cria uma nova equipe e seleciona o rótulo **confidencial** , a única opção de privacidade que está disponível para o usuário é **particular**.</span><span class="sxs-lookup"><span data-stu-id="815b2-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="815b2-124">Outras opções de privacidade, como público e de toda a organização, não estão disponíveis para que o usuário selecione:</span><span class="sxs-lookup"><span data-stu-id="815b2-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![Captura de tela de rótulo confidencial de confidencialidade](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="815b2-126">Da mesma forma, você cria e publica um rótulo de sensibilidade chamado "geral" com a opção de privacidade de rótulo configurada como **público**.</span><span class="sxs-lookup"><span data-stu-id="815b2-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="815b2-127">Quando um usuário cria uma nova equipe, ele só pode criar equipes públicas ou de toda a organização quando eles selecionam este rótulo:</span><span class="sxs-lookup"><span data-stu-id="815b2-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![Captura de tela do rótulo de sensibilidade geral](media/sensitivity-labels-general-example.png)

<span data-ttu-id="815b2-129">Quando uma equipe é criada, o rótulo de sensibilidade fica visível no canto superior direito dos canais da equipe.</span><span class="sxs-lookup"><span data-stu-id="815b2-129">When a team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-channel.png)

<span data-ttu-id="815b2-131">Um proprietário de equipe pode alterar o rótulo de sensibilidade e a configuração de privacidade da equipe a qualquer momento, acessando a equipe e, em seguida, clique em **Editar equipe**.</span><span class="sxs-lookup"><span data-stu-id="815b2-131">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![Captura de tela do rótulo de sensibilidade nas propriedades da equipe](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="815b2-133">Controlar o acesso de convidados às equipes</span><span class="sxs-lookup"><span data-stu-id="815b2-133">Control guest access to teams</span></span>

<span data-ttu-id="815b2-134">Você pode usar rótulos de sensibilidade para controlar o acesso de convidados às suas equipes.</span><span class="sxs-lookup"><span data-stu-id="815b2-134">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="815b2-135">As equipes criadas com um rótulo que não permite acesso de convidado só estão disponíveis para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="815b2-135">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="815b2-136">Pessoas de fora da sua organização não podem ser adicionadas à equipe.</span><span class="sxs-lookup"><span data-stu-id="815b2-136">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="815b2-137">Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="815b2-137">Microsoft Teams admin center</span></span>

<span data-ttu-id="815b2-138">Você pode aplicar rótulos de sensibilidade ao criar ou editar uma equipe no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="815b2-138">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="815b2-139">Os rótulos de sensibilidade também são visíveis nas propriedades da equipe e na coluna **classificação** na página **gerenciar equipes** do centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="815b2-139">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="815b2-140">Relacionadas</span><span class="sxs-lookup"><span data-stu-id="815b2-140">Limitations</span></span>

<span data-ttu-id="815b2-141">Antes de usar rótulos de sensibilidade para o Teams, lembre-se das seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="815b2-141">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="815b2-142">**Nomes de rótulos pai não são exibidos para subrótulos**</span><span class="sxs-lookup"><span data-stu-id="815b2-142">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="815b2-143">O Teams dá suporte a subrótulos, mas não exibe o nome do rótulo pai.</span><span class="sxs-lookup"><span data-stu-id="815b2-143">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="815b2-144">Por exemplo, **confidencial** \\ **todos os funcionários** são exibidos como **todos os funcionários**.</span><span class="sxs-lookup"><span data-stu-id="815b2-144">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="815b2-145">**Rótulos de sensibilidade não são compatíveis com APIs do teams Graph, cmdlets e modelos do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="815b2-145">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="815b2-146">Os usuários não poderão aplicar rótulos de sensibilidade em equipes criadas diretamente por meio das APIs do teams Graph, cmdlets do PowerShell do Teams e modelos do teams.</span><span class="sxs-lookup"><span data-stu-id="815b2-146">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="815b2-147">**Suporte a canais privados**</span><span class="sxs-lookup"><span data-stu-id="815b2-147">**Support for private channels**</span></span>
    
    <span data-ttu-id="815b2-148">Os canais privados criados em uma equipe herdam o rótulo de sensibilidade aplicado a uma equipe.</span><span class="sxs-lookup"><span data-stu-id="815b2-148">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="815b2-149">O mesmo rótulo é aplicado automaticamente no conjunto de sites do SharePoint para o canal privado.</span><span class="sxs-lookup"><span data-stu-id="815b2-149">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="815b2-150">No entanto, se um usuário alterar diretamente o rótulo de sensibilidade em um site do SharePoint para um canal privado, essa alteração de rótulo não será refletida no cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="815b2-150">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="815b2-151">Nesse cenário, os usuários continuam a ver o rótulo de sensibilidade original aplicado na equipe no cabeçalho do canal privado.</span><span class="sxs-lookup"><span data-stu-id="815b2-151">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="815b2-152">Como criar e configurar rótulos de sensibilidade para equipes</span><span class="sxs-lookup"><span data-stu-id="815b2-152">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="815b2-153">Use as instruções da documentação do Microsoft 365 para criar e configurar rótulos de sensibilidade para equipes:</span><span class="sxs-lookup"><span data-stu-id="815b2-153">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="815b2-154">[Use rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, grupos do microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="815b2-154">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
