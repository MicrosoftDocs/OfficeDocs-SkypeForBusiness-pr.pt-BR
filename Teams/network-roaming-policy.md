---
title: Política de roaming de rede
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Saiba como gerenciar as configurações da política de roaming de rede do Teams.
ms.openlocfilehash: 684bb9f30abb6a474582d83614d0e259ed44b21a
ms.sourcegitcommit: 4af3638637456f21bc97f510ed9d2f7ff2da07e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2022
ms.locfileid: "63660716"
---
# <a name="manage-video-and-media-settings-with-the-network-roaming-policy"></a>Gerenciar configurações de vídeo e mídia com a política de roaming de rede

Além de gerenciar as configurações de vídeo e mídia com políticas de reunião, agora você pode controlar dinamicamente o uso dos seguintes atributos usados pelo cliente Microsoft Teams usando o TeamsNetworkRoamingPolicy: 

- Vídeo IP
- Taxa de bits de mídia

Essa política permite atribuir configurações a sites de rede. O cliente Teams irá escolher dinamicamente as configurações com base no site de rede ao qual ele se conecta. Quando o cliente Teams entrar em um site de rede com uma política de roaming atribuída, essa política será usada. Se não houver política atribuída, os valores definidos na política de reunião serão usados. Para obter mais informações sobre as configurações de áudio e vídeo da política de reunião, confira [Configurações de política de reunião para áudio e vídeo](meeting-policies-audio-and-video.md).

## <a name="configure-the-teamsnetworkroamingpolicy"></a>Configurar o TeamsNetworkRoamingPolicy

Para configurar o TeamsNetworkRoamingPolicy, use os seguintes cmdlets do PowerShell:

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)

O TeamsNetworkRoamingPolicy contém os seguintes parâmetros:

- AllowIPVideo – Essa configuração controla se o vídeo pode ser habilitado em reuniões hospedadas por um usuário e em chamadas individuais e de grupo iniciadas por um usuário.

- MediaBitRateKb – Esta configuração determina a taxa média total de bits da mídia para as transmissões de compartilhamento de áudio, vídeo e aplicativos baseados em vídeo em chamadas e reuniões do usuário.

Depois de configurar a política, atribua-a a um ou mais sites de rede usando o cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) da seguinte forma:

```PowerShell
 Set-CsTenantNetworkSite -NetworkRoamingPolicy
 ``` 
 
 Para remover uma política de um site de rede, use o seguinte cmdlet:
 
 ```PowerShell
 Set-CsTenantNetworkSite -NetworkRoamingPolicy $null
 ```

Para habilitar a política de roaming de rede para usuários que não estão habilitados para voz corporativa, você também deve habilitar a configuração AllowNetworkConfigurationSettingsLookup em TeamsMeetingPolicy. Essa configuração está desativada por padrão.

Para obter mais informações sobre como criar sites de rede, confira [Configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md). 

## <a name="examples"></a>Exemplos

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## <a name="supported-clients"></a>Clientes com suporte

- Windows 
- Área de trabalho do MacOS

## <a name="known-issues"></a>Problemas conhecidos

Ao especificar New- e Get-CsTeamsNetworkRoamingPolicy no Teams Online PowerShell v 2.0.0, você verá dados extras sendo exibidos.


## <a name="related-topics"></a>Tópicos relacionados

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)
- [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)