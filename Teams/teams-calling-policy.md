---
title: 'Políticas de chamada em Microsoft Teams: recursos de chamada e encaminhamento de chamada'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Saiba como criar, modificar e adicionar usuários a políticas de chamada personalizadas em Microsoft Teams, bem como várias configurações de política de chamada.
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
ms.openlocfilehash: 60a6f78d99f6481f2c10db5467f3e7e7bad9f7fb
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2021
ms.locfileid: "60606950"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Chamada e encaminhamento de chamada no Teams

Em Microsoft Teams, as políticas de chamada controlam quais recursos de encaminhamento de chamada e chamada estão disponíveis para os usuários. As políticas de chamadas determinam se um usuário pode fazer chamadas privadas, usar encaminhamento de chamadas ou toque simultâneo para outros usuários ou números de telefone externos, rotear chamadas para caixa postal, enviar chamadas para grupos de chamadas, usar delegação para chamadas de entrada e saída e assim por diante.

Você pode usar a política global (padrão em toda a organização) criada automaticamente ou criar e atribuir políticas personalizadas.

## <a name="create-a-custom-calling-policy"></a>Criar uma política de chamada personalizada

Siga estas etapas para criar uma política de chamada personalizada.

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Políticas de Chamada** de  >  **Voz**.
2. Selecione **Adicionar**.
3. A ativar ou desativar os recursos que você deseja usar em sua política de chamada.
4. Para controlar se os usuários podem rotear chamadas de entrada para a caixa postal, selecione **Habilitado ou** **Controlado pelo usuário.** Para impedir o roteamento para a caixa postal, selecione **Desabilitado**.
5. Selecione **Salvar**.

## <a name="edit-a-calling-policy"></a>Editar uma política de chamada

Siga estas etapas para editar uma política de chamada existente.

1. Na navegação à esquerda do centro de administração Microsoft Teams, selecione **Políticas de Chamada** de  >  **Voz**.
2. Clique ao lado da política que você deseja modificar e selecione **Editar**.
3. Faça as alterações que você deseja e clique em **Salvar**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Atribuir uma política de chamada personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Configurações de política de chamada

Aqui estão as configurações que você pode configurar para políticas de chamada.

### <a name="make-private-calls"></a>Fazer chamadas privadas

Essa configuração controla todos os recursos de chamada Teams. Desativar isso para desativar todas as funcionalidades de chamada no Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Encaminhamento de chamada e toque simultâneo para pessoas em sua organização

Essa configuração controla se as chamadas de entrada podem ser encaminhadas para outros usuários ou podem tocar outra pessoa ao mesmo tempo.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Encaminhamento de chamadas e toque simultâneo para números de telefone externos

Essa configuração controla se as chamadas de entrada podem ser encaminhadas para um número externo ou podem tocar um número externo ao mesmo tempo.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>A caixa postal está disponível para roteamento de chamadas de entrada

Essa configuração permite que as chamadas de entrada sejam enviadas para a caixa postal. As opções válidas são:

- **Habilitado** A caixa postal está sempre disponível para chamadas de entrada.
- **Desabilitado**  A caixa postal não está disponível para chamadas de entrada.
- **Controlado pelo usuário** Os usuários podem determinar se querem que a caixa postal seja disponibilizada.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Chamadas de entrada podem ser roteados para grupos de chamadas

Essa configuração controla se as chamadas de entrada podem ser encaminhadas para um grupo de chamadas.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delegação para chamadas de entrada e saída

Essa configuração permite que as chamadas de entrada sejam roteados para representantes, permitindo que os representantes façam chamadas de saída em nome dos usuários para os quais eles delegaram permissões. Para obter mais informações, [consulte Compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Impedir o desvio de chamada e enviar chamadas por meio da PSTN

Definir isso como **On** enviará chamadas por meio da PSTN e incorre em encargos em vez de enviá-las pela rede e ignorar os pedágios.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>O ocupado ocupado está disponível quando em uma chamada

Ocupado em Ocupado (Opções de Ocupado) permite configurar como as chamadas de entrada são tratadas quando um usuário já está em uma chamada ou conferência ou tem uma chamada em espera. Chamadas novas ou de entrada podem ser rejeitadas com um sinal de ocupado ou podem ser roteadas de acordo com as configurações sem resposta do usuário. Você pode habilitar opções de ocupado no nível do locatário ou no nível do usuário. Independentemente de como suas opções de ocupado estão configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos de iniciar novas chamadas ou conferências. Essa configuração está desabilitada por padrão.

### <a name="web-pstn-calling"></a>Web PSTN calling

Essa configuração permite que os usuários chamem números PSTN usando o Teams web.

### <a name="incoming-meeting-invites-are-automatically-answered"></a>Os convites de reunião de entrada são atendidos automaticamente

Essa configuração controla se os convites de reunião de entrada são atendidos automaticamente. Ela está desativada por padrão. Lembre-se de que essa configuração se aplica somente a convites de reunião de entrada. Não se aplica a outros tipos de chamadas.

### <a name="allow-music-on-hold"></a>Permitir música em espera

Essa configuração permite ativar ou desativar a música em espera quando um chamador PSTN é colocado em espera. Ele está ligado por padrão. Essa configuração não se aplica aos recursos de estacionamento de chamada e representante de chefe e está disponível apenas por meio do PowerShell.

## <a name="related-articles"></a>Artigos relacionados

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Atribua políticas a seus usuários no Teams](policy-assignment-overview.md)
