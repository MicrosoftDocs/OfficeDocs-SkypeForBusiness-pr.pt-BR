---
title: Usar o Office 365 e conectores personalizados no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Os conectores mantêm a sua equipe atualizada ao entregar conteúdo e atualizações de serviços que você usa com frequência diretamente em um canal.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8235ce9eb950df0c04ab41949500a640376e612
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245204"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="73340-103">Usar o Office 365 e conectores personalizados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73340-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="73340-104">Os conectores mantêm sua equipe em dia fornecendo conteúdo usado com frequência e atualizações de serviço diretamente em um canal.</span><span class="sxs-lookup"><span data-stu-id="73340-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="73340-105">Com os conectores, os usuários do Microsoft Teams podem receber atualizações de serviços populares, como Twitter, Trello, Wunderlist, GitHub e serviços do DevOps do Azure dentro do fluxo de chat de sua equipe.</span><span class="sxs-lookup"><span data-stu-id="73340-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="73340-106">Qualquer membro de uma equipe pode conectar sua equipe a serviços de nuvem populares com os conectores, se as permissões da equipe permitirem, e todos os membros da equipe forem notificados sobre as atividades desse serviço.</span><span class="sxs-lookup"><span data-stu-id="73340-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="73340-107">Os conectores continuarão a funcionar mesmo após o membro que, inicialmente, configurar o conector.</span><span class="sxs-lookup"><span data-stu-id="73340-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="73340-108">Qualquer membro da equipe com as permissões para adicionar à instalação pode modificar os conectores por outros membros.</span><span class="sxs-lookup"><span data-stu-id="73340-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="73340-109">Os conectores do Office 365 podem ser usados com o Microsoft Teams e com os grupos do Office 365, facilitando para todos os membros manter a sincronia e receber informações relevantes rapidamente.</span><span class="sxs-lookup"><span data-stu-id="73340-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="73340-110">O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="73340-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="73340-111">No entanto, vale a pena observar que a desabilitação de conectores para o grupo do Office 365 em que uma equipe depende da capacidade de criar conectores para essa equipe também será desativada.</span><span class="sxs-lookup"><span data-stu-id="73340-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="73340-112">Adicionar um conector a um canal</span><span class="sxs-lookup"><span data-stu-id="73340-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="73340-113">No momento, você pode adicionar conectores usando clientes da Web e de área de trabalho do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="73340-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="73340-114">No entanto, as informações postadas por esses conectores podem ser vistas em **todos os clientes** , inclusive móvel.</span><span class="sxs-lookup"><span data-stu-id="73340-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="73340-115">Para adicionar um conector a um canal, clique nas **reticências (...)** à direita de um nome de canal e, em seguida \*\*\*\*, clique em conectores.</span><span class="sxs-lookup"><span data-stu-id="73340-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![Captura de tela da interface do teams com a opção conectores selecionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="73340-117">Você pode selecionar uma variedade de conectores disponíveis e, em seguida, clicar em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="73340-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![Captura de tela da caixa de diálogo conectores mostrando os conectores disponíveis.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="73340-119">Preencha as informações necessárias do conector selecionado e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73340-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="73340-120">Cada conector precisa de um conjunto de informações diversas para funcionar corretamente e alguns podem exigir que você inicie sessão no serviço usando os links fornecidos na página de configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="73340-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Captura de tela da página de configuração do conector RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="73340-122">Os dados fornecidos pelo conector são publicados automaticamente no canal.</span><span class="sxs-lookup"><span data-stu-id="73340-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Captura de tela da interface do Teams mostrando uma conversa em um canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="73340-124">Desenvolvimento de conectores personalizados</span><span class="sxs-lookup"><span data-stu-id="73340-124">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="73340-125">É muito fácil desenvolver conectores personalizados que podem ser integrados a seus aplicativos de linha de negócios (LOB).</span><span class="sxs-lookup"><span data-stu-id="73340-125">It is very easy to develop custom connectors that can integrate with your line-of-business (LOB) applications.</span></span> <span data-ttu-id="73340-126">Você pode usar o conector de webhook de **entrada** interno para criar um ponto de extremidade para um canal que obtém dados de qualquer aplicativo usando métodos post http.</span><span class="sxs-lookup"><span data-stu-id="73340-126">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel that pulls data from any application using HTTP post methods.</span></span>

1. <span data-ttu-id="73340-127">E o **Incoming Webhook** como qualquer outro conector.</span><span class="sxs-lookup"><span data-stu-id="73340-127">Add the **Incoming Webhook** like any other connector.</span></span>

    ![Captura de tela da opção de adicionar o conector Incoming Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. <span data-ttu-id="73340-129">Para criar um Webhook, especifique um **nome**, atualize a imagem do Webhook, se necessário, e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="73340-129">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![Captura de tela da página de configuração do conector de webhook de entrada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. <span data-ttu-id="73340-131">Os aplicativos que empurram dados para esse canal exigem a URL do conector do webhook.</span><span class="sxs-lookup"><span data-stu-id="73340-131">Applications that push data to this channel require the Webhook connector URL.</span></span> <span data-ttu-id="73340-132">Uma URL exclusiva é criada quando você cria o webhook.</span><span class="sxs-lookup"><span data-stu-id="73340-132">A unique URL is created when you create the Webhook.</span></span> <span data-ttu-id="73340-133">Compartilhe esta URL com seus desenvolvedores, para que eles possam configurar seus aplicativos para enviar dados por push, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="73340-133">Share this URL with your developers so that they can configure their applications to push data, as needed.</span></span>

    ![Captura de tela da URL exclusiva do Webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. <span data-ttu-id="73340-135">Quando um aplicativo externo leva dados para um conector, a mensagem é mostrada na lista de conversas do canal como uma mensagem especial chamada de mensagem do **Cartão do Conector**.</span><span class="sxs-lookup"><span data-stu-id="73340-135">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![Captura de tela da interface do Teams mostrando uma mensagem do Cartão do Conector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     <span data-ttu-id="73340-137">Os desenvolvedores podem configurar seus aplicativos para criar esses cartões enviando uma solicitação HTTP com uma carga JSON simples para o endereço do webhook de uma equipe, que é uma URL exclusiva desse ponto de extremidade fornecida pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="73340-137">Developers can configure their applications to create these cards by sending an HTTP request with a simple JSON payload to a team’s Webhook address, which is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="73340-138">Faça com que seus desenvolvedores consultem [introdução aos conectores do Office 365 para Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), na Microsoft Developer Network, que tenha instruções detalhadas e exemplos de conector.</span><span class="sxs-lookup"><span data-stu-id="73340-138">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, which has detailed instructions and connector samples.</span></span> <span data-ttu-id="73340-139">Outros recursos incluem [Conectar aplicativos aos seus grupos no Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) e [Centro de Desenvolvimento do Office – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span><span class="sxs-lookup"><span data-stu-id="73340-139">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
