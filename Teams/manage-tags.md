---
title: Gerenciar marcas no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
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
description: Saiba como gerenciar como as marcas são usadas em sua organização no Microsoft Teams.
ms.openlocfilehash: 5da1d1549e6171656b0065036819be0fac450759
ms.sourcegitcommit: 494e5956619084ff8f0a4f42efb5081c4530488a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2020
ms.locfileid: "42551038"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="dce50-103">Gerenciar marcas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dce50-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="dce50-104">Ainda não consegue ver esse recurso no centro de administração do Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="dce50-104">Don't see this feature in the Microsoft Teams admin center yet?</span></span> <span data-ttu-id="dce50-105">Ele está sendo implantado e talvez ainda não esteja disponível em sua organização.</span><span class="sxs-lookup"><span data-stu-id="dce50-105">It's currently being rolled out and might not be available in your organization yet.</span></span> <span data-ttu-id="dce50-106">Para manter-se atualizado sobre os recursos futuros do Teams, consulte o [mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span><span class="sxs-lookup"><span data-stu-id="dce50-106">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

<span data-ttu-id="dce50-107">As marcas no Microsoft Teams permitem que os usuários se comuniquem com um subconjunto de pessoas de uma equipe.</span><span class="sxs-lookup"><span data-stu-id="dce50-107">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="dce50-108">As marcas podem ser adicionadas a um ou vários membros da equipe para que você se conecte facilmente com o subconjunto correto de pessoas.</span><span class="sxs-lookup"><span data-stu-id="dce50-108">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="dce50-109">Os proprietários e membros da equipe (se o recurso estiver habilitado para eles) podem adicionar uma ou mais marcas a uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="dce50-109">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="dce50-110">As marcas podem ser usadas em @mentions por qualquer pessoa na equipe em uma postagem de canal ou para iniciar uma conversa apenas com as pessoas que receberam essa marca.</span><span class="sxs-lookup"><span data-stu-id="dce50-110">The tags can then be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="dce50-111">Marcas ainda não são suportadas em canais privados.</span><span class="sxs-lookup"><span data-stu-id="dce50-111">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="dce50-112">Como as marcas funcionam</span><span class="sxs-lookup"><span data-stu-id="dce50-112">How tags work</span></span>

<span data-ttu-id="dce50-113">Uma marca pode ser adicionada a uma pessoa em uma equipe específica.</span><span class="sxs-lookup"><span data-stu-id="dce50-113">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="dce50-114">Depois que uma marca é adicionada, ela pode ser usada em @mentions em um chat ou em qualquer canal padrão da equipe.</span><span class="sxs-lookup"><span data-stu-id="dce50-114">After a tag is added, it can be used in @mentions in a chat or in any standard channel of the team.</span></span> <span data-ttu-id="dce50-115">Veja a seguir alguns exemplos de como as marcas podem ser usadas no Teams:</span><span class="sxs-lookup"><span data-stu-id="dce50-115">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="dce50-116">Um gerente de loja quer postar um comunicado para um canal e notificar todos os caixas.</span><span class="sxs-lookup"><span data-stu-id="dce50-116">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="dce50-117">Um gerente de produto de grupo quer enviar mensagens para todos os gerentes de produto em um canal.</span><span class="sxs-lookup"><span data-stu-id="dce50-117">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="dce50-118">Um administrador hospitalar quer enviar uma mensagem para todos os radiologists de um canal.</span><span class="sxs-lookup"><span data-stu-id="dce50-118">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="dce50-119">Um gerente de marketing deseja iniciar um chat em grupo com todos os designers.</span><span class="sxs-lookup"><span data-stu-id="dce50-119">A marketing manager wants to start a group chat with all designers.</span></span> 

<span data-ttu-id="dce50-120">Para saber mais, confira [usando marcas no Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span><span class="sxs-lookup"><span data-stu-id="dce50-120">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="dce50-121">Gerenciar marcas para a sua organização</span><span class="sxs-lookup"><span data-stu-id="dce50-121">Manage tags for your organization</span></span>

<span data-ttu-id="dce50-122">Como administrador, você pode controlar quem pode adicionar marcas e como as marcas são usadas em toda a organização no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dce50-122">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Captura de tela das configurações de marcação no centro de administração do Microsoft Teams](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="dce50-124">Definir quem pode adicionar marcas</span><span class="sxs-lookup"><span data-stu-id="dce50-124">Set who can add tags</span></span>

<span data-ttu-id="dce50-125">Por padrão, os proprietários da equipe podem adicionar marcas.</span><span class="sxs-lookup"><span data-stu-id="dce50-125">By default, team owners can add tags.</span></span> <span data-ttu-id="dce50-126">Você pode alterar essa configuração para permitir que os proprietários da equipe e os membros da equipe adicionem marcas ou você pode desativar as marcas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="dce50-126">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="dce50-127">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em configurações da > **equipe**de **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="dce50-127">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="dce50-128">Em **marcação**, ao lado de **marcação está habilitado para**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="dce50-128">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="dce50-129">**Proprietários e membros da equipe**: permitir que proprietários e membros da equipe adicionem marcas.</span><span class="sxs-lookup"><span data-stu-id="dce50-129">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="dce50-130">**Proprietários da equipe**: permitir que os proprietários de equipe adicionem marcas.</span><span class="sxs-lookup"><span data-stu-id="dce50-130">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="dce50-131">**Disabled**: desativar marcas.</span><span class="sxs-lookup"><span data-stu-id="dce50-131">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="dce50-132">Definir configurações de marcas</span><span class="sxs-lookup"><span data-stu-id="dce50-132">Configure tags settings</span></span>

<span data-ttu-id="dce50-133">Você pode definir as seguintes configurações de marcas para controlar a forma como as marcas são usadas em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="dce50-133">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="dce50-134">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em configurações da > **equipe**de **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="dce50-134">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="dce50-135">Em **marcação**, defina o seguinte, dependendo das necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="dce50-135">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="dce50-136">O **proprietário da equipe pode substituir quem pode aplicar as marcas**: quando está ativado, os proprietários da equipe podem permitir ou impedir que os membros adicionem marcas nas configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="dce50-136">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="dce50-137">**Os membros podem adicionar marcas adicionais**: se você permitir que os membros da equipe adicionem marcas, ative essa opção para permitir que os membros da equipe adicionem marcas diferentes das marcas padrão sugeridas que você definiu.</span><span class="sxs-lookup"><span data-stu-id="dce50-137">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="dce50-138">Se estiver desativado, os membros da equipe só poderão usar as marcas padrão.</span><span class="sxs-lookup"><span data-stu-id="dce50-138">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="dce50-139">**Marcas padrão sugeridas**: Use isto para adicionar um conjunto de marcas padrão.</span><span class="sxs-lookup"><span data-stu-id="dce50-139">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="dce50-140">Você pode adicionar até 25 marcas e cada marca pode conter no máximo 25 caracteres.</span><span class="sxs-lookup"><span data-stu-id="dce50-140">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="dce50-141">Os proprietários e membros da equipe (se o recurso estiver habilitado para eles) podem usar essas sugestões, adicionar a eles ou criar um novo conjunto de marcas.</span><span class="sxs-lookup"><span data-stu-id="dce50-141">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="dce50-142">Gerenciar as configurações de marcas para uma equipe</span><span class="sxs-lookup"><span data-stu-id="dce50-142">Manage tags settings for a team</span></span>

<span data-ttu-id="dce50-143">Se você ativou o **proprietário da equipe pode substituir quem pode aplicar marcas** no centro de administração do Microsoft Teams, os proprietários da equipe podem definir se os membros podem adicionar marcas no nível da equipe.</span><span class="sxs-lookup"><span data-stu-id="dce50-143">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="dce50-144">Para fazer isso, na guia **configurações** de uma equipe, vá até **marcas**e escolha quem pode adicionar marcas.</span><span class="sxs-lookup"><span data-stu-id="dce50-144">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![Captura de tela da configuração marcas no nível da equipe](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="dce50-146">Adicionar marcas no Teams</span><span class="sxs-lookup"><span data-stu-id="dce50-146">Add tags in Teams</span></span>

<span data-ttu-id="dce50-147">No Teams, a guia **Membros** da página Gerenciar equipe de uma equipe inclui uma coluna **marcas** .</span><span class="sxs-lookup"><span data-stu-id="dce50-147">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="dce50-148">Proprietários e membros da equipe (se o recurso estiver habilitado para eles) podem clicar em **gerenciar marcas** ao lado de um membro para ver a lista de marcas sugeridas para esse membro e adicionar marcas à lista.</span><span class="sxs-lookup"><span data-stu-id="dce50-148">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="dce50-149">Captura de tela de como aplicar marcas no cliente do teams</span><span class="sxs-lookup"><span data-stu-id="dce50-149">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
