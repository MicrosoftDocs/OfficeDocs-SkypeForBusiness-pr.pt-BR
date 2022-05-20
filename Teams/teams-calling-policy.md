---
title: 'Políticas de chamada Microsoft Teams: recursos de chamada e encaminhamento de chamadas'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Saiba como criar, modificar e adicionar usuários a políticas de chamada personalizadas no Microsoft Teams, bem como várias configurações de política de chamada.
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a52b30e1ced457377d7dd1c820192cb856827ba
ms.sourcegitcommit: 3b86e55787c34da76428d6915964ac4f3c6239fc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2022
ms.locfileid: "65601589"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Chamadas e encaminhamento de chamadas no Teams

No Microsoft Teams, as políticas de chamada controlam quais recursos de encaminhamento de chamadas e chamadas estão disponíveis para os usuários. As políticas de chamada determinam se um usuário pode fazer chamadas privadas, usar encaminhamento de chamadas ou toque simultâneo para outros usuários ou números de telefone externos, rotear chamadas para a caixa postal, enviar chamadas para grupos de chamadas, usar delegação para chamadas de entrada e saída e assim por diante.

Você pode usar a política global (padrão de toda a organização) criada automaticamente ou criar e atribuir políticas personalizadas.

## <a name="create-a-custom-calling-policy"></a>Criar uma política de chamada personalizada

Siga estas etapas para criar uma política de chamada personalizada.

1. No painel de navegação à esquerda do Microsoft Teams de administração, vá para **políticas do** **VoiceCalling** > .
2. Selecione **Adicionar**.
3. Ative ou desative os recursos que você deseja usar em sua política de chamada.
4. Para controlar se os usuários podem encaminhar chamadas de entrada para a caixa postal, selecione **Habilitado ou** **Controlado pelo usuário**. Para evitar o roteamento para a caixa postal, selecione **Desabilitado**.
5. Selecione **Salvar**.

## <a name="edit-a-calling-policy"></a>Editar uma política de chamada

Siga estas etapas para editar uma política de chamada existente.

1. No painel de navegação esquerdo do Microsoft Teams de administração, selecione **políticas** **voiceCalling** > .
2. Clique ao lado da política que você deseja modificar e selecione **Editar**.
3. Faça as alterações desejadas e clique em **Salvar**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Atribuir uma política de chamada personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Configurações de política de chamada

Aqui estão as configurações que você pode definir para políticas de chamada.

### <a name="make-private-calls"></a>Fazer chamadas privadas

Essa configuração controla todos os recursos de chamada Teams. Desative isso para desativar todas as funcionalidades de chamada Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Encaminhamento de chamadas e toque simultâneo para as pessoas em sua organização

Essa configuração controla se as chamadas de entrada podem ser encaminhadas para outros usuários ou se podem ligar para outra pessoa ao mesmo tempo.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Encaminhamento de chamadas e toque simultâneo para números de telefone externos

Essa configuração controla se as chamadas de entrada podem ser encaminhadas para um número externo ou se podem tocar em um número externo ao mesmo tempo.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>A caixa postal está disponível para roteamento de chamadas de entrada

Essa configuração permite que chamadas de entrada sejam enviadas para a caixa postal. As opções válidas são:

- **Habilitado** A caixa postal está sempre disponível para chamadas de entrada.
- **Desativado**  A caixa postal não está disponível para chamadas de entrada.
- **Controlado pelo usuário** Os usuários podem determinar se querem que a caixa postal esteja disponível.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Chamadas de entrada podem ser roteados para grupos de chamadas

Essa configuração controla se as chamadas de entrada podem ser encaminhadas para um grupo de chamadas.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delegação para chamadas de entrada e saída

Essa configuração permite que as chamadas de entrada sejam roteados para delegados, permitindo que os representantes façam chamadas de saída em nome dos usuários para os quais eles têm permissões delegadas. Para obter mais informações, [consulte Compartilhar uma linha telefônica com um delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Impedir o bypass de chamada tarifada e enviar chamadas por meio do PSTN

Definir isso como **Ativado** enviará chamadas por meio do PSTN e incorrerá em encargos em vez de enviá-las pela rede e ignorar os pedágios.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>Ocupado em disponibilidade disponível quando em uma chamada

Ocupado em Disponibilidade (Opções de Disponibilidade) permite configurar como as chamadas de entrada são tratadas quando um usuário já está em uma chamada ou conferência ou tem uma chamada em espera. Chamadas novas ou de entrada podem ser rejeitadas com um sinal de ocupado ou podem ser roteadas de acordo com as configurações não respondidas do usuário. Você pode habilitar as opções de disponibilidade no nível do locatário ou no nível do usuário. Independentemente de como as opções de disponibilidade estão configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos de iniciar novas chamadas ou conferências. Essa configuração é desabilitada por padrão.

### <a name="web-pstn-calling"></a>Chamada PSTN Web

Essa configuração permite que os usuários chamem números PSTN usando o Teams cliente Web.

### <a name="automatically-answer-incoming-meeting-invites"></a>Responder automaticamente aos convites de reunião recebidos

Essa configuração controla se os convites de reunião de entrada são respondidos automaticamente. Ela está desativada por padrão. Lembre-se de que essa configuração se aplica somente a convites de reunião de entrada. Ele não se aplica a outros tipos de chamadas.

### <a name="allow-music-on-hold"></a>Permitir música em espera

Essa configuração permite ativar ou desativar a música em espera quando um chamador PSTN é colocado em espera. Ele é ativado por padrão. Essa configuração não se aplica aos recursos de estacionamento de chamada e representante do chefe.

### <a name="allow-sip-devices-calling"></a>Permitir chamadas de dispositivos SIP

Essa configuração permite que os usuários usem um dispositivo SIP para fazer e receber chamadas.

### <a name="spam-filtering"></a>Filtragem de spam

Essa configuração permite controlar o tipo de filtragem de Spam disponível em chamadas de entrada.

### <a name="call-recording-live-captions-and-transcription"></a>Gravação de chamadas, legendas ao vivo e transcrição

Essas configurações permitem controlar se a gravação de chamadas, as legendas ao vivo e a transcrição estão disponíveis para os usuários.

## <a name="related-articles"></a>Artigos relacionados

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy)

[Remove-CsTeamsCallingPolicy](/powershell/module/skype/remove-csteamscallingpolicy)

[Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)
