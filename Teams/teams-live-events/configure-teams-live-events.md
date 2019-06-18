---
title: Configurar eventos ao vivo no Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Saiba como gerenciar as configurações de eventos dinâmicos do teams que são mantidas em sua organização.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83d7e43e75b71eefdb4a95f26c14c27956e763f9
ms.sourcegitcommit: 9d9376c6e5e6d79e33ba54fb8ce87509a2f57754
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2019
ms.locfileid: "35013033"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="3045b-103">Configurar eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3045b-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="3045b-104">Use as configurações de eventos ao vivo do teams para definir configurações para eventos dinâmicos que são mantidos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3045b-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="3045b-105">Você pode configurar uma URL de suporte e configurar um provedor de distribuição de vídeo de terceiros.</span><span class="sxs-lookup"><span data-stu-id="3045b-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="3045b-106">Essas configurações se aplicam a todos os eventos dinâmicos que são criados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3045b-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="3045b-107">Você pode facilmente gerenciar essas configurações no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3045b-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3045b-108">No painel de navegação esquerdo, vá para**configurações de eventos ao vivo**de **reuniões** > .</span><span class="sxs-lookup"><span data-stu-id="3045b-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="3045b-109">![Captura de tela das configurações de eventos ao vivo do teams] (../media/teams-live-events-settings.png "Captura de tela das configurações de eventos do teams Live que você pode configurar no centro de administração do Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="3045b-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="3045b-110">Configurar a URL de suporte a eventos</span><span class="sxs-lookup"><span data-stu-id="3045b-110">Set up event support URL</span></span>

<span data-ttu-id="3045b-111">Esta URL é mostrada para participantes do evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="3045b-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="3045b-112">Adicione a URL de suporte para a sua organização para dar aos participantes uma maneira de entrar em contato com o suporte durante um evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="3045b-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="3045b-114">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3045b-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3045b-115">No painel de navegação esquerdo, vá para **reuniões** > **ao vivo configurações de eventos**.</span><span class="sxs-lookup"><span data-stu-id="3045b-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="3045b-116">Em **URL de suporte**, insira a URL de suporte da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3045b-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="3045b-117">![Configuração da URL de suporte para eventos dinâmicos no centro de administração] (../media/teams-live-events-settings-supporturl.png "Captura de tela da configuração da URL de suporte para eventos ao vivo") do teams</span><span class="sxs-lookup"><span data-stu-id="3045b-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="3045b-118">Usar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3045b-118">Using Windows PowerShell</span></span>
<span data-ttu-id="3045b-119">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3045b-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="3045b-120">Para obter mais informações, consulte [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3045b-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="3045b-121">Configurar um provedor de distribuição de vídeo de terceiros</span><span class="sxs-lookup"><span data-stu-id="3045b-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="3045b-122">Se você comprou e configurou uma solução SDN (software defined Network) ou uma solução Enterprise Content Delivery Network (eCDN) por meio de um parceiro de entrega de vídeo da Microsoft, configure o provedor para eventos dinâmicos no Teams.</span><span class="sxs-lookup"><span data-stu-id="3045b-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="3045b-124">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3045b-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3045b-125">No painel de navegação esquerdo, vá para **reuniões** > **ao vivo configurações de eventos**.</span><span class="sxs-lookup"><span data-stu-id="3045b-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="3045b-126">Em **provedores de distribuição de vídeo de terceiros**, conclua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3045b-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="3045b-127">![Configurações de provedor de distribuição de vídeo de terceiros no centro de administração] (../media/teams-live-events-settings-distribution-provider.png "Captura de tela das configurações de provedor de distribuição de vídeo de terceiros para eventos dinâmicos")</span><span class="sxs-lookup"><span data-stu-id="3045b-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="3045b-128">**Usar um provedor de distribuição de terceiros** Ative esta opção para habilitar o provedor de distribuição de vídeo de terceiros.</span><span class="sxs-lookup"><span data-stu-id="3045b-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="3045b-129">**Nome do provedor do Sdn** Escolha o provedor que você está usando.</span><span class="sxs-lookup"><span data-stu-id="3045b-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="3045b-130">**Chave de licença do provedor** Digite a ID da licença que você recebeu do contato do provedor.</span><span class="sxs-lookup"><span data-stu-id="3045b-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="3045b-131">**URL do modelo de API do Sdn** Digite a URL do modelo de API que você recebeu do contato do provedor.</span><span class="sxs-lookup"><span data-stu-id="3045b-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="3045b-132">Usar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3045b-132">Using Windows PowerShell</span></span>
<span data-ttu-id="3045b-133">Obtenha a ID da licença ou o token da API e o modelo de API do contato do provedor e execute um dos seguintes procedimentos, dependendo do provedor que você está usando:</span><span class="sxs-lookup"><span data-stu-id="3045b-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="3045b-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="3045b-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="3045b-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="3045b-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="3045b-136">Para obter mais informações, consulte [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3045b-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="3045b-137">Se você planeja criar eventos dinâmicos usando um dispositivo ou aplicativo externo, também precisará [configurar seu provedor de eCDN com o Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="3045b-137">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="3045b-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3045b-138">Related topics</span></span>
- [<span data-ttu-id="3045b-139">O que são os eventos ao vivo do Teams?</span><span class="sxs-lookup"><span data-stu-id="3045b-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="3045b-140">Planejar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="3045b-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="3045b-141">Configurar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="3045b-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)