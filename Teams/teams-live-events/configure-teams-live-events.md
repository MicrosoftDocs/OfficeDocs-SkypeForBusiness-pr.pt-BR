---
title: Configurar eventos ao vivo no Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Saiba como gerenciar as configurações de eventos dinâmicos do teams que são mantidas em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: afbcd90db9a17f509076bae1271bf541dfb93fd4
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030887"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="18dd1-103">Configurar eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18dd1-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="18dd1-104">Use as configurações de eventos ao vivo do teams para definir configurações para eventos dinâmicos que são mantidos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="18dd1-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="18dd1-105">Você pode configurar uma URL de suporte e configurar um provedor de distribuição de vídeo de terceiros.</span><span class="sxs-lookup"><span data-stu-id="18dd1-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="18dd1-106">Essas configurações se aplicam a todos os eventos dinâmicos que são criados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="18dd1-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="18dd1-107">Você pode facilmente gerenciar essas configurações no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="18dd1-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="18dd1-108">No painel de navegação esquerdo, vá **Meetings** para  >  **configurações de eventos ao vivo** de reuniões.</span><span class="sxs-lookup"><span data-stu-id="18dd1-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="18dd1-109">![Captura de tela das configurações de eventos ao vivo do teams](../media/teams-live-events-settings.png "Captura de tela das configurações de eventos do teams Live que você pode configurar no centro de administração do Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="18dd1-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="18dd1-110">Configurar a URL de suporte a eventos</span><span class="sxs-lookup"><span data-stu-id="18dd1-110">Set up event support URL</span></span>

<span data-ttu-id="18dd1-111">Esta URL é mostrada para participantes do evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="18dd1-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="18dd1-112">Adicione a URL de suporte para a sua organização para dar aos participantes uma maneira de entrar em contato com o suporte durante um evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="18dd1-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="18dd1-114">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18dd1-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="18dd1-115">No painel de navegação esquerdo, vá para **reuniões**  >  **ao vivo configurações de eventos**.</span><span class="sxs-lookup"><span data-stu-id="18dd1-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="18dd1-116">Em **URL de suporte** , insira a URL de suporte da sua organização.</span><span class="sxs-lookup"><span data-stu-id="18dd1-116">Under **Support URL** , enter your organization's support URL.</span></span>

    <span data-ttu-id="18dd1-117">![Configuração da URL de suporte para eventos dinâmicos no centro de administração](../media/teams-live-events-settings-supporturl.png "Captura de tela da configuração da URL de suporte para eventos ao vivo do teams")</span><span class="sxs-lookup"><span data-stu-id="18dd1-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="18dd1-118">Usar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18dd1-118">Using Windows PowerShell</span></span>

<span data-ttu-id="18dd1-119">Execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="18dd1-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="18dd1-120">Para obter mais informações, consulte [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="18dd1-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="18dd1-121">Configurar um provedor de distribuição de vídeo de terceiros</span><span class="sxs-lookup"><span data-stu-id="18dd1-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="18dd1-122">Se você comprou e configurou uma solução SDN (software defined Network) ou uma solução Enterprise Content Delivery Network (eCDN) por meio de um parceiro de entrega de vídeo da Microsoft, configure o provedor para eventos dinâmicos no Teams.</span><span class="sxs-lookup"><span data-stu-id="18dd1-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) <span data-ttu-id="18dd1-124">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18dd1-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="18dd1-125">No painel de navegação esquerdo, vá para **reuniões**  >  **ao vivo configurações de eventos**.</span><span class="sxs-lookup"><span data-stu-id="18dd1-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="18dd1-126">Em **provedores de distribuição de vídeo de terceiros** , conclua o seguinte:</span><span class="sxs-lookup"><span data-stu-id="18dd1-126">Under **Third-party video distribution providers** , complete the following:</span></span> 

    <span data-ttu-id="18dd1-127">![Configurações de provedor de distribuição de vídeo de terceiros no centro de administração](../media/teams-live-events-settings-distribution-provider.png "Captura de tela das configurações de provedor de distribuição de vídeo de terceiros para eventos dinâmicos")</span><span class="sxs-lookup"><span data-stu-id="18dd1-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="18dd1-128">**Usar um provedor de distribuição de terceiros** Ative esta opção para habilitar o provedor de distribuição de vídeo de terceiros.</span><span class="sxs-lookup"><span data-stu-id="18dd1-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="18dd1-129">**Nome do provedor do Sdn** Escolha o provedor que você está usando.</span><span class="sxs-lookup"><span data-stu-id="18dd1-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="18dd1-130">**Chave de licença do provedor** Digite a ID da licença que você recebeu do contato do provedor.</span><span class="sxs-lookup"><span data-stu-id="18dd1-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="18dd1-131">**URL do modelo de API do Sdn** Digite a URL do modelo de API que você recebeu do contato do provedor.</span><span class="sxs-lookup"><span data-stu-id="18dd1-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="18dd1-132">Usar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18dd1-132">Using Windows PowerShell</span></span>
<span data-ttu-id="18dd1-133">Obtenha a ID da licença ou o token da API e o modelo de API do contato do provedor e execute um dos seguintes procedimentos, dependendo do provedor que você está usando:</span><span class="sxs-lookup"><span data-stu-id="18dd1-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="18dd1-134">**Hive**</span><span class="sxs-lookup"><span data-stu-id="18dd1-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="18dd1-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="18dd1-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="18dd1-136">**Riverbed**</span><span class="sxs-lookup"><span data-stu-id="18dd1-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

<span data-ttu-id="18dd1-137">Para obter mais informações, consulte [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="18dd1-137">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="18dd1-138">Se você planeja criar eventos dinâmicos usando um dispositivo ou aplicativo externo, também precisará [configurar seu provedor de eCDN com o Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="18dd1-138">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="18dd1-139">A mudança do Microsoft Stream para o [OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião](../tmr-meeting-recording-change.md) será uma abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="18dd1-139">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="18dd1-140">No lançamento você poderá optar por aceitar essa experiência, em novembro você terá que recusar se quiser continuar usando o Stream e, no início de 2021, exigiremos que todos os clientes usem o OneDrive for Business e o Microsoft Office SharePoint Online para novas gravações de reunião.</span><span class="sxs-lookup"><span data-stu-id="18dd1-140">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="related-topics"></a><span data-ttu-id="18dd1-141">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="18dd1-141">Related topics</span></span>
- [<span data-ttu-id="18dd1-142">O que são os eventos ao vivo do Teams?</span><span class="sxs-lookup"><span data-stu-id="18dd1-142">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="18dd1-143">Planejar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="18dd1-143">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="18dd1-144">Configurar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="18dd1-144">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
