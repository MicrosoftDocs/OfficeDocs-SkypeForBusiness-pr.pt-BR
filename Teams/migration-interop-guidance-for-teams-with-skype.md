---
title: Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Diretrizes para gerenciar a transição do Teams para o Skype for Business
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87fc1401087292e8acd624e0917ead2b7998a2fd
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573396"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business

> [!Tip] 
> Assista à seguinte sessão para saber mais sobre [Coexistência e Interoperabilidade](https://aka.ms/teams-upgrade-coexistence-interop)

Quando uma organização com o Skype for Business começa a adotar o Teams, os administradores podem gerenciar a experiência do usuário em suas organizações usando o conceito de “modo” de coexistência, que é uma propriedade do TeamsUpgradePolicy. Usando esse modo de coexistência, os administradores gerenciam a interoperabilidade e a migração à medida que gerenciam a transição do Skype for Business para o Teams.  O modo de usuário vai determinar em qual cliente as conversas e chamadas de entradas chegarão, bem como em quais serviços (Teams ou Skype for Business) as novas reuniões serão agendadas. Tal modo também vai determinar quais recursos estarão disponíveis no cliente do Teams. 


## <a name="fundamental-concepts"></a>Conceitos fundamentais

1.  *Interoperabilidade*: comunicação entre duas pessoas, ou quais são um usuário do Lync/Skype for Business e um usuário do Teams.

2.  *Federação*: comunicação entre usuários de locatários diferentes.

3.  Todos os usuários do Teams têm uma conta subjacente do Skype for Business que é "hospedada" online ou localmente:
    - Os usuários que já usam o Skype for Business online usam a sua conta online já existente.
    - Os usuários que já usam o Skype for Business local usam a sua conta local já existente.
    - Os usuários para os quais não é possível detectar uma conta existente do Skype for Business terão uma conta do Skype for Business online provisionada automaticamente quando o usuário for criado no Teams.

4.  Se você tiver uma implantação local do Skype for Business ou do Lync, e desejar que esses usuários sejam usuários do Teams, você deve, no mínimo, garantir que o Azure AD Connect esteja sincronizando o atributo msRTCSIP-DeploymentLocator no AAD, para que o Teams/Skype for Business online detectem corretamente seu ambiente local. Além disso, para migrar todos os usuários para o modo TeamsOnly (por exemplo, atualizar um usuário) *primeiro é necessário configurar o modo híbrido do Skype for Business*. Para obter mais detalhes, confira [Configurar o Azure AD Connect para Skype for Business e Teams](https://docs.microsoft.com/pt-BR/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  A interoperabilidade entre o Teams e os usuários do Skype for Business só é possível *se o usuário do Teams estiver hospedado online no Skype for Business*. O usuário do Skype for Business pode ser hospedado ou no local (e requer a configuração de recursos híbridos do Skype for Business) ou online. Os usuários que estiverem hospedados no Skype for Business localmente poderão usar o Teams no modo Ilhas (definido mais adiante neste documento), mas não poderão usar o Teams para interoperabilidade ou federação com outros usuários que usam o Skype for Business.  

6.  O comportamento de atualização e Interoperabilidade é determinado com base no modo de Coexistência de um usuário, descrito mais adiante. O modo é gerenciado pela TeamsUpgradePolicy. 

7.  Atualizar um usuário para o modo TeamsOnly garante que todas as conversas e chamadas de entrada vão sempre chegar no cliente do Teams do usuário, independentemente de qual cliente elas se originaram. Esses usuários também agendarão todas as novas reuniões no Teams. Para estar no modo TeamsOnly, um usuário deve estar hospedado online no Skype for Business. Isso é necessário para garantir a interoperabilidade, a Federação e a administração total do usuário do Teams. Para atualizar um usuário para TeamsOnly:
    - Se o usuário estiver hospedado no Skype for Business online (ou se nunca teve uma conta do Skype), conceda a ele a TeamsUpgradePolicy com o modo = TeamsOnly fazendo uso da instância "UpgradeToTeams" do PowerShell, ou use o Centro de Administração do Teams para selecionar o modo de TeamsOnly.
    - Se o usuário estiver hospedado localmente, faço uso `Move-CsUser` das ferramentas de administração local para primeiramente mover o usuário para o Skype for Business online.  Se você tiver o Skype for Business Server 2019 ou o CU8 para o Skype for Business Server 2015, você poderá especificar a `-MoveToTeams`opção `Move-CsUser` para mover o usuário diretamente para o Teams como parte da mudança online. Essa opção também migra as reuniões do usuário para o Teams. Se `-MoveToTeams` não for especificado ou não estiver disponível, logo depois de `Move-CsUser` concluir, atribua o modo TeamsOnly para esse usuário usando ou o PowerShell ou o Centro de Administração do Teams. Para obter mais detalhes, confira [Migrar usuários entre o local e a nuvem](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Para saber mais sobre a migração de reuniões, confira [Usando o Serviço de Migração de Reuniões (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

8.  Para usar o Sistema de Telefonia da Microsoft com o Teams, os usuários devem estar no modo de TeamsOnly (por exemplo, hospedado no Skype for Business Online e atualizados para o Teams). Eles devem também ser configurados para o[Roteamento Direto](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) do Sistema de Telefonia da Microsoft (que permite a você usar o Sistema de Telefone com os seus próprios troncos de SIP e SBC) ou então possuir um Plano de Chamadas de Office 365. O Roteamento Direto do Sistema de Telefonia da Microsoft não é compatível com o modo Ilhas.    

9.  Agendar reuniões no Teams com Conferências de Áudio (discagem local ou discagem telefônica por PSTN) está disponível independentemente do usuário estar hospedado Skype for Business online ou no Skype for Business no local. 


## <a name="coexistence-modes"></a>Modos de Coexistência

A interoperabilidade e a migração são gerenciadas com base no “modo de coexistência” usando a TeamsUpgradePolicy. Os modos de coexistência oferecem uma experiência simples e previsível para os usuários finais à medida que as organizações migram do Skype for Business para o Teams. Para uma organização migrando para o Teams, o modo de TeamsOnly é o destino final de cada usuário, embora nem todos os usuários precisem ser atribuídos o modo TeamsOnly (ou qualquer outro) ao mesmo tempo. Antes que os usuários todos adotem o modo TeamsOnly, as organizações podem usar qualquer um dos modos do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantir uma comunicação dentro do padrão esperado entre os usuários que são TeamsOnly e aqueles que ainda não o são.


De uma perspectiva técnica, o modo do usuário determina vários aspectos da experiência do usuário:

- *Roteamento de entrada*: Qual o cliente ( do Teams ou do Skype for Business) que recebe bate-papos e chamadas de entrada? 
- *Publicação de presença*: a presença do usuário mostrada para outros usuários é determinada com base em suas atividades no Teams ou no Skype for Business? 
- *Agendamento de reunião*: qual serviço é usado para agendar novas reuniões e garantir que o suplemento correto estará presente no Outlook? Observe que TeamsUpgradePolicy não rege participação em reuniões. Os usuários sempre poderão *participar de* qualquer reunião, seja ela uma reunião do Skype for Business ou uma reunião do Teams.
- *Experiência do cliente*: qual funcionalidade está disponível no Temas e/ou no cliente do Skype for Business? Os usuários podem iniciar chamadas e chats no Teams, Skype for Business ou ambos? A experiência de Equipes e Canais está disponível?  

Para saber mais sobre o comportamento de roteamento e presença com base no modo, confira [Coexistência com o Skype for Business](https://docs.microsoft.com/pt-BR/MicrosoftTeams/coexistence-chat-calls-presence).

No entanto, da perspectiva da experiência, o modo pode ser simplesmente descrito como o modo de determinar a experiência para:
- *Chat e Chamadas*: qual o cliente usado pelo usuário ?
- *Agendamento de Reuniões*: os usuários agendam novas reuniões como reuniões do Teams ou reuniões do Skype for Business?
- *Disponibilidade da funcionalidade de colaboração no cliente do Teams*. A função Equipes & Canais e Arquivos vai estar disponível enquanto os usuários ainda estiverem usando o Skype for Business?

Os modos estão listados abaixo.
</br>
</br>

|Modo|Chamadas e Chat|Agendador de Reunião<sup>1</sup>|Equipes e Canais|Caso de Uso|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Exige hospedagem no Skype for Business Online*|Teams|Teams|Sim|Estado final depois de atualizado. Será o padrão para novos locatários.|
|Ilhas|Qualquer das opções|Qualquer das opções|Sim|Configuração padrão. Permite que um único usuário avalie os dois clientes um junto ao outro. Bate-papos e chamadas podem chegar em qualquer dos clientes, por isso os usuários precisam sempre executar ambos. Para evitar uma experiência confusa ou indesejada do Skype for Business, comunicações externas (federadas), serviços de voz PSTN e aplicativos de voz, integração com o Office e várias outras integrações continuam a ser operadas pelo Skype for Business.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|Sim|Reuniões em primeiro lugar. Principalmente destinado para que organizações locais se beneficiem da funcionalidade das reuniões do Teams, se as mesmas ainda não estiverem prontas para migrar para a nuvem.|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|Sim|O ponto de partida alternativo para organizações complexas que precisam de um controle administrativo mais rígido.|
|SfBOnly|Skype for Business|Skype for Business|Não<sup>3</sup>|Cenário especializado para organizações com critérios rigorosos de controle de dados. O Teams é usado apenas para aceitar o convite para participar de reuniões agendadas por outras pessoas.|
||||||

</br>
</br>

**Observações:**

<sup>1</sup> A capacidade de participar de uma reunião existente (sejam agendadas no Teams ou no Skype for Business) não é governada por modo. Por padrão, os usuários sempre podem participar de qualquer reunião para a qual tenham sido convidados.

<sup>2</sup> Por padrão, ao atribuir TeamsOnly ou SfbWithTeamsCollabAndMeetings a um usuário individual, todas as reuniões do Skype for Business existentes agendadas pelo usuário para o futuro serão convertidas em reuniões do Teams. Se desejar, você pode deixar essas reuniões como reuniões do Skype for Business especificando `-MigrateMeetingsToTeams $false` ao conceder a TeamsUpgradePolicy ou desmarcando a caixa de seleção no portal de administração do Teams.   Lembre-se de que a capacidade de mover reuniões do Skype for Business para o Teams não está disponível ao conceder TeamsUpgradePolicy a todo o locatário. 

<sup>3</sup>No momento, o Teams não possui a capacidade de desabilitar a função Equipes e Canais, portanto isso continua habilitado por enquanto.



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: gerenciando a migração e a coexistência

A TeamsUpgradePolicy expõe duas propriedades principais: Modo e NotifySfbUsers. 
</br>
</br>

|Parâmetro|Tipo|Valores permitidos</br>(padrão grafado em itálico)|Descrição|
|---|---|---|---|
|Modo|Enum|*Ilhas*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica em modo que o cliente deve operar.|
|NotifySfbUsers|Bool|*Falso* ou verdadeiro|Indica se deve haver um banner no cliente do Skype for Business informando ao usuário que o Teams irá substituir o Skype for Business em breve. Isso não pode ser verdadeiro no caso de modo = TeamsOnly.|
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
- Para atualizar um usuário ($SipAddress) para o Teams, conceda a instância “UpgradeToTeams”:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Para atualizar o locatário inteiro, omita o parâmetro de identidade do comando grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>Considerações sobre a Federação

A Federação do Teams para outro usuário usando o Skype for Business exige que o usuário do Teams esteja hospedado no Skype for Business.

TeamsUpgradePolicy determina o roteamento para chamadas e conversas federadas e de entrada. O comportamento de roteamento federado é o mesmo para cenários de mesmo locatário, *exceto no modo de Ilhas*.  Quando os destinatários estiverem no modo de Ilhas: 
- Chats e chamadas iniciados a partir do Teams são recebidos no SfB se o destinatário estiver em um *locatário federado*.
- Chats e chamadas iniciados a partir do Teams são recebidos no Teams se o destinatário estiver no *mesmo locatário*.
- Chats e chamadas iniciados a partir do SfB sempre chegam no Skype for Business.

Para obter mais detalhes, consulte [Coexistência com o Skype for Business](https://docs.microsoft.com/pt-BR/MicrosoftTeams/coexistence-chat-calls-presence).

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>A experiência do usuário do cliente do Teams ao usar os modos do SfB
Quando um usuário encontra-se em qualquer um dos modos do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), todas as conversas e chamadas de entrada serão roteadas para o cliente do Skype for Business do usuário. Para evitar a confusão do usuário final e garantir o roteamento apropriado, a funcionalidade de chamada e de chat no cliente do Teams será desabilitada automaticamente quando um usuário estiver em qualquer modo do Skype for Business. Da mesma forma, o agendamento de reunião no Teams será desabilitado automaticamente quando os usuários estiverem nos modos SfBOnly ou SfBWithTeamsCollab e habilitados automaticamente quando um usuário estiver no modo de SfBWithTeamsCollabAndMeetings. Para mais detalhes, confira[Experiência e conformidade do cliente do Teams a modos de coexistência](https://docs.microsoft.com/pt-BR/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Antes da receber a implementação automática do Equipes e Canais do Teams, os modos SfbOnly e SfBWithTeamsCollab se comportam da mesma maneira.


## <a name="detailed-mode-descriptions"></a>Descrições detalhadas do modo
</br>
</br>

|Modo|Explicação|
|---|---|
|**Ilhas**</br>(padrão)|Um usuário executa lado a lado tanto o Skype for Business quanto o Teams. Este usuário:</br><ul><li>Pode iniciar chats e chamadas VoIP no cliente do Skype for Business ou no do Teams. Observação: os usuários com o Skype for Business hospedado no local não podem iniciar do Teams para alcançar outro usuário do Skype for Business, independentemente do modo do destinatário.<li>Recebe chats & chamadas VoIP iniciadas no Skype for Business por outro usuário no cliente do seu Skype for Business.<li>Recebe chats & chamadas VoIP iniciadas no Teams por outro usuário no cliente do seu Teams se eles estiverem no *mesmo locatário*.<li>Recebe chats & chamadas VoIP iniciadas no Teams por outro usuário no cliente do seu Skype for Business se eles estiverem em um *locatário federado*. <li>Possui a funcionalidade PSTN, como indicado abaixo:<ul><li>Quando o usuário está hospedado no Skype for Business no local e o tem o Enterprise Voice, as chamadas de PSTN são sempre iniciadas e recebidas no Skype for Business.<li>Quando o usuário é hospedado no Skype for Business Online e tem o Sistema de Telefonia Microsoft, o usuário sempre inicia e recebe chamadas PSTN no Skype for Business:<ul><li>Isso acontece mesmo que o usuário tenha um Plano de Chamadas da Microsoft ou se conecte à rede PSTN por meio do Skype for Business Cloud Connector Edition ou de uma implantação local do Skype for Business Server (voz híbrida).<li>**Observação: o Roteamento Direto do Sistema de Telefonia da Microsoft não é compatível com o modo Ilhas.**</ul></ul><li>Recebe Filas de Chamadas da Microsoft e chamadas de Atendedor Automático no Skype for Business.<li>Pode agendar reuniões no Teams ou no Skype for Business (e verá os dois plug-ins por padrão).<li>Pode entrar em qualquer reunião do Skype for Business ou do Teams; a reunião será aberta no respectivo cliente.</ul>|
|**SfBOnly**|Um usuário que executa apenas o Skype for Business. Este usuário:</br><ul><li>Pode iniciar chats e chamadas somente no Skype for Business.<li>Recebe todos os chat por chat ou chamadas no cliente do Skype for Business, independentemente de onde foi iniciado, a menos que o iniciador seja um usuário do Teams com Skype for Business hospedado no local.*<li>Só pode agendar reuniões do Skype for Business, mas pode entrar em reuniões do Skype for Business ou do Teams.</br>\** Usar o modo de Ilhas com usuários locais não é recomendável em combinação com outros usuários no modo SfBOnly. Se um usuário do Teams com o Skype for Business hospedado no local iniciar uma chamada ou um chat para um usuário SfBOnly, o usuário do SfBOnly não será alcançável e receberá um email de chat/chamada perdido. *|
|**SfBWithTeamsCollab**|Um usuário executa lado a lado tanto o Skype for Business quanto o Teams. Este usuário:</br><ul><li>Tem a funcionalidade de um usuário no modo SfBOnly.<li>Possui o Teams ativado somente para colaboração em grupo (Canais); chat/chamadas/agendamento de reunião estão desabilitados.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Um usuário executa lado a lado tanto o Skype for Business quanto o Teams. Este usuário:<ul><li>Tem a funcionalidade de chat e de chamada do usuário no modo SfBOnly.<li>Tem o Teams habilitado para colaboração em grupo (Canais, incluindo conversas de canal); o chat e as chamadas estão desabilitados.<li>Pode agendar reuniões apenas no Teams, mas pode participar de reuniões do Skype for Business ou do Teams.</ul>|
|**TeamsOnly**</br>(exige hospedagem no SfB Online)|Um usuário executa apenas o Teams. Este usuário:<ul><li>Recebe conversas e chamadas no cliente do seu Teams, independentemente de onde foram iniciadas.<li>Pode iniciar chats e chamadas somente no Teams.<li>Pode agendar reuniões somente no Teams, mas pode participar de reuniões do Skype for Business ou do Teams.<li>Pode continuar a usar os telefones IP do Skype for Business.<br><br>*Não é recomendável usar o modo de TeamsOnly em combinação com outros usuários no modo de Ilhas, até que a adoção do Teams esteja saturada, ou seja, todos os usuários do modo de Ilhas usem e monitorem ativamente tanto os clientes do Teams quanto do Skype for Business. Se um usuário do TeamsOnly iniciar uma chamada ou um chat para um usuário Ilhas, essa chamada ou chat será direcionado para o cliente do Teams do usuário Ilhas. Se o usuário do Ilhas não usa ou monitora o Teams, esse usuário aparecerá offline e não poderá ser alcançado pelo usuário TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Tópicos relacionados

[Coexistência com o Skype for Business](https://docs.microsoft.com/pt-BR/MicrosoftTeams/coexistence-chat-calls-presence)

[Experiência e conformidade do cliente do Teams a modos de coexistência](https://docs.microsoft.com/pt-BR/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
