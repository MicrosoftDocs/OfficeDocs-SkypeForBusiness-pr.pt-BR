---
title: Políticas de chamada no Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Saiba como criar, modificar e adicionar usuários a políticas de chamadas personalizadas no Microsoft Teams, além de várias configurações de política de chamada.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: a94bf072aa4db0ba0b3f65fb5340c22ab09581e4
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43914072"
---
<a name="calling-policies-in-microsoft-teams"></a>Políticas de chamada no Microsoft Teams
===================================

No Microsoft Teams, as políticas de chamada controlam quais recursos de chamadas e encaminhamento de chamadas estão disponíveis para os usuários. As políticas de chamada determinam se um usuário pode fazer chamadas privadas, usar o encaminhamento de chamadas ou o toque simultâneo para outros usuários ou números de telefone externos, encaminhar chamadas para correio de voz, enviar chamadas para grupos de chamadas, usar a delegação para chamadas de entrada e de saída e assim por diante. Uma política global padrão é criada automaticamente, mas os administradores também podem criar e atribuir políticas de chamadas personalizadas.

## <a name="create-a-custom-calling-policy"></a>Criar uma política de chamada personalizada

Siga estas etapas para criar uma política de chamada personalizada.

1. No centro de administração do Microsoft Teams, selecione**política de chamadas**de **voz** > .
2. Selecione **nova política**.
3. Ative os recursos que você deseja usar na sua política de chamadas. Todas as seleções são **desativadas** por padrão.
4. Para controlar se os usuários podem rotear chamadas recebidas para o correio de voz, selecione **sempre habilitado** ou **controlado pelo usuário**. Para impedir o roteamento para correio de voz, selecione **sempre desabilitado**.
5. Selecione **salvar**.

## <a name="modify-an-existing-calling-policy"></a>Modificar uma política de chamada existente

Siga estas etapas para modificar uma política de chamada existente.

1. No centro de administração do Microsoft Teams, selecione**política de chamadas**de **voz** > .
2. Clique em ao lado da política que você deseja modificar e, em seguida, selecione **Editar**.
3. Ative os recursos que você deseja usar na sua política de chamadas. Todas as seleções são **desativadas** por padrão.
4. Para controlar se os usuários podem rotear chamadas recebidas para o correio de voz, selecione **sempre habilitado** ou **controlado pelo usuário**. Para impedir o roteamento para correio de voz, selecione **sempre desabilitado**.
5. Selecione **salvar**.

## <a name="assign-a-calling-policy-to-a-user"></a>Atribuir uma política de chamada a um usuário

Siga estas etapas para atribuir uma política de chamada personalizada a um usuário.

1. No centro de administração do Microsoft Teams, selecione**política de chamadas**de **voz** > .
2. Clique em ao lado do nome da política para selecioná-lo e, em seguida, selecione **gerenciar usuários**.
3. No painel **gerenciar usuários** , procure o nome do usuário. (Você deve inserir pelo menos três caracteres.)
4. Selecione o nome do usuário e, em seguida, selecione **Adicionar**.
5. Selecione **salvar**.

## <a name="calling-policy-settings"></a>Configurações de política de chamada

Use as configurações a seguir para criar uma política de chamada personalizada.

### <a name="user-can-make-private-calls"></a>O usuário pode fazer chamadas privadas

Esta configuração controla todos os recursos de chamada no Teams. Desative essa opção para desativar toda a funcionalidade de chamada no Microsoft Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>Encaminhamento de chamadas e toque simultâneo para outros usuários

Esta configuração controla se as chamadas de entrada podem ser encaminhadas para outros usuários ou podem tocar em outra pessoa ao mesmo tempo. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Encaminhamento de chamadas e toque simultâneo para números de telefone externos

Essa configuração controla se as chamadas de entrada podem ser encaminhadas para um número externo ou podem tocar em um número externo ao mesmo tempo.

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>O correio de voz está disponível para roteamento de chamadas de entrada para usuários

Essa configuração permite que as chamadas recebidas sejam enviadas para o correio de voz. As opções válidas são:

   - **Sempre habilitado** O correio de voz está sempre disponível para chamadas recebidas. 
   - **Sempre desabilitado**  O correio de voz não está disponível para chamadas recebidas. 
   - **Controlado pelo usuário**. Os usuários podem determinar se desejam que o correio de voz esteja disponível.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>As chamadas recebidas podem ser roteadas para grupos de chamadas 

> [!Include [feature preview](includes/preview-feature.md)]

Esta configuração controla se as chamadas de entrada podem ser encaminhadas para um grupo de chamadas.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Permitir Delegação para chamadas de entrada e de saída

> [!Include [feature preview](includes/preview-feature.md)]

Essa configuração permite que as chamadas recebidas sejam roteadas a delegados, permitindo que os representantes façam chamadas de saída em nome dos usuários para os quais tenham permissões delegadas. Para obter mais informações, consulte [compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Impedir que a chamada seja ignorada e enviar chamadas por meio da PSTN 

**Quando** essa configuração é enviada, as chamadas são enviadas pela PSTN e são cobradas em vez de serem enviadas pela rede e ignorando as tarifas.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Ocupado em ocupado está disponível durante uma chamada

Ocupado em ocupado (opções de ocupado)) é uma nova configuração em políticas de chamadas de equipes que permite que você configure como as chamadas de entrada são manipuladas quando um usuário já está em uma chamada ou conferência ou tem uma chamada colocada em espera. Chamadas novas ou recebidas podem ser recusadas com um sinal de ocupado. Você pode habilitar as opções de ocupado no nível do locatário ou no nível do usuário. Independentemente de como as opções ocupadas são configuradas, os usuários de uma chamada ou conferência ou aquelas com uma chamada em espera não são impedidos de iniciar novas chamadas nem conferências. Essa configuração é desabilitada por padrão.

### <a name="allow-music-on-hold"></a>Permitir música em espera

Essas configurações permitem ativar ou desativar a música em espera quando um chamador PSTN é colocado em espera. Ele está ativado por padrão. Esta configuração não se aplica a recursos de estacionamento de chamada e chefe de chefe e só está disponível no momento pelo PowerShell. 

## <a name="see-also"></a>Confira também

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
