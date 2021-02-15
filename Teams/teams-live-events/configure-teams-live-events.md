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
- enabler-strategic
description: Saiba como gerenciar as configurações de eventos ao vivo do Teams que são realizados em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c62b7ed2afcfdb9baa779c57f3fcf566295053b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831191"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurar eventos ao vivo no Microsoft Teams

Use as configurações de eventos ao vivo do Teams para definir configurações para eventos ao vivo que são realizados em sua organização. Você pode configurar uma URL de suporte e configurar um provedor de distribuição de vídeo de terceiros. Essas configurações se aplicam a todos os eventos ao vivo criados em sua organização.

Você pode gerenciar facilmente essas configurações no Centro de administração do Microsoft Teams. No painel de navegação esquerdo, vá para **configurações de** eventos do Meetings  >  **Live.**

![Captura de tela das configurações de eventos ao vivo do Teams](../media/teams-live-events-settings.png "Captura de tela das configurações de eventos ao vivo do Teams que você pode configurar no Centro de administração do Microsoft Teams")

## <a name="set-up-event-support-url"></a>Configurar a URL de suporte a eventos

Essa URL é mostrada aos participantes do evento ao vivo. Adicione a URL de suporte da sua organização para dar aos participantes uma maneira de contatar o suporte durante um evento ao vivo.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá para **Configurações do** evento Meetings  >  **Live.**
2. Em **URL de** Suporte, insira a URL de suporte da sua organização.

    ![Configuração da URL de suporte para eventos ao vivo no centro de administração](../media/teams-live-events-settings-supporturl.png "Captura de tela da configuração de URL de suporte para eventos ao vivo do Teams")

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell

Execute o seguinte:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Para obter mais informações, [consulte Set-CsTeamsMeetingBroadcastConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurar um provedor de distribuição de vídeo de terceiros 

Se você comprou e configurou uma solução SDN (rede definida por software) ou uma solução de rede de distribuição de conteúdo corporativo (ECDN) por meio de um parceiro de distribuição de vídeo da Microsoft, configure o provedor para eventos ao vivo no Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](../media/teams-logo-30x30.png) Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá para **Configurações do** evento Meetings  >  **Live.**
2. Em **provedores de distribuição de vídeo de terceiros,** conclua o seguinte: 

    ![Configurações do provedor de distribuição de vídeo de terceiros no centro de administração](../media/teams-live-events-settings-distribution-provider.png "Captura de tela das configurações do provedor de distribuição de vídeo de terceiros para eventos ao vivo")

    - **Usar um provedor de distribuição de terceiros** Ative esse recurso para habilitar o provedor de distribuição de vídeo de terceiros.
    - **Nome do provedor SDN** Escolha o provedor que você está usando.
    - **Chave de licença do provedor** Insira a ID de licença que você recebeu do contato do provedor.
    - **URL do modelo de API SDN** Insira a URL do modelo de API que você recebeu do contato do provedor.

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell
Receba a ID de licença ou o token de API e o modelo de API do contato do provedor e execute um dos seguintes recursos, dependendo do provedor que você está usando:

**Hive** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Riverbed** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

Para obter mais informações, [consulte Set-CsTeamsMeetingBroadcastConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)

> [!NOTE]
> Se você planeja criar eventos ao vivo usando um aplicativo ou dispositivo externo, também precisará configurar seu provedor [de eCDN com o Microsoft Stream.](https://docs.microsoft.com/stream/network-caching) 

>[!Note]
> A mudança do Microsoft Stream para o [OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião](../tmr-meeting-recording-change.md) será uma abordagem em fases. No lançamento você poderá optar por aceitar essa experiência, em novembro você terá que recusar se quiser continuar usando o Stream e, no início de 2021, exigiremos que todos os clientes usem o OneDrive for Business e o Microsoft Office SharePoint Online para novas gravações de reunião.

### <a name="related-topics"></a>Tópicos relacionados
- [O que são os eventos ao vivo do Teams?](what-are-teams-live-events.md)
- [Planejar eventos ao vivo do Teams](plan-for-teams-live-events.md)
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
