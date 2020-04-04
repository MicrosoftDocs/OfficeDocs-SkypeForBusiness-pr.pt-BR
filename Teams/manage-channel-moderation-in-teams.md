---
title: Configurar e gerenciar a moderação do canal
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como configurar os canais para moderação no Microsoft Teams, incluindo como adicionar membros da equipe como moderadores do canal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 128676bbe4ec27300013836425bf221e3de10f9b
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136801"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="b9c91-103">Configurar e gerenciar a moderação do canal no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9c91-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="b9c91-104">No Microsoft Teams, os proprietários da equipe podem ativar a moderação de um canal para controlar quem pode iniciar novas postagens e responder a postagens nesse canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-104">In Microsoft Teams, team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="b9c91-105">Os proprietários da equipe também podem adicionar membros da equipe como moderadores.</span><span class="sxs-lookup"><span data-stu-id="b9c91-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="b9c91-106">Um proprietário de equipe pode não ter o conhecimento do assunto no nível do canal para dar um melhor suporte à moderação do canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="b9c91-107">Ao permitir que os membros específicos da equipe sejam moderados para um canal, a responsabilidade de gerenciar conteúdo e contexto dentro de um canal é compartilhada entre os proprietários da equipe e os moderadores do canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="b9c91-108">Por exemplo, um proprietário de equipe pode adicionar donos de empresas ou proprietários de conteúdo como moderadores, o que permite que eles controlem o compartilhamento de informações nesse canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="b9c91-109">O que um moderador de canal pode fazer?</span><span class="sxs-lookup"><span data-stu-id="b9c91-109">What can a channel moderator do?</span></span>

<span data-ttu-id="b9c91-110">Os moderadores do canal podem:</span><span class="sxs-lookup"><span data-stu-id="b9c91-110">Channel moderators can:</span></span>

- <span data-ttu-id="b9c91-111">Inicie novas postagens no canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-111">Start new posts in the channel.</span></span> <span data-ttu-id="b9c91-112">Quando a moderação está ativada para um canal, somente moderadores podem iniciar novas postagens nesse canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-112">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="b9c91-113">Adicionar e remover membros da equipe como moderadores em um canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-113">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="b9c91-114">Lembre-se de que, por padrão, os proprietários da equipe são Moderadores do canal e não podem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="b9c91-114">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="b9c91-115">Controle se os membros da equipe podem responder às mensagens de canal existentes e se os bots e conectores podem enviar mensagens de canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-115">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="b9c91-116">Cenários</span><span class="sxs-lookup"><span data-stu-id="b9c91-116">Scenarios</span></span>

<span data-ttu-id="b9c91-117">Veja a seguir alguns exemplos de como a sua organização pode usar a moderação de canal no Teams.</span><span class="sxs-lookup"><span data-stu-id="b9c91-117">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="b9c91-118">Usar um canal como um canal de anúncio</span><span class="sxs-lookup"><span data-stu-id="b9c91-118">Use a channel as an announcement channel</span></span>

<span data-ttu-id="b9c91-119">A equipe de marketing usa um canal específico para compartilhar anúncios e resultados importantes do projeto.</span><span class="sxs-lookup"><span data-stu-id="b9c91-119">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="b9c91-120">Às vezes, os membros da equipe lançam conteúdo para o canal que mais apropriadamente pertence a outros canais.</span><span class="sxs-lookup"><span data-stu-id="b9c91-120">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="b9c91-121">O proprietário da equipe deseja restringir o compartilhamento de informações no canal para apenas anúncios, para que os membros da equipe possam usar esse canal para manter-se a par do que é importante.</span><span class="sxs-lookup"><span data-stu-id="b9c91-121">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="b9c91-122">Nesse cenário, o proprietário da equipe adiciona marketing lidera como moderadores para que possam postar comunicados no canal e desativar a capacidade dos membros da equipe de responder às mensagens nesse canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-122">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="b9c91-123">Usar um canal para discussões de classe no Teams for Education</span><span class="sxs-lookup"><span data-stu-id="b9c91-123">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="b9c91-124">No Teams for Education, um professor de ciência deseja usar um canal para envolver os alunos em discussões enfocadas em tópicos específicos da sala de aula.</span><span class="sxs-lookup"><span data-stu-id="b9c91-124">In Teams for Education, a science teacher want to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="b9c91-125">Nesse cenário, o professor permite que seus assistentes de ensino moderam o canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-125">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="b9c91-126">Os assistentes de ensino podem criar novas postagens para iniciar e conduzir discussões com os alunos.</span><span class="sxs-lookup"><span data-stu-id="b9c91-126">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="b9c91-127">Gerenciar a moderação do canal</span><span class="sxs-lookup"><span data-stu-id="b9c91-127">Manage channel moderation</span></span>

<span data-ttu-id="b9c91-128">No Teams, vá para o canal, clique em **mais opções...**  >  **Gerenciar canal**.</span><span class="sxs-lookup"><span data-stu-id="b9c91-128">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="b9c91-129">Aqui você pode ativar e desativar a moderação, adicionar membros da equipe como moderadores e definir preferências.</span><span class="sxs-lookup"><span data-stu-id="b9c91-129">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="b9c91-130">A moderação do canal é uma configuração por canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-130">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="b9c91-131">Não há nenhuma configuração em nível de locatário para a moderação do canal.</span><span class="sxs-lookup"><span data-stu-id="b9c91-131">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="b9c91-132">Se você quiser adicionar uma configuração de moderação de canal no nível do locatário, solicite o [UserVoice do teams](https://microsoftteams.uservoice.com/).</span><span class="sxs-lookup"><span data-stu-id="b9c91-132">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![Manage-Channel-Moderation-in-Teams-Preferences. png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="b9c91-134">Ativar ou desativar a moderação de um canal</span><span class="sxs-lookup"><span data-stu-id="b9c91-134">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="b9c91-135">Por padrão, a moderação está desativada, o que significa que as configurações de canal usuais se aplicam a proprietários de equipe e membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="b9c91-135">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="b9c91-136">Por exemplo, você pode restringir novas postagens somente a membros da equipe ou permitir que todos, incluindo convidados, iniciem novas postagens.</span><span class="sxs-lookup"><span data-stu-id="b9c91-136">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="b9c91-137">Para ativar a moderação de um canal, em **moderação do canal**, clique **em ativado**.</span><span class="sxs-lookup"><span data-stu-id="b9c91-137">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="b9c91-138">Quando a moderação do canal está ativada, somente moderadores podem iniciar novas postagens.</span><span class="sxs-lookup"><span data-stu-id="b9c91-138">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="b9c91-139">Adicionar ou remover moderadores de canal</span><span class="sxs-lookup"><span data-stu-id="b9c91-139">Add or remove channel moderators</span></span>

<span data-ttu-id="b9c91-140">Em **quem são os moderadores?**, clique em **gerenciar**e, em seguida, adicione ou remova os membros da equipe como moderadores.</span><span class="sxs-lookup"><span data-stu-id="b9c91-140">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="b9c91-141">Os moderadores e proprietários da equipe podem adicionar e remover outros moderadores.</span><span class="sxs-lookup"><span data-stu-id="b9c91-141">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="b9c91-142">Definir permissões de membros da equipe</span><span class="sxs-lookup"><span data-stu-id="b9c91-142">Set team member permissions</span></span>

<span data-ttu-id="b9c91-143">Em **permissões de membro da equipe**, marque as caixas de seleção ao lado das atividades que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="b9c91-143">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9c91-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b9c91-144">Related topics</span></span>

- [<span data-ttu-id="b9c91-145">Visão geral de equipes e canais no Teams</span><span class="sxs-lookup"><span data-stu-id="b9c91-145">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
