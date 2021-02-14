---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Saiba mais sobre a experiência do cliente do Teams e a conformidade com os modos de coexistência (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: 20d1ff52fa59f31b796d2580a0e2819c80caaf42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821021"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiência e conformidade do cliente do Teams a modos de coexistência

<a name="about-upgrade-basic"></a>

A finalidade dos modos de coexistência do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) é fornecer uma experiência simples e previsível para os usuários finais à medida que as organizações migram do Skype for Business para o Teams.  Para uma organização que  está mudando para o Teams, o modo Somente equipes é o destino final para cada usuário, embora nem todos os usuários precisem ter apenas o **Teams** (ou qualquer outro modo) ao mesmo tempo.  Antes de os usuários chegarem ao modo TeamsOnly, as organizações podem usar qualquer um dos modos de coexistência do Skype for Business para garantir uma comunicação previsível entre usuários somente do **Teams** e aqueles que ainda não estão. 

Quando um usuário está em qualquer um dos modos do Skype for Business, todos os chats de entrada e chamadas são roteados para o cliente Skype for Business do usuário. Para evitar confusão do usuário final e garantir o roteamento adequado, a funcionalidade de chamadas e chat no cliente do Teams é desabilitada quando um usuário está em qualquer um dos modos do Skype for Business. Da mesma forma, o agendamento de reunião no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab e explicitamente habilitados quando um usuário está no modo SfBWithTeamsCollabAndMeetings.

Como a presença é uma indicação de acessibilidade por meio de chat e chamada, quando o chat e as chamada são desabilitados, a própria presença no Teams (ou seja, a exibição da própria presença no cliente do Teams na imagem do usuário) também fica oculta. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Como a funcionalidade disponível no cliente do Teams muda com base no modo

A funcionalidade disponível no Teams depende do modo de coexistência do usuário, conforme definido pelo TeamsUpgradePolicy. A tabela a seguir resume o comportamento:

|Modo eficaz do usuário|Experiência no cliente do Teams|
|---|---|
|Qualquer modo do Skype for Business|As chamada, o chat e a autoexecução estão desabilitados.|
|SfBWithTeamsCollabAndMeetings|O agendamento de reunião está disponível|
|SfBWithTeamsCollab ou SfBOnly<sup>1</sup>|O agendamento de reunião não está disponível|
|||

As capturas de tela a seguir  ilustram a diferença entre o **modo Somente equipes** ou ilhas e todos os outros modos. Observe que os ícones de chat e chamada  estão disponíveis por padrão com o modo Somente do **Teams** ou Ilhas (captura de tela à esquerda), mas não com os outros modos (captura de tela à direita):

![Uma comparação lado a lado dos modos do Teams](media/teams-mode-comparison.png)

Além disso, a autoexecução não está disponível nos outros modos, conforme mostrado aqui.

![Captura de tela de autoexecução em Reuniões Primeiro](media/meetings-first-no-self-presence-general.png)
 
**Observação:** 
 <sup>1</sup> Neste momento, o SfBwithTeamsCollab e o SfBOnly se comportam da mesma forma, mas a intenção é que o modo SfBOnly também desabilite a funcionalidade Canais e Arquivos no Teams. Na medida provisória, os Canais podem ser ocultos usando a política permissões do aplicativo.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impacto do Modo em outras configurações de política
Conforme descrito acima, o modo de coexistência de um usuário afeta qual funcionalidade está disponível no cliente do Teams do usuário. Isso significa que o valor do modo pode ter precedência sobre o valor de outras configurações de política, dependendo do modo. Especificamente, o modo de coexistência afeta se as seguintes configurações de política são atendida:

|**Modalidade (Aplicativo)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Chamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Agendamento de reunião|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Os *administradores* não precisam definir explicitamente essas configurações de política ao usar o modo de co-existência, mas é importante compreender que essas configurações se comportam efetivamente da seguinte maneira para um determinado modo. 

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly ou Islands|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Desabilitado|Desabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab ou SfBOnly|Desabilitado|Desabilitado|Desabilitado|Desabilitado|
||||||

Ao usar o PowerShell, o cmdlet verifica a configuração das configurações correspondentes em `Grant-CsTeamsUpgradePolicy` TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações seriam superadas pelo TeamsUpgradePolicy e, em caso afirmativo, uma mensagem informativa é fornecida no PowerShell.  Conforme mencionado acima, não é mais necessário definir essas outras configurações de política. Veja a seguir um exemplo da aparência do aviso do PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Tópicos relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




