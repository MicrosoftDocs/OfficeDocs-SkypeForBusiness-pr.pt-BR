---
title: Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Diretrizes para gerenciar a transição para as equipes do Skype para negócios
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb1a23fb64f2a6c2d24e70f69a7997b1ec2049a6
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461568"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business

> [!Tip] 
> Assista a sessão a seguir para saber mais sobre [interoperabilidade e coexistência](https://aka.ms/teams-upgrade-coexistence-interop)

Como uma organização com Skype para negócios começa a adotar as equipes, os administradores podem gerenciar a experiência do usuário em suas organizações utilizando o conceito de coexistência "modo", que é uma propriedade de TeamsUpgradePolicy. Usando o modo, os administradores gerenciam interoperabilidade e migração à medida que eles gerenciam a transição do Skype para negócios às equipes.  Modo de um usuário determina em qual cliente chats de entrada e chamadas land, bem como quais novas reuniões de serviço (equipes ou Skype para negócios) são agendados no. No futuro, modo também será usado para definir o comportamento do cliente de equipes em termos de funcionalidade para a qual estará disponível. 


## <a name="fundamental-concepts"></a>Conceitos fundamentais

1.  *Interoperabilidade* : 1 para 1 a comunicação entre um Lync/Skype para o usuário de negócios e um usuário de equipes.

2.  *Federação* : a comunicação entre os usuários de diferentes locatários.

3.  Todas as equipes que os usuários tenham um Skype subjacente para conta de negócios que seja "hospedados" seja online ou local:
    - Os usuários que já usando Skype para Business Online usar sua conta online existente.
    - Os usuários que já usando Skype para negócios/Lync local usar sua conta local existente.
    - Os usuários para o qual nós não conseguir detectar um Skype existente para a conta comercial terá um Skype para Business Online conta provisionada automaticamente quando o usuário equipes é criado. Nenhum Skype licença de negócios é necessária.

4.  Se você possui uma implantação de local de qualquer um dos Skype para Lync ou comercial e quiser que os usuários sejam usuários de equipes, você deve no mínimo garantir que o Azure Connect da AD está sincronizando o msRTCSIP-DeploymentLocator atributo em AAD, portanto, que as equipes/Skype para negócios Online adequadamente detecta seu ambiente local. Além disso, para mover todos os usuários para o modo somente equipes (ou seja, atualize um usuário), *você deve primeiro configurar Skype para modo híbrido de negócios*. Para obter mais detalhes, consulte [Configurar o Azure Connect de AD para Skype para equipes e de negócios](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  Interoperabilidade entre equipes e Skype para usuários comerciais só será possível *se o usuário de equipes é hospedado online no Skype para negócios*. O destinatário Skype para usuários corporativos podem ser hospedados tanto no local (e é necessário configurar o Skype para o híbrido de negócios) ou online. Os usuários hospedados no Skype para negócios local podem usar as equipes no modo de ilhas (definido mais adiante neste documento), mas não podem usar as equipes para interoperabilidade ou estabelecer uma federação com outros usuários que estejam usando Skype para negócios.  

6.  Comportamento de atualização e interoperabilidade são determinados com base no modo de coexistência de um usuário, mais tarde descrito abaixo. Modo é gerenciado pelo TeamsUpgradePolicy. TeamsInteropPolicy não está mais modo respeitado e concedendo = Legacy não é mais permitido. 

7.  Atualizando de um usuário para o modo de TeamsOnly garante que todas as chamadas e chats de entrada serão sempre land no cliente de equipes do usuário, independentemente de qual cliente ele orignated de. Esses usuários também agendará todas as novas reuniões em equipes. Para estar no modo de TeamsOnly, um usuário deve ser hospedado online no Skype para negócios. Isso é necessário para assegurar a interoperabilidade, Federação e administração completa do usuário equipes. Para atualizar um usuário para TeamsOnly:
    - Se o usuário estiver hospedado no Skype para negócios online (ou nunca teve qualquer conta Skype), conceder a eles TeamsUpgradePolicy com modo = TeamsOnly usando a instância de "UpgradeToTeams" usando o PowerShell ou use o Centro de administração de equipes para selecionar o modo de TeamsOnly.
    - Se o usuário for hospedados no local, use `Move-CsUser` o local admin ferramentas para mover-se primeiro ao usuário Skype para Business Online.  Se você tiver Skype para Business Server 2019 ou CU8 para Skype para Business Server 2015, você pode especificar o `-MoveToTeams` alternar no `Move-CsUser` para mover o usuário diretamente às equipes como parte da movimentação online. Essa opção também será migrada reuniões do usuário às equipes (embora no momento, só está funcional para clientes de toque migração da reunião). Se `-MoveToTeams` não for especificado ou não disponível, em seguida, após `Move-CsUser` for concluída, atribuir o modo de TeamsOnly para o usuário usando o PowerShell ou o Centro de administração de equipes. Para obter mais detalhes, consulte [mover usuários entre o local e a nuvem](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Para obter mais detalhes sobre a migração de reunião, consulte [usando o serviço de migração de reunião (MMS)](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

8.  Para usar os recursos de sistema telefônico de equipes com equipes, os usuários devem estar no modo de TeamsOnly (isto é, hospedadas em Skype para Business Online e atualizados para equipes), e eles devem ser configurados para o sistema telefônico de Microsoft [Roteamento direto](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (que permite que você use um sistema telefônico com seus próprios troncos SIP e um SBC) ou ter um Office 365 chamar plano.   

9.  Agendamento de reuniões de equipes com a conferência de áudio (discada ou discagem via PSTN) está atualmente disponível somente para usuários que estejam hospedados em Skype para negócios Online. Suporte a usuários de equipes com Skype um local para a conta comercial está em um toque.


## <a name="coexistence-modes"></a>Modos de coexistência

Interoperabilidade e migração são gerenciadas com base em "modo de coexistência" usando TeamsUpgradePolicy. Modos de coexistência oferecem uma experiência simple e previsível para usuários finais como transição de organizações do Skype para negócios às equipes. Para uma organização mudando para equipes, o modo TeamsOnly é o destino final para cada usuário, embora nem todos os usuários precisam ser atribuídas TeamsOnly (ou em qualquer modo) ao mesmo tempo. Antes de usuários está atingindo o modo TeamsOnly, as organizações podem usar qualquer um do Skype para modos de negócios (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantir a comunicação entre os usuários que são TeamsOnly e aqueles que não são ainda previsível.


De uma perspectiva técnica, o modo de um usuário rege vários aspectos da experiência do usuário:

- *Roteamento de entrada*: no qual fazer do cliente (equipes ou Skype para negócios) entrada bate-papos e chama land? 
- *Publicação de presença*: É a presença do usuário que é mostrada para outros usuários com base em suas atividades em equipes ou Skype para negócios? 
- *Agendamento de reunião*: qual o serviço é usado para agendar as novas reuniões e garantir que o suplemento adequado está presente no Outlook. Observe que TeamsUpgradePolicy não controlar a participação da reunião. Os usuários podem sempre *join* qualquer reunião, se ele ser um Skype para uma reunião de equipes ou de reunião de negócios.
- *Experiência do cliente*: qual funcionalidade está disponível nos equipes e/ou Skype para o cliente de negócios? Os usuários podem iniciar o chamadas e chats em equipes, Skype para negócios ou ambos? Experiência de equipes & canais está disponível?  Conforme descrito neste artigo, esse aspecto final do modo agora está começando a ser entregue.

Para obter mais detalhes sobre o comportamento de presença e roteamento baseada no modo, consulte [coexistência com o Skype para negócios](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

No entanto, de uma perspectiva de experiência, modo pode mais simplesmente ser descrito como definindo a experiência para:
- *Bate-papo e chamando*: qual cliente um usuário usar?
- *Agendamento de reuniões*: faça os usuários a agendar reuniões novas como equipes ou Skype para reuniões de negócios?
- *Disponibilidade da funcionalidade de colaboração no cliente de equipes*. Funcionalidade de arquivos e equipes & canais está disponível enquanto os usuários ainda têm Skype para os negócios?

Os modos estão listados abaixo.
</br>
</br>

|Modo|Chamada e bate-papo|Agendamento de reunião<sup>1</sup>|As equipes & canais|Caso de uso|
|---|---|---|---|---|
|**TeamsOnly**</br>*Requer home no Skype para negócios Online*|Microsoft Teams|Microsoft Teams|Sim|O estado final do que estão sendo atualizados. Também é o padrão para novos inquilinos com estações de <500.|
|Ilhas|Qualquer um dos|Qualquer um dos|Sim|Configuração padrão. Permite que um único usuário avaliar os dois lado a lado do cliente. Bate-papos e chamadas podem land em qualquer cliente, para que os usuários sempre devem executar dois clientes.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Microsoft Teams|Sim|"Reuniões primeiro". Principalmente para organizações de no local tirar proveito da funcionalidade de reunião de equipes, se elas não estiverem ainda está pronto para o modo de chamada para a nuvem.|
|SfBWithTeamsCollab<sup>2</sup>|Skype for Business|Skype for Business|Sim|Ponto de partida alternativo para complexos organizações que precisam de maior controle administrativo|
|SfBOnly|Skype for Business|Skype for Business|Nenhum<sup>3</sup>|Especializados cenário para organizações com requisitos restritos ao redor do controle de dados. As equipes é usado apenas para participar de reuniões agendadas por outros usuários.|
||||||

</br>
</br>

**Observações:**

<sup>1</sup> a capacidade de ingressar em uma reunião existente (se agendadas no equipes ou no Skype para negócios) não é controlada pelo modo. Por padrão, os usuários sempre podem ingressar qualquer reunião que foram convidados para.

<sup>2</sup> SfBWithTeamsCollab e SfBWithTeamsCollabAndMeetings atualmente só estão disponíveis no PowerShell.  Uma vez é entregue a experiência do cliente concluídas, esses modos estará disponíveis no Portal de administração. 

<sup>3</sup> atualmente, equipes não tem a capacidade de desativar a funcionalidade de equipes e canais, de modo que isso permanece ativado por enquanto.



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: gerenciamento migração e coexistência

TeamsUpgradePolicy expõe duas propriedades principais: modo e NotifySfbUsers. 
</br>
</br>

|Parâmetro|Tipo|Valores permitidos</br>(padrão em itálico)|Descrição|
|---|---|---|---|
|Modo|Enum|*Ilhas*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica o modo que deve ser executado no cliente.|
|NotifySfbUsers|Bool|*Falso* ou true|Indica se deseja mostrar um banner no Skype para cliente corporativos informando que o usuário que equipes breve substituirá Skype para negócios. Ele não pode ser true se o modo = TeamsOnly.|
|||||

As equipes fornece todas as instâncias relevantes do TeamsUpgradePolicy via políticas internas, somente leitura. Portanto, obter apenas e Grant cmdlets estão disponíveis. As instâncias internas estão listadas abaixo.
</br>
</br>

|Identidade |Modo|NotifySfbUsers|
|---|---|---|
|Ilhas|Ilhas|False|
|IslandsWithNotify|Ilhas|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|Global</br>*Padrão*|Ilhas|False|
||||

Essas instâncias de política podem ser concedidas a usuários individuais ou em uma base de todo o inquilino. Por exemplo:
- Para atualizar um usuário ($SipAddress) para equipes, conceda a instância de "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Para atualizar o locatário inteiro, omita o parâmetro identity do comando grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>Considerações de Federação

A federação de equipes para outro usuário usando o Skype para negócios requer o usuário equipes hospedados online Skype para negócios. Eventualmente, as equipes que os usuários hospedados no Skype para negócios local será capazes de estabelecer uma federação com equipes somente os usuários.

TeamsUpgradePolicy rege o roteamento de chamadas e chats federados de entrada. Comportamento de roteamento federado é iguais aos cenários de mesmo inquilino, *exceto no modo de ilhas*.  Quando os destinatários estão no modo de ilhas: 
- Bate-papos e chamadas iniciadas a partir land equipes em SfB se o destinatário está em um *locatário federado*.
- Bate-papos e chamadas iniciadas a partir land equipes em equipes se o destinatário está no *mesmo inquilino*.
- Bate-papos e chamadas iniciadas a partir SfB sempre land no Skype para negócios.

Para obter mais detalhes, consulte [coexistência com o Skype para negócios](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

## <a name="the-intended-client-user-experience-in-teams-when-using-sfb-modes"></a>O usuário do cliente pretendido experiência com equipes ao usar os modos de SfB
Quando um usuário estiver em qualquer um do Skype para modos de negócios (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), todas as chamadas e chats de entrada são roteadas para Skype do usuário para o cliente de negócios. Para evitar a confusão do usuário final e garantir o roteamento apropriado, a funcionalidade de chamada e bate-papo no cliente equipes é *destinado a ser desabilitado quando um usuário está em qualquer uma do Skype para modos de negócios*. Da mesma forma, agendamento de reuniões em equipes é *destinado a ser explicitamente desabilitado quando os usuários estiverem nos modos de SfBOnly ou SfBWithTeamsCollab*e explicitamente habilitados quando um usuário está no modo de SfBWithTeamsCollabAndMeetings. 

### <a name="automatic-conformance-of-teams-client-based-on-mode-planned"></a>Conformidade automática do cliente de equipes com base no modo (planejado) 
A funcionalidade para desabilitar automaticamente o bate-papo e chamar a funcionalidade, bem como habilitar/desabilitar baseada no modo de agendamento de reuniões é agora começando a distribuição para os clientes de toque mas ainda não é amplamente disponíveis. Para obter detalhes sobre a nova funcionalidade, consulte [experiência do cliente de equipes e conformidade para modos de coexistência](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

### <a name="manual-configuration-of-workload-policy-settings-prior-to-automatic-conformance"></a>Configuração manual das configurações de política de carga de trabalho, antes da conformidade automática
Até que essa solução para conformidade automática para modos de entrega, os administradores podem impor a experiência do cliente pretendido do modo TeamsUpgradePolicy Configurando manualmente os valores de TeamsMessagingPolicy, TeamsCallingPolicy, e TeamsMeetingPolicy. Além disso, ao usar `Grant-CsTeamsUpgradePolicy` no PowerShell, o cmdlet verifica se a configuração das definições correspondentes no TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy a determmine se essas configurações são compatíveis com o modo especificado. Se qualquer um não estejam configurado corretamente, o grant terá êxito, mas um aviso será fornecido indicando quais configurações não estão configuradas corretamente. O administrador deve subsequentemente atualizar as políticas indicadas para oferecer uma experiência de usuário compatíveis do final em equipes. Se o administrador decide não agir como resultado de aviso, os usuários ainda podem ter acesso ao chat, chamar e/ou recursos de agendamento no equipes dependendo dos valores de TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy, de reunião qual pode resultar em uma experiência de usuário final confusa.

Para obter detalhes sobre qual política configurações são verificadas quando o TeamsUpgadePolicy é concedido, consulte [experiência do cliente de equipes e conformidade para modos de coexistência](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).


**Observação:** Antes da entrega da aplicação automática do comportamento do cliente descrito acima, cada um dos modos SfB se comportam basicamente da mesma. Os modos de SfBOnly, SfBWithTeamsCollab e SfBWithTeamsCollabAndMeetings são todas idênticos em como eles rotear as chamadas de entrada e de chats. A única diferença, por enquanto, é no se o Outlook Addins para equipes e Skype para negócios estão habilitados. Até que a criar cliente diferenciado é entregue, 1 somente dos modos de SfB está habilitada no Portal de administração. Mas todos os modos estão disponíveis no PowerShell.


## <a name="teamsinteroppolicy-and-legacy-mode-has-been-retired"></a>TeamsInteropPolicy e modo herdado foi descontinuado 

TeamsInteropPolicy foi substituída pelo TeamsUpgradePolicy. Todos os componentes que anteriormente cumpridas TeamsInteropPolicy foram atualizados para honram TeamsUpgradePolicy em vez disso.  Microsoft anteriormente tinha introduziu o modo de "Herdados" no TeamsUpgradePolicy para facilitar a transição de TeamsInteropPolicy para TeamsUpgradePolicy. No modo de legado, os componentes de roteamento que compreendidas TeamsUpgradePolicy seria reverter para TeamsInteropPolicy. Roteamento agora suporta totalmente TeamsUpgradePolicy. Modo herdado não é mais suportado e não é mais possível conceder modo herdado


## <a name="detailed-mode-descriptions"></a>Descrições de modo detalhado
</br>
</br>

|Modo|Explicação (includeding planejada a experiência do cliente)|
|---|---|
|**Ilhas**</br>(padrão)|Um usuário executa ambos os Skype para negócios e equipes--lado a lado. Esse usuário:</br><ul><li>Pode iniciar o bate-papos e chamadas de VOIP em um dos Skype para equipes ou negócios do cliente. Observação: Usuários com Skype para negócios hospedados no local não é possível iniciar das equipes de acessar outra Skype para usuário de negócios, independentemente do modo do destinatário.<li>Recebe chats & VOIP chama iniciado no Skype for Business por outro usuário em seu Skype para o cliente de negócios.<li>Recebe chats & VOIP chamadas iniciadas no equipes por outro usuário no cliente suas equipes se estiverem no *mesmo inquilino*.<li>Recebe chats & VOIP chama iniciado em equipes por outro usuário no seu Skype para o cliente de negócios se eles estiverem em um *locatário federado*. <li>Oferece a funcionalidade de PSTN, conforme observado abaixo:<ul><li>Se o usuário estiver hospedado no Skype para negócios local, chamadas PSTN são iniciadas e recebidas no Skype para negócios.<li>Se o usuário está hospedado online, o usuário tem o sistema telefônico, no qual caso o usuário:<ul><li>Inicia e recebe chamadas PSTN em equipes se o usuário estiver configurado para roteamento direto<li>Inicia e recebe chamadas PSTN em Skype para os negócios, se o usuário tiver MS chamar planejar ou conecta-se à rede PSTN por meio de um dos Skype para Business Edition do conector de nuvem ou uma implantação local do Skype para Business Server (voice híbrido)</ul></ul><li>Pode agendar reuniões em equipes ou Skype para negócios (e verá ambas plug-ins por padrão).<li>Podem ingressar em qualquer Skype para reunião de negócios ou equipes; a reunião será aberto no respectivo cliente.</ul>|
|**SfBOnly**|Um usuário executa apenas Skype para negócios. Esse usuário:</br><ul><li>Pode iniciar o bate-papos e chamadas do Skype para negócios.<li>Recebe qualquer chat/chamada em seu Skype para o cliente de negócios, independentemente de onde for iniciado, a menos que o iniciador é um usuário de equipes com Skype para negócios hospedados no local. * <li>Pode agendar apenas Skype para reuniões de negócios, mas pode ingressar Skype para reuniões de negócios ou equipes. </br> *Usando Ilhas com usuários no local não é recomendado em combinação com outros usuários no modo de SfBOnly. Se um usuário de equipes com Skype para negócios hospedado no local inicia uma chamada ou converse com um usuário SfBOnly, o usuário SfBOnly é inalcançável e recebe um email.* de bate-papo/chamadas não atendidas|
|**SfBWithTeamsCollab**|Um usuário executa ambos os Skype para negócios e equipes--lado a lado. Esse usuário:</br><ul><li>Tem a funcionalidade de um usuário no modo de SfBOnly.<li>As equipes tem habilitado somente para colaboração de grupo (canais); agendamento de bate-papo/chamada/reunião estão desabilitadas.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Um usuário executa ambos os Skype para negócios e equipes--lado a lado. Esse usuário:<ul><li>Tem o bate-papo e a funcionalidade de chamada do usuário no modo de SfBOnly.<li>Tem equipes ativadas para colaboração de grupo (canais - inclui as conversas de canal); bate-papo e chamadas estão desabilitadas.<li>Pode agendar reuniões de equipes apenas, mas pode ingressar Skype para reuniões de negócios ou equipes.</ul>|
|**TeamsOnly**</br>(requer SfB Online residencial)|Um usuário executa apenas equipes. Esse usuário:<ul><li>Recebe qualquer bate-papos e chamadas em seu cliente de equipes, independentemente de onde for iniciado.<li>Pode iniciar o bate-papos e chamadas de equipes.<li>Pode agendar reuniões em equipes, mas pode ingressar Skype para reuniões de negócios ou equipes.<li>Pode continuar a usar o Skype para telefones IP de negócios.</ul> |
|||




## <a name="related-topics"></a>Tópicos relacionados

[Coexistência com o Skype for Business](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Experiência e conformidade do cliente do Teams a modos de coexistência](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)


