---
title: Usar o Office 365 e conectores personalizados no Microsoft Teams | Suporte da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Os conectores mantêm a sua equipe atualizada ao entregar conteúdo e atualizações de serviços que você usa com frequência diretamente em um canal."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 08f2526686c894e44193fb53d51f9f59d6960279
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2017
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="03fba-103">Usar o Office 365 e conectores personalizados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="03fba-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="03fba-104">Os conectores mantêm a sua equipe atualizada ao entregar conteúdo e atualizações de serviços que você usa com frequência diretamente em um canal.</span><span class="sxs-lookup"><span data-stu-id="03fba-104">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="03fba-105">Com os conectores, os usuários do Microsoft Teams podem receber atualizações de serviços populares, como Twitter, Trello, Wunderlist, GitHub e VSTS no fluxo de bate-papo de suas equipes.</span><span class="sxs-lookup"><span data-stu-id="03fba-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and VSTS within the chat stream in their team.</span></span>

<span data-ttu-id="03fba-106">Qualquer membro da equipe pode conectar sua equipe a serviços populares em nuvem com os conectores, e todos os membros da equipe são notificados das atividades desse serviço.</span><span class="sxs-lookup"><span data-stu-id="03fba-106">Any member of a team can connect their team to popular cloud services with the connectors, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="03fba-107">Se um usuário for removido de uma equipe, todos os conectores adicionados à equipe pelo usuário removido deixam de funcionar.</span><span class="sxs-lookup"><span data-stu-id="03fba-107">If a user is removed from a team, any connectors added to the team by the removed user do stop working.</span></span> <span data-ttu-id="03fba-108">As reuniões agendadas continuam funcionando porque estão no calendário do grupo.</span><span class="sxs-lookup"><span data-stu-id="03fba-108">Scheduled meetings continue to work because they're on the group calendar.</span></span>

<span data-ttu-id="03fba-109">Os conectores do Office 365 podem ser usados com o Microsoft Teams e com os grupos do Office 365, facilitando para todos os membros manter a sincronia e receber informações relevantes rapidamente.</span><span class="sxs-lookup"><span data-stu-id="03fba-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="03fba-110">O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="03fba-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span>

<span data-ttu-id="03fba-111">No momento, os conectores podem ser adicionados usando os clientes Microsoft Teams de desktop e web.</span><span class="sxs-lookup"><span data-stu-id="03fba-111">Currently, connectors can be added by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="03fba-112">No entanto, as informações publicadas por esses conectores podem ser visualizadas usando **todos os clientes**, inclusive de celular.</span><span class="sxs-lookup"><span data-stu-id="03fba-112">However, information posted by these connectors can be viewed using **all clients** including mobile.</span></span>

1.  <span data-ttu-id="03fba-113">Para adicionar um conector a um canal, clique nas **reticências (…),** ao lado direito do nome do canal, e então clique em **Conectores.**</span><span class="sxs-lookup"><span data-stu-id="03fba-113">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors.**</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  <span data-ttu-id="03fba-114">Os usuários podem escolher a partir de uma grande variedade de conectores, e então clicar em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="03fba-114">Users can select from a variety of available connectors, then click **Add**.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  <span data-ttu-id="03fba-115">Preencha as informações necessárias do conector selecionado e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="03fba-115">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="03fba-116">Cada conector precisa de um conjunto de informações diversas para funcionar corretamente e alguns podem exigir que você inicie sessão no serviço usando os links fornecidos na página de configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="03fba-116">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  <span data-ttu-id="03fba-117">Os dados fornecidos pelo conector são publicados automaticamente no canal.</span><span class="sxs-lookup"><span data-stu-id="03fba-117">Data provided by the connector is automatically posted to the channel.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="03fba-118">Desenvolvimento de conectores personalizados</span><span class="sxs-lookup"><span data-stu-id="03fba-118">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="03fba-119">Desenvolver conectores personalizados que podem se integrar aos seus aplicativos Line-of-Business (LOB) é muito fácil.</span><span class="sxs-lookup"><span data-stu-id="03fba-119">It is very easy to develop custom connectors that can integrate into your Line-of-Business (LOB) applications.</span></span> <span data-ttu-id="03fba-120">Você pode usar o conector interno **Incoming Webhook** para criar um endpoint para um canal que pega dados de qualquer aplicativo usando métodos de publicação HTTP.</span><span class="sxs-lookup"><span data-stu-id="03fba-120">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel, that pulls data from any application using HTTP post methods.</span></span>

1.  <span data-ttu-id="03fba-121">E o **Incoming Webhook** como qualquer outro conector.</span><span class="sxs-lookup"><span data-stu-id="03fba-121">Add the **Incoming Webhook** like any other connector.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="03fba-122">Para criar um Webhook, especifique um **nome**, atualize a imagem do Webhook, se necessário, e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="03fba-122">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="03fba-123">Os aplicativos que levam dados para este canal precisam da URL do conector Webhook.</span><span class="sxs-lookup"><span data-stu-id="03fba-123">Applications that push data to this channel, require the Webhook connector URL.</span></span> <span data-ttu-id="03fba-124">É criada uma **URL exclusiva** ao criar o **Webhook**.</span><span class="sxs-lookup"><span data-stu-id="03fba-124">A **unique URL** is created when you created the **Webhook**.</span></span> <span data-ttu-id="03fba-125">Compartilhe essa URL com os seus desenvolvedores para que eles possam configurar seus aplicativos para pegar os dados conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="03fba-125">Share this URL with your developers, so that they can configure their applications to push data, as needed.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  <span data-ttu-id="03fba-126">Quando um aplicativo externo leva dados para um conector, a mensagem é mostrada na lista de conversas do canal como uma mensagem especial chamada de mensagem do** Cartão do Conector**.</span><span class="sxs-lookup"><span data-stu-id="03fba-126">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

<span data-ttu-id="03fba-127">Os desenvolvedores podem configurar seus aplicativos para criar esses cartões enviando uma solicitação HTTP com um payload JSON simples para o endereço Webhook do Microsoft Team, que é uma URL exclusiva desse endpoint fornecido pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="03fba-127">Developers can configure their applications to create these cards, by sending an HTTP request with a simple JSON payload to a Microsoft Team’s Webhook address, that is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="03fba-128">Solicite que os seus desenvolvedores consultem [Introdução aos Conectores do Office 365 para o Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783) na Rede do Desenvolvedor da Microsoft, com instruções detalhadas e exemplos de conectores.</span><span class="sxs-lookup"><span data-stu-id="03fba-128">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783), on the Microsoft Developer Network, with detailed instructions and connector samples.</span></span> <span data-ttu-id="03fba-129">Outros recursos incluem [Conectar aplicativos aos seus grupos no Outlook](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) e [Centro de Desenvolvimento do Office – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span><span class="sxs-lookup"><span data-stu-id="03fba-129">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
