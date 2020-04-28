---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Saiba mais sobre a experiência do cliente e a conformidade do teams nos modos de coexistência (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
localization_priority: Normal
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
ms.openlocfilehash: 0c67046128c79608f19a4a1f4474164a949f37ef
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903356"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiência e conformidade do cliente do Teams a modos de coexistência

<a name="about-upgrade-basic"></a>

A finalidade dos modos de coexistência do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) é fornecer uma experiência simples e previsível para os usuários finais como as organizações migrando do Skype for Business para o Teams.  Para uma organização se movendo para o Microsoft Teams, o modo **somente Teams** é o destino final de cada usuário, mas nem todos os usuários precisam ter **somente equipes** atribuídas (ou qualquer outro modo) ao mesmo tempo.  Antes de os usuários alcançarem o modo TeamsOnly, as organizações podem usar qualquer um dos modos de coexistência do Skype for Business para garantir a comunicação previsível entre os usuários que são **somente equipes** e os que ainda não estão. 

Quando um usuário está em qualquer um dos modos do Skype for Business, todos os chats e chamadas recebidos são roteados para o cliente Skype for Business do usuário. Para evitar a confusão do usuário final e garantir o roteamento adequado, a chamada e a funcionalidade de chat no cliente do teams são desabilitadas quando um usuário está em qualquer um dos modos do Skype for Business. Da mesma forma, o agendamento da reunião no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab, e explicitamente habilitados quando um usuário está no modo de SfBWithTeamsCollabAndMeetings.

Como a presença é uma indicação de acessibilidade por meio de chat e chamadas, quando o chat e as chamadas são desabilitados, a auto-instalação no Microsoft Teams (ou seja, a exibição da própria presença de uma no cliente do teams na imagem do usuário) também está oculta. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Como a funcionalidade disponível no cliente do teams muda com base no modo

A funcionalidade disponível no Teams depende do modo de coexistência do usuário, conforme definido pela TeamsUpgradePolicy. A tabela a seguir resume o comportamento:

|Modo efetivo do usuário|Experiência no cliente da equipe|
|---|---|
|Qualquer modo do Skype for Business|As chamadas, os chats e a presença automática são desabilitados.|
|SfBWithTeamsCollabAndMeetings|O agendamento da reunião está disponível|
|SfBWithTeamsCollab ou SfBOnly<sup>1</sup>|O agendamento da reunião não está disponível|
|||

As capturas de tela a seguir ilustram a diferença entre **somente as equipes** ou o modo de **ilhas** e todos os outros modos. Observe que os ícones de chat e de chamada estão disponíveis por padrão com **apenas Teams** ou modo de **ilhas** (captura de tela à esquerda), mas não com os outros modos (captura de tela à direita):

![Uma comparação lado a lado dos modos de equipe](media/teams-mode-comparison.png)

Além disso, a própria presença não está disponível nos outros modos, conforme mostrado aqui.

![Captura de tela de presença automática em reuniões primeiro](media/meetings-first-no-self-presence-general.png)
 
**Observação:**
<sup>1</sup> no momento, SfBwithTeamsCollab e SfBOnly se comportam da mesma maneira, mas a intenção é para o modo de SfBOnly também desabilitar a funcionalidade de canais e arquivos no Microsoft Teams. No ínterim, os canais podem ser ocultos usando a política de permissões do aplicativo.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impacto do modo em outras configurações de política
Conforme descrito acima, o modo de coexistência de um usuário afeta a funcionalidade disponível no cliente do teams do usuário. Isso significa que o valor de Mode pode prevalecer sobre o valor de outras configurações de política, dependendo do modo. Especificamente, o modo de coexistência impacta se as seguintes configurações de política são atendidas:

|**Modalidade (app)**|**Política. setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Chamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Agendamento de reunião|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Os administradores *não* precisam definir explicitamente essas configurações de política ao usar o modo de coexistência, mas é importante entender que essas configurações se comportam de forma eficaz para um determinado modo. 

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly ou ilhas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Desabilitado|Desabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab ou SfBOnly|Desabilitado|Desabilitado|Desabilitado|Desabilitado|
||||||

Ao usar o PowerShell, `Grant-CsTeamsUpgradePolicy` o cmdlet verifica a configuração das configurações correspondentes em TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações seriam substituídas por TeamsUpgradePolicy e, nesse caso, uma mensagem informativa é fornecida no PowerShell.  Conforme observado acima, não é mais necessário definir essas outras configurações de política. Veja a seguir um exemplo de como é a aparência do aviso do PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Tópicos relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




