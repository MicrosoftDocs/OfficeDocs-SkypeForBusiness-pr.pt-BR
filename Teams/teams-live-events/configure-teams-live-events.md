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
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Definir configurações de evento ao vivo no Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Use as configurações de eventos ao vivo de equipes para definir configurações para live eventos que são mantidos em sua organização. Você pode configurar uma URL de suporte e configurar um provedor de distribuição de vídeo de terceiros. Essas configurações se aplicam a todos os eventos ao vivo que são criados em sua organização. 

Você pode gerenciar facilmente essas configurações no Microsoft Teams & Skype para o Centro de administração de negócios. No painel de navegação esquerdo, vá para **reuniões** > **configurações de eventos ao vivo**. 

![Live-evento-settings.png] (../media/teams-live-events-settings.png "Captura de tela das equipes live configurações dos eventos que você pode definir no Microsoft equipes & Skype para centro de administração de negócios") 

## <a name="set-up-event-support-url"></a>Configurar a URL de suporte do evento

Essa URL é mostrada para os participantes do evento de live. Adicione a URL de suporte para a sua organização para oferecer uma maneira de contato do suporte durante um evento ao vivo de participantes.

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![as equipes de logotipo-30x30.png](../media/teams-logo-30x30.png) Usando o Microsoft Teams & Skype para centro de administração de negócios

1. No painel de navegação esquerdo, vá para **reuniões** > **configurações de evento ao vivo**.
2. Em **Suporte de URL**, insira a URL de suporte da sua organização. 

    ![Configuração de URL de suporte para live eventos no Microsoft equipes & Skype para centro de administração de negócios] (../media/teams-live-events-settings-supporturl.png "Captura de tela de suporte para a URL de configuração para equipes eventos ao vivo")

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell
Execute o seguinte:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Para obter mais informações, consulte [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurar um provedor de distribuição de vídeo de terceiros 

Se você comprou e configurar uma solução de software definida de rede (SDN) ou uma solução de rede (eCDN) de fornecimento de conteúdo corporativo por meio de um parceiro de entrega de vídeo da Microsoft, configure o provedor para eventos ao vivo em equipes. 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![as equipes de logotipo-30x30.png](../media/teams-logo-30x30.png) Usando o Microsoft Teams & Skype para centro de administração de negócios

1. No painel de navegação esquerdo, vá para **reuniões** > **configurações de evento ao vivo**.
2. Em **provedores de distribuição de vídeo de terceiros**, conclua o seguinte: 

    ![Configurações do provedor de distribuição de vídeo de terceiros no Microsoft equipes & Skype para centro de administração de negócios] (../media/teams-live-events-settings-distribution-provider.png "Captura de tela das configurações do provedor de distribuição de vídeo de terceiros para live eventos")

    - **Use um provedor de distribuição de terceiros** Desative essa opção para habilitar o provedor de distribuição de vídeo de terceiros.
    - **Nome do provedor SDN** Escolha o provedor que você está usando.
    - **Chave de licença de provedor** Insira a ID de licença que você obteve de seu contato do provedor.
    - **URL do modelo de API SDN** Insira a URL do modelo de API que você obteve de seu contato do provedor.

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell
Obter o token de ID ou o API de licença e o modelo de API de seu contato do provedor e, em seguida, execute um dos seguintes procedimentos, dependendo do provedor que você está usando:

**Hive** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
Para obter mais informações, consulte [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Se você planeja criar eventos ao vivo que usam codificadores externos, você também precisará [configurar seu provedor de eCDN com Microsoft Stream](https://docs.microsoft.com/stream/network-caching). 

### <a name="related-topics"></a>Tópicos relacionados
- [Quais são as equipes live eventos?](what-are-teams-live-events.md)
- [Planejamento de eventos ao vivo de equipes](plan-for-teams-live-events.md)
- [Configurar para equipes eventos ao vivo](set-up-for-teams-live-events.md)