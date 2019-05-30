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
ms.openlocfilehash: 277f5b326a2c8c4427ae4cea740630d4d1e6f0c7
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548641"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurar eventos ao vivo no Microsoft Teams

Use as configurações de eventos ao vivo do teams para definir configurações para eventos dinâmicos que são mantidos em sua organização. Você pode configurar uma URL de suporte e configurar um provedor de distribuição de vídeo de terceiros. Essas configurações se aplicam a todos os eventos dinâmicos que são criados em sua organização. 

Você pode facilmente gerenciar essas configurações no centro de administração do Microsoft Teams. No painel de navegação esquerdo, vá para**configurações de eventos ao vivo**de **reuniões** > . 

![Captura de tela das configurações de eventos ao vivo do teams] (../media/teams-live-events-settings.png "Captura de tela das configurações de eventos do teams Live que você pode configurar no centro de administração do Microsoft Teams") 

## <a name="set-up-event-support-url"></a>Configurar a URL de suporte a eventos

Esta URL é mostrada para participantes do evento ao vivo. Adicione a URL de suporte para a sua organização para dar aos participantes uma maneira de entrar em contato com o suporte durante um evento ao vivo.

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) Usar o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá para **reuniões** > **ao vivo configurações de eventos**.
2. Em **URL de suporte**, insira a URL de suporte da sua organização. 

    ![Configuração da URL de suporte para eventos dinâmicos no centro de administração] (../media/teams-live-events-settings-supporturl.png "Captura de tela da configuração da URL de suporte para eventos ao vivo") do teams

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell
Execute o seguinte:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Para obter mais informações, consulte [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurar um provedor de distribuição de vídeo de terceiros 

Se você comprou e configurou uma solução SDN (software defined Network) ou uma solução Enterprise Content Delivery Network (eCDN) por meio de um parceiro de entrega de vídeo da Microsoft, configure o provedor para eventos dinâmicos no Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) Usar o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá para **reuniões** > **ao vivo configurações de eventos**.
2. Em **provedores de distribuição de vídeo de terceiros**, conclua o seguinte: 

    ![Configurações de provedor de distribuição de vídeo de terceiros no centro de administração] (../media/teams-live-events-settings-distribution-provider.png "Captura de tela das configurações de provedor de distribuição de vídeo de terceiros para eventos dinâmicos")

    - **Usar um provedor de distribuição de terceiros** Ative esta opção para habilitar o provedor de distribuição de vídeo de terceiros.
    - **Nome do provedor do Sdn** Escolha o provedor que você está usando.
    - **Chave de licença do provedor** Digite a ID da licença que você recebeu do contato do provedor.
    - **URL do modelo de API do Sdn** Digite a URL do modelo de API que você recebeu do contato do provedor.

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell
Obtenha a ID da licença ou o token da API e o modelo de API do contato do provedor e execute um dos seguintes procedimentos, dependendo do provedor que você está usando:

**Hive** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
Para obter mais informações, consulte [set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Se você planeja criar eventos dinâmicos que usam codificadores externos, também precisará [configurar seu provedor de eCDN com o Microsoft Stream](https://docs.microsoft.com/stream/network-caching). 

### <a name="related-topics"></a>Tópicos relacionados
- [O que são os eventos ao vivo do Teams?](what-are-teams-live-events.md)
- [Planejar eventos ao vivo do Teams](plan-for-teams-live-events.md)
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)