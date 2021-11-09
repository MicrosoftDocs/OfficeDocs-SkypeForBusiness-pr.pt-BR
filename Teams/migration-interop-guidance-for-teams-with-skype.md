---
title: Migração e interoperabilidade - Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Entenda os conceitos fundamentais para gerenciar a transição da sua organização para Teams de Skype for Business.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e7138acede1f6d67d5bd13d1e5edf413389f8b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865459"
---
# <a name="coexistence-modes---reference"></a>Modos de coexistência - Referência

> [!Important] 
> - Após a aposentadoria do Skype for Business Online em 31 de julho de 2021, não é mais possível atribuir um modo de coexistência diferente do TeamsOnly a um usuário que está na nuvem. Como era o caso antes da aposentadoria, os usuários que se Skype for Business Server locais podem ser atribuídos a qualquer modo diferente *do* TeamsOnly. 

Os modos de coexistência fornecem uma experiência simples e previsível para os usuários finais à medida que as organizações transitam de Skype for Business para Teams. Para uma organização migrando para o Teams, o modo de TeamsOnly é o destino final de cada usuário, embora nem todos os usuários precisem ser atribuídos o modo TeamsOnly (ou qualquer outro) ao mesmo tempo. Antes de os usuários chegarem ao modo TeamsOnly, as organizações podem usar qualquer um dos modos Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantir uma comunicação previsível entre os usuários que são TeamsOnly e aqueles que ainda não estão.

De uma perspectiva técnica, o modo do usuário rege vários aspectos da experiência do usuário:

- *Roteamento de entrada*: Qual o cliente ( do Teams ou do Skype for Business) que recebe bate-papos e chamadas de entrada? 
- *Publicação de presença*: a presença do usuário mostrada para outros usuários é determinada com base em suas atividades no Teams ou no Skype for Business? 
- *Agendamento de reunião*: qual serviço é usado para agendar novas reuniões e garantir que o suplemento correto estará presente no Outlook? TeamsUpgradePolicy não governa a junção de reuniões. Os usuários sempre poderão *participar de* qualquer reunião, seja ela uma reunião do Skype for Business ou uma reunião do Teams.
- *Experiência do cliente*: qual funcionalidade está disponível no Temas e/ou no cliente do Skype for Business? Os usuários podem iniciar chamadas e chats em Teams, Skype for Business ou ambos? A experiência de Equipes e Canais está disponível?  

Para obter mais informações sobre o roteamento e o comportamento de presença com base no modo, consulte [Coexistência com Skype for Business](./coexistence-chat-calls-presence.md).

No entanto, do ponto de vista da experiência, o modo pode ser descrito como definindo a experiência para:
- *Chat e Chamadas*: qual o cliente usado pelo usuário ?
- *Agendamento de Reuniões*: os usuários agendam novas reuniões como reuniões do Teams ou reuniões do Skype for Business?
- *Disponibilidade da funcionalidade de colaboração no cliente do Teams*. A função Equipes & Canais e Arquivos vai estar disponível enquanto os usuários ainda estiverem usando o Skype for Business?

Os modos estão listados abaixo. Os usuários de nuvem devem ser o TeamsOnly, e os usuários que estão no local devem ser qualquer modo diferente do TeamsOnly. 
</br>
</br>

|Modo|Chamadas e Chat|Agendador de Reunião<sup>1</sup>|Equipes e Canais|Caso de Uso|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Somente é possível se o usuário não tiver uma conta local no Skype for Business Server*|Teams|Teams|Sim|Estado final depois de atualizado. O padrão para novos locatários, a menos que uma configuração híbrida seja detectada.|
|Ilhas|Qualquer das opções|Qualquer das opções|Sim|Configuração padrão para organizações híbridas. Permite que um único usuário avalie os dois clientes um junto ao outro. Bate-papos e chamadas podem chegar em qualquer dos clientes, por isso os usuários precisam sempre executar ambos. Para evitar uma experiência confusa ou indesejada do Skype for Business, comunicações externas (federadas), serviços de voz PSTN e aplicativos de voz, integração com o Office e várias outras integrações continuam a ser operadas pelo Skype for Business.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|Sim|Reuniões em primeiro lugar. Principalmente destinado para que organizações locais se beneficiem da funcionalidade das reuniões do Teams, se as mesmas ainda não estiverem prontas para migrar para a nuvem.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Sim|O ponto de partida alternativo para organizações complexas que precisam de um controle administrativo mais rígido.|
|SfBOnly|Skype for Business|Skype for Business|Não<sup>3</sup>|Cenário especializado para organizações com critérios rigorosos de controle de dados. O Teams é usado apenas para aceitar o convite para participar de reuniões agendadas por outras pessoas.|
||||||

</br>
</br>

**Observações:**

<sup>1</sup> A capacidade de ingressar em uma reunião existente (seja agendada no Teams ou no Skype for Business) não é governada pelo modo. Por padrão, os usuários sempre podem participar de qualquer reunião para a qual tenham sido convidados.

<sup>2</sup> Por padrão, ao atribuir TeamsOnly ou SfbWithTeamsCollabAndMeetings a um usuário individual, todas as reuniões do Skype for Business existentes agendadas pelo usuário para o futuro serão convertidas em reuniões do Teams. Se desejar, você pode deixar essas reuniões como reuniões do Skype for Business especificando `-MigrateMeetingsToTeams $false` ao conceder a TeamsUpgradePolicy ou desmarcando a caixa de seleção no portal de administração do Teams. A capacidade de converter reuniões de Skype for Business para Teams não está disponível ao conceder o TeamsUpgradePolicy em toda a locatário. 

<sup>3</sup>No momento, o Teams não possui a capacidade de desabilitar a função Equipes e Canais, portanto isso continua habilitado por enquanto.


## <a name="using-teamsupgradepolicy"></a>Usando TeamsUpgradePolicy

A TeamsUpgradePolicy expõe duas propriedades principais: Modo e NotifySfbUsers. 
</br>
</br>

|Parâmetro|Tipo|Valores permitidos</br>(padrão grafado em itálico)|Descrição|
|---|---|---|---|
|Modo|Enum|*Ilhas*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica em modo que o cliente deve operar.|
|NotifySfbUsers|Bool|*Falso* ou verdadeiro|Indica se deve haver um banner no cliente do Skype for Business informando ao usuário que o Teams irá substituir o Skype for Business em breve. Isso não pode ser verdadeiro se Mode=TeamsOnly.|
|||||

O Teams oferece todas as instâncias relevantes do TeamsUpgradePolicy por meio de políticas internas e de acesso somente leitura. Portanto, somente os cmdlets Get e Grant estão disponíveis. As instâncias internas estão listadas abaixo.
</br>
</br>

|Identidade|Modo|NotifySfbUsers|
|---|---|---|
|Ilhas|Ilhas|Falso|
|IslandsWithNotify|Ilhas|Verdadeiro|
|SfBOnly|SfBOnly|Falso|
|SfBOnlyWithNotify|SfBOnly|Verdadeiro|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Falso|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|Verdadeiro|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|Falso|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|Verdadeiro|
|UpgradeToTeams|TeamsOnly|Falso|
|Global</br>*Padrão*|Ilhas|Falso|
||||

Essas instâncias de política podem ser concedidas ou a usuários individuais ou a todo o locatário. Por exemplo:
- Para atualizar um usuário ($SipAddress) para Teams, conceda a instância "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Para atualizar o locatário inteiro, omita o parâmetro de identidade do comando grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>A Teams do usuário cliente ao usar Skype for Business modos

Quando um usuário está em qualquer um dos modos Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), todos os chats de entrada e chamadas são roteados para o cliente Skype for Business do usuário. Para evitar confusão do usuário final e garantir o roteamento adequado, a funcionalidade de chamada e de chat no cliente Teams é desabilitada automaticamente quando um usuário está em qualquer um dos modos Skype for Business de usuário. Da mesma forma, o agendamento de reunião no Teams será desabilitado automaticamente quando os usuários estiverem nos modos SfBOnly ou SfBWithTeamsCollab e habilitados automaticamente quando um usuário estiver no modo de SfBWithTeamsCollabAndMeetings. Para mais detalhes, confira[Experiência e conformidade do cliente do Teams a modos de coexistência](./teams-client-experience-and-conformance-to-coexistence-modes.md).

> [!Note] 
> - Antes da receber a implementação automática do Equipes e Canais do Teams, os modos SfbOnly e SfBWithTeamsCollab se comportam da mesma maneira.


## <a name="detailed-mode-descriptions"></a>Descrições detalhadas do modo
</br>
</br>

|Modo|Explicação|
|---|---|
|**Ilhas**</br>(somente no local)|Um usuário executa o Skype for Business e Teams lado a lado. Este usuário:</br><ul><li>Pode iniciar chats e chamadas VoIP no cliente do Skype for Business ou no do Teams. Observação: os usuários com o Skype for Business hospedado no local não podem iniciar do Teams para alcançar outro usuário do Skype for Business, independentemente do modo do destinatário.<li>Recebe chats & chamadas VoIP iniciadas no Skype for Business por outro usuário no cliente do seu Skype for Business.<li>Recebe chats & chamadas VoIP iniciadas no Teams por outro usuário no cliente do seu Teams se eles estiverem no *mesmo locatário*.<li>Recebe chats & chamadas VoIP iniciadas no Teams por outro usuário no cliente do seu Skype for Business se eles estiverem em um *locatário federado*. <li>Possui a funcionalidade PSTN, como indicado abaixo:<ul><li>Quando o usuário está hospedado no Skype for Business no local e o tem o Enterprise Voice, as chamadas de PSTN são sempre iniciadas e recebidas no Skype for Business.<li>Quando o usuário é hospedado no Skype for Business Online e tem o Sistema de Telefonia Microsoft, o usuário sempre inicia e recebe chamadas PSTN no Skype for Business:<ul><li>Isso acontece se o usuário tem um Plano de Chamadas da Microsoft ou se conecta à rede PSTN por meio de Skype for Business Cloud Connector Edition ou uma implantação local do Skype for Business Server (voz híbrida).<li>**Observação: Sistema de Telefonia roteamento direto não é suportado no modo Ilhas.**</ul></ul><li>Recebe filas de chamadas da Microsoft e chamadas de Atendimento Automático Skype for Business:<ul><li>Telefone números atribuídos a Filas de Chamadas e Atendimento **Automático** não podem ser Sistema de Telefonia números de Roteamento Direto no modo Ilhas.</ul></ul><li>Pode agendar reuniões no Teams ou no Skype for Business (e verá os dois plug-ins por padrão).<li>Pode entrar em qualquer reunião do Skype for Business ou do Teams; a reunião será aberta no respectivo cliente.</ul>|
|**SfBOnly**</br>(somente no local)|Um usuário que executa apenas o Skype for Business. Este usuário:</br><ul><li>Pode iniciar chats e chamadas somente no Skype for Business.<li>Recebe todos os chat por chat ou chamadas no cliente do Skype for Business, independentemente de onde foi iniciado, a menos que o iniciador seja um usuário do Teams com Skype for Business hospedado no local.*<li>Só pode agendar reuniões do Skype for Business, mas pode entrar em reuniões do Skype for Business ou do Teams.</br>\** Usar o modo de Ilhas com usuários locais não é recomendável em combinação com outros usuários no modo SfBOnly. Se um usuário Teams com o Skype for Business no local iniciar uma chamada ou um chat para um usuário SfBOnly, o usuário SfBOnly não poderá ser alcançada e receberá um chat ou email de chamada perdido.*|
|**SfBWithTeamsCollab**</br>(somente no local)|Um usuário executa o Skype for Business e Teams lado a lado. Este usuário:</br><ul><li>Tem a funcionalidade de um usuário no modo SfBOnly.<li>Possui o Teams ativado somente para colaboração em grupo (Canais); chat/chamadas/agendamento de reunião estão desabilitados.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>(somente no local)|Um usuário executa o Skype for Business e Teams lado a lado. Este usuário:<ul><li>Tem a funcionalidade de chat e de chamada do usuário no modo SfBOnly.<li>Tem o Teams habilitado para colaboração em grupo (Canais, incluindo conversas de canal); o chat e as chamadas estão desabilitados.<li>Pode agendar reuniões apenas no Teams, mas pode participar de reuniões do Skype for Business ou do Teams.</ul>|
|**TeamsOnly**</br>(somente usuários de nuvem)|Um usuário executa apenas o Teams. Este usuário:<ul><li>Recebe conversas e chamadas no cliente do seu Teams, independentemente de onde foram iniciadas.<li>Pode iniciar chats e chamadas somente no Teams.<li>Pode agendar reuniões somente no Teams, mas pode participar de reuniões do Skype for Business ou do Teams.<li>Pode continuar a usar os telefones IP do Skype for Business.<br><br>*O uso do modo TeamsOnly em combinação com outros usuários no modo Ilhas não é recomendado até que Teams adoção seja saturada; ou seja, todos os usuários do modo Ilhas usam e monitoram ativamente os clientes Teams e Skype for Business. Se um usuário do TeamsOnly iniciar uma chamada ou um chat para um usuário de Ilhas, essa chamada ou chat será adado no cliente de Teams do usuário das Ilhas; se o usuário das Ilhas não usar ou monitorar Teams, esse usuário aparecerá offline e não poderá ser alcançada pelo usuário do TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Tópicos relacionados

[Coexistência com o Skype for Business](./coexistence-chat-calls-presence.md)

[Experiência e conformidade do cliente do Teams a modos de coexistência](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
