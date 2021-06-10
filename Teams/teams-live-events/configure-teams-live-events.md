---
title: Configurar eventos ao vivo no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: Saiba como gerenciar configurações para Teams eventos ao vivo que são realizados em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9749484344d969671e8a0195de3386a57388d275
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637873"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="1d72e-103">Configurar eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d72e-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="1d72e-104">Use Teams configurações de eventos ao vivo para definir configurações para eventos ao vivo que são realizados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1d72e-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="1d72e-105">Você pode configurar uma URL de suporte e configurar um provedor de distribuição de vídeo de terceiros.</span><span class="sxs-lookup"><span data-stu-id="1d72e-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="1d72e-106">Essas configurações se aplicam a todos os eventos ao vivo criados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1d72e-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="1d72e-107">Você pode gerenciar facilmente essas configurações no Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="1d72e-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1d72e-108">Na navegação à esquerda, vá para **Reuniões**  >  **Ao vivo configurações de eventos**.</span><span class="sxs-lookup"><span data-stu-id="1d72e-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="1d72e-109">![Captura de tela de Teams de eventos ao vivo](../media/teams-live-events-settings.png "Captura de tela Teams configurações de eventos ao vivo que você pode configurar no Microsoft Teams de administração")</span><span class="sxs-lookup"><span data-stu-id="1d72e-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="1d72e-110">Configurar a URL de suporte a eventos</span><span class="sxs-lookup"><span data-stu-id="1d72e-110">Set up event support URL</span></span>

<span data-ttu-id="1d72e-111">Essa URL é mostrada para participantes do evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="1d72e-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="1d72e-112">Adicione a URL de suporte para sua organização para dar aos participantes uma maneira de contatar o suporte durante um evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="1d72e-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="1d72e-114&quot;>Usando o centro de administração do Microsoft Teams</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1d72e-114&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;1d72e-115&quot;>Na navegação à esquerda, vá para **Configurações do** evento Meetings  >  **Live**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1d72e-115&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;1d72e-116&quot;>Em **URL de Suporte,** insira a URL de suporte da sua organização.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1d72e-116&quot;>Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id=&quot;1d72e-117&quot;>![Configuração de URL de suporte para eventos ao vivo no centro de administração](../media/teams-live-events-settings-supporturl.png &quot;Captura de tela da configuração de URL de suporte para Teams eventos ao vivo")</span><span class="sxs-lookup"><span data-stu-id="1d72e-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="1d72e-118">Usar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d72e-118">Using Windows PowerShell</span></span>

<span data-ttu-id="1d72e-119">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1d72e-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="1d72e-120">Para obter mais informações, [consulte Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1d72e-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="1d72e-121">Configurar um provedor de distribuição de vídeo de terceiros</span><span class="sxs-lookup"><span data-stu-id="1d72e-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="1d72e-122">Se você comprou e configurou uma solução de rede definida por software (SDN) ou uma solução de rede de distribuição de conteúdo empresarial (eCDN) por meio de um parceiro de entrega de vídeo da Microsoft, configure o provedor para eventos ao vivo no Teams.</span><span class="sxs-lookup"><span data-stu-id="1d72e-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="1d72e-124&quot;>Usando o centro de administração do Microsoft Teams</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1d72e-124&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;1d72e-125&quot;>Na navegação à esquerda, vá para **Configurações do** evento Meetings  >  **Live**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1d72e-125&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;1d72e-126&quot;>Em **Provedores de distribuição de vídeo de terceiros,** conclua o seguinte:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1d72e-126&quot;>Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id=&quot;1d72e-127&quot;>![Configurações do provedor de distribuição de vídeo de terceiros no centro de administração](../media/teams-live-events-settings-distribution-provider.png &quot;Captura de tela das configurações do provedor de distribuição de vídeo de terceiros para eventos ao vivo")</span><span class="sxs-lookup"><span data-stu-id="1d72e-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="1d72e-128">**Usar um provedor de distribuição de terceiros** Ative isso para habilitar o provedor de distribuição de vídeo de terceiros.</span><span class="sxs-lookup"><span data-stu-id="1d72e-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="1d72e-129">**Nome do provedor SDN** Escolha o provedor que você está usando.</span><span class="sxs-lookup"><span data-stu-id="1d72e-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="1d72e-130">**Chave de licença do provedor** Insira a ID de licença que você recebeu do contato do provedor.</span><span class="sxs-lookup"><span data-stu-id="1d72e-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="1d72e-131">**URL do modelo de API do SDN** Insira a URL do modelo de API que você recebeu do contato do provedor.</span><span class="sxs-lookup"><span data-stu-id="1d72e-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="1d72e-132">Usar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d72e-132">Using Windows PowerShell</span></span>
<span data-ttu-id="1d72e-133">Obter a ID de licença ou token de API e modelo de API do contato do provedor e execute um dos seguintes, dependendo do provedor que você está usando:</span><span class="sxs-lookup"><span data-stu-id="1d72e-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="1d72e-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="1d72e-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="1d72e-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="1d72e-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="1d72e-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="1d72e-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
<span data-ttu-id="1d72e-137">**Ramp**</span><span class="sxs-lookup"><span data-stu-id="1d72e-137">**Ramp**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

<span data-ttu-id="1d72e-138">Para obter mais informações, [consulte Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1d72e-138">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="1d72e-139">Se você planeja criar eventos ao vivo usando um aplicativo ou dispositivo externo, também precisará configurar seu provedor [de eCDN com o Microsoft Stream.](/stream/network-caching)</span><span class="sxs-lookup"><span data-stu-id="1d72e-139">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="1d72e-p104">A mudança do Microsoft Stream para o [OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião](../tmr-meeting-recording-change.md) será uma abordagem em fases. No lançamento você poderá optar por aceitar essa experiência, em novembro você terá que recusar se quiser continuar usando o Stream e, no início de 2021, exigiremos que todos os clientes usem o OneDrive for Business e o Microsoft Office SharePoint Online para novas gravações de reunião.</span><span class="sxs-lookup"><span data-stu-id="1d72e-p104">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

>[!Note]
> <span data-ttu-id="1d72e-142">Sua solução eCDN escolhida está sujeita aos termos de serviço e política de privacidade do provedor de terceiros selecionados, que regerão o uso da solução do provedor eCDN.</span><span class="sxs-lookup"><span data-stu-id="1d72e-142">Your chosen eCDN solution is subject to the selected 3rd party provider’s terms of service and privacy policy, which will govern your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="1d72e-143">Seu uso da solução do provedor eCDN não estará sujeito aos termos de licenciamento por volume da Microsoft ou aos Termos de Serviços Online.</span><span class="sxs-lookup"><span data-stu-id="1d72e-143">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="1d72e-144">Se você não concordar com os termos do provedor de terceiros, não habilita a solução eCDN em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1d72e-144">If you don't agree to the 3rd party provider’s terms, then don't enable the eCDN solution in Microsoft Teams.</span></span>

### <a name="related-topics"></a><span data-ttu-id="1d72e-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1d72e-145">Related topics</span></span>
- [<span data-ttu-id="1d72e-146">O que são os eventos ao vivo do Teams?</span><span class="sxs-lookup"><span data-stu-id="1d72e-146">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="1d72e-147">Planejar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="1d72e-147">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="1d72e-148">Configurar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="1d72e-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
