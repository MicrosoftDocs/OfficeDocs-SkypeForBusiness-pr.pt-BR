---
title: Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Orientação para gerenciar a transição para o Microsoft Teams do Skype for Business
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.teamsupgrade.overview
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6656cab6918cfa0b04da28f0197137a300bbf79
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207187"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business

> [!Tip] 
> Assista à sessão a seguir para saber mais sobre [coexistência e](https://aka.ms/teams-upgrade-coexistence-interop) interoperabilidade

Como uma organização com o Skype for Business começa a adotar equipes, os administradores podem gerenciar a experiência do usuário em sua organização usando o conceito de "modo" de coexistência, que é uma propriedade de TeamsUpgradePolicy. Usando o modo, os administradores gerenciam a interoperabilidade e a migração à medida que gerenciam a transição do Skype for Business para o Teams.  O modo de um usuário determina onde o cliente entra chats e chamadas e em que serviço (Teams ou Skype for Business) novas reuniões estão agendadas. Ele também controla qual funcionalidade está disponível no cliente do teams. 


## <a name="fundamental-concepts"></a>Conceitos fundamentais

1.  ** Interoperabilidade: 1 a 1 comunicação entre um usuário do Lync/Skype for Business e um usuário do teams.

2.  *Federação* : comunicação entre usuários de locatários diferentes.

3.  Todos os usuários do teams têm uma conta do Skype for Business subjacente que está "hospedada" online ou local:
    - Os usuários que já usam o Skype for Business online usam a conta online existente.
    - Os usuários que já usam o Skype for Business/Lync local usam a conta local existente.
    - Os usuários que não puderem detectar uma conta existente do Skype for Business terão uma conta do Skype for Business online provisionada automaticamente quando o usuário do teams for criado.

4.  Se você tiver uma implantação local do Skype for Business ou do Lync, e quiser que esses usuários sejam usuários do Teams, você deve, no mínimo, garantir que o Azure AD Connect esteja sincronizando o atributo msRTCSIP-DeploymentLocator no AAD, para que o Teams/Skype for Business O online detecta corretamente seu ambiente local. Além disso, para mover qualquer usuário para o modo somente Teams (ou seja, atualizar um usuário), *você deve primeiro configurar o modo híbrido do Skype for Business*. Para obter mais detalhes, consulte [Configurar o Azure ad Connect para Skype for Business e Teams](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  A interoperabilidade entre equipes e usuários do Skype for Business só é possível *se o usuário do teams estiver hospedado online no Skype for Business*. O usuário do Skype for Business do destinatário pode ser hospedado no local (e requer a configuração do Skype for Business Hybrid) ou online. Os usuários que são hospedados no Skype for Business local podem usar o Microsoft Teams no modo de ilhas (definido mais tarde neste documento), mas não podem usar o Microsoft Teams para interoperabilidade ou Federação com outros usuários que usam o Skype for Business.  

6.  O comportamento de atualização e interoperabilidade é determinado com base no modo de coexistência de um usuário, descrito mais tarde abaixo. O modo é gerenciado pelo TeamsUpgradePolicy. 

7.  A atualização de um usuário para o modo TeamsOnly garante que todos os chats e chamadas recebidos sempre irão parar no cliente da equipe do usuário, independentemente do cliente do qual ele originou. Esses usuários também agendarão todas as novas reuniões no Teams. Para estar no modo TeamsOnly, um usuário deve estar online no Skype for Business. Isso é necessário para garantir a interoperabilidade, a Federação e a administração total do usuário do teams. Para atualizar um usuário para o TeamsOnly:
    - Se o usuário estiver hospedado no Skype for Business online (ou nunca tiver uma conta do Skype), conceda a eles TeamsUpgradePolicy o Mode = TeamsOnly usando a instância "UpgradeToTeams" usando o PowerShell ou use o centro de administração do teams para selecionar o modo de TeamsOnly.
    - Se o usuário for hospedado no local, use `Move-CsUser` as ferramentas de administração local para mover o usuário para o Skype for Business online.  Se você tiver o Skype for Business Server 2019 ou o CU8 para o Skype for Business Server 2015, poderá `-MoveToTeams` especificar a `Move-CsUser` opção para mover o usuário diretamente para o Microsoft Teams como parte da mudança online. Essa opção também migrará as reuniões do usuário para o Microsoft Teams. Se `-MoveToTeams` não estiver especificado ou não estiver disponível, depois `Move-CsUser` de concluído, atribua o modo TeamsOnly para aquele usuário usando o PowerShell ou o centro de administração do teams. Para obter mais detalhes, consulte [mover usuários entre locais e na nuvem](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Para obter mais detalhes sobre a migração de reuniões, consulte [usando o serviço de migração de reunião (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

8.  Para usar o sistema telefônico da Microsoft com o Teams, os usuários devem estar no modo TeamsOnly (ou seja, hospedado no Skype for Business Online e atualizados para o Microsoft Teams) e devem ser configurados para o [Roteamento direto](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) do sistema de telefone da Microsoft (que permite que você use o sistema telefônico com seus próprios troncos SIP e SBC) ou ter um plano de chamadas do Office 365. Não há suporte para o roteamento direto do sistema telefônico da Microsoft no modo de ilhas.    

9.  Agendar reuniões de equipes com videoconferências (discagem ou discagem por PSTN) está disponível independentemente de o usuário estar hospedado no Skype for Business online ou no local do Skype for Business no local. 


## <a name="coexistence-modes"></a>Modos de coexistência

A interoperabilidade e a migração são gerenciadas com base no "modo de coexistência" usando o TeamsUpgradePolicy. Os modos de coexistência fornecem uma experiência simples e previsível para os usuários finais como organizações que migram do Skype for Business para o Teams. Para uma organização se movendo para o Microsoft Teams, o modo TeamsOnly é o destino final de cada usuário, mas nem todos os usuários precisam ter TeamsOnly (ou qualquer modo) atribuídos ao mesmo tempo. Antes de os usuários alcançarem o modo TeamsOnly, as organizações podem usar qualquer um dos modos do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantir a comunicação previsível entre os usuários que são TeamsOnly e aqueles que ainda não estão.


De uma perspectiva técnica, o modo de um usuário rege vários aspectos da experiência do usuário:

- *Roteamento de entrada*: em que cliente (Teams ou Skype for Business) faz chats recebidos e chama Land? 
- *Publicação de presença*: é a presença do usuário que é mostrada para outros usuários com base em suas atividades no Microsoft Teams ou no Skype for Business? 
- *Agendamento de reuniões*: qual serviço é usado para agendar novas reuniões e garantir que o suplemento adequado está presente no Outlook? Observe que o TeamsUpgradePolicy não controla o ingresso na reunião. Os usuários sempre ** podem ingressar em qualquer reunião, seja uma reunião do Skype for Business ou uma reunião do teams.
- *Experiência do cliente*: qual funcionalidade está disponível no Teams e/ou no cliente do Skype for Business? Os usuários podem iniciar chamadas e chats no Teams, no Skype for Business ou em ambos? A experiência do teams & Channels está disponível?  

Para obter mais detalhes sobre o comportamento de roteamento e presença com base no modo, consulte [coexistência com o Skype for Business](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

No entanto, de uma perspectiva da experiência, o modo pode mais simplesmente ser descrito como definir a experiência para:
- *Chat e chamadas*: qual cliente usa o usuário?
- *Agendamento de reunião*: os usuários agendam novas reuniões como Teams ou reuniões do Skype for Business?
- *Disponibilidade da funcionalidade de colaboração no cliente do teams*. O Microsoft Teams & a funcionalidade de canais e arquivos disponíveis enquanto os usuários ainda têm o Skype for Business?

Os modos estão listados abaixo.
</br>
</br>

|Modo|Chamadas e chats|Agendamento de reunião<sup>1</sup>|Canais & do teams|Caso de uso|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Requer Home no Skype for Business Online*|Microsoft Teams|Microsoft Teams|Sim|O estado final da atualização. Também o padrão para novos locatários com <assentos de 500.|
|McDonald|Destas|Destas|Sim|Configuração padrão. Permite que um único usuário avalie os dois clientes lado a lado. Chats e chamadas podem chegar em qualquer um dos clientes, portanto os usuários sempre devem executar ambos os clientes. Para evitar uma experiência confusa ou regressiva de Skype for Business, comunicações externas (federadas), serviços de voz PSTN e aplicativos de voz, integração do Office e várias outras integrações continuam a ser administradas pelo Skype for Business.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Microsoft Teams|Sim|"Reuniões primeiro". Principalmente para organizações locais se beneficiarem da funcionalidade de reunião do Teams, se elas ainda não estiverem prontas para mover chamadas para a nuvem.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Sim|Ponto de partida alternativo para organizações complexas que precisam de controle administrativo mais restrito.|
|SfBOnly|Skype for Business|Skype for Business|Não<sup>3</sup>|Cenário especializado para organizações com requisitos estritos em relação ao controle de dados. O Teams é usado apenas para ingressar em reuniões agendadas por outras pessoas.|
||||||

</br>
</br>

**Informa**

<sup>1</sup> a capacidade de ingressar em uma reunião existente (seja agendada no Teams ou no Skype for Business) não é regida pelo modo. Por padrão, os usuários sempre podem ingressar em qualquer reunião para a qual tenham sido convidados.

<sup>2</sup> por padrão, ao atribuir TeamsOnly ou SfbWithTeamsCollabAndMeetings a um usuário individual, todas as reuniões do Skype for Business existentes agendadas pelo usuário para o futuro são convertidas em reuniões de equipe. Se quiser, você pode deixar essas reuniões como reuniões do Skype for Business especificando `-MigrateMeetingsToTeams $false` ao conceder TeamsUpgradePolicy ou desmarcando a caixa de seleção no portal de administração do teams.   Observe que a capacidade de converter reuniões do Skype for Business para o Teams não é avaialble ao conceder TeamsUpgradePolicy de acordo com o locatário. 

<sup></sup> no momento, o Teams não tem a capacidade de desabilitar a funcionalidade de equipes e canais, portanto, ele permanece habilitado por enquanto.



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: gerenciamento da migração e coexistência

TeamsUpgradePolicy expõe duas propriedades principais: Mode e NotifySfbUsers. 
</br>
</br>

|Parâmetro|Tipo|Valores permitidos</br>(padrão em itálico)|Descrição|
|---|---|---|---|
|Modo|Possuem|*McDonald*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica o modo em que o cliente deve ser executado.|
|NotifySfbUsers|Bool|*Falso* ou verdadeiro|Indica se uma faixa deve ser mostrada no cliente Skype for Business informando ao usuário que o Microsoft Teams vai substituir o Skype for Business em breve. Isso não pode ser verdadeiro se Mode = TeamsOnly.|
|||||

O Teams fornece todas as instâncias relevantes do TeamsUpgradePolicy por meio de políticas internas e somente leitura. Portanto, apenas Get e Grant cmdlets estão disponíveis. As instâncias internas estão listadas abaixo.
</br>
</br>

|Identity|Modo|NotifySfbUsers|
|---|---|---|
|McDonald|McDonald|False|
|IslandsWithNotify|McDonald|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|Global</br>*Padrão*|McDonald|False|
||||

Essas instâncias de política podem ser concedidas a usuários individuais ou com base em todo o locatário. Por exemplo:
- Para atualizar um usuário ($SipAddress) para o Microsoft Teams, conceda a instância "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Para atualizar o locatário inteiro, omita o parâmetro Identity do comando Grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>Considerações de Federação

A Federação do teams para outro usuário usando o Skype for Business exige que o usuário do teams seja hospedado online no Skype for Business. Por fim, os usuários do teams hospedados no Skype for Business local poderão se federar com usuários do Microsoft Teams.

O TeamsUpgradePolicy rege o roteamento para chats e chamadas federados e de entrada. O comportamento de roteamento federado é o mesmo dos cenários do mesmo locatário, *exceto no modo de ilhas*.  Quando os destinatários estão no modo de ilhas: 
- Chats e chamadas iniciadas do teams Land no SfB se o destinatário estiver em um *locatário federado*.
- Chats e chamadas iniciadas do teams Land nas equipes se o destinatário estiver no *mesmo locatário*.
- Chats e chamadas iniciados a partir do SfB sempre se encontram no Skype for Business.

Para obter mais detalhes, consulte [coexistência com o Skype for Business](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>A experiência do usuário do cliente do teams ao usar os modos de SfB
Quando um usuário está em qualquer um dos modos do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), todos os chats recebidos e as chamadas são roteados para o cliente Skype for Business do usuário. Para evitar a confusão do usuário final e garantir o roteamento adequado, a chamada e a funcionalidade de chat no cliente do teams são automaticamente desabilitadas quando um usuário está em qualquer um dos modos do Skype for Business. Da mesma forma, o agendamento da reunião no Teams é automaticamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab e habilitados automaticamente quando um usuário está no modo de SfBWithTeamsCollabAndMeetings. Para obter detalhes, consulte [experiência do cliente e conformidade do teams para modos de coexistência](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Antes da entrega da imposição automática de equipes e canais, os modos SfbOnly e SfBWithTeamsCollab se comportam da mesma maneira.


## <a name="detailed-mode-descriptions"></a>Descrições do modo detalhado
</br>
</br>

|Modo|Explicação|
|---|---|
|**McDonald**</br>assume|Um usuário executa o Skype for Business e o Teams lado a lado. Este usuário:</br><ul><li>Pode iniciar chats e chamadas VoIP em um cliente Skype for Business ou Teams. Observação: os usuários com o Skype for Business hospedado no local não podem iniciar no Microsoft Teams para entrarem em outro usuário do Skype for Business, independentemente do modo do destinatário.<li>Recebe chats & chamadas VoIP iniciadas no Skype for Business por outro usuário no cliente Skype for Business.<li>Recebe chats & chamadas VoIP iniciadas no Teams por outro usuário em seu cliente de equipes se elas estiverem no *mesmo locatário*.<li>Recebe chats & chamadas VoIP iniciadas no Teams por outro usuário em seu cliente Skype for Business se elas estiverem em um *locatário federado*. <li>Tem a funcionalidade PSTN, conforme observado abaixo:<ul><li>Quando o usuário é hospedado no Skype for Business local e tem Enterprise Voice, as chamadas PSTN são sempre iniciadas e recebidas no Skype for Business.<li>Quando o usuário é hospedado no Skype for Business Online e tem o Microsoft Phone System, o usuário sempre inicia e recebe chamadas PSTN no Skype for Business:<ul><li>Isso acontece independentemente de o usuário ter um plano de chamadas da Microsoft ou se conecta à rede PSTN via Skype for Business Cloud Connector Edition ou uma implantação local do Skype for Business Server (voz híbrida).<li>**Observação: o roteamento direto do Microsoft Teams Phone System não é compatível com o modo de ilhas.**</ul></ul><li>Recebe filas de chamadas da Microsoft e chamadas de atendedor automático no Skype for Business.<li>Pode agendar reuniões no Microsoft Teams ou no Skype for Business (e você verá ambos os plug-ins por padrão).<li>Pode participar de qualquer reunião do Skype for Business ou do teams; a reunião será aberta no respectivo cliente.</ul>|
|**SfBOnly**|Um usuário executa somente o Skype for Business. Este usuário:</br><ul><li>Pode iniciar chats e chamadas apenas a partir do Skype for Business.<li>Recebe qualquer chat/chamada em seu cliente Skype for Business, independentemente de onde for iniciado, a menos que o iniciador seja um usuário do teams com o Skype for Business hospedado em local. *Pode agendar apenas reuniões do Skype for Business, mas pode ingressar em reuniões do Skype for Business ou do teams. <li> </br> *Usar o modo de ilhas com usuários locais não é recomendado em combinação com outros usuários no modo SfBOnly. Se um usuário do teams com o Skype for Business hospedado no local iniciar uma chamada ou um chat para um usuário do SfBOnly, o usuário do SfBOnly não será alcançável e receberá um chat ou uma chamada de email perdida. *|
|**SfBWithTeamsCollab**|Um usuário executa o Skype for Business e o Teams lado a lado. Este usuário:</br><ul><li>Tem a funcionalidade de um usuário no modo SfBOnly.<li>Com o Microsoft Teams habilitado somente para colaboração em grupo (canais); o agendamento de chat/chamadas/reunião está desabilitado.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Um usuário executa o Skype for Business e o Teams lado a lado. Este usuário:<ul><li>Tem a funcionalidade de chat e chamadas do usuário no modo SfBOnly.<li>Tem o Microsoft Teams habilitado para colaboração em grupo (canais-inclui conversas de canal); o chat e as chamadas estão desativados.<li>Pode agendar apenas reuniões de equipes, mas pode ingressar em reuniões do Skype for Business ou do teams.</ul>|
|**TeamsOnly**</br>(requer a página inicial do SfB online)|Um usuário executa apenas equipes. Este usuário:<ul><li>Recebe chats e chamadas no cliente da equipe, independentemente de onde for iniciado.<li>Pode iniciar chats e chamadas apenas a partir de equipes.<li>Só pode agendar reuniões no Microsoft Teams, mas pode ingressar em reuniões do Skype for Business ou do teams.<li>Pode continuar a usar os telefones IP do Skype for Business.<br><br>*Usar o modo TeamsOnly em combinação com outros usuários no modo ilhas não é recomendado até que a adoção do Team seja saturada, ou seja, todos os usuários do modo de ilhas usam e monitoram ativamente tanto o Teams quanto os clientes do Skype for Business. Se um usuário do TeamsOnly iniciar uma chamada ou chat para um usuário de ilhas, essa chamada ou chat será iniciada no cliente das equipes do usuário da Ilhas; Se o usuário das ilhas não usar ou monitorar equipes, esse usuário será exibido offline e não poderá ser acessado pelo usuário do TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Tópicos relacionados

[Coexistência com o Skype for Business](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Experiência e conformidade do cliente do Teams a modos de coexistência](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Usar o serviço de migração de reunião (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
