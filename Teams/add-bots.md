---
title: Adicionar bots para bate-papos privados e canais no Microsoft Teams | Suporte da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como adicionar bots no Microsoft Teams para bate-papos privados e canais, criar bots personalizados e carregue seu próprio bot para bate-papo privado."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: b1473a621f9f40ef3220546988db0635721acb7c
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="79a25-103">Adicionar bots para bate-papos privados e canais no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79a25-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="79a25-104">Os bots são programas automatizados configurados para responder a questões ou fornecer atualizações ou notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados.</span><span class="sxs-lookup"><span data-stu-id="79a25-104">Bots are automated programs that are set up to respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="79a25-105">Os Bots permitem que os usuários interajam com serviços em nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de conversas de bate-papo no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79a25-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="79a25-106">Os bots do Microsoft Teams são construídos no [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) e os bots que são desenvolvidos usando essa estrutura podem ser ativados facilmente para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79a25-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370) and the bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span>

<span data-ttu-id="79a25-107">No momento, o Microsoft Teams suporta bots em bate-papos privados e canais dentro de uma equipe.</span><span class="sxs-lookup"><span data-stu-id="79a25-107">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="79a25-108">Os administradores podem controlar se o uso de bots é permitido ou proibido dentro do locatário do Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="79a25-108">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="79a25-109">Os bots desenvolvidos e disponibilizados pela comunidade podem ser aproveitados no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79a25-109">Bots developed by the community and are made available, can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="79a25-110">A funcionalidade do bot e o carregamento lateral do bot devem ser ativados em nível de locatário para que os bots personalizados sejam funcionais.</span><span class="sxs-lookup"><span data-stu-id="79a25-110">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="79a25-111">Os bots podem ser usados em bate-papos privados ou em canais.</span><span class="sxs-lookup"><span data-stu-id="79a25-111">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="79a25-112">Para os canais, proprietários e membros de equipes podem adicionar bots.</span><span class="sxs-lookup"><span data-stu-id="79a25-112">For channels, team owners or members can add bots.</span></span>

<a name="add-bots-for-private-chat-and-channels"></a><span data-ttu-id="79a25-113">Adicionar bots para bate-papos privados e canais</span><span class="sxs-lookup"><span data-stu-id="79a25-113">Add bots for Private Chat and channels</span></span>
--------------------------------------

<span data-ttu-id="79a25-114">Existem duas formas de integrar um bot em bate-papos privados e canais:</span><span class="sxs-lookup"><span data-stu-id="79a25-114">There are two ways to integrate a bot for private chats and channels:</span></span>

1.  <span data-ttu-id="79a25-115">Instalar bots disponíveis publicamente para **bate-papos privados** ou **canais**.</span><span class="sxs-lookup"><span data-stu-id="79a25-115">Install publicly available bots for **private chat** or **channels**.</span></span> <span data-ttu-id="79a25-116">(Essa é a primeira opção.)</span><span class="sxs-lookup"><span data-stu-id="79a25-116">(This is the first option.)</span></span>

2.  <span data-ttu-id="79a25-117">Como alternativa, para encontrar bots, navegue até **Bate-papo**, pesquise por um **contato** e clique em **Descobrir aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="79a25-117">Alternatively, to find bots, navigate to **Chat**, search for a **contact,** and click **Discover apps.**</span></span>

![Captura de tela da janela de Pesquisa com aplicativos de Descoberta mostrados como resultado da pesquisa.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="79a25-119">Selecione com qual **Bot** você deseja ter uma conversa, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="79a25-119">Select which **Bot** you want to have a conversation with, as shown below.</span></span>

![Captura de tela da janela dos aplicativos de Descoberta com a guia Bots selecionada.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image2.png)

4.  <span data-ttu-id="79a25-121">Depois de escolher, dê **permissões** ao bot e selecione se deseja usar **bots em um bate-papo privado** ou selecione uma **Equipe** para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="79a25-121">Once selected, provide the bot **permissions,** and select whether you want to use **bots in a private chat** or select a **Team** to use it in.</span></span>

![Captura de tela da página do aplicativo AzureBot.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image3.png)

5.  <span data-ttu-id="79a25-123">Como alternativa, para usar um bot dentro do canal de uma equipe, basta clicar em **Visualizar equipe e bots**.</span><span class="sxs-lookup"><span data-stu-id="79a25-123">Alternatively, to use a bot within a channel of a team, simply click **View Team and Bots**.</span></span> <span data-ttu-id="79a25-124">Aqui, você pode descobrir mais bots.</span><span class="sxs-lookup"><span data-stu-id="79a25-124">Here you can Discover additional bots.</span></span>

6.  <span data-ttu-id="79a25-125">Um bot pode ser removido da equipe a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="79a25-125">At any time, a bot can be removed from the team.</span></span> <span data-ttu-id="79a25-126">Basta clicar em **Visualizar equipe e bots** para ver todos os bots, e então **remover** o que desejar.</span><span class="sxs-lookup"><span data-stu-id="79a25-126">Simply click **View Team and Bots,** to see all bots and then **remove** the one you’d like.</span></span>

![Captura de tela da guia Bots com a descrição do AzureBot exibida.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image4.png)

<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="79a25-128">Criar bots personalizados para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79a25-128">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="79a25-129">Você pode facilmente criar um bot que se integre nos seus aplicativos LOB usando o Microsoft Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="79a25-129">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="79a25-130">Consulte a orientação de [Criar e testar um bot para o Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber como você pode desenvolver e publicar seus próprios bots.</span><span class="sxs-lookup"><span data-stu-id="79a25-130">Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="79a25-131">Quando você cria um bot e o registra com o Bot Framework, você pode optar por publicá-lo ou não.</span><span class="sxs-lookup"><span data-stu-id="79a25-131">When you create a bot and register it with the Bot Framework, you can choose to publish it or not.</span></span> <span data-ttu-id="79a25-132">Se você não o publicar, o bot permanecerá privado.</span><span class="sxs-lookup"><span data-stu-id="79a25-132">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="79a25-133">Você também pode exigir que seus usuários façam login antes de usar o bot.</span><span class="sxs-lookup"><span data-stu-id="79a25-133">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="79a25-134">A exigência de login assegura que apenas os funcionários da sua organização possam acessar o bot, mesmo que o ID do aplicativo do bot se torne conhecido.</span><span class="sxs-lookup"><span data-stu-id="79a25-134">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="79a25-135">Veja [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) no GitHub para ver um exemplo de código de como autenticar os usuários no seu diretório ativo usando bots.</span><span class="sxs-lookup"><span data-stu-id="79a25-135">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="79a25-136">Os bots podem ser testados usando o [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) antes que sejam implantados no seu Teams.</span><span class="sxs-lookup"><span data-stu-id="79a25-136">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="79a25-137">Carregue o seu próprio bot para bate-papos privados</span><span class="sxs-lookup"><span data-stu-id="79a25-137">Side load your own bot for private chat</span></span>
---------------------------------------

1.  <span data-ttu-id="79a25-138">Depois de criar seu bot, navegue até a página do **Painel do Bot** [](https://go.microsoft.com/fwlink/?linkid=854374) para o bot que você desenvolveu e, em **Detalhes**, copie o **ID do aplicativo da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="79a25-138">Once you have created your Bot, navigate to the **Bot Dashboard** [page](https://go.microsoft.com/fwlink/?linkid=854374) for the bot you developed, and under **Details**, copy the **Microsoft App ID**.</span></span>

![Captura de tela da página de detalhes de um bot com o ID do aplicativo da Microsoft destacado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="79a25-140">No Microsoft Teams, no painel de **Bate-papo**, selecione o **ícone Adicionar bate-papo**.</span><span class="sxs-lookup"><span data-stu-id="79a25-140">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="79a25-141">Em **Para:,** copie o **ID do aplicativo da Microsoft** do seu bot.</span><span class="sxs-lookup"><span data-stu-id="79a25-141">For **To:,** paste your bot's **Microsoft app ID**.</span></span>

![Captura de tela de um painel de bate-papo com o ícone de Adicionar bate-papo e a linha Para com o ID do aplicativo da Microsoft destacado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="79a25-143">O ID do aplicativo determina o **nome do bot,** e então você poderá iniciar uma conversa de bate-papo com esse bot.</span><span class="sxs-lookup"><span data-stu-id="79a25-143">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
