---
title: Usar Microsoft 365 e conectores personalizados
author: SerdarSoysal
ms.author: serdars
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
description: Os conectores mantêm sua equipe atualizada com conteúdo e atualizações de serviços que você usa frequentemente diretamente em um canal.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62406da5e9feff7286023b955bd031bddda110b1
ms.sourcegitcommit: 358038cee16ac041da10a67c26cf463901ae53d8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52669143"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="1e17f-103">Use Microsoft 365 conectores personalizados e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e17f-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>

<span data-ttu-id="1e17f-104">Os conectores mantêm sua equipe atual, fornecendo atualizações de conteúdo e serviço usados com frequência diretamente em um canal.</span><span class="sxs-lookup"><span data-stu-id="1e17f-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="1e17f-105">Com conectores, os usuários Microsoft Teams podem receber atualizações de serviços populares, como Trello, Wunderlist, GitHub e Azure DevOps Services no fluxo de chat em sua equipe.</span><span class="sxs-lookup"><span data-stu-id="1e17f-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="1e17f-106">Qualquer membro de uma equipe pode conectar sua equipe a serviços de nuvem populares com os conectores se as permissões de equipe permitirem e todos os membros da equipe são notificados das atividades desse serviço.</span><span class="sxs-lookup"><span data-stu-id="1e17f-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="1e17f-107">Os conectores continuarão a funcionar mesmo depois que o membro que tiver configurado inicialmente o conector tiver sido deixado.</span><span class="sxs-lookup"><span data-stu-id="1e17f-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="1e17f-108">Qualquer membro da equipe com as permissões para adicionar\remover pode modificar a configuração de conectores por outros membros.</span><span class="sxs-lookup"><span data-stu-id="1e17f-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="1e17f-109">Microsoft 365 conectores podem ser usados com grupos de Microsoft Teams e Microsoft 365, facilitando que todos os membros fiquem em sincronia e recebam informações relevantes rapidamente.</span><span class="sxs-lookup"><span data-stu-id="1e17f-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="1e17f-110">O Microsoft Teams e o Exchange usam o mesmo modelo de conector, permitindo que você use os mesmos conectores em ambas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="1e17f-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="1e17f-111">No entanto, vale a pena notar que desabilitar conectores para o grupo Microsoft 365 que uma equipe depende desabilitará a capacidade de criar conectores para essa equipe também.</span><span class="sxs-lookup"><span data-stu-id="1e17f-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

> <span data-ttu-id="1e17f-112">[Observação] Os conectores são desabilitados por padrão nos ambientes de Community (GCC) do Governo.</span><span class="sxs-lookup"><span data-stu-id="1e17f-112">[Note] Connectors are disable by default in the Government Cloud Community (GCC) environments.</span></span> <span data-ttu-id="1e17f-113">Se você precisar habilita-los, desmarque os parâmetros ConnectorsEnabled ou ConnectorsEnabledForTeams para $true com o cmdlet [SetOrganizationConfig.](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="1e17f-113">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet.</span></span> <span data-ttu-id="1e17f-114">Anteriormente, você precisava se conectar ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1e17f-114">You previously needed to connect to the [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="add-a-connector-to-a-channel"></a><span data-ttu-id="1e17f-115">Adicionar um conector a um canal</span><span class="sxs-lookup"><span data-stu-id="1e17f-115">Add a connector to a channel</span></span>

<span data-ttu-id="1e17f-116">Atualmente, você pode adicionar conectores usando Microsoft Teams de área de trabalho e web.</span><span class="sxs-lookup"><span data-stu-id="1e17f-116">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="1e17f-117">No entanto, as informações postadas por esses conectores podem ser exibidas em **todos os clientes,** incluindo móveis.</span><span class="sxs-lookup"><span data-stu-id="1e17f-117">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="1e17f-118">Para adicionar um conector a um canal, clique nas **releições (...),** à direita de um nome de canal e clique em **Conectores**.</span><span class="sxs-lookup"><span data-stu-id="1e17f-118">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e17f-119">![Captura de tela da interface Teams com a opção Conectores selecionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="1e17f-119">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="1e17f-120">Você pode selecionar entre vários conectores disponíveis e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1e17f-120">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e17f-121">![Captura de tela da caixa de diálogo Conectores mostrando os conectores disponíveis.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="1e17f-121">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="1e17f-122">Preencha as informações necessárias do conector selecionado e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e17f-122">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="1e17f-123">Cada conector precisa de um conjunto de informações diversas para funcionar corretamente e alguns podem exigir que você inicie sessão no serviço usando os links fornecidos na página de configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="1e17f-123">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e17f-124">![Captura de tela da página de configuração do conector RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="1e17f-124">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="1e17f-125">Os dados fornecidos pelo conector são publicados automaticamente no canal.</span><span class="sxs-lookup"><span data-stu-id="1e17f-125">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1e17f-126">![Captura de tela da interface do Teams mostrando uma conversa em um canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="1e17f-126">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="1e17f-127">**Notificação de atualização da URL do conector**</span><span class="sxs-lookup"><span data-stu-id="1e17f-127">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="1e17f-128">Os Teams conectores estão fazendo a transição para uma nova URL para melhorar a segurança.</span><span class="sxs-lookup"><span data-stu-id="1e17f-128">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="1e17f-129">Durante o curso dessa transição, você receberá determinadas notificações para atualizar seu conector configurado para usar a nova URL.</span><span class="sxs-lookup"><span data-stu-id="1e17f-129">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="1e17f-130">É altamente recomendável que você atualize seu conector imediatamente para evitar qualquer interrupção nos serviços do conector.</span><span class="sxs-lookup"><span data-stu-id="1e17f-130">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="1e17f-131">As etapas a seguir precisam ser seguidas para atualizar a URL:</span><span class="sxs-lookup"><span data-stu-id="1e17f-131">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="1e17f-132">Na página de configuração de conectores, uma mensagem "Atenção Necessária" será exibida no botão "Gerenciar" para as conexões que precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="1e17f-132">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="1e17f-133">![Captura de tela da mensagem "Atenção Necessária".](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="1e17f-133">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="1e17f-134">Para conectores de webhook de entrada, os usuários podem recriar a conexão simplesmente selecionando **Atualizar URL** e usando a URL de webhook recém-gerada.</span><span class="sxs-lookup"><span data-stu-id="1e17f-134">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="1e17f-135">![Captura de tela do botão "Atualizar URL".](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="1e17f-135">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="1e17f-136">Para outros tipos de conector, o usuário precisaria remover o conector e recriar a configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="1e17f-136">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="1e17f-137">Você verá uma mensagem "A URL está atualizada" depois que a URL tiver sido atualizada com êxito.</span><span class="sxs-lookup"><span data-stu-id="1e17f-137">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="1e17f-138">![Captura de tela da mensagem "URL está atualizada".](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="1e17f-138">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


## <a name="develop-custom-connectors"></a><span data-ttu-id="1e17f-139">Desenvolvimento de conectores personalizados</span><span class="sxs-lookup"><span data-stu-id="1e17f-139">Develop custom connectors</span></span>


<span data-ttu-id="1e17f-140">Você também pode criar conectores personalizados, bem como webhooks de entrada e de saída.</span><span class="sxs-lookup"><span data-stu-id="1e17f-140">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="1e17f-141">Para obter mais informações, consulte nossa [documentação do desenvolvedor](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).</span><span class="sxs-lookup"><span data-stu-id="1e17f-141">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
