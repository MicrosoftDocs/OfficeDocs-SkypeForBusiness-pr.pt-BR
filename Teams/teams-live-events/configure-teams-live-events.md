---
title: Configurar eventos ao vivo no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
description: Saiba como gerenciar configurações para eventos ao vivo do Teams realizados em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ff5dada4c1f37c6afaf2948a5cef2b6169350d0
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767612"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurar eventos ao vivo no Microsoft Teams

Use as configurações de eventos ao vivo do Teams para configurar configurações para eventos ao vivo que são realizados em sua organização. Você pode configurar uma URL de suporte e configurar um provedor de distribuição de vídeo de terceiros. Essas configurações se aplicam a todos os eventos ao vivo criados em sua organização.

Você pode gerenciar facilmente essas configurações no centro de administração do Microsoft Teams. Na navegação à esquerda, acesse **Configurações de eventos do** **Meetings** >  Live.

![Captura de tela das configurações de eventos ao vivo do Teams.](../media/teams-live-events-settings-new.png "Captura de tela das configurações de eventos ao vivo do Teams que você pode configurar no centro de administração do Microsoft Teams")

## <a name="set-up-event-support-url"></a>Configurar URL de suporte ao evento

Essa URL é mostrada aos participantes do evento ao vivo. Adicione a URL de suporte para sua organização para dar aos participantes uma maneira de contatar o suporte durante um evento ao vivo.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda, acesse **Configurações de evento** **do Meetings** >  Live.
2. Em **URL de suporte**, insira a URL de suporte da sua organização.

    ![Configuração de URL de suporte para eventos ao vivo no centro de administração.](../media/teams-live-events-settings-supporturl.png "Captura de tela da configuração de URL de suporte para eventos ao vivo do Teams")

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell

Execute o seguinte:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```

Para obter mais informações, consulte [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).

## <a name="configure-a-third-party-video-distribution-provider"></a>Configurar um provedor de distribuição de vídeo de terceiros

Se você comprou e configurou uma solução SDN (rede definida por software) ou uma solução de eCDN (rede de entrega de conteúdo empresarial) por meio de um parceiro de entrega de vídeo da Microsoft, configure o provedor para eventos ao vivo no Teams.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda, acesse **Configurações de evento** **do Meetings** >  Live.
2. Em **Provedores de distribuição de vídeo de terceiros**, conclua o seguinte:

    ![Configurações do provedor de distribuição de vídeo de terceiros no centro de administração.](../media/teams-live-events-settings-distribution-provider-new.png "Captura de tela das configurações do provedor de distribuição de vídeo de terceiros para eventos ao vivo")

    - **Provedor de distribuição de terceiros** Ative este ON para habilitar o provedor de distribuição de vídeo de terceiros.
    - **Nome do provedor SDN** Escolha o provedor que você está usando.
    - **Configuração do SDN** Insira detalhes da Configuração do SDN.

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell

Obtenha a ID de licença ou o token de API e o modelo de API do seu contato com o provedor e execute um dos seguintes procedimentos, dependendo do provedor que você estiver usando:

**Microsoft eCDN**
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName microsoft
```
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
**Ramp** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

Para obter mais informações, consulte [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).

> [!NOTE]
> Se você planeja criar eventos ao vivo usando um aplicativo ou dispositivo externo, também precisará [configurar seu provedor eCDN](../teams-stream-ecdn.md).

>[!Note]
> Sua solução eCDN escolhida está sujeita aos termos de serviço e política de privacidade do provedor de terceiros selecionados, que controlarão o uso da solução do provedor eCDN. O uso da solução do provedor eCDN não estará sujeito aos termos de licenciamento de volume da Microsoft ou aos Termos de Serviços Online. Se você não concordar com os termos do provedor de terceiros, não habilite a solução eCDN no Microsoft Teams.

### <a name="related-topics"></a>Tópicos relacionados

- [O que são os eventos ao vivo do Teams?](what-are-teams-live-events.md)
- [Planejar eventos ao vivo do Teams](plan-for-teams-live-events.md)
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
