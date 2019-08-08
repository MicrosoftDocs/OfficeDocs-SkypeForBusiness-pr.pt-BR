---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Experiência do cliente do Teams e comformabilidade para modos de coexistência
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 85f74b63f465bd0004e8b9a2ef93c79b00196495
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243900"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiência e conformidade do cliente do Teams a modos de coexistência

> [!NOTE]
> Esta página descreve alterações importantes e recentemente lançadas no comportamento do cliente do teams quando os usuários estão em qualquer um dos modos do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).


A finalidade dos modos de coexistência é fornecer uma experiência simples e previsível para os usuários finais como as organizações migrando do Skype for Business para o Teams.  Para uma organização se movendo para o Microsoft Teams, o modo de TeamsOnly é o destino final de cada usuário, mas nem todos os usuários precisam ser atribuídos TeamsOnly (ou qualquer outro modo) ao mesmo tempo.  Antes de os usuários alcançarem o modo TeamsOnly, as organizações podem usar qualquer um dos modos do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantir a comunicação previsível entre os usuários que são TeamsOnly e aqueles que ainda não estão. 

Quando um usuário está em qualquer um dos modos do Skype for Business, todos os chats e chamadas recebidos são roteados para o cliente Skype for Business do usuário. Para evitar a confusão do usuário final e garantir o roteamento adequado, a chamada e a funcionalidade de chat no cliente do teams são desabilitadas quando um usuário está em qualquer um dos modos do Skype for Business. Da mesma forma, o agendamento da reunião no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab, e explicitamente habilitados quando um usuário está no modo de SfBWithTeamsCollabAndMeetings.   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Como a funcionalidade disponível no cliente do teams muda com base no modo
A funcionalidade disponível no Teams depende do modo de coexistência do usuário, conforme definido pela TeamsUpgradePolicy. A tabela a seguir resume o comportamento:

|Modo efetivo do usuário|Experiência no cliente da equipe|
|---|---|
|Qualquer modo do Skype for Business|A chamada e o chat estão desativados.|
|SfBWithTeamsCollabAndMeetings|O agendamento da reunião está disponível|
|SfBWithTeamsCollab ou SfBOnly<sup>1</sup>|O agendamento da reunião não está disponível|
|||

As capturas de tela a seguir ilustram a diferença entre o modo de TeamsOnly ou de ilhas e todos os outros modos. Observe que os ícones de chat e de chamada estão disponíveis com TeamsOnly ou o modo de ilhas (captura de tela à esquerda), mas não com os outros modos (captura de tela à direita):

![Uma comparação lado a lado dos modos de equipe](media/teams-mode-comparison.png)


 
**Observação:**
<sup>1</sup> por enquanto, SfBwithTeamsCollab e SfBOnly comportam-se da mesma maneira, mas a intenção é para o modo de SfBOnly também desativar a funcionalidade de canais e arquivos no Microsoft Teams; Contudo, no momento, não há nenhuma configuração que permita que essa funcionalidade em equipes seja desabilitada.


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

Ao usar o PowerShell, `Grant-CsTeamsUpgradePolicy` o cmdlet verifica a configuração das configurações correspondentes em TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações seriam substituídas por TeamsUpgradePolicy e, nesse caso, uma a mensagem informativa é fornecida no PowerShell.  Conforme observado acima, não é mais necessário definir essas outras configurações de política. Veja a seguir um exemplo de como é a aparência do aviso do PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>Tópicos relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




