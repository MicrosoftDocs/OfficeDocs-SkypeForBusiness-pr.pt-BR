---
title: Conferência na rede para videoconferência
ms.author: crowe
author: CarolynRowe
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: A seguir, a descrição da funcionalidade de visualização aberta para videoconferência na rede.
ms.openlocfilehash: 38b8be382ccd1b80002688cdb7fce9aa166efc2c
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369175"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>Abrir a visualização de conferências na rede para videoconferências

A visualização aberta de conferências na rede está disponível para todos os clientes. A conferência on-Network permite que as organizações enviem chamadas de videoconferências de entrada e saída para números de discagem da Microsoft por meio do roteamento direto. Essa funcionalidade não se destina a estender o suporte de videoconferência a outros números de discagem. A conferência pela rede não é suportada se é usada para rotear chamadas recebidas para o serviço de audioconferência por meio de números de telefone de discagem de terceiros.

Este artigo descreve os pré-requisitos e as etapas de configuração necessárias para habilitar a conferência na rede de sua organização.

> [!IMPORTANT]
> A conferência na rede não deve ser implantada com nenhum equipamento de telefonia na Índia.
  
## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar a conferência na rede, certifique-se de que sua organização atenda aos seguintes pré-requisitos: 

- Certifique-se de que todos os usuários de sua organização estejam habilitados, ou serão habilitados, para videoconferências no modo somente Teams. O roteamento de chamadas de videoconferência de entrada e saída para a conferência pela rede só tem suporte em reuniões de equipe.

- Atribua licenças de audioconferência a todos os usuários que usarão conferências na rede.

- Configurar o serviço de audioconferência. Para obter informações adicionais, consulte [Configurar a conferência de áudio para o Microsoft Teams](set-up-audio-conferencing-in-teams.md).

- Configure o seu controlador de borda de sessão (SBC) para roteamento direto. Para obter informações adicionais, consulte [planejar o roteamento direto](direct-routing-plan.md) e [Configurar o roteamento direto](direct-routing-configure.md). 

  Se você estiver configurando o roteamento direto somente para fins de videoconferência, será necessário concluir "etapa 1: conectar seu SBC" para conferência na rede.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>Habilitar o roteamento de chamadas discadas para a conferência de áudio da Microsoft por meio do roteamento direto 

Para direcionar as chamadas de discagem feitas por seus usuários locais para o serviço de audioconferência por meio do roteamento direto, você precisa configurar as regras de roteamento adequadas para o SBCs e os Exchange (s) filiais (s).

Você precisa configurar o equipamento de telefonia dos seus sites para direcionar chamadas para qualquer número de serviço da ponte de conferência da sua organização por meio de um tronco de roteamento direto.

Você pode encontrar os números de serviço no centro de administração do teams em **reuniões-> pontes de conferência** ou usando o cmdlet do PowerShell Get-CsOnlineDialInConferencingBridge do Skype for Business online. Para obter mais informações, consulte uma lista de [números de audioconferência no Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).

> [!NOTE]
> Este recurso não está disponível para os usuários com a licença de conferência de áudio de pagamento por minuto.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>Habilitar o roteamento de chamadas discadas da reunião do teams por meio do direcionamento direto

As chamadas de reunião discada do teams são iniciadas dentro de uma reunião da sua organização até números PSTN, incluindo chamadas para mim e chamadas para trazer novos participantes para uma reunião. 

Para habilitar o roteamento de discagem externa da reunião do teams por meio do roteamento direto, você precisa criar e atribuir uma política de roteamento de audioconferência chamada "OnlineAudioConferencingRoutingPolicy". 

A política OnlineAudioConferencingRoutingPolicy é equivalente à CsOnlineVoiceRoutingPolicy de chamadas PSTN do 1:1 via roteamento direto. A política OnlineAudioConferencingRoutingPolicy pode ser gerenciada usando os seguintes cmdlets:

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

Para obter mais informações sobre roteamento para roteamento direto, consulte [Configurar roteamento de voz para roteamento direto](direct-routing-voice-routing.md).


Para habilitar o roteamento de chamadas discadas de uma reunião por meio do direcionamento direto, você precisa: 

- Configurar as políticas de roteamento de audioconferência
- Configurar o roteamento no equipamento de telefonia da sua organização
- Adicionais Configurar um plano de discagem

Chamadas discada de reuniões do teams estão chegando do número de serviço padrão na ponte de conferência. Para obter informações adicionais sobre o número de serviço padrão da ponte de videoconferência, consulte [alterar os números de telefone na sua ponte de videoconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

### <a name="configure-audio-conferencing-routing-policies"></a>Configurar as políticas de roteamento de audioconferência

A política de roteamento de audioconferência OnlineAudioConferencingRoutingPolicy determina quais chamadas discadas de reunião são roteadas para troncos de roteamento direto. Se você estiver familiarizado com a política CsOnlineVoiceRoutingPolicy, essa política funciona de forma muito semelhante.

As etapas a seguir são necessárias para configurar as políticas de roteamento de audioconferência:
1.  Criar usos de PSTN
2.  Configurar rotas de voz
3.  Criar políticas de roteamento de voz da conferência de áudio
4.  Atribuir uma política a seus usuários


#### <a name="create-pstn-usages"></a>Criar usos de PSTN

Os usos de PSTN são coleções de rotas de voz. Quando uma chamada de discagem estiver iniciada da reunião de um determinado organizador, as rotas de voz serão usadas para determinar o caminho de roteamento da chamada com base nos usos de PSTN associados ao usuário por meio da política de roteamento de voz do usuário.

Você pode criar um uso de PSTN usando o cmdlet "Set-CsOnlinePstnUsage". Por exemplo:

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>Configurar rotas de voz

As rotas de voz determinam o gateway PSTN que deve ser usado para direcionar uma chamada com base no número de telefone discado de uma reunião do teams. As rotas de voz determinam o gateway PSTN que deve ser usado para direcionar uma determinada chamada combinando o número de telefone discado de uma reunião do teams com um padrão Regex. Durante a criação de uma rota de voz, a rota deve estar associada a um ou mais usos de PSTN.

Você pode criar uma rota de voz e definir o Regex e os gateways a serem associados à rota de voz usando o cmdlet "New-CsOnlineVoiceRoute". Por exemplo:

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>Criar políticas de roteamento de voz da conferência de áudio

As políticas de roteamento de voz de audioconferência determinam as possíveis rotas que podem ser usadas para direcionar uma chamada originada das reuniões de um organizador com base no número de telefone de destino da chamada de discagem de reunião. As políticas de roteamento de voz do áudio audioconferência são associadas a um ou mais usos de PSTN, que, por sua vez, determinam as possíveis rotas que serão tentadas para serem usadas para as chamadas discadas da reunião dos organizadores associados à política.

Você pode criar uma política de roteamento de voz de audioconferência usando o cmdlet "New-CsOnlineAudioConferencingRoutingPolicy". Por exemplo:

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

Depois que a política é atribuída a um usuário e quando uma chamada de discagem externa da reunião é iniciada a partir de uma das reuniões do usuário, as rotas de voz nos usos PSTN associados ao organizador por meio da política de roteamento de voz do usuário serão avaliadas. Se o destino da chamada discada da reunião corresponder a um Regex em uma das rotas de voz associadas ao organizador, a chamada de discagem de reunião será roteada para o gateway PSTN definido na rota de voz. Se o destino da chamada discada da reunião não corresponder a nenhuma das rotas de voz associadas ao organizador, a chamada de discagem de reunião será roteada pela Microsoft.

#### <a name="assign-a-policy-to-your-users"></a>Atribuir uma política a seus usuários

Depois que as políticas de roteamento de audioconferência são definidas, agora você pode atribuí-las aos usuários. Depois que as políticas forem atribuídas a elas, as chamadas de discagem de reunião serão avaliadas para determinar o caminho de roteamento. As políticas de roteamento de audioconferência são sempre avaliadas com base no organizador da reunião, independentemente do usuário na reunião que inicia uma chamada de discagem de reunião.

Você pode atribuir uma política de roteamento de voz de audioconferência a um usuário usando o cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy". Por exemplo:

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>Configurar o roteamento no equipamento de telefonia da sua organização

No equipamento de telefonia da sua organização, você precisa garantir que as chamadas de discagem externa da reunião roteadas pelo encaminhamento direto sejam roteadas para o destino pretendido.


### <a name="optional-configure-a-dial-plan"></a>Adicionais Configurar um plano de discagem

Um plano de discagem é um conjunto de regras de normalização que traduz os números de telefone discados por um usuário individual em um formato alternativo (geralmente E. 164) para fins de autorização de chamadas e encaminhamento de chamadas.

Por padrão, os usuários do teams podem discar para números PSTN no formato E. 164, isto é, + \<country code\> \<number\> . No entanto, os planos de discagem podem ser usados para permitir que os usuários disquem números de telefone em outros formatos, por exemplo, extensões de 4 dígitos.

Se quiser habilitar a discagem baseada na extensão por meio de conferências na rede, você pode configurar planos de discagem para que correspondam ao padrão de discagem de extensão para os intervalos de número de telefone do número de telefone de sua organização. Para configurar planos de discagem, consulte [criar e gerenciar planos de discagem](create-and-manage-dial-plans.md).


## <a name="known-issues-in-open-preview"></a>Problemas conhecidos do Open Preview

Veja a seguir uma lista de problemas conhecidos presentes atualmente na versão prévia aberta da conferência em rede. A Microsoft está trabalhando para resolver esses problemas.

| Problema | Possíveis |
| :--- | :--- |
| Chamadas discadas com IDs de chamadas anônimas/ocultas que são roteadas através da conferência pela rede não podem ser conectadas à reunião. | Se possível, defina uma configuração em seu PBX ou SBC para sempre enviar uma identificação de chamada para chamadas roteadas via Conferência na rede.|
| Em alguns casos, a mensagem de boas-vindas que é reproduzida aos usuários quando ele disca para o serviço ("bem-vindo ao serviço de audioconferência...") é truncada e os usuários não ouvem a palavra "bem-vindo".| Não há soluções alternativas para esse problema no momento. |




## <a name="related-topics"></a>Tópicos relacionados


