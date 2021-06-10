---
title: Configurar e gerenciar a moderação do canal
author: cichur
ms.author: v-cichur
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
description: Saiba como configurar canais para moderação em Microsoft Teams, incluindo como adicionar membros da equipe como moderadores de canal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 81e5159cf0e64a4c5b88afea51de528c299daf80
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948637"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="f1431-103">Configurar e gerenciar a moderação de canal Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1431-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="f1431-104">Em Microsoft Teams, os proprietários de equipe podem ativar a moderação para um canal padrão para controlar quem pode iniciar novas postagens e responder a postagens nesse canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="f1431-105">Os proprietários da equipe também podem adicionar membros da equipe como moderadores.</span><span class="sxs-lookup"><span data-stu-id="f1431-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="f1431-106">Um proprietário de equipe pode não ter a experiência do assunto no nível do canal para melhor suportar a moderação do canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="f1431-107">Ao permitir que membros específicos da equipe moderam um canal, a responsabilidade de gerenciar conteúdo e contexto em um canal é compartilhada entre proprietários de equipe e moderadores de canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="f1431-108">Por exemplo, um proprietário de equipe pode adicionar proprietários de negócios ou proprietários de conteúdo como moderadores, o que permite controlar o compartilhamento de informações nesse canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="f1431-109">A moderação de canal está disponível para canais padrão.</span><span class="sxs-lookup"><span data-stu-id="f1431-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="f1431-110">Não está disponível para o canal geral ou para canais privados.</span><span class="sxs-lookup"><span data-stu-id="f1431-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="f1431-111">O que um moderador de canal pode fazer?</span><span class="sxs-lookup"><span data-stu-id="f1431-111">What can a channel moderator do?</span></span>

<span data-ttu-id="f1431-112">Os moderadores de canal podem:</span><span class="sxs-lookup"><span data-stu-id="f1431-112">Channel moderators can:</span></span>

- <span data-ttu-id="f1431-113">Inicie novas postagens no canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-113">Start new posts in the channel.</span></span> <span data-ttu-id="f1431-114">Quando a moderação é ativas para um canal, somente os moderadores podem iniciar novas postagens nesse canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="f1431-115">Adicione e remova os membros da equipe como moderadores a um canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="f1431-116">Lembre-se de que, por padrão, os proprietários de equipe são moderadores de canal e não podem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="f1431-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="f1431-117">Controle se os membros da equipe podem responder a mensagens de canal existentes e se bots e conectores podem enviar mensagens de canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="f1431-118">Cenários</span><span class="sxs-lookup"><span data-stu-id="f1431-118">Scenarios</span></span>

<span data-ttu-id="f1431-119">Aqui estão alguns exemplos de como sua organização pode usar a moderação de canal Teams.</span><span class="sxs-lookup"><span data-stu-id="f1431-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="f1431-120">Usar um canal como canal de anúncio</span><span class="sxs-lookup"><span data-stu-id="f1431-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="f1431-121">A equipe de Marketing usa um canal específico para compartilhar os principais comunicados e entregas do projeto.</span><span class="sxs-lookup"><span data-stu-id="f1431-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="f1431-122">Às vezes, os membros da equipe postam conteúdo no canal que pertence mais adequadamente a outros canais.</span><span class="sxs-lookup"><span data-stu-id="f1431-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="f1431-123">O proprietário da equipe deseja restringir o compartilhamento de informações no canal apenas para anúncios para que os membros da equipe possam usar esse canal para se manterem atentos ao que é importante.</span><span class="sxs-lookup"><span data-stu-id="f1431-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="f1431-124">Nesse cenário, o proprietário da equipe adiciona leads de Marketing como moderadores para que eles possam postar anúncios no canal e desligar a capacidade de os membros da equipe responderem às mensagens nesse canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="f1431-125">Usar um canal para discussões de classe no Teams education</span><span class="sxs-lookup"><span data-stu-id="f1431-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="f1431-126">No Teams educação, um professor de ciências deseja usar um canal para envolver os alunos em discussões focadas em tópicos específicos da sala de aula.</span><span class="sxs-lookup"><span data-stu-id="f1431-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="f1431-127">Nesse cenário, o professor permite que seus assistentes de ensino moderam o canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="f1431-128">Os assistentes de ensino podem criar novas postagens para iniciar e conduzir discussões com os alunos.</span><span class="sxs-lookup"><span data-stu-id="f1431-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="f1431-129">Gerenciar moderação de canal</span><span class="sxs-lookup"><span data-stu-id="f1431-129">Manage channel moderation</span></span>

<span data-ttu-id="f1431-130">Em Teams, vá para o canal, clique em **Mais opções...**  >  **Gerenciar canal**.</span><span class="sxs-lookup"><span data-stu-id="f1431-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="f1431-131">A partir daqui, você pode ativar e desativar a moderação, adicionar membros da equipe como moderadores e definir preferências.</span><span class="sxs-lookup"><span data-stu-id="f1431-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="f1431-132">Moderação de canal é uma configuração por canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="f1431-133">Não há configuração no nível de locatário para moderação de canal.</span><span class="sxs-lookup"><span data-stu-id="f1431-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="f1431-134">Se quiser que adicionemos uma configuração de moderação de canal no nível de locatário, solicite-a [Teams UserVoice](https://microsoftteams.uservoice.com/).</span><span class="sxs-lookup"><span data-stu-id="f1431-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![preferências para managing-channel-moderation-in-teams](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="f1431-136">Ativar ou desativar a moderação de um canal</span><span class="sxs-lookup"><span data-stu-id="f1431-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="f1431-137">Por padrão, a moderação está desligada, o que significa que as configurações de canal usuais se aplicam aos proprietários da equipe e aos membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="f1431-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="f1431-138">Por exemplo, você pode restringir novas postagens apenas para membros da equipe ou permitir que todos, incluindo convidados, iniciem novas postagens.</span><span class="sxs-lookup"><span data-stu-id="f1431-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="f1431-139">Para ativar a moderação de um canal, em **Moderação de Canal,** **clique** em .</span><span class="sxs-lookup"><span data-stu-id="f1431-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="f1431-140">Quando a moderação do canal está em, somente moderadores podem iniciar novas postagens.</span><span class="sxs-lookup"><span data-stu-id="f1431-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="f1431-141">Adicionar ou remover moderadores de canal</span><span class="sxs-lookup"><span data-stu-id="f1431-141">Add or remove channel moderators</span></span>

<span data-ttu-id="f1431-142">Em **Who os moderadores?**, clique em **Gerenciar** e, em seguida, adicionar ou remover membros da equipe como moderadores.</span><span class="sxs-lookup"><span data-stu-id="f1431-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="f1431-143">Os proprietários e moderadores de equipe podem adicionar e remover outros moderadores.</span><span class="sxs-lookup"><span data-stu-id="f1431-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="f1431-144">Definir permissões de membro da equipe</span><span class="sxs-lookup"><span data-stu-id="f1431-144">Set team member permissions</span></span>

<span data-ttu-id="f1431-145">Em **Permissões de membro da equipe,** selecione as caixas de seleção ao lado das atividades que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="f1431-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f1431-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f1431-146">Related topics</span></span>

- [<span data-ttu-id="f1431-147">Visão geral de equipes e canais no Teams</span><span class="sxs-lookup"><span data-stu-id="f1431-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
