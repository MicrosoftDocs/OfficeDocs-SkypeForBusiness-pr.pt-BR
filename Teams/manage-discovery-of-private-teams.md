---
title: Gerenciar a descoberta de equipes privadas em Teams da Microsoft
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como controlar se as equipes privadas podem ser descobertas pelos usuários do Microsoft Teams usando sugestões nos resultados de pesquisa e de galeria da equipe.
ms.openlocfilehash: 3609a592c3c940e9f7cbec6ca5c58fd072322c46
ms.sourcegitcommit: 0bb55cad74b15fc821ae916799aa8c0cb13dd31d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2019
ms.locfileid: "33497949"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="a9ead-103">Gerenciar a descoberta de equipes privadas em Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9ead-103">Manage discovery of private teams in Microsoft Teams</span></span>

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

<span data-ttu-id="a9ead-104">Proprietários de equipe e os administradores podem controlar se as equipes privadas podem ser descobertas pelos usuários Teams da Microsoft em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a9ead-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="a9ead-105">Quando uma equipe privada é detectável, ele aparecerá nos resultados da pesquisa e está incluído no sugestões na Galeria de equipe, junto com as equipes públicas em equipes.</span><span class="sxs-lookup"><span data-stu-id="a9ead-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="a9ead-106">Isso torna fácil para os usuários procurar e encontre as equipes privadas que desejam ingressar.</span><span class="sxs-lookup"><span data-stu-id="a9ead-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="a9ead-107">Os usuários podem solicitar para ingressar em uma equipe privada que um proprietário de equipe pode, em seguida, aprovar ou negar.</span><span class="sxs-lookup"><span data-stu-id="a9ead-107">Users can request to join a private team which a team owner can then approve or deny.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="a9ead-108">Visão geral das equipes públicas, privadas equipes e descoberta em equipes</span><span class="sxs-lookup"><span data-stu-id="a9ead-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="a9ead-109">A maioria das organizações têm os seguintes tipos de equipes - públicas equipes, equipes privadas detectáveis e equipes privadas não detectáveis.</span><span class="sxs-lookup"><span data-stu-id="a9ead-109">Most organizations have the following kinds of teams - public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Galeria de equipe](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="a9ead-111">Equipes de públicas</span><span class="sxs-lookup"><span data-stu-id="a9ead-111">Public teams</span></span>

<span data-ttu-id="a9ead-112">Equipes públicas estão disponíveis para todos os usuários em sua organização ingressar.</span><span class="sxs-lookup"><span data-stu-id="a9ead-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="a9ead-113">As equipes de públicas são visíveis para todos na Galeria de equipes e os usuários podem ingressar em uma equipe pública sem precisar obter aprovação do proprietário equipe.</span><span class="sxs-lookup"><span data-stu-id="a9ead-113">Public teams are visible to everyone in the teams gallery and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="a9ead-114">Exemplos de equipes públicas incluem uma equipe para discutir notícias em uma equipe de rodízio pessoas trabalhem, uma equipe para obter feedback dogfood para os produtos e tecnologia.</span><span class="sxs-lookup"><span data-stu-id="a9ead-114">Examples of public teams include a team to discuss news in technology, a team to get dogfood feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="a9ead-115">Equipes privadas detectáveis</span><span class="sxs-lookup"><span data-stu-id="a9ead-115">Discoverable private teams</span></span>

<span data-ttu-id="a9ead-116">Detectáveis equipes privadas só podem ser incluídas quando o proprietário de equipe adiciona usuários a eles.</span><span class="sxs-lookup"><span data-stu-id="a9ead-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="a9ead-117">Quando você faz uma equipe privada detectáveis, a equipe está incluída na lista de equipes sugeridas e resultados de pesquisa na Galeria de equipes.</span><span class="sxs-lookup"><span data-stu-id="a9ead-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="a9ead-118">Use detectáveis equipes privadas para projetos e grupos na sua organização que todos está ciente e onde o acesso a conversas e arquivos na equipe de precisam ser controlados.</span><span class="sxs-lookup"><span data-stu-id="a9ead-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="a9ead-119">Exemplos incluem uma equipe para seu departamento de RH, uma equipe para todos os gerentes em sua organização e uma equipe para um gerente e seus relatórios diretos.</span><span class="sxs-lookup"><span data-stu-id="a9ead-119">Examples include a team for your HR department, a team for all managers at your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="a9ead-120">Não-detectável equipes privadas</span><span class="sxs-lookup"><span data-stu-id="a9ead-120">Non-discoverable private teams</span></span>

<span data-ttu-id="a9ead-121">Não-detectável equipes privadas só podem ser incluídas quando o proprietário de equipe adiciona usuários a eles.</span><span class="sxs-lookup"><span data-stu-id="a9ead-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="a9ead-122">Quando você faz uma equipe privada não detectável, ele tem oculto da lista de equipes sugeridas e removidas dos resultados da pesquisa na Galeria de equipes.</span><span class="sxs-lookup"><span data-stu-id="a9ead-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="a9ead-123">Use as equipes de não-identificável para colaborar nos tópicos altamente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="a9ead-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="a9ead-124">Exemplos incluem uma equipe para discutir uma aquisição futura e uma equipe para discutir uma alteração na direção estratégica de sua organização.</span><span class="sxs-lookup"><span data-stu-id="a9ead-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="a9ead-125">Defina se novas equipes privadas são detectáveis</span><span class="sxs-lookup"><span data-stu-id="a9ead-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="a9ead-126">Quando um proprietário de equipe cria uma equipe privada, eles podem optar por torná-lo localizável, definindo a configuração de descoberta da equipe.</span><span class="sxs-lookup"><span data-stu-id="a9ead-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="a9ead-127">Por padrão, as novas equipes privadas são pesquisáveis e detectáveis.</span><span class="sxs-lookup"><span data-stu-id="a9ead-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="a9ead-128">Se o proprietário de equipe não quiser que a equipe particular seja mostrada no sugestões e resultados de pesquisa, eles podem desativar a configuração selecionando **Alterar configuração** ao lado de **Este equipe é pesquisável e detectáveis**.</span><span class="sxs-lookup"><span data-stu-id="a9ead-128">If the team owner doesn't want the private team to show up in search results and suggestions, they can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![configuração de descoberta de novas equipes privadas](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="a9ead-130">Defina se as equipes privadas existentes estão detectáveis</span><span class="sxs-lookup"><span data-stu-id="a9ead-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="a9ead-131">Proprietários de equipe podem definir a configuração de descoberta para uma equipe privada existente diretamente nas configurações de equipe e os administradores podem fazer isso usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9ead-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="a9ead-132">Nas configurações de equipe</span><span class="sxs-lookup"><span data-stu-id="a9ead-132">In team settings</span></span>

<span data-ttu-id="a9ead-133">Em equipes, vá para a equipe privada, clique em **mais ˙˙˙ de opções** > **equipe gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a9ead-133">In Teams, go to the private team, click **More options ˙˙˙** > **Manage team**.</span></span> <span data-ttu-id="a9ead-134">Na guia **configurações** , expanda a **descoberta de equipe**e desmarque ou marque a caixa de seleção **Ativar o recurso de descoberta** .</span><span class="sxs-lookup"><span data-stu-id="a9ead-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![configuração de descoberta para equipes privadas existentes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a><span data-ttu-id="a9ead-136">Usando o PowerShell (em breve)</span><span class="sxs-lookup"><span data-stu-id="a9ead-136">Using PowerShell (coming soon)</span></span>

<span data-ttu-id="a9ead-137">Use o cmdlet **Set-equipe** para desativar ou ativar a configuração de descoberta para uma equipe privada existente.</span><span class="sxs-lookup"><span data-stu-id="a9ead-137">Use the **Set-Team** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="a9ead-138">Aqui está um exemplo de como tornar uma equipe detectável:</span><span class="sxs-lookup"><span data-stu-id="a9ead-138">Here's an example of how to make a team discoverable:</span></span>

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
<span data-ttu-id="a9ead-139">Você pode usar esse cmdlet em um script para definir a configuração de descoberta de equipes privadas existentes em massa.</span><span class="sxs-lookup"><span data-stu-id="a9ead-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="a9ead-140">Definir se os usuários podem descobrir equipes privadas</span><span class="sxs-lookup"><span data-stu-id="a9ead-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="a9ead-141">Como um administrador, você pode controlar quais usuários em sua organização têm permissão para descobrir privadas equipes nos resultados da pesquisa e sugestões em equipes.</span><span class="sxs-lookup"><span data-stu-id="a9ead-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="a9ead-142">Criar uma diretiva usando o cmdlet **New-CsTeamsChannelsPolicy** e, em seguida, atribuir a política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="a9ead-142">Create a policy by using the **New-CsTeamsChannelsPolicy** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="a9ead-143">Defina o parâmetro **AllowPrivateTeamDiscovery** como **true** para permitir que os usuários que receberem a política para ver as equipes de privada detectáveis em resultados da pesquisa e sugestões.</span><span class="sxs-lookup"><span data-stu-id="a9ead-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="a9ead-144">O parâmetro **AllowPrivateTeamDiscovery** a definição como **false** remove todas as equipes privadas detectáveis resultados da pesquisa e sugestões para os usuários atribuídos a política.</span><span class="sxs-lookup"><span data-stu-id="a9ead-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="a9ead-145">Por padrão, **AllowPrivateTeamDiscovery** é definido como **true** para todos os usuários em uma organização.</span><span class="sxs-lookup"><span data-stu-id="a9ead-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="a9ead-146">Neste exemplo, criamos uma política de chamada VendorPolicy que impede que os usuários descobrindo qualquer equipes privadas que são feitas detectáveis e, em seguida, atribuímos a política a uma usuária chamada vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="a9ead-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> <span data-ttu-id="a9ead-147">Privada equipes que não são detectáveis nunca são mostradas em resultados da pesquisa e sugestões, independentemente da configuração de política.</span><span class="sxs-lookup"><span data-stu-id="a9ead-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="a9ead-148">Por exemplo, se você desativar a configuração de descoberta para uma equipe privada, os usuários não conseguem descubram da equipe, mesmo que o parâmetro **AllowPrivateTeamDiscovery** seja definido como **true** na configuração de diretiva para os usuários.</span><span class="sxs-lookup"><span data-stu-id="a9ead-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9ead-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a9ead-149">Related topics</span></span>
- [<span data-ttu-id="a9ead-150">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="a9ead-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)