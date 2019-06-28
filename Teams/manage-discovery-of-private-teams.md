---
title: Gerenciar a descoberta de equipes particulares no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como controlar se as equipes particulares podem ser descobertas pelos usuários do Microsoft Teams por meio de sugestões na Galeria de equipe e nos resultados da pesquisa.
ms.openlocfilehash: 099daaed42e108e63a5f8334bd2ed89744479dbd
ms.sourcegitcommit: 3abc3dcaa79ebd8e4326fa282874500c4425e64f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/28/2019
ms.locfileid: "35347872"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="e89a4-103">Gerenciar a descoberta de equipes particulares no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e89a4-103">Manage discovery of private teams in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="e89a4-104">Administradores e proprietários de equipe podem controlar se as equipes particulares podem ser descobertas pelos usuários do Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e89a4-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="e89a4-105">Quando uma equipe privada é detectável, ela é mostrada nos resultados da pesquisa e está incluída em sugestões na Galeria de equipes juntamente com equipes públicas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e89a4-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="e89a4-106">Isso torna mais fácil para os usuários procurarem e encontrarem as equipes particulares que desejam participar.</span><span class="sxs-lookup"><span data-stu-id="e89a4-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="e89a4-107">Os usuários podem solicitar para ingressar em uma equipe particular, e o proprietário da equipe pode aprovar ou recusar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="e89a4-107">Users can request to join a private team, and a team owner can then approve or deny the request.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="e89a4-108">Visão geral de equipes públicas, equipes particulares e descoberta no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e89a4-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="e89a4-109">A maioria das organizações tem os seguintes tipos de Teams: equipes públicas, equipes privadas detectáveis e equipes privadas não detectáveis.</span><span class="sxs-lookup"><span data-stu-id="e89a4-109">Most organizations have the following kinds of teams: public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Captura de tela da Galeria de equipes](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="e89a4-111">Equipes públicas</span><span class="sxs-lookup"><span data-stu-id="e89a4-111">Public teams</span></span>

<span data-ttu-id="e89a4-112">As equipes públicas estão disponíveis para que todos os usuários de sua organização ingressem.</span><span class="sxs-lookup"><span data-stu-id="e89a4-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="e89a4-113">As equipes públicas são visíveis para todos na Galeria de equipes, e os usuários podem ingressar em uma equipe pública sem ter que obter a aprovação do proprietário da equipe.</span><span class="sxs-lookup"><span data-stu-id="e89a4-113">Public teams are visible to everyone in the teams gallery, and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="e89a4-114">Exemplos de equipes públicas incluem uma equipe para discutir notícias sobre tecnologia, uma equipe para obter comentários de seus produtos e uma equipe para que as pessoas carpoolingm de trabalhar.</span><span class="sxs-lookup"><span data-stu-id="e89a4-114">Examples of public teams include a team to discuss technology news, a team to get feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="e89a4-115">Equipes privadas detectáveis</span><span class="sxs-lookup"><span data-stu-id="e89a4-115">Discoverable private teams</span></span>

<span data-ttu-id="e89a4-116">As equipes privadas detectáveis só podem ser Unidas quando o proprietário da equipe adiciona usuários a elas.</span><span class="sxs-lookup"><span data-stu-id="e89a4-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="e89a4-117">Quando você torna uma equipe particular detectável, a equipe está incluída na lista de equipes sugeridas e nos resultados da pesquisa na galeria do teams.</span><span class="sxs-lookup"><span data-stu-id="e89a4-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="e89a4-118">Use equipes particulares detectáveis para projetos e grupos em sua organização que todos estão cientes e onde o acesso a conversas e arquivos na equipe precisa ser controlado.</span><span class="sxs-lookup"><span data-stu-id="e89a4-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="e89a4-119">Os exemplos incluem uma equipe para seu departamento de RH, uma equipe para todos os gerentes da sua organização e uma equipe para um gerente e seus relatórios diretos.</span><span class="sxs-lookup"><span data-stu-id="e89a4-119">Examples include a team for your HR department, a team for all managers in your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="e89a4-120">Equipes privadas não detectáveis</span><span class="sxs-lookup"><span data-stu-id="e89a4-120">Non-discoverable private teams</span></span>

<span data-ttu-id="e89a4-121">As equipes privadas não detectáveis só podem ser Unidas quando o proprietário da equipe adiciona usuários a elas.</span><span class="sxs-lookup"><span data-stu-id="e89a4-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="e89a4-122">Quando você torna uma equipe privada não detectável, ela fica oculta na lista de equipes sugeridas e removida dos resultados da pesquisa na galeria do teams.</span><span class="sxs-lookup"><span data-stu-id="e89a4-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="e89a4-123">Use o Microsoft Teams não detectável para colaborar em tópicos confidenciais e altamente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="e89a4-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="e89a4-124">Os exemplos incluem uma equipe para discutir uma aquisição futura e uma equipe para discutir uma alteração na orientação estratégica da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e89a4-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="e89a4-125">Definir se novas equipes particulares são detectáveis</span><span class="sxs-lookup"><span data-stu-id="e89a4-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="e89a4-126">Quando um proprietário da equipe cria uma equipe particular, ele pode optar por torná-lo detectável Configurando a configuração de descoberta da equipe.</span><span class="sxs-lookup"><span data-stu-id="e89a4-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="e89a4-127">Por padrão, novas equipes particulares são pesquisáveis e detectáveis.</span><span class="sxs-lookup"><span data-stu-id="e89a4-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="e89a4-128">Se o proprietário da equipe não quiser que a equipe privada apareça nos resultados da pesquisa e sugestões, o proprietário poderá desativar a configuração selecionando **Alterar configuração** ao lado **desta equipe pode ser pesquisada e detectável**.</span><span class="sxs-lookup"><span data-stu-id="e89a4-128">If the team owner doesn't want the private team to show up in search results and suggestions, the owner can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![Captura de tela da configuração de descoberta para novas equipes particulares](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="e89a4-130">Definir se as equipes privadas existentes são detectáveis</span><span class="sxs-lookup"><span data-stu-id="e89a4-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="e89a4-131">Os proprietários da equipe podem definir a configuração de descoberta para uma equipe particular existente diretamente nas configurações da equipe e os administradores podem fazê-lo usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e89a4-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="e89a4-132">Em configurações da equipe</span><span class="sxs-lookup"><span data-stu-id="e89a4-132">In team settings</span></span>

<span data-ttu-id="e89a4-133">No Teams, vá para a equipe particular, clique em **mais opções** > **Gerenciar equipe**.</span><span class="sxs-lookup"><span data-stu-id="e89a4-133">In Teams, go to the private team, click **More options** > **Manage team**.</span></span> <span data-ttu-id="e89a4-134">Na guia **configurações** , expanda **descoberta de equipe**e desmarque ou marque a caixa de seleção **habilitar** a descoberta.</span><span class="sxs-lookup"><span data-stu-id="e89a4-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![Captura de tela da configuração de descoberta para equipes privadas existentes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="e89a4-136">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e89a4-136">Using PowerShell</span></span>

<span data-ttu-id="e89a4-137">Use o cmdlet **[set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** para desativar ou ativar a configuração de descoberta para uma equipe privada existente.</span><span class="sxs-lookup"><span data-stu-id="e89a4-137">Use the **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="e89a4-138">Veja um exemplo de como deixar uma equipe detectável:</span><span class="sxs-lookup"><span data-stu-id="e89a4-138">Here's an example of how to make a team discoverable:</span></span>
```
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
```
<span data-ttu-id="e89a4-139">Você pode usar esse cmdlet em um script para definir a configuração de descoberta de equipes particulares existentes em massa.</span><span class="sxs-lookup"><span data-stu-id="e89a4-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="e89a4-140">Definir se os usuários podem descobrir equipes privadas</span><span class="sxs-lookup"><span data-stu-id="e89a4-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="e89a4-141">Como administrador, você também pode controlar quais usuários em sua organização podem descobrir equipes particulares nos resultados da pesquisa e sugestões no Teams.</span><span class="sxs-lookup"><span data-stu-id="e89a4-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="e89a4-142">Crie uma política usando o cmdlet **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** e, em seguida, atribua a política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="e89a4-142">Create a policy by using the **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="e89a4-143">Defina o parâmetro **AllowPrivateTeamDiscovery** como **true** para permitir aos usuários que a política sejam atribuídas a Confira equipes particulares detectáveis nos resultados da pesquisa e sugestões.</span><span class="sxs-lookup"><span data-stu-id="e89a4-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="e89a4-144">Definir o parâmetro **AllowPrivateTeamDiscovery** como **false** remove todas as equipes particulares detectáveis dos resultados da pesquisa e sugestões para os usuários atribuídos à política.</span><span class="sxs-lookup"><span data-stu-id="e89a4-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="e89a4-145">Por padrão, **AllowPrivateTeamDiscovery** é definido como **verdadeiro** para todos os usuários de uma organização.</span><span class="sxs-lookup"><span data-stu-id="e89a4-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="e89a4-146">Neste exemplo, criamos uma política denominada VendorPolicy que impede os usuários de descobrir qualquer equipe particular que seja tornada detectável e, em seguida, atribuímos a política a um usuário chamado vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="e89a4-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span>
```
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> <span data-ttu-id="e89a4-147">As equipes privadas não detectáveis nunca são mostradas em resultados e sugestões de pesquisa, independentemente da configuração de política.</span><span class="sxs-lookup"><span data-stu-id="e89a4-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="e89a4-148">Por exemplo, se você desativar a configuração de descoberta para uma equipe particular, os usuários não conseguirão descobrir a equipe, mesmo que o parâmetro **AllowPrivateTeamDiscovery** esteja definido como **true** na configuração de política para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="e89a4-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e89a4-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e89a4-149">Related topics</span></span>
- [<span data-ttu-id="e89a4-150">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="e89a4-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)