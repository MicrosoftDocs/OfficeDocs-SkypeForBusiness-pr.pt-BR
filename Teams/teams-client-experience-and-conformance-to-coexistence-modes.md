---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Experiência do cliente de equipes e conformidade aos modos de coexistência
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e62dd8a19e2207f6b40864cab19a3fda48d184fe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204648"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiência e conformidade do cliente do Teams a modos de coexistência

> [!NOTE]
> Esta página descreve alterações importantes, liberadas recentemente no comportamento do cliente de equipes, quando os usuários estiverem em qualquer uma do Skype para modos de negócios (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).


A finalidade dos modos de coexistência é fornecer uma experiência previsível simple para usuários finais como transição de organizações do Skype para negócios às equipes.  Para uma organização mudando para equipes, o modo TeamsOnly é o destino final para cada usuário, embora nem todos os usuários precisam ser atribuídas TeamsOnly (ou qualquer outro modo) ao mesmo tempo.  Antes de usuários está atingindo o modo TeamsOnly, as organizações podem usar qualquer um do Skype para modos de negócios (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantir a comunicação entre os usuários que são TeamsOnly e aqueles que não são ainda previsível. 

Quando um usuário estiver em qualquer um do Skype para modos de negócios, todas as chamadas e chats de entrada são roteadas para Skype do usuário para o cliente de negócios. Para evitar a confusão do usuário final e garantir o roteamento apropriado, a funcionalidade de chamada e bate-papo no cliente equipes está desabilitada quando um usuário está em qualquer uma do Skype para modos de negócios. Da mesma forma, o agendamento de reuniões em equipes é explicitamente desabilitado quando os usuários estiverem nos modos de SfBOnly ou SfBWithTeamsCollab e explicitamente habilitado quando um usuário está no modo de SfBWithTeamsCollabAndMeetings.   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Como a funcionalidade disponível no cliente de equipes muda com base no modo
A funcionalidade disponível nas equipes depende do modo de coexistência do usuário, como definido pelo TeamsUpgradePolicy. A tabela a seguir resume o comportamento:

|Modo de usuário efetivo|Experiência com o cliente de equipes|
|---|---|
|Qualquer Skype para o modo de negócios|Chamada e bate-papo estão desabilitadas.|
|SfBWithTeamsCollabAndMeetings|Agendamento de reunião está disponível|
|SfBWithTeamsCollab ou SfBOnly<sup>1</sup>|Agendamento de reunião não está disponível|
|||

As capturas de tela a seguintes ilustram a diferença entre modo TeamsOnly ou Ilhas e todos os outros modos. Observe que os ícones de bate-papo e chamadas estão disponíveis com TeamsOnly ou Ilhas modo (captura de tela da esquerda), mas não com outros modos (captura de tela direita):

![Mostra as comparações de modo de equipes](media/teams-mode-comparison.png)


 
**Observação:**
<sup>1</sup> no momento, SfBwithTeamsCollab e SfBOnly se comportam da mesma, mas a intenção é para o modo de SfBOnly também desativar a funcionalidade de arquivos e canais em equipes; No entanto, não há atualmente nenhuma configuração que permite essa funcionalidade em equipes a ser desabilitado.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impacto do modo em outras configurações de política
Conforme descrito acima, do impacto de modo para a coexistência do usuário a funcionalidade para a qual está disponível no cliente de equipes do usuário. Isso significa que o valor do modo pode têm precedência sobre o valor de outras configurações de política, dependendo do modo. Especificamente, o modo de coexistência impacta se as seguintes configurações de diretiva são observadas:

|**Modalidade (App)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Chamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Agendamento de reuniões|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Os administradores precisam *não* explicitamente definir essas configurações de diretiva quando usando o modo de coexistência, mas ele é importante entender que essas configurações efetivamente se comportam como a seguir para um determinado modo. 

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly ou Ilhas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Desabilitado|Desabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab ou SfBOnly|Desabilitado|Desabilitado|Desabilitado|Desabilitado|
||||||

Ao usar o PowerShell, a `Grant-CsTeamsUpgradePolicy` cmdlet verifica a configuração das respectivas configurações na TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações seriam ser substituídas pelos TeamsUpgradePolicy e em caso afirmativo, um mensagem informativa é fornecida no PowerShell.  Conforme observado anteriormente, não é necessário definir essas outras configurações de diretiva. Abaixo é um exemplo de aviso PowerShell se parece com:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>Tópicos relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




