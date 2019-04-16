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
ms.openlocfilehash: 20dc75dfeb39fbd7a00e6c389dc923617265cc0b
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869802"
---
<a name="calling-policies-in-microsoft-teams"></a>Políticas de chamada no Microsoft Teams
==========================================

No Microsoft Teams, chamando políticas controlam quais chamadas e recursos de encaminhamento de chamadas estão disponíveis aos usuários. As políticas de chamada determinam se um usuário pode fazer chamadas privadas, use o encaminhamento de chamadas ou usam rotear as chamadas para caixa postal, chamadas de envio para grupos de chamada, toque para outros usuários ou números de telefone externo simultâneo, delegação para chamadas de entrada e saídas, e assim por diante. Uma política global de padrão é criada automaticamente, mas os administradores também podem criar e atribuir políticas personalizadas de chamada.

## <a name="calling-policy-settings"></a>Configurações de política de chamada

|Configuração de política de chamada | Descrição |
|-----------------------|-------------|
|Usuário pode fazer chamadas particulares | Controla a todos os recursos de chamada em equipes. Desativar Isso desativará todas as funcionalidades de chamada em equipes.|
|Encaminhamento de chamadas e toque simultâneo para outros usuários | Controla se as chamadas de entrada podem ser encaminhadas para outros usuários ou podem ligar para outra pessoa ao mesmo tempo. |
|Encaminhamento de chamadas e toque simultâneo aos números de telefone externo | Controla se as chamadas de entrada podem ser encaminhadas para um número externo ou ligar para um número externo ao mesmo tempo.|
|Caixa postal está disponível para roteamento de chamadas de entrada para os usuários | Chamadas de entrada permite que sejam enviadas para a caixa postal. Opções válidas são **sempre habilitada**, **sempre desabilitados**ou **usuário controlados**. |
|Chamadas de entrada podem ser roteadas para chamar a grupos | Controla se as chamadas recebidas podem ser encaminhadas para um grupo de chamada.  |
|Permite a delegação de chamadas de entrada e saídas | Permite que as chamadas de entrada sejam roteadas para os representantes; permite que representantes para fazer chamadas de saída em nome dos usuários para o qual eles têm permissões delegadas. |
|Impedir que o desvio de Chamada Tarifada e enviar chamadas pela PSTN | Essa configuração para **ativado** enviará chamadas através de PSTN e incorrer encargos em vez de utilizar a rede e obter isenção das tarifas. |
|Ocupado em ocupado está disponível durante uma chamada.| Configura as chamadas recebidas como são manipulados quando um usuário já estiver em uma chamada ou conferência. Chamadas de entrada ou novas podem ser rejeitadas com um sinal de ocupado. |

### <a name="busy-options-busy-on-busy-setting"></a>Opções de ocupado (ocupado na configuração ocupado)

Opções de disponibilidade é uma nova configuração em equipes chamadas diretivas que permite que você configure as chamadas de entrada como são manipuladas quando um usuário já estiver em uma chamada ou conferência ou colocou uma chamada em espera. Chamadas de entrada ou novas podem ser rejeitadas com um sinal de ocupado. Você pode habilitar opções de disponibilidade em um nível de locatário ou em um nível de usuário. 

Independentemente de como suas opções de disponibilidade são configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos desde o início de novas chamadas ou conferências.

Você pode usar o ocupado na configuração ocupada em chamar as configurações de diretiva para configurar as opções de disponibilidade. Essa configuração é desabilitada por padrão.

## <a name="create-a-custom-calling-policy"></a>Criar uma política personalizada de chamada

Siga estas etapas para criar uma nova política personalizada chamada.

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
