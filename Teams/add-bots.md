---
title: Adicionar bots para bate-papos privados e canais no Microsoft Teams
author: LolaJacobsen, DamienDoumer
ms.author: lolaj, Damien
manager: serdars
ms.date: 12/05/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras
description: Saiba como adicionar bots no Microsoft Teams para bate-papos privados e canais, criar bots personalizados e carregue seu próprio bot para bate-papo privado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a4e921ea668fc59b520fdb068355db82bfe24481
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298520"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="5db95-103">Adicionar bots para bate-papos privados e canais no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5db95-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="5db95-104">Os bots são programas automatizados que respondem a consultas ou fornecem atualizações e notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados.</span><span class="sxs-lookup"><span data-stu-id="5db95-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="5db95-105">Os Bots permitem que os usuários interajam com serviços em nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de conversas de bate-papo no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5db95-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="5db95-106">Os bots do Microsoft Teams são baseados no [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span><span class="sxs-lookup"><span data-stu-id="5db95-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="5db95-107">Os bots desenvolvidos usando essa estrutura podem ser facilmente habilitados para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5db95-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="5db95-108">Para saber mais, confira [Gerenciar configurações do Microsoft Teams para sua organização](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="5db95-108">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="5db95-109">No momento, o Microsoft Teams suporta bots em bate-papos privados e canais dentro de uma equipe.</span><span class="sxs-lookup"><span data-stu-id="5db95-109">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="5db95-110">Os administradores podem controlar se o uso de bots é permitido ou proibido dentro do locatário do Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="5db95-110">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="5db95-111">Os bots desenvolvidos pela comunidade podem ser utilizados no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5db95-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="5db95-112">A funcionalidade do bot e o carregamento lateral do bot devem ser ativados em nível de locatário para que os bots personalizados sejam funcionais.</span><span class="sxs-lookup"><span data-stu-id="5db95-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="5db95-113">Os bots podem ser usados em bate-papos privados ou em canais.</span><span class="sxs-lookup"><span data-stu-id="5db95-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="5db95-114">Para os canais, proprietários e membros de equipes podem adicionar bots.</span><span class="sxs-lookup"><span data-stu-id="5db95-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="5db95-115">Para obter mais informações, consulte a seção "Usando bots" em [Aplicativos e serviços](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span><span class="sxs-lookup"><span data-stu-id="5db95-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="5db95-116">Criar bots personalizados para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5db95-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="5db95-117">Você pode facilmente criar um bot que se integre nos seus aplicativos LOB usando o Microsoft Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="5db95-117">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="5db95-118">Consulte a orientação de [Criar e testar um bot para o Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber como você pode desenvolver e publicar seus próprios bots.</span><span class="sxs-lookup"><span data-stu-id="5db95-118">Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="5db95-119">Quando você cria um bot e o registra com o Bot Framework, pode optar por publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="5db95-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="5db95-120">Se você não o publicar, o bot permanecerá privado.</span><span class="sxs-lookup"><span data-stu-id="5db95-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="5db95-121">Você também pode exigir que seus usuários façam login antes de usar o bot.</span><span class="sxs-lookup"><span data-stu-id="5db95-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="5db95-122">A exigência de login assegura que apenas os funcionários da sua organização possam acessar o bot, mesmo que o ID do aplicativo do bot se torne conhecido.</span><span class="sxs-lookup"><span data-stu-id="5db95-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="5db95-123">Veja [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) no GitHub para ver um exemplo de código de como autenticar os usuários no seu diretório ativo usando bots.</span><span class="sxs-lookup"><span data-stu-id="5db95-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="5db95-124">Os bots podem ser testados usando o [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) antes que sejam implantados no seu Teams.</span><span class="sxs-lookup"><span data-stu-id="5db95-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="5db95-125">Carregue o seu próprio bot para bate-papos privados</span><span class="sxs-lookup"><span data-stu-id="5db95-125">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="5db95-126">Depois de criar sua bot, vá para as **Configurações do aplicativo** para o bot que você desenvolvido, em seguida, em **configurações de aplicativo**, copie o valor da configuração **MicrosoftAppId** . ![Página de captura de tela das configurações de aplicativo para um bot com a ID de aplicativo Microsoft realçado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="5db95-126">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="5db95-127">No Microsoft Teams, no painel de **Bate-papo**, selecione o **ícone Adicionar bate-papo**.</span><span class="sxs-lookup"><span data-stu-id="5db95-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="5db95-128">Em **Para**, cole a **ID do Aplicativo da Microsoft** de seu bot.</span><span class="sxs-lookup"><span data-stu-id="5db95-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="5db95-129">![Captura de tela de um painel de chat com o ícone para Adicionar chat e a linha Para com a ID do Aplicativo da Microsoft destacada.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="5db95-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="5db95-130">O ID do aplicativo determina o **nome do bot,** e então você poderá iniciar uma conversa de bate-papo com esse bot.</span><span class="sxs-lookup"><span data-stu-id="5db95-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>

<a name="side-load-your-bot-for-channels"></a><span data-ttu-id="5db95-131">No lado do seu bot de canais de carga</span><span class="sxs-lookup"><span data-stu-id="5db95-131">Side load your bot for channels</span></span>
-----------------------------------

<span data-ttu-id="5db95-132">Se você deseja compartilhar seu bot com seus colegas, aqui está como adicioná-lo a canais de equipes diferentes:</span><span class="sxs-lookup"><span data-stu-id="5db95-132">If you want to share your bot with your colleagues, here's how to add it to channels of different teams:</span></span>

1. <span data-ttu-id="5db95-133">Após ter [criado um pacote de aplicativos para o seu bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), abra o equipes e navegue para a equipe nos quais você vai ser lado carregamento o bot.</span><span class="sxs-lookup"><span data-stu-id="5db95-133">After you have [created an app package for your bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), open Teams and browse to the team in which you'll be side-loading the bot.</span></span>
2. <span data-ttu-id="5db95-134">Adicione o **[Studio de aplicativo](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app às equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5db95-134">Add **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app to Microsoft Teams.</span></span>
3. <span data-ttu-id="5db95-135">No App Studio, selecione o **Editor de manifesto** na guia ![captura de tela do guia Editor de manifesto.](media/Adding_Bot_To_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="5db95-135">In App Studio, select the **Manifest Editor** Tab. ![Manifest Editor Tab Screenshot.](media/Adding_Bot_To_Teams.png)</span></span>
4. <span data-ttu-id="5db95-136">Para adicionar sua bot, em recursos, selecione bot e optar por adicionar um bot existente, então você terá a opção para escolher um bot existente de um depósito ou insira a Id de um dos seus bots existentes.</span><span class="sxs-lookup"><span data-stu-id="5db95-136">To add your bot, In capabilities, select bot and chose to add an existing bot, then you will have the option to chose an existing bot from a drop or enter the Id of one of your existing bots.</span></span>
<span data-ttu-id="5db95-137">![Selecione seu bot já criado.](media/Select_Existing_Bot.png)</span><span class="sxs-lookup"><span data-stu-id="5db95-137">![Select your bot you already created.](media/Select_Existing_Bot.png)</span></span>
5. <span data-ttu-id="5db95-138">Navegue até o local do seu pacote de aplicativos, selecioná-la e, em seguida, clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5db95-138">Browse to the location of your app package, select it, and then click **Open**.</span></span>
6. <span data-ttu-id="5db95-139">Selecione o nome do seu bot (não se esqueça de marcar a caixa de seleção "Equipe" na seção escopo)</span><span class="sxs-lookup"><span data-stu-id="5db95-139">Select your bot's name (Don't forget to check the "Team" checkbox under the scope section)</span></span>
7. <span data-ttu-id="5db95-140">Selecione o teste e distribua a opção.</span><span class="sxs-lookup"><span data-stu-id="5db95-140">Select the Test and distribute option.</span></span>
8. <span data-ttu-id="5db95-141">Selecione a equipe do qual você deseja se conectar seu bot na caixa de diálogo que é exibida.</span><span class="sxs-lookup"><span data-stu-id="5db95-141">Select the team where you wish to connect your bot to in the dialog which pops up.</span></span>

<span data-ttu-id="5db95-142">Com isso, o seu bot será disponíveis na equipe do Team seu Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5db95-142">With this, your bot will be available in your Microsoft Team's team.</span></span>
