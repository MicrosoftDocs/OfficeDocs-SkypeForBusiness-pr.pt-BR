---
title: Configurar eventos ao vivo no Microsoft Teams
author: serdarsoysal
ms.author: serdars
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
description: Saiba como gerenciar configurações para Teams eventos ao vivo que são realizados em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1d1608bda574e504e6985ee55c8f06607f710a4
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046037"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Configurar eventos ao vivo no Microsoft Teams

Use Teams configurações de eventos ao vivo para definir configurações para eventos ao vivo que são realizados em sua organização. Você pode configurar uma URL de suporte e configurar um provedor de distribuição de vídeo de terceiros. Essas configurações se aplicam a todos os eventos ao vivo criados em sua organização.

Você pode gerenciar facilmente essas configurações no Microsoft Teams de administração. Na navegação à esquerda, vá para **Reuniões**  >  **Ao vivo configurações de eventos**.

![Captura de tela de Teams de eventos ao vivo.](../media/teams-live-events-settings-new.png "Captura de tela Teams configurações de eventos ao vivo que você pode configurar no Microsoft Teams de administração")

## <a name="set-up-event-support-url"></a>Configurar a URL de suporte a eventos

Essa URL é mostrada para participantes do evento ao vivo. Adicione a URL de suporte para sua organização para dar aos participantes uma maneira de contatar o suporte durante um evento ao vivo.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo Microsoft Teams.](../media/teams-logo-30x30.png) Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda, vá para **Configurações do** evento Meetings  >  **Live**.
2. Em **URL de Suporte,** insira a URL de suporte da sua organização.

    ![Configuração de URL de suporte para eventos ao vivo no centro de administração.](../media/teams-live-events-settings-supporturl.png "Captura de tela da configuração de URL de suporte para Teams eventos ao vivo")

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell

Execute o seguinte:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Para obter mais informações, [consulte Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).
## <a name="configure-a-third-party-video-distribution-provider"></a>Configurar um provedor de distribuição de vídeo de terceiros 

Se você comprou e configurou uma solução de rede definida por software (SDN) ou uma solução de rede de distribuição de conteúdo empresarial (eCDN) por meio de um parceiro de entrega de vídeo da Microsoft, configure o provedor para eventos ao vivo no Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo Microsoft Teams.](../media/teams-logo-30x30.png) Usando o Microsoft Teams de administração,

1. Na navegação à esquerda, vá para **Configurações do** evento Meetings  >  **Live**.
2. Em **Provedores de distribuição de vídeo de terceiros,** conclua o seguinte: 

    ![Configurações do provedor de distribuição de vídeo de terceiros no centro de administração.](../media/teams-live-events-settings-distribution-provider-new.png "Captura de tela das configurações do provedor de distribuição de vídeo de terceiros para eventos ao vivo")

    - **Usar um provedor de distribuição de terceiros** Ative isso para habilitar o provedor de distribuição de vídeo de terceiros.
    - **Nome do provedor SDN** Escolha o provedor que você está usando.
    - **Configuração do SDN** Insira detalhes de Configuração do SDN.
        
### <a name="using-windows-powershell"></a>Usar o Windows PowerShell
Obter a ID de licença ou token de API e modelo de API do contato do provedor e execute um dos seguintes, dependendo do provedor que você está usando:

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
**Peer5**
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName peer5 -SdnLicenseId {peer5CustomerId}
```

Para obter mais informações, [consulte Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).

> [!NOTE]
> Se você planeja criar eventos ao vivo usando um aplicativo ou dispositivo externo, também precisará configurar seu provedor [de eCDN com o Microsoft Stream.](/stream/network-caching) 

>[!Note]
> A mudança do Microsoft Stream para o [OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião](../tmr-meeting-recording-change.md) será uma abordagem em fases. No lançamento você poderá optar por aceitar essa experiência, em novembro você terá que recusar se quiser continuar usando o Stream e, no início de 2021, exigiremos que todos os clientes usem o OneDrive for Business e o Microsoft Office SharePoint Online para novas gravações de reunião.

>[!Note]
> Sua solução eCDN escolhida está sujeita aos termos de serviço e política de privacidade do provedor de terceiros selecionados, que regerão o uso da solução do provedor eCDN. Seu uso da solução do provedor eCDN não estará sujeito aos termos de licenciamento por volume da Microsoft ou aos Termos de Serviços Online. Se você não concordar com os termos do provedor de terceiros, não habilita a solução eCDN em Microsoft Teams.

### <a name="related-topics"></a>Tópicos relacionados
- [O que são os eventos ao vivo do Teams?](what-are-teams-live-events.md)
- [Planejar eventos ao vivo do Teams](plan-for-teams-live-events.md)
- [Configurar eventos ao vivo do Teams](set-up-for-teams-live-events.md)
