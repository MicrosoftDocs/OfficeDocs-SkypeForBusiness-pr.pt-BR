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
description: O exemplo a seguir descreve a rede para Audioconferência.
ms.openlocfilehash: 9b986bb8cd4d432c563e60f03e2dcdf496749f36
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675953"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>Conferência na rede para Audioconferência

A Conferência na rede permite que as organizações enviem chamadas de entrada e Audioconferência para números de discagem da Microsoft por meio do Roteamento Direto. Essa funcionalidade não se destina a estender o suporte de Audioconferência para números de discagem de terceiros. Não há suporte para a Conferência na rede se ela for usada para rotear chamadas de entrada para o serviço Audioconferência por meio de números de telefone de discagem de terceiros ou chamadas de saída para o PSTN da Ponte do Microsoft Audioconferência.

Este artigo descreve os pré-requisitos e as etapas de configuração necessárias para habilitar a Conferência na rede para sua organização.

> [!IMPORTANT]
> A Conferência na rede NÃO deve ser implantada com nenhum equipamento de telefonia na Índia.

## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar a Conferência na rede, verifique se sua organização atende aos seguintes pré-requisitos:

- Verifique se todos os usuários em sua organização que estão habilitados ou serão habilitados para Audioconferência estão usando Teams para todas as Reuniões. O roteamento de chamadas de Audioconferência de entrada e saída por meio da Conferência na rede só é compatível com Teams reuniões.

- Atribua Audioconferência licenças a todos os usuários que usarão a Conferência na rede.

- Configure o serviço Audioconferência serviço. Para obter informações adicionais, [consulte Configurar Audioconferência para Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Configure o controlador de borda de sessão (SBC) para roteamento direto. Para obter informações adicionais, consulte [Planejar o Roteamento Direto](direct-routing-plan.md) e [Configurar o Roteamento Direto](direct-routing-configure.md).

  Se você estiver configurando o Roteamento Direto somente para fins de Audioconferência, precisará concluir apenas a "Etapa 1: Conexão seu SBC" para Conferência na rede.

## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Habilitar o roteamento de chamadas discada para o Microsoft Audioconferência roteamento direto

Para rotear chamadas discadas feitas pelos usuários locais para o serviço Audioconferência por meio do Roteamento Direto, você precisa configurar as regras de roteamento apropriadas para seus SBCs e PBXs (Exchange(s) branch privado).

Você precisa configurar o equipamento de telefonia de seus sites para rotear chamadas para qualquer número de serviço da ponte de conferência da sua organização por meio de um tronco de Roteamento Direto.

Você pode encontrar os números de serviço no centro de administração do Teams em **Meetings -> Conferencing Bridges** ou usando o cmdlet Get-CsOnlineDialInConferencingBridge do Skype for Business Online PowerShell. Para obter informações adicionais, consulte uma lista [de Audioconferência em Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Esse recurso não está disponível para usuários com a licença de pagamento por Audioconferência minuto.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Habilitar o roteamento Teams chamadas de discagem de reunião por meio do Roteamento Direto

Teams chamadas de discagem de reunião são iniciadas de dentro de uma reunião em sua organização para números PSTN, incluindo chamadas e chamadas para levar novos participantes a uma reunião.

Para habilitar Teams roteamento de discagem de reunião por meio do Roteamento Direto para usuários na rede, você precisa criar e atribuir uma política de roteamento de Audioconferência chamada "OnlineAudioConferencingRoutingPolicy".

A política OnlineAudioConferencingRoutingPolicy é equivalente à CsOnlineVoiceRoutingPolicy para chamadas PSTN 1:1 via Roteamento Direto. A política OnlineAudioConferencingRoutingPolicy pode ser gerenciada usando os seguintes cmdlets:

- New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Para obter mais informações sobre roteamento para Roteamento Direto, consulte [Configurar o roteamento de voz para Roteamento Direto](direct-routing-voice-routing.md).

Para habilitar o roteamento de chamadas discada de reunião por meio do Roteamento Direto, você precisa:

- Configurar políticas Audioconferência roteamento
- Configurar o roteamento no equipamento de telefonia da sua organização
- (Opcional) Configurar um plano de discagem

Chamadas discadas de Teams reuniões são provenientes do número de serviço padrão na ponte de conferência. Para obter informações adicionais sobre o número de serviço padrão da ponte Audioconferência, consulte Alterar os números de telefone em [sua ponte Audioconferência dados](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Configurar políticas Audioconferência roteamento

A Audioconferência de roteamento OnlineAudioConferencingRoutingPolicy determina quais chamadas discadas de reunião são roteadas para troncos de Roteamento Direto. Se você estiver familiarizado com a política CsOnlineVoiceRoutingPolicy, essa política funcionará de maneira muito semelhante.

As etapas a seguir são necessárias para configurar políticas de Audioconferência roteamento:

1. Criar usos de PSTN
1. Configurar rotas de voz
1. Criar políticas Audioconferência de roteamento de voz
1. Atribuir uma política aos usuários

#### <a name="create-pstn-usages"></a>Criar usos de PSTN

Os usos de PSTN são coleções de rotas de voz. Quando uma chamada discada é iniciada a partir da reunião de um determinado organizador, as rotas de voz serão usadas para determinar o caminho de roteamento da chamada com base nos usos PSTN associados ao usuário por meio da política de roteamento de voz do usuário.

Você pode criar um uso de PSTN usando o cmdlet "Set-CsOnlinePstnUsage". Por exemplo:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurar rotas de voz

As rotas de voz determinam o gateway PSTN que deve ser usado para rotear uma chamada com base no número de telefone discado de uma Teams reunião. As rotas de voz determinam o gateway PSTN que deve ser usado para rotear uma determinada chamada correspondendo o número de telefone discado de uma reunião Teams com um padrão regex. Ao criar uma rota de voz, a rota deve estar associada a um ou mais usos de PSTN.

Você pode criar uma rota de voz e definir o regex e os gateways a serem associados à rota de voz usando o cmdlet "New-CsOnlineVoiceRoute". Por exemplo:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Criar políticas Audioconferência de roteamento de voz

Audioconferência políticas de roteamento de voz determinam as possíveis rotas que podem ser usadas para rotear uma chamada originada das reuniões de um organizador com base no número de telefone de destino da chamada discada da reunião. Audioconferência políticas de roteamento de voz estão associadas a um ou mais usos de PSTN, que, por sua vez, determinam as possíveis rotas que serão tentadas para serem usadas para as chamadas discadas da reunião dos organizadores associados à política.

Você pode criar uma Audioconferência de roteamento de voz usando o cmdlet "New- CsOnlineAudioConferencingRoutingPolicy". Por exemplo:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Depois que a política for atribuída a um usuário e quando uma chamada de discagem de reunião for iniciada de uma das reuniões do usuário, as rotas de voz nos usos PSTN associados ao organizador por meio da política de roteamento de voz do usuário serão avaliadas. Se o destino da chamada discada da reunião corresponder a um regex em uma das rotas de voz associadas ao organizador, a chamada discada da reunião será roteada para o gateway PSTN definido na rota de voz. Se o destino da chamada discada da reunião não corresponder a nenhuma das rotas de voz associadas ao organizador, a chamada de discagem da reunião será roteada pela Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Atribuir uma política aos usuários

Depois que as Audioconferência de roteamento são definidas, agora você pode atribuí-las aos usuários. Depois que as políticas forem atribuídas a elas, as chamadas de discagem de reunião serão avaliadas em relação a ela para determinar o caminho de roteamento. Audioconferência políticas de roteamento são sempre avaliadas com base no organizador da reunião, independentemente do usuário na reunião que inicia uma chamada discada da reunião.

Você pode atribuir uma Audioconferência de roteamento de voz a um usuário usando o cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Por exemplo:

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1"
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurar o roteamento no equipamento de telefonia da sua organização

No equipamento de telefonia de sua organização, você precisa garantir que as chamadas de discagem de reunião roteados por meio do Roteamento Direto sejam roteados para o destino pretendido na rede.

### <a name="optional-configure-a-dial-plan"></a>(Opcional) Configurar um plano de discagem

Um plano de discagem é um conjunto de regras de normalização que convertem números de telefone discados por um usuário individual em um formato alternativo (normalmente E.164) para fins de autorização de chamada e roteamento de chamadas.

Por padrão, Teams usuários podem discar para números PSTN no formato E.164, ou seja, +\<country code\>\<number\>. No entanto, os planos de discagem podem ser usados para permitir que os usuários disquem números de telefone em outros formatos, por exemplo, extensões de 4 dígitos.

Se você quiser habilitar a discagem baseada em extensão por meio de conferência na rede, poderá configurar planos de discagem para corresponder o padrão de discagem de extensão aos intervalos de número de telefone do número de telefone da sua organização. Para configurar planos de discagem, consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md).

## <a name="related-topics"></a>Tópicos relacionados
