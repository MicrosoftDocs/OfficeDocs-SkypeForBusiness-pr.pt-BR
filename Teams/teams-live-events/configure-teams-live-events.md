---
title: Definir configurações de evento ao vivo no Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Saiba como gerenciar configurações para eventos ao vivo de equipes que são mantidos em sua organização.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8e12b6b85b61bb8c6312054be07dc37365c62c0
ms.sourcegitcommit: 2e9761a3b195d31080bff3c9cc17a18adcd5350e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2018
ms.locfileid: "25748145"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="7b36b-103">Definir configurações de evento ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7b36b-103">Configure live event settings in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="7b36b-104">Use as configurações de eventos ao vivo de equipes para definir configurações para live eventos que são mantidos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7b36b-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="7b36b-105">Você pode configurar uma URL de suporte e configurar um provedor de distribuição de vídeo de terceiros.</span><span class="sxs-lookup"><span data-stu-id="7b36b-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="7b36b-106">Essas configurações se aplicam a todos os eventos ao vivo que são criados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7b36b-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="7b36b-107">Você pode gerenciar facilmente essas configurações no Microsoft Teams & Skype para o Centro de administração de negócios.</span><span class="sxs-lookup"><span data-stu-id="7b36b-107">You can easily manage these settings in the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="7b36b-108">No painel de navegação esquerdo, vá para **reuniões** > **configurações de eventos ao vivo**.</span><span class="sxs-lookup"><span data-stu-id="7b36b-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="7b36b-109">![Live-evento-settings.png] (../media/teams-live-events-settings.png "Captura de tela das equipes live configurações dos eventos que você pode definir no Microsoft equipes & Skype para centro de administração de negócios")</span><span class="sxs-lookup"><span data-stu-id="7b36b-109">![live-event-settings.png](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams & Skype for Business admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="7b36b-110">Configurar a URL de suporte do evento</span><span class="sxs-lookup"><span data-stu-id="7b36b-110">Set up event support URL</span></span>

<span data-ttu-id="7b36b-111">Essa URL é mostrada para os participantes do evento de live.</span><span class="sxs-lookup"><span data-stu-id="7b36b-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="7b36b-112">Adicione a URL de suporte para a sua organização para oferecer uma maneira de contato do suporte durante um evento ao vivo de participantes.</span><span class="sxs-lookup"><span data-stu-id="7b36b-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![as equipes de logotipo-30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="7b36b-114">Usando o Microsoft Teams & Skype para centro de administração de negócios</span><span class="sxs-lookup"><span data-stu-id="7b36b-114">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="7b36b-115">No painel de navegação esquerdo, vá para **reuniões** > **configurações de evento ao vivo**.</span><span class="sxs-lookup"><span data-stu-id="7b36b-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="7b36b-116">Em **Suporte de URL**, insira a URL de suporte da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7b36b-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="7b36b-117">![Configuração de URL de suporte para live eventos no Microsoft equipes & Skype para centro de administração de negócios] (../media/teams-live-events-settings-supporturl.png "Captura de tela de suporte para a URL de configuração para equipes eventos ao vivo")</span><span class="sxs-lookup"><span data-stu-id="7b36b-117">![Support URL setting for live events in the Microsoft Teams & Skype for Business admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="7b36b-118">Usar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b36b-118">Using Windows PowerShell</span></span>
<span data-ttu-id="7b36b-119">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7b36b-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="7b36b-120">Para obter mais informações, consulte [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7b36b-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="7b36b-121">Configurar um provedor de distribuição de vídeo de terceiros</span><span class="sxs-lookup"><span data-stu-id="7b36b-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="7b36b-122">Se você comprou e configurar uma solução de software definida de rede (SDN) ou uma solução de rede (eCDN) de fornecimento de conteúdo corporativo por meio de um parceiro de entrega de vídeo da Microsoft, configure o provedor para eventos ao vivo em equipes.</span><span class="sxs-lookup"><span data-stu-id="7b36b-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![as equipes de logotipo-30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="7b36b-124">Usando o Microsoft Teams & Skype para centro de administração de negócios</span><span class="sxs-lookup"><span data-stu-id="7b36b-124">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="7b36b-125">No painel de navegação esquerdo, vá para **reuniões** > **configurações de evento ao vivo**.</span><span class="sxs-lookup"><span data-stu-id="7b36b-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="7b36b-126">Em **provedores de distribuição de vídeo de terceiros**, conclua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7b36b-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="7b36b-127">![Configurações do provedor de distribuição de vídeo de terceiros no Microsoft equipes & Skype para centro de administração de negócios] (../media/teams-live-events-settings-distribution-provider.png "Captura de tela das configurações do provedor de distribuição de vídeo de terceiros para live eventos")</span><span class="sxs-lookup"><span data-stu-id="7b36b-127">![Third-party video distribution provider settings in the Microsoft Teams & Skype for Business admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="7b36b-128">**Use um provedor de distribuição de terceiros** Desative essa opção para habilitar o provedor de distribuição de vídeo de terceiros.</span><span class="sxs-lookup"><span data-stu-id="7b36b-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="7b36b-129">**Nome do provedor SDN** Escolha o provedor que você está usando.</span><span class="sxs-lookup"><span data-stu-id="7b36b-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="7b36b-130">**Chave de licença de provedor** Insira a ID de licença que você obteve de seu contato do provedor.</span><span class="sxs-lookup"><span data-stu-id="7b36b-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="7b36b-131">**URL do modelo de API SDN** Insira a URL do modelo de API que você obteve de seu contato do provedor.</span><span class="sxs-lookup"><span data-stu-id="7b36b-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="7b36b-132">Usar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b36b-132">Using Windows PowerShell</span></span>
<span data-ttu-id="7b36b-133">Obter o token de ID ou o API de licença e o modelo de API de seu contato do provedor e, em seguida, execute um dos seguintes procedimentos, dependendo do provedor que você está usando:</span><span class="sxs-lookup"><span data-stu-id="7b36b-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="7b36b-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="7b36b-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="7b36b-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="7b36b-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="7b36b-136">Para obter mais informações, consulte [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7b36b-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="7b36b-137">Se você planeja criar eventos ao vivo que usam codificadores externos, você também precisará [configurar seu provedor de eCDN com Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="7b36b-137">If you plan to create live events that use external encoders, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="7b36b-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7b36b-138">Related topics</span></span>
- [<span data-ttu-id="7b36b-139">Quais são as equipes live eventos?</span><span class="sxs-lookup"><span data-stu-id="7b36b-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="7b36b-140">Planejamento de eventos ao vivo de equipes</span><span class="sxs-lookup"><span data-stu-id="7b36b-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="7b36b-141">Configurar para equipes eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="7b36b-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)