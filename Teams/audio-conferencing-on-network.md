---
title: Conferência na rede para Audioconferência
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: O seguinte descreve On-network para Audioconferência.
ms.openlocfilehash: c6820bade333b6672d00e4f52a361280c10c8771
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055661"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>Conferência na rede para Audioconferência

A Conferência na rede permite que as organizações enviem chamadas de Audioconferência de entrada e saída para números de discagem da Microsoft por meio do Roteamento Direto. Esse recurso não se destina a estender o suporte da Audioconferência para números de discagem de terceiros. A Conferência na rede não será suportada se ela for usada para rotear chamadas de entrada para o serviço de Audioconferência por meio de números de telefone de discagem de terceiros ou chamadas de saída para o PSTN da Ponte de Audioconferência da Microsoft.

Este artigo descreve os pré-requisitos e as etapas de configuração necessárias para habilitar a Conferência na rede para sua organização.

> [!IMPORTANT]
> A Conferência na rede NÃO deve ser implantada com qualquer equipamento de telefonia na Índia.
  
## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar a Conferência na rede, certifique-se de que sua organização atenda aos seguintes pré-requisitos:

- Certifique-se de que todos os usuários da sua organização que estão habilitados ou serão habilitados para Audioconferência estão usando Teams para todas as Reuniões. O roteamento de chamadas de Audioconferência de entrada e saída por meio de Conferência na rede só é suportado para reuniões Teams de entrada.

- Atribua licenças de Audioconferência a todos os usuários que usarão Conferência na rede.

- Configurar o serviço de Audioconferência. Para obter informações adicionais, [consulte Configurar Audioconferência para Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Configurar o Controlador de Borda de Sessão (SBC) para Roteamento Direto. Para obter informações adicionais, consulte [Plan Direct Routing](direct-routing-plan.md) and Configure Direct [Routing](direct-routing-configure.md).

  Se você estiver configurando o Roteamento Direto somente para fins de Audioconferência, será necessário concluir apenas a "Etapa 1: Conexão seu SBC" para Conferência na rede.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Habilitar o roteamento de chamadas discar para a Audioconferência da Microsoft por meio do Roteamento Direto

Para rotear chamadas discadas feitas por seus usuários locais para o serviço de Audioconferência por meio de Roteamento Direto, você precisa configurar regras de roteamento apropriadas para seus SBCs e pbxs (pbxs) de filial Exchange privada.

Você precisa configurar o equipamento de telefonia de seus sites para rotear chamadas para qualquer número de serviço da ponte de conferência da sua organização por meio de um tronco de Roteamento Direto.

Você pode encontrar os números de serviço no centro de administração Teams **em Pontes** de Conferência de Reuniões -> ou usando o cmdlet do Skype for Business Online PowerShell Get-CsOnlineDialInConferencingBridge. Para obter informações adicionais, consulte uma lista de números de [Audioconferência em Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Esse recurso não está disponível para usuários com a licença de Audioconferência paga por minuto.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Habilitar o roteamento Teams chamadas discagem de reunião por meio do Roteamento Direto

Teams chamadas de discagem de reunião são iniciadas de dentro de uma reunião em sua organização para números PSTN, incluindo chamadas de chamada e chamadas para trazer novos participantes para uma reunião.

Para habilitar Teams roteamento de discagem de reunião por meio do Roteamento Direto para usuários na rede, você precisa criar e atribuir uma política de roteamento de Audioconferência chamada "OnlineAudioConferencingRoutingPolicy".

A política OnlineAudioConferencingRoutingPolicy é equivalente à CsOnlineVoiceRoutingPolicy para chamadas PSTN 1:1 via Roteamento Direto. A política OnlineAudioConferencingRoutingPolicy pode ser gerenciada usando os seguintes cmdlets:

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Para obter mais informações sobre roteamento para Roteamento Direto, consulte [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).

Para habilitar o roteamento de chamadas discagem de reunião por meio do Roteamento Direto, você precisa:

- Configurar políticas de roteamento de audioconferência
- Configurar o roteamento no equipamento de telefonia da sua organização
- (Opcional) Configurar um plano de discagem

Chamadas discar de Teams reuniões vêm do número de serviço padrão na ponte de conferência. Para obter informações adicionais sobre o número de serviço padrão da ponte de Audioconferência, consulte Alterar os números de telefone em sua ponte [de Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Configurar políticas de roteamento de audioconferência

A política de roteamento de Audioconferência OnlineAudioConferencingRoutingPolicy determina quais chamadas de discagem de reunião são roteados para troncos de Roteamento Direto. Se você estiver familiarizado com a política CsOnlineVoiceRoutingPolicy, essa política funcionará de maneira muito semelhante.

As etapas a seguir são necessárias para configurar políticas de roteamento de Audioconferência:

1. Criar usos PSTN
1. Configurar rotas de voz
1. Criar políticas de roteamento de voz de audioconferência
1. Atribuir uma política aos usuários

#### <a name="create-pstn-usages"></a>Criar usos PSTN

Os usos de PSTN são coleções de rotas de voz. Quando uma chamada discada é iniciada a partir da reunião de um determinado organizador, as rotas de voz serão usadas para determinar o caminho de roteamento da chamada com base nos usos PSTN associados ao usuário por meio da política de roteamento de voz do usuário.

Você pode criar um uso PSTN usando o cmdlet "Set-CsOnlinePstnUsage". Por exemplo:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurar rotas de voz

As rotas de voz determinam o gateway PSTN que deve ser usado para rotear uma chamada com base no número de telefone discado de uma reunião Teams. As rotas de voz determinam o gateway PSTN que deve ser usado para rotear uma determinada chamada, correspondendo ao número de telefone discado de uma reunião Teams com um padrão regex. Ao criar uma rota de voz, a rota deve estar associada a um ou mais usos de PSTN.

Você pode criar uma rota de voz e definir o regex e os gateways a serem associados à rota de voz usando o cmdlet "New-CsOnlineVoiceRoute". Por exemplo:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Criar políticas de roteamento de voz de audioconferência

As políticas de roteamento de voz de audioconferência determinam as possíveis rotas que podem ser usadas para rotear uma chamada proveniente das reuniões de um organizador com base no número de telefone de destino da chamada discada da reunião. As políticas de roteamento de voz de audioconferência estão associadas a um ou mais usos de PSTN, que, por sua vez, determinam as possíveis rotas que serão tentadas para serem usadas para as chamadas de discagem de reunião dos organizadores associados à política.

Você pode criar uma política de roteamento de voz de Audioconferência usando o cmdlet "New-CsOnlineAudioConferencingRoutingPolicy". Por exemplo:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Depois que a política é atribuída a um usuário e quando uma chamada discada de reunião é iniciada em uma das reuniões do usuário, as rotas de voz nos usos PSTN associados ao organizador por meio da política de roteamento de voz do usuário serão avaliadas. Se o destino da chamada discada da reunião corresponde a um regex em uma das rotas de voz associadas ao organizador, a chamada discada da reunião será roteada para o gateway PSTN definido na rota de voz. Se o destino da chamada discada da reunião não corresponder a nenhuma das rotas de voz associadas ao organizador, a chamada discada da reunião será roteada pela Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Atribuir uma política aos usuários

Depois que as políticas de roteamento de Audioconferência são definidas, agora você pode atribuí-las aos usuários. Depois que as políticas são atribuídas a elas, as chamadas discadas da reunião serão avaliadas em relação a ela para determinar o caminho de roteamento. As políticas de roteamento de audioconferência sempre são avaliadas com base no organizador da reunião, independentemente do usuário na reunião que inicia uma chamada discada de reunião.

Você pode atribuir uma política de roteamento de voz de Audioconferência a um usuário usando o cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Por exemplo:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurar o roteamento no equipamento de telefonia da sua organização

No equipamento de telefonia da sua organização, você precisa garantir que as chamadas de discagem de reunião roteados por Roteamento Direto sejam roteados para o destino pretendido na rede.

### <a name="optional-configure-a-dial-plan"></a>(Opcional) Configurar um plano de discagem

Um plano de discagem é um conjunto de regras de normalização que convertem números de telefone discados por um usuário individual em um formato alternativo (normalmente E.164) para fins de autorização de chamada e roteamento de chamadas.

Por padrão, Teams usuários podem discar para números PSTN no formato E.164, ou seja, + \<country code\> \<number\> . No entanto, os planos de discagem podem ser usados para permitir que os usuários disquem números de telefone em outros formatos, por exemplo, extensões de 4 dígitos.

Se quiser habilitar a discagem baseada em extensão por meio de conferência na rede, você pode configurar planos de discagem para corresponder o padrão de discagem de extensão aos intervalos de número de telefone do número de telefone da sua organização. Para configurar planos de discagem, consulte [Create and manage dial plans](create-and-manage-dial-plans.md).

## <a name="related-topics"></a>Tópicos relacionados
