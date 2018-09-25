---
title: Adicionar bots para bate-papos privados e canais no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: lucarras
description: Saiba como adicionar bots no Microsoft Teams para bate-papos privados e canais, criar bots personalizados e carregue seu próprio bot para bate-papo privado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ff6cf5af3a1a2129ee22ae0ff51ac4216ccaefe
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013357"
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a><span data-ttu-id="dd6cb-103">Adicionar bots para bate-papos privados e canais no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd6cb-103">Add bots for private chats and channels in Microsoft Teams</span></span>
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="dd6cb-104">Os bots são programas automatizados que respondem a consultas ou fornecem atualizações e notificações sobre detalhes que os usuários consideram interessantes ou sobre os quais desejam se manter informados.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-104">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="dd6cb-105">Os Bots permitem que os usuários interajam com serviços em nuvem, como gerenciamento de tarefas, agendamento e pesquisa através de conversas de bate-papo no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-105">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="dd6cb-106">Os bots do Microsoft Teams são baseados no [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span><span class="sxs-lookup"><span data-stu-id="dd6cb-106">Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://go.microsoft.com/fwlink/?linkid=854370).</span></span> <span data-ttu-id="dd6cb-107">Os bots desenvolvidos usando essa estrutura podem ser facilmente habilitados para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-107">The bots that are developed using this framework can be enabled easily for Microsoft Teams.</span></span> <span data-ttu-id="dd6cb-108">Para obter mais informações, consulte [os recursos de gerenciar equipes da Microsoft em sua organização do Office 365](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="dd6cb-108">For more information, see [Manage Microsoft Teams features in your Office 365 organization](enable-features-office-365.md).</span></span>

<span data-ttu-id="dd6cb-109">No momento, o Microsoft Teams suporta bots em bate-papos privados e canais dentro de uma equipe.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-109">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="dd6cb-110">Os administradores podem controlar se o uso de bots é permitido ou proibido dentro do locatário do Office 365.<span id="_T-Bot" class="anchor"></span></span><span class="sxs-lookup"><span data-stu-id="dd6cb-110">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.<span id="_T-Bot" class="anchor"></span></span></span>

<span data-ttu-id="dd6cb-111">Os bots desenvolvidos pela comunidade podem ser utilizados no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-111">Bots developed by the community can be leveraged within Microsoft Teams.</span></span> <span data-ttu-id="dd6cb-112">A funcionalidade do bot e o carregamento lateral do bot devem ser ativados em nível de locatário para que os bots personalizados sejam funcionais.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-112">The bot’s functionality and bot’s side loading must be enabled on the tenant level for custom bots to be functional.</span></span> <span data-ttu-id="dd6cb-113">Os bots podem ser usados em bate-papos privados ou em canais.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-113">Bots can be used in private chats or in channels.</span></span> <span data-ttu-id="dd6cb-114">Para os canais, proprietários e membros de equipes podem adicionar bots.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-114">For channels, team owners or members can add bots.</span></span>

<span data-ttu-id="dd6cb-115">Para obter mais informações, consulte a seção "Usando bots" em [Aplicativos e serviços](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span><span class="sxs-lookup"><span data-stu-id="dd6cb-115">For more information, see the section "Using bots" in [Apps and services](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).</span></span> 




<a name="create-custom-bots-for-microsoft-teams"></a><span data-ttu-id="dd6cb-116">Criar bots personalizados para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd6cb-116">Create custom bots for Microsoft Teams</span></span>
--------------------------------------

<span data-ttu-id="dd6cb-117">Você pode facilmente criar um bot que se integre nos seus aplicativos LOB usando o Microsoft Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-117">You can easily create a bot that integrates in to your LOB applications, using the Microsoft Bot Framework.</span></span> <span data-ttu-id="dd6cb-118">Consulte a orientação de [Criar e testar um bot para o Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) para saber como você pode desenvolver e publicar seus próprios bots.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-118">Please refer to [Creating and Testing a bot for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854371) guidance to learn how you can develop and publish your own bots.</span></span>

<span data-ttu-id="dd6cb-119">Quando você cria um bot e o registra com o Bot Framework, pode optar por publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-119">When you create a bot and register it with the Bot Framework, you can choose to publish it.</span></span> <span data-ttu-id="dd6cb-120">Se você não o publicar, o bot permanecerá privado.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-120">If you don't publish it, the bot remains private.</span></span> <span data-ttu-id="dd6cb-121">Você também pode exigir que seus usuários façam login antes de usar o bot.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-121">You can also require your users to log in before using the bot.</span></span> <span data-ttu-id="dd6cb-122">A exigência de login assegura que apenas os funcionários da sua organização possam acessar o bot, mesmo que o ID do aplicativo do bot se torne conhecido.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-122">Requiring login makes sure only employees of your organization can access the bot, even if the bot's application ID becomes known.</span></span> <span data-ttu-id="dd6cb-123">Veja [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) no GitHub para ver um exemplo de código de como autenticar os usuários no seu diretório ativo usando bots.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-123">See [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) on GitHub for a code example of how to authenticate users against your Active Directory using bots.</span></span>

<span data-ttu-id="dd6cb-124">Os bots podem ser testados usando o [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) antes que sejam implantados no seu Teams.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-124">Bots can be tested using the [Bot Framework Emulator](https://go.microsoft.com/fwlink/?linkid=854373) before they are deployed into your Teams.</span></span>

<a name="side-load-your-own-bot-for-private-chat"></a><span data-ttu-id="dd6cb-125">Carregue o seu próprio bot para bate-papos privados</span><span class="sxs-lookup"><span data-stu-id="dd6cb-125">Side load your own bot for private chat</span></span>
---------------------------------------

1. <span data-ttu-id="dd6cb-126">Depois de criar sua bot, vá para as **Configurações do aplicativo** para o bot que você desenvolvido, em seguida, em **configurações de aplicativo**, copie o valor da configuração **MicrosoftAppId** . ![Página de captura de tela das configurações de aplicativo para um bot com a ID de aplicativo Microsoft realçado.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span><span class="sxs-lookup"><span data-stu-id="dd6cb-126">After you have created your bot, go to the **Application Settings** for the bot you developed, then under **App settings**, copy the value of the **MicrosoftAppId** setting.![Screenshot of Application Settings page for a bot with the Microsoft App ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)</span></span>



2.  <span data-ttu-id="dd6cb-127">No Microsoft Teams, no painel de **Bate-papo**, selecione o **ícone Adicionar bate-papo**.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-127">From within Microsoft Teams, on the **Chat** pane, select the **Add chat icon**.</span></span> <span data-ttu-id="dd6cb-128">Em **Para**, cole a **ID do Aplicativo da Microsoft** de seu bot.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-128">For **To**, paste your bot's **Microsoft app ID**.</span></span> <span data-ttu-id="dd6cb-129">![Captura de tela de um painel de chat com o ícone para Adicionar chat e a linha Para com a ID do Aplicativo da Microsoft destacada.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span><span class="sxs-lookup"><span data-stu-id="dd6cb-129">![Screenshot of a chat pane with the icon for Add chat and the To line with the Microsoft app ID highlighted.](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)</span></span>



3.  <span data-ttu-id="dd6cb-130">O ID do aplicativo determina o **nome do bot,** e então você poderá iniciar uma conversa de bate-papo com esse bot.</span><span class="sxs-lookup"><span data-stu-id="dd6cb-130">The app ID will resolve to your **bot name,** and then you can initiate a chat conversation with that bot.</span></span>
