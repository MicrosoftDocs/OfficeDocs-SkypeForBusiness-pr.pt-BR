---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Saiba mais sobre a experiência do cliente do Teams e a conformidade com os modos de coexistência (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91ea07d74bf9b08f627d86191ea08fc0eda1ac4c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605830"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiência e conformidade do cliente do Teams a modos de coexistência

<a name="about-upgrade-basic"></a>

A finalidade dos modos de coexistência do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) é fornecer uma experiência simples e previsível para os usuários finais à medida que as organizações fazem a transição do Skype for Business para o Teams.  Para uma organização migrando para o Teams, o modo Somente equipes é o destino final para cada usuário, embora nem todos os usuários precisem ser atribuídos apenas ao **Teams** (ou qualquer outro modo) ao mesmo tempo.  Antes de os usuários alcançarem o modo TeamsOnly, as organizações podem usar qualquer um dos modos de coexistência do Skype for Business para garantir uma comunicação previsível  entre os usuários que são apenas teams e aqueles que ainda não estão. 

Quando um usuário está em qualquer um dos modos Skype for Business, todos os chats e chamadas de entrada são roteados para o cliente Skype for Business usuário. Para evitar confusão do usuário final e garantir o roteamento adequado, a funcionalidade de chamada e chat no cliente do Teams é desabilitada quando um usuário está em qualquer um dos modos Skype for Business aplicativo. Da mesma forma, o agendamento de reuniões no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab e explicitamente habilitados quando um usuário está no modo SfBWithTeamsCollabAndMeetings.

Como a presença é uma indicação de acessibilidade por meio de chat e chamada, quando o chat e a chamada são desabilitados, a auto-presença no Teams (ou seja, a exibição da própria presença no cliente do Teams na imagem do usuário) também fica oculta. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Como a funcionalidade disponível no cliente do Teams muda com base no modo

A funcionalidade disponível no Teams depende do modo de coexistência do usuário, conforme definido por TeamsUpgradePolicy. A tabela a seguir resume o comportamento:

|Modo efetivo do usuário|Experiência no cliente do Teams|
|---|---|
|Qualquer Skype for Business padrão|Chamadas, chat e autoatendimento estão desabilitados.|
|SfBWithTeamsCollabAndMeetings|O agendamento de reunião está disponível|
|SfBWithTeamsCollab ou SfBOnly<sup>1</sup>|O agendamento de reunião não está disponível|
|||

As capturas de tela a seguir ilustram a diferença entre o modo **Somente Equipes** ou **Ilhas** e todos os outros modos. Observe que os ícones de chat e chamada estão disponíveis por padrão com o modo **Somente Equipes** ou Ilhas (captura de tela à esquerda), mas não com os outros modos (captura de tela à direita):

![Uma comparação lado a lado dos modos do Teams.](media/teams-mode-comparison.png)

Além disso, a auto-presença não está disponível nos outros modos, conforme mostrado aqui.

![Captura de tela da auto-presença no Meetings First.](media/meetings-first-no-self-presence-general.png)
 
**Nota:**
 <sup>1</sup> Neste momento, SfBwithTeamsCollab e SfBOnly se comportam da mesma forma, mas a intenção é que o modo SfBOnly também desabilite a funcionalidade Canais e Arquivos no Teams. Nesse ínterim, os canais podem ser ocultos usando a política de Permissões de Aplicativo.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impacto do modo em outras configurações de política
Conforme descrito acima, o impacto no modo de coexistência de um usuário é qual funcionalidade está disponível no cliente do Teams do usuário. Isso significa que o valor do modo pode ter precedência sobre o valor de outras configurações de política, dependendo do modo. Especificamente, o modo de coexistência afeta se as seguintes configurações de política são respeitadas:

|**Modalidade (Aplicativo)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Chamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Agendamento de reunião|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Os administradores  não precisam definir explicitamente essas configurações de política ao usar o modo de coexistência, mas é importante entender que essas configurações se comportam efetivamente da seguinte maneira para um determinado modo. 

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly ou Ilhas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Desabilitado|Desabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab ou SfBOnly|Desabilitado|Desabilitado|Desabilitado|Desabilitado|
||||||

Ao usar o PowerShell, `Grant-CsTeamsUpgradePolicy` o cmdlet verifica a configuração das configurações correspondentes em TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações seriam substituídas pelo TeamsUpgradePolicy e, nesse caso, uma mensagem informativa é fornecida no PowerShell.  Conforme mencionado acima, não é mais necessário definir essas outras configurações de política. A seguir está um exemplo da aparência do aviso do PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Tópicos relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)