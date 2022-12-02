---
title: 'Políticas de chamada no Microsoft Teams: recursos de chamada e encaminhamento de chamadas'
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: a02df903574c7e7db796294ad90c9e05ab732eb0
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245691"
---
# <a name="calling-policies-calling-and-call-forwarding-features-in-teams"></a>Políticas de chamada: recursos de chamada e encaminhamento de chamadas no Teams

No Microsoft Teams, as políticas de chamada controlam quais recursos de encaminhamento de chamadas e chamadas estão disponíveis para os usuários. As políticas de chamada determinam se um usuário pode fazer chamadas privadas, usar encaminhamento de chamadas ou toque simultâneo para outros usuários ou números de telefone externos, rotear chamadas para a caixa postal, enviar chamadas para grupos de chamadas, usar delegação para chamadas de entrada e saída e assim por diante.

Você pode usar a política global (padrão em toda a organização) criada automaticamente ou criar e atribuir políticas personalizadas.

## <a name="create-a-custom-calling-policy"></a>Criar uma política de chamada personalizada

Siga estas etapas para criar uma política de chamada personalizada.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **políticas de Chamada de** **Voz** > .
2. Selecione **Adicionar**.
3. Ative ou desative os recursos que você deseja usar em sua política de chamada.
    - Por exemplo, para controlar se os usuários podem rotear chamadas de entrada para a caixa postal, selecione **Habilitado** ou **Controlado pelo usuário**. Para impedir o roteamento para a caixa postal, selecione **Não habilitado**.
4. Selecione **Salvar**.

## <a name="edit-a-calling-policy"></a>Editar uma política de chamada

Siga estas etapas para editar uma política de chamada existente.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **Políticas de Chamada de** **Voz** > .
2. Clique ao lado da política que você deseja modificar e selecione **Editar**.
3. Faça as alterações desejadas e clique em **Salvar**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Atribuir uma política de chamada personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Configurações de política de chamada

Aqui estão as configurações que você pode configurar para políticas de chamada.

### <a name="make-private-calls"></a>Fazer chamadas privadas

Essa configuração controla todos os recursos de chamada no Teams. Desative isso para desativar todas as funcionalidades de chamada no Teams.

### <a name="cloud-recording-for-calling"></a>Gravação de nuvem para chamada

Essa configuração controla se os usuários podem gravar chamadas. Isso está desativado por padrão.

### <a name="transcription"></a>Transcrição

Essa configuração controla se a transcrição de chamadas está disponível para seus usuários. Isso está desativado por padrão.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Encaminhamento de chamadas e toque simultâneo para pessoas em sua organização

Essa configuração controla se as chamadas recebidas podem ser encaminhadas para outros usuários ou podem ligar para outra pessoa em sua organização ao mesmo tempo. Isso está ativado por padrão.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Encaminhamento de chamadas e toque simultâneo para números de telefone externos

Essa configuração controla se as chamadas recebidas podem ser encaminhadas para um número externo ou podem tocar um número externo ao mesmo tempo. Isso está ativado por padrão.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>A caixa postal está disponível para roteamento de chamadas de entrada

Essa configuração permite que chamadas de entrada sejam enviadas para a caixa postal. A configuração padrão é **controlada pelo usuário**. As opções válidas são:

- **Habilitado** A caixa postal está sempre disponível para chamadas de entrada.
- **Não habilitado**  A caixa postal não está disponível para chamadas de entrada.
- **Controlado pelo usuário** Os usuários podem determinar se querem que a caixa postal esteja disponível.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>As chamadas de entrada podem ser roteadas para grupos de chamadas

Essa configuração controla se as chamadas recebidas podem ser encaminhadas para um grupo de chamadas. Isso é ativado por padrão.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delegação para chamadas de entrada e saída

Essa configuração permite que as chamadas de entrada sejam roteadas para delegados, permitindo que os delegados façam chamadas de saída em nome dos usuários para os quais eles delegaram permissões. Essa configuração é ativada por padrão. Para obter mais informações, consulte [Compartilhar uma linha telefônica com um delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Impedir o bypass de pedágio e enviar chamadas por meio do PSTN

Definir isso como **Ativado** enviará chamadas por meio do PSTN e incorrerá em encargos em vez de enviá-las pela rede e ignorar os pedágios. Essa configuração está desativada por padrão.

### <a name="music-on-hold-for-pstn-calls"></a>Música em espera para chamadas PSTN

Essa configuração permite que você ative ou desative a música em espera quando um chamador PSTN é colocado em espera. Ele está ativado por padrão. Essa configuração não se aplica aos recursos de representante do parque e do chefe. Leia mais sobre como [configurar músicas personalizadas](music-on-hold.md).

### <a name="busy-on-busy-when-in-a-call"></a>Ocupado em ocupado quando em uma chamada

Ocupado quando em uma chamada (também chamada de "opções ocupadas") permite configurar como as chamadas de entrada são tratadas quando um usuário já está em uma chamada ou conferência ou tem uma chamada colocada em espera. Chamadas novas ou de entrada podem ser rejeitadas com um sinal ocupado ou podem ser roteadas de acordo com as configurações sem resposta do usuário. Independentemente de como suas opções ocupadas estão configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos de iniciar novas chamadas ou conferências. Essa configuração é definida como **Não habilitada** por padrão.

- **Não habilitado** Nenhuma opção ocupada está habilitada e chamadas novas ou de entrada ainda podem ir para o usuário enquanto o usuário já estiver em uma chamada.
- **Habilitado** Chamadas novas ou de entrada serão rejeitadas com um sinal ocupado.
- **Sem resposta** As configurações sem resposta do usuário serão usadas, como roteamento para caixa postal ou encaminhamento para outro usuário.

### <a name="web-pstn-calling"></a>Chamada web PSTN

Essa configuração permite que os usuários chamem números PSTN usando o cliente Web do Teams. Isso está ativado por padrão.

### <a name="real-time-captions-in-teams-calls"></a>Legendas em tempo real em chamadas do Teams

Essa configuração controla se as legendas em tempo real nas chamadas do Teams estão disponíveis para seus usuários. Isso é ativado por padrão.

### <a name="automatically-answer-incoming-meeting-invites"></a>Responder automaticamente aos convites de reunião de entrada

Essa configuração controla se os convites de reunião de entrada são respondidos automaticamente. Ela está desativada por padrão. Tenha em mente que essa configuração se aplica apenas a convites de reunião de entrada. Não se aplica a outros tipos de chamadas.

### <a name="spam-filtering"></a>Filtragem de spam

Essa configuração permite controlar o tipo de filtragem de spam disponível em chamadas recebidas. As verificações básicas e do Captcha Interactive Voice (IVR) podem ser executadas. Isso é ativado por padrão.

### <a name="sip-devices-can-be-used-for-calls"></a>Dispositivos SIP podem ser usados para chamadas

Essa configuração permite que os usuários usem um dispositivo SIP para fazer e receber chamadas. Isso é desativado por padrão.

### <a name="open-apps-in-browser-for-incoming-pstn-calls"></a>Abrir aplicativos no navegador para chamadas PSTN de entrada

Essa configuração controla se os aplicativos são abertos automaticamente no navegador para chamadas PSTN de entrada para seus usuários. Isso pode ser usado para passar o número de telefone de um chamador de entrada para um aplicativo para encontrar o registro de cliente associado enquanto a chamada está ocorrendo. Essa configuração está desativada por padrão.

Se ativado, um link para o aplicativo precisará ser dado na **URL para abrir aplicativos no navegador para a caixa de chamadas PSTN de entrada** . Você pode usar o espaço reservado {phone} para passar o número de telefone (no formato E.164) para a URL fornecida. Ou você pode fornecer uma URL genérica sem qualquer espaço reservado. Isso simplesmente iniciará a URL listada.

![Captura de tela de Abrir aplicativos no navegador para a configuração de política de chamadas PSTN de entrada.](media/teams-open-apps-in-browser-pstn.png)

## <a name="related-articles"></a>Artigos relacionados

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Atribua políticas a seus usuários no Teams](policy-assignment-overview.md)

[Opções de conectividade PSTN](pstn-connectivity.md)

[Configurar configurações de chamada para seus usuários](user-call-settings.md)
