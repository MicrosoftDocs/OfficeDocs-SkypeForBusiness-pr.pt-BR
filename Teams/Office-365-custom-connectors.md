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
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Os conectores mantêm a sua equipe atualizada ao entregar conteúdo e atualizações de serviços que você usa com frequência diretamente em um canal.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc65939048fd8e54bd122a4dc52d2a611b8453cc
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834371"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="58496-103">Usar o Office 365 e conectores personalizados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58496-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="58496-104">Os conectores mantêm sua equipe em dia fornecendo conteúdo usado com frequência e atualizações de serviço diretamente em um canal.</span><span class="sxs-lookup"><span data-stu-id="58496-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="58496-105">Com os conectores, os usuários do Microsoft Teams podem receber atualizações de serviços populares, como Twitter, Trello, Wunderlist, GitHub e serviços do DevOps do Azure dentro do fluxo de chat de sua equipe.</span><span class="sxs-lookup"><span data-stu-id="58496-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="58496-106">Qualquer membro de uma equipe pode conectar sua equipe a serviços de nuvem populares com os conectores, se as permissões da equipe permitirem, e todos os membros da equipe forem notificados sobre as atividades desse serviço.</span><span class="sxs-lookup"><span data-stu-id="58496-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="58496-107">Os conectores continuarão a funcionar mesmo após o membro que, inicialmente, configurar o conector.</span><span class="sxs-lookup"><span data-stu-id="58496-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="58496-108">Qualquer membro da equipe com as permissões para adicionar à instalação pode modificar os conectores por outros membros.</span><span class="sxs-lookup"><span data-stu-id="58496-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="58496-109">Os conectores do Office 365 podem ser usados com o Microsoft Teams e com os grupos do Office 365, facilitando para todos os membros manter a sincronia e receber informações relevantes rapidamente.</span><span class="sxs-lookup"><span data-stu-id="58496-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="58496-110">O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="58496-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="58496-111">No entanto, vale a pena observar que a desabilitação de conectores para o grupo do Office 365 em que uma equipe depende da capacidade de criar conectores para essa equipe também será desativada.</span><span class="sxs-lookup"><span data-stu-id="58496-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="58496-112">Adicionar um conector a um canal</span><span class="sxs-lookup"><span data-stu-id="58496-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="58496-113">No momento, você pode adicionar conectores usando clientes da Web e de área de trabalho do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="58496-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="58496-114">No entanto, as informações postadas por esses conectores podem ser vistas em **todos os clientes** , inclusive móvel.</span><span class="sxs-lookup"><span data-stu-id="58496-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="58496-115">Para adicionar um conector a um canal, clique nas **reticências (...)** à direita de um nome de canal e, em seguida, clique em **conectores**.</span><span class="sxs-lookup"><span data-stu-id="58496-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![Captura de tela da interface do teams com a opção conectores selecionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="58496-117">Você pode selecionar uma variedade de conectores disponíveis e, em seguida, clicar em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="58496-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![Captura de tela da caixa de diálogo conectores mostrando os conectores disponíveis.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="58496-119">Preencha as informações necessárias do conector selecionado e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="58496-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="58496-120">Cada conector precisa de um conjunto de informações diversas para funcionar corretamente e alguns podem exigir que você inicie sessão no serviço usando os links fornecidos na página de configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="58496-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![Captura de tela da página de configuração do conector RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="58496-122">Os dados fornecidos pelo conector são publicados automaticamente no canal.</span><span class="sxs-lookup"><span data-stu-id="58496-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![Captura de tela da interface do Teams mostrando uma conversa em um canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="58496-124">Desenvolvimento de conectores personalizados</span><span class="sxs-lookup"><span data-stu-id="58496-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="58496-125">Você também pode criar conectores personalizados, bem como WebHooks de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="58496-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="58496-126">Para obter mais informações, consulte nossa [documentação do desenvolvedor](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).</span><span class="sxs-lookup"><span data-stu-id="58496-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
