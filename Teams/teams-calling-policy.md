---
title: Políticas de chamada no Microsoft Teams
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Saiba como criar, modificar e adicionar usuários a políticas de chamada personalizadas no Microsoft Teams, bem como várias configurações de política de chamada.
localization_priority: Normal
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
ms.openlocfilehash: 03ec48de66bc5b179b3a1d8cfe006b1789d09a33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48581059"
---
<a name="calling-policies-in-microsoft-teams"></a>Políticas de chamada no Microsoft Teams
===================================

No Microsoft Teams, as políticas de chamada controlam quais recursos de encaminhamento de chamada e chamada estão disponíveis para os usuários. As políticas de chamada determinam se um usuário pode fazer chamadas privadas, usar o encaminhamento de chamadas ou tocar simultaneamente para outros usuários ou números de telefone externos, encaminhar chamadas para a caixa postal, enviar chamadas para grupos de chamada, usar delegação para chamadas de entrada e saída e assim por diante.

Você pode usar a política global (padrão de toda a organização) criada automaticamente ou criar e atribuir políticas personalizadas.

## <a name="create-a-custom-calling-policy"></a>Criar uma política de chamada personalizada

Siga estas etapas para criar uma política de chamada personalizada.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para políticas **de Chamada**  >  **de Voz.**
2. Selecione **Adicionar**.
3. A ligue ou desligue os recursos que você deseja usar em sua política de chamada.
4. Para controlar se os usuários podem encaminhar chamadas de entrada para a caixa postal, selecione **Habilitado** ou **Controlado pelo usuário.** Para impedir o roteamento para a caixa postal, selecione **Desabilitado.**
5. Selecione **Salvar**.

## <a name="edit-a-calling-policy"></a>Editar uma política de chamada

Siga estas etapas para editar uma política de chamada existente.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, selecione políticas **de Chamada**  >  **de Voz.**
2. Clique ao lado da política que você deseja modificar e selecione **Editar.**
3. Faça as alterações que você deseja e clique em **Salvar.**

## <a name="assign-a-custom-calling-policy-to-users"></a>Atribuir uma política de chamada personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Configurações de política de chamada

Aqui estão as configurações que você pode configurar para políticas de chamada.

### <a name="make-private-calls"></a>Fazer chamadas privadas

Essa configuração controla todos os recursos de chamada no Teams. Desativar esse recurso para desativar todas as funcionalidades de chamada no Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Encaminhamento de chamada e toque simultâneo para as pessoas em sua organização

Essa configuração controla se as chamadas de entrada podem ser encaminhadas para outros usuários ou podem ligar para outra pessoa ao mesmo tempo. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Encaminhamento de chamadas e toque simultâneo para números de telefone externos

Essa configuração controla se as chamadas de entrada podem ser encaminhadas para um número externo ou podem tocar um número externo ao mesmo tempo.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>A caixa postal está disponível para roteamento de chamadas de entrada

Essa configuração permite que as chamadas de entrada sejam enviadas para a caixa postal. As opções válidas são:

- **Habilitado** A caixa postal está sempre disponível para chamadas de entrada.
- **Desabilitado**  A caixa postal não está disponível para chamadas de entrada.
- **Usuário controlado** Os usuários podem determinar se querem que a caixa postal seja disponibilizada.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>As chamadas de entrada podem ser roteada para grupos de chamadas 

> [!Include [feature preview](includes/preview-feature.md)]

Essa configuração controla se as chamadas de entrada podem ser encaminhadas para um grupo de chamadas.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Permitir delegação para chamadas de entrada e saída

> [!Include [feature preview](includes/preview-feature.md)]

Essa configuração permite que as chamadas de entrada sejam roteada para representantes, permitindo que os representantes façam chamadas de saída em nome dos usuários para os quais eles têm permissões delegadas. Para obter mais informações, [consulte Compartilhar uma linha telefônica com um representante.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Impedir o bypass de chamada tarifada e enviar chamadas pelo PSTN 

Definir essa opção **como Em** enviará chamadas pelo PSTN e taxas incorrem em vez de enviá-las pela rede e ignorar as tarifas tarifadas.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Ocupado em Ocupado está disponível durante uma chamada

Ocupado em Ocupado (Opções de Ocupado) é uma nova configuração que permite configurar como as chamadas recebidas são tratadas quando um usuário já está em uma chamada ou conferência ou tem uma chamada colocada em espera. Chamadas novas ou recebidas podem ser rejeitadas com um sinal de ocupado. Você pode habilitar as opções de ocupado no nível do locatário ou no nível do usuário. Independentemente de como suas opções de ocupado estão configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos de iniciar novas chamadas ou conferências. Essa configuração está desabilitada por padrão.

### <a name="allow-web-pstn-calling"></a>Permitir chamada PSTN Web

Essa configuração permite que os usuários liguem para números PSTN usando o cliente Web do Teams.

### <a name="allow-music-on-hold"></a>Permitir música em espera

Essa configuração permite ativar ou desativar a música em espera quando um chamador PSTN é colocado em espera. Ele está ligado por padrão. Essa configuração não se aplica aos recursos de representante do parque de chamada e do chefe, e atualmente só está disponível por meio do PowerShell.

## <a name="related-topics"></a>Tópicos relacionados

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[Atribua políticas a seus usuários no Teams](assign-policies.md)
