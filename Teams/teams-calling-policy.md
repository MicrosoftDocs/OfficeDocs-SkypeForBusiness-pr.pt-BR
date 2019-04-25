---
title: Políticas de chamada no Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/15/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Saiba mais sobre as configurações de política de chamada do Teams da Microsoft.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e56f0c89859b940a82e76f8de35ff524a757ec9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224996"
---
<a name="calling-policies-in-microsoft-teams"></a>Políticas de chamada no Microsoft Teams
==========================================

No Microsoft Teams, chamando políticas controlam quais chamadas e recursos de encaminhamento de chamadas estão disponíveis aos usuários. As políticas de chamada determinam se um usuário pode fazer chamadas privadas, use o encaminhamento de chamadas ou usam rotear as chamadas para caixa postal, chamadas de envio para grupos de chamada, toque para outros usuários ou números de telefone externo simultâneo, delegação para chamadas de entrada e saídas, e assim por diante. Uma política global de padrão é criada automaticamente, mas os administradores também podem criar e atribuir políticas personalizadas de chamada.

## <a name="create-a-custom-calling-policy"></a>Criar uma política personalizada de chamada

Siga estas etapas para criar uma política personalizada de chamada.

1. No Centro de administração do Microsoft Teams, selecione **voz** > **política de chamada**.
2. Selecione **nova política**.
3. Ative os recursos que você deseja usar na sua política de chamada. Todas as seleções estão **desligadas** por padrão.
4. Para controlar se os usuários podem rotear chamadas de entrada para a caixa postal, selecione **sempre habilitada** ou **usuário controlados**. Para impedir o roteamento para a caixa postal, selecione **sempre desabilitado**.
5. Selecione **Salvar**.

## <a name="modify-an-existing-calling-policy"></a>Modificar uma política de chamada existente

Siga estas etapas para modificar uma política de chamada existente.

1. No Centro de administração do Microsoft Teams, selecione **voz** > **política de chamada**.
2. Clique em Avançar para a política que você deseja modificar e selecione **Editar**.
3. Ative os recursos que você deseja usar na sua política de chamada. Todas as seleções estão **desligadas** por padrão.
4. Para controlar se os usuários podem rotear chamadas de entrada para a caixa postal, selecione **sempre habilitada** ou **usuário controlados**. Para impedir o roteamento para a caixa postal, selecione **sempre desabilitado**.
5. Selecione **Salvar**.

## <a name="assign-a-calling-policy-to-a-user"></a>Atribuir uma política de chamada a um usuário

Siga estas etapas para atribuir uma política de chamada personalizada a um usuário.

1. No Centro de administração do Microsoft Teams, selecione **voz** > **política de chamada**.
2. Clique em ao lado do nome de política para selecioná-lo e selecione **Gerenciar usuários**.
3. No painel de **Gerenciar usuários** , procure o nome do usuário. (Você deve inserir pelo menos três caracteres).
4. Selecione o nome do usuário e selecione **Adicionar**.
5. Selecione **Salvar**.

## <a name="calling-policy-settings"></a>Configurações de política de chamada

Use as configurações a seguir para criar uma política personalizada de chamada.

### <a name="user-can-make-private-calls"></a>Usuário pode fazer chamadas particulares

Esta configuração controla a todos os recursos de chamada em equipes. Desative essa opção para desativar a todas as funcionalidades de chamada em equipes.

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>Encaminhamento de chamadas e toque simultâneo para outros usuários

Essa configuração controla se as chamadas recebidas podem ser encaminhadas para outros usuários ou podem ligar para outra pessoa ao mesmo tempo. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Encaminhamento de chamadas e toque simultâneo aos números de telefone externo

Essa configuração controla se as chamadas recebidas podem ser encaminhadas para um número externo ou ligar para um número externo ao mesmo tempo.

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>Caixa postal está disponível para roteamento de chamadas de entrada para os usuários

Esta configuração habilita as chamadas de entrada sejam enviadas para a caixa postal. Opções válidas são:

   - **Sempre habilitada** Caixa postal sempre está disponível para chamadas de entrada. 
   - **Sempre desabilitado**  Caixa postal não está disponível para chamadas de entrada. 
   - O **usuário é controlado**. Os usuários podem determinar se querem voicemail esteja disponível.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Chamadas de entrada podem ser roteadas para chamar a grupos 

Esta configuração controla se as chamadas recebidas podem ser encaminhadas para um grupo de chamada.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Permite a delegação de chamadas de entrada e saídas

Esta configuração habilita as chamadas de entrada sejam roteadas para os representantes, permitindo a representantes para fazer chamadas de saída em nome dos usuários para o qual eles têm permissões delegadas. Para obter mais informações, consulte [compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Impedir que o desvio de Chamada Tarifada e enviar chamadas pela PSTN 

Essa configuração para **ativado** enviará chamadas pela PSTN e incorrer encargos em vez de enviá-los por meio da rede e obter isenção das tarifas.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Ocupado em ocupado está disponível durante uma chamada

Ocupado em ocupado (opções de ocupado)) é uma nova configuração de políticas de chamada que permite que você configure as chamadas de entrada como são manipuladas quando um usuário já estiver em uma chamada ou conferência ou tem uma chamada de equipes colocados em espera. Chamadas de entrada ou novas podem ser rejeitadas com um sinal de ocupado. Você pode habilitar opções de disponibilidade em um nível de locatário ou em um nível de usuário. Independentemente de como suas opções de disponibilidade são configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos desde o início de novas chamadas ou conferências. Essa configuração é desabilitada por padrão.

