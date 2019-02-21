---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Experiência do cliente de equipes e conformidade aos modos de coexistência
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd81915739d9ad2087dec5b66595efd1c49e2c84
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "30120888"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Experiência e conformidade do cliente do Teams a modos de coexistência

> [!NOTE]
> Esta página descreve importantes futuras alterações no comportamento do cliente de equipes, quando os usuários estiverem em qualquer uma do Skype para modos de negócios (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).


A finalidade dos modos de coexistência é fornecer uma experiência previsível simple para usuários finais como transição de organizações do Skype para negócios às equipes.  Para uma organização mudando para equipes, o modo TeamsOnly é o destino final para cada usuário, embora nem todos os usuários precisam ser atribuídas TeamsOnly (ou qualquer outro modo) ao mesmo tempo.  Antes de usuários está atingindo o modo TeamsOnly, as organizações podem usar qualquer um do Skype para modos de negócios (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantir a comunicação entre os usuários que são TeamsOnly e aqueles que não são ainda previsível. 

Quando um usuário estiver em qualquer um do Skype para modos de negócios, todas as chamadas e chats de entrada são roteadas para Skype do usuário para o cliente de negócios. Para evitar a confusão do usuário final e garantir o roteamento apropriado, a funcionalidade de chamada e bate-papo no cliente equipes destina-se a ser desabilitado quando um usuário está em qualquer uma do Skype para modos de negócios. Da mesma forma, agendamento de reuniões em equipes é destinado a ser explicitamente desabilitado quando os usuários estiverem nos modos de SfBOnly ou SfBWithTeamsCollab e explicitamente habilitado quando um usuário está no modo de SfBWithTeamsCollabAndMeetings.  Para desabilitar automaticamente a funcionalidade de bate-papo e chamar a funcionalidade, bem como habilitar/desabilitar baseada no modo de agendamento de reunião está agora começando a distribuição para os clientes de toque.  

Antes dessa funcionalidade, a orientação da Microsoft foi garantir a experiência de usuário apropriados, definindo as configurações correspondentes na mensagem, chamar e políticas de reunião. No entanto, não havia nenhuma imposição formal, e desde que os usuários por padrão tinham acesso total a todas as funcionalidades no cliente equipes, alguns usuários podem ter retidas acesso a algumas ou todas essas experiências no cliente de equipes, independentemente do seu modo.  Como resultado, como essa funcionalidade rola check-out, alguns usuários podem ver uma alteração na sua experiência no cliente equipes conforme a experiência do usuário começa para se adequar ao seu modo.  A tabela abaixo mostra o novo comportamento:


|Modo de usuário efetivo|Experiência com o cliente de equipes|
|---|---|
|Qualquer Skype para o modo de negócios|Chamada e bate-papo<sup>1</sup> estão desabilitadas.|
|SfBWithTeamsCollabAndMeetings|Agendamento de reunião está disponível|
|SfBWithTeamsCollab ou SfBOnly<sup>2</sup>|Agendamento de reunião não está disponível|
|||

**Observações:**
<sup>1</sup> bate-papo de reunião ainda está disponível.
<sup>2</sup> no momento, SfBwithTeamsCollab e SfBOnly se comportam da mesma, mas a intenção é para o modo de SfBOnly também desativar a funcionalidade de arquivos e canais em equipes; No entanto, não há atualmente nenhuma configuração que permite essa funcionalidade em equipes a ser desabilitado.


## <a name="how-organizations-can-prepare-for-automatic-ux-conformance-to-modes"></a>Como as organizações podem preparar quanto à conformidade eu automática com modos

Antes que essa alteração aplicação, as organizações podem atingir a experiência desejada no cliente equipes usando políticas adicionais, conforme descrito nesta seção. Isso garante que a distribuição seja perfeita para usuários finais. Observe que depois que a alteração rola check-out, definir essas diretivas não será necessária.  Como alternativa, as organizações que não deseja para os usuários a funcionalidade no cliente equipes, reduziram podem deslocar seus usuários para o modo de ilhas ou TeamsOnly, no entanto, que afetará o roteamento, bem.

Para configurar manualmente a experiência do usuário final, os administradores usam as seguintes políticas e configurações:


|**Modalidade (App)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Chamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Agendamento de reuniões|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||


Os administradores devem definir cada uma dessas configurações para os seguintes valores para um determinado modo:

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly ou Ilhas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Desabilitado|Desabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab ou SfBOnly|Desabilitado|Desabilitado|Desabilitado|Desabilitado|
||||||

Antes da distribuição de conformidade automática da experiência do usuário com base em modos, o `Grant-CsTeamsUpgradePolicy` cmdlet verifica a configuração das respectivas configurações na TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas as configurações são compatíveis com o modo especificado. Se qualquer um não estejam configurado corretamente, o grant terá êxito, mas um aviso será fornecido no PowerShell indicando quais configurações específicas não estão configuradas corretamente. Abaixo é um exemplo de como o aviso do PowerShell pode parecer:


`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

*Aviso: O usuário 'user1@contoso.com' tem atualmente valores de política efetiva habilitado para: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. A curto prazo, concedendo quando TeamsUpgradePolicy com modo = SfBWithTeamsCollab a um usuário, você deve também separadamente atribuir a política para garantir que o usuário tem os valores de política efetiva desabilitado para: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. No futuro, o recurso automaticamente aceita a TeamsUpgradePolicy.*

Na visualização tal um aviso, o administrador subsequentemente deve atualizar as políticas indicadas para oferecer uma experiência de usuário compatíveis do final em equipes. Se o administrador decide não agir como resultado de aviso, os usuários ainda podem ter acesso ao chat, chamar e/ou recursos de agendamento no equipes dependendo dos valores de TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy, de reunião qual pode resultar em uma experiência de usuário final confusa.

Depois que a conformidade automática da experiência do cliente equipes com base no modo de TeamsUpgradePolicy estiver disponível, não será necessário para definir essas políticas. O valor do modo de TeamsUpgradePolicy terá precedência sobre os valores dessas configurações específicas. Conformidade automática é obtida durante a solução de diretiva com a infra-estrutura da diretiva. Em caso de conflito das configurações diferentes, o comportamento com base no modo vencerá os valores de AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling e AllowChannelMeetingScheduling. Depois que a conformidade automática é entregue, os avisos do PowerShell serão atualizados para informar ao administrador que automaticamente aplicará a experiência do cliente, apesar de todos os valores de TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy.







