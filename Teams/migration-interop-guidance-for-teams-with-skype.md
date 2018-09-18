---
title: Diretrizes de migração e interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Diretrizes para gerenciar a transição para as equipes do Skype para negócios
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: bfd2c7efd606a143fffca25c7379f2a29bf505da
ms.sourcegitcommit: 2a1766158b21f0387cd8e4a00aab2dcde4059fbb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "23999020"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Diretrizes de migração e interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios

Em abril de 2018, Microsoft esclarecido sua orientação para migrar a equipes do Skype para negócios e como esses dois clientes podem coexistir-se para um determinado usuário. Nesse momento, podemos anunciado alterações planejadas para simplificar a capacidade de gerenciamento e aumentar a satisfação do usuário final. Desde então, a Microsoft forneceu uma atualização para a experiência do usuário admin, consistente ao plano. A orientação neste documento reflete as alterações.

Como anunciada anteriormente, TeamsInteropPolicy será desativado (direcionado para o final do T3) e sua funcionalidade está sendo consolidada em TeamsUpgradePolicy. Interoperabilidade e migração serão gerenciados usando "modo de coexistência", conforme determinado pela TeamsUpgradePolicy, que agora está disponível. Seleção de modo do usuário orientará ambos os roteamento de chamadas de entrada e de bate-papos e no qual cliente o usuário pode iniciar o bate-papos e chamadas ou agendar reuniões. Enquanto TeamsInteropPolicy será desativado, ele ainda precisa ser definida em paralelo com TeamsUpgradePolicy durante a phaseout.  

Como parte desse esforço, a Microsoft recentemente atualizou o "Microsoft equipes & Skype para Business Admin Center" (também conhecido como Portal moderno) para refletir o novo modelo de gerenciamento com base em modos de coexistência. No Portal moderno, configurar TeamsUpgradePolicy serão automaticamente agora também definir TeamsInteropPolicy como valor consistente, portanto TeamsInteropPolicy não mais é exposta na interface do usuário. *No entanto, os administradores usando o PowerShell ainda devem definir TeamsUpgradePolicy tanto TeamsInteropPolicy juntos para garantir o roteamento apropriado.* Após concluir a transição para TeamsUpgradePolicy, não será necessário para definir também TeamsInteropPolicy.
</br>
</br>
|**Gerenciando a interoperabilidade e migração**|**Portal moderno**|**PowerShell**|
|----|----|----|----|
|Até setembro de 2018 (datas está sujeita a alterações)|Use TeamsUpgradePolicy|Usar TeamsUpgradePolicy e TeamsInteropPolicy |
|Postar setembro de 2018 (datas está sujeita a alterações)|Use TeamsUpgradePolicy|Use TeamsUpgradePolicy apenas; TeamsInteropPolicy preterido|
|||||

Para justificar a introdução dos modos de coexistência e a aposentadoria pendente do TeamsInteropPolicy, a Microsoft está fornecendo esta orientação agora para que os clientes que usam equipes hoje podem gerenciar a transição.

## <a name="in-this-article"></a>Neste artigo

- [Conceitos fundamentais](#fundamental-concepts)
- [Modos de coexistência](#coexistence-modes)
- [TeamsUpgradePolicy: gerenciamento migração e coexistência](#teamsupgradepolicy-managing-migration-and-co-existence)
- [TeamsInteropPolicy para ser retirado](#teamsinteroppolicy-to-be-retired)
- [Conclusão da transição para o gerenciamento de modo](#completing-the-transition-to-mode-management)
- [Ação necessária para as organizações que já tem usado o TeamsInteropPolicy](#action-required-for-organizations-that-have-already-used-teamsinteroppolicy)   
- [Descrições de modo detalhado](#detailed-mode-descriptions) 
- [Resumo das alterações de funcionalidade planejada para simplificar a coexistência e migração](#summary-of-planned-functionality-changes-to-simplify-coexistence-and-migration) 
- [Problemas conhecidos](#known-issues)

## <a name="fundamental-concepts"></a>Conceitos fundamentais

1.  *Interoperabilidade* : 1 para 1 a comunicação entre um Lync/Skype para o usuário de negócios e um usuário de equipes.

2.  *Federação* : a comunicação entre os usuários de diferentes locatários.

3.  Todas as equipes que os usuários tenham um Skype subjacente para conta de negócios que seja "hospedados" seja online ou local:
    - Os usuários que já usando Skype para Business Online usar sua conta online existente.
    - Os usuários que já usando Skype para negócios/Lync local usar sua conta local existente.
    - Os usuários para o qual nós não conseguir detectar um Skype existente para a conta comercial terá um Skype para Business Online conta provisionada automaticamente quando o usuário equipes é criado. Nenhum Skype licença de negócios é necessária.

4.  Se você possui uma implantação de local de qualquer um dos Skype para Lync ou comercial e quiser que os usuários sejam usuários de equipes, você deve no mínimo garantir que o Azure Connect da AD está sincronizando o msRTCSIP-DeploymentLocator atributo em AAD, portanto, que as equipes/Skype para negócios Online adequadamente detecta seu ambiente local. Além disso, para mover todos os usuários para o modo somente equipes (ou seja, atualize um usuário), *você deve configurar Skype para modo híbrido de negócios*.

5.  Interoperabilidade entre equipes e Skype para usuários comerciais só será possível *se o usuário de equipes é hospedado online no Skype para negócios*. O Skype para usuários corporativos podem ser hospedados tanto no local (e é necessário configurar o Skype para o híbrido de negócios) ou online. Os usuários hospedados no Skype para negócios local podem usar as equipes no modo de ilhas (definido mais adiante neste documento), mas não podem usar as equipes para interoperabilidade ou estabelecer uma federação com outros usuários que estejam usando Skype para negócios.  

6.  Para atualizar um usuário para equipes (ou seja, conceder TeamsUpgradePolicy com modo = TeamsOnly), o usuário deve ser hospedado online no Skype para negócios. Isso é necessário para assegurar a interoperabilidade, Federação e administração completa do usuário equipes. Para atualizar os usuários que estão hospedados no local, use `Move-CsUser` o local admin ferramentas para mover-se primeiro ao usuário Skype para Business Online. Em seguida, conceder TeamsUpgradePolicy e TeamsInteropPolicy ao usuário online ou usar o Portal moderno para atribuir o modo de TeamsOnly. Uma vez CU8 para Skype para Business Server 2015 é enviado, cliente pode simplesmente usar o novo `-MoveToTeams` alternar no `Move-CsUser` que combina estes 2 passos em 1.

7.  As políticas de núcleo de gerenciamento de atualização e interoperabilidade são TeamsUpgradePolicy e TeamsInteropPolicy.  No entanto, TeamsInteropPolicy é no processo que está sendo desativado e toda a funcionalidade será substituída pelo TeamsUpgradePolicy. Até que a transição for concluída, os clientes devem definir o TeamsUpgradePolicy e o TeamsInteropPolicy consistentemente (conforme descrito [posterior](#important) neste documento) para garantir o funcionamento adequado, ou usar o novo Portal moderno, que faz isso automaticamente.

8.  Para usar os recursos de sistema telefônico de equipes, os usuários devem estar no modo de TeamsOnly (isto é, hospedadas em Skype para Business Online e atualizados para equipes), e eles devem ser configurados para o Microsoft System direto roteamento de telefone (o que permite que você use um sistema telefônico com seu próprios SIP troncos e SBC) ou ter um Office 365 chamar plano. Roteamento direto está [disponível no mercado](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) a partir de 28 de junho de 2018.  

9.  Agendamento de reuniões de equipes com a conferência de áudio (discada ou discagem via PSTN) está atualmente disponível somente para usuários que estejam hospedados em Skype para negócios Online. Suporte a usuários de equipes com Skype um local para a conta comercial está em um toque.


## <a name="coexistence-modes"></a>Modos de coexistência

Para simplificar a capacidade de gerenciamento e aumentar a satisfação do usuário final, migração e interoperabilidade são agora gerenciadas com base em "modo de coexistência" usando TeamsUpgradePolicy. Modo de um usuário determina:

- *Roteamento de entrada* : no qual fazer do cliente (equipes ou Skype para negócios) entrada bate-papos e chama land? Essa funcionalidade substitui o que anteriormente era manipulado pelo TeamsInteropPolicy. TeamsInteropPolicy vai ser retirado após a conclusão da transição. ***Durante a transição, TeamsUpgradePolicy e o TeamsInteropPolicy devem ser definida de maneira coordenada, conforme descrito na próxima seção***.
- *Agendamento de reunião* : qual o serviço é usado para agendar as novas reuniões e garantir que o suplemento adequado está presente no Outlook? Suporte do suplemento do Outlook é esperado a serem implantados nas próximas semanas. Observe que TeamsUpgradePolicy não controlar a participação da reunião. Os usuários podem sempre *join* qualquer reunião, se ele ser um Skype para uma reunião de equipes ou de reunião de negócios.
- *Experiência do cliente* : qual funcionalidade está disponível nos equipes e/ou Skype para o cliente de negócios? Isso é implementado para o modo de TeamsOnly. Suporte para outros modos depende do TeamsAppPolicy futura. Quando essa nova política estiver inserida, o TeamsUpgradePolicy terão uma dependência nele para garantir que as equipes está configurado corretamente para o modo desejado.

Os modos planejados estão listados abaixo. SfBWithTeamsCollab e SfBWithTeamsCollabAndMeetings permitirá o uso misto de ambos os clientes, mas com nenhuma funcionalidade sobreposta. Modo de ilhas permite o uso de ambos os clientes, mas com funcionalidade de sobrepostas. Por exemplo, no modo de ilhas, um usuário pode iniciar um chat em qualquer um dos Skype para equipes ou comercial, mas em SfBWithTeamsCollab, eles só podem conversar em Skype para negócios. Observe que nem todos os modos ainda estão disponíveis.  
</br>
</br>
|Modo|Comportamento de roteamento|Agendamento de reuniões|Experiência do cliente|
|---|---|---|---|
|Ilhas|Faz uma chamada de entrada VOIP e chats land no mesmo cliente como originador<sup>1</sup>|Ambos|Os usuários finais podem iniciar chamadas e chats de qualquer cliente e pode agendar reuniões de qualquer cliente.|
|SfBOnly|Bate-papos e chamadas de entrada são roteadas para Skype para negócios|Skype para negócios apenas|Os usuários finais podem iniciar chamadas e chats do Skype para negócios e apenas agendar Skype para reuniões de negócios. (AINDA NÃO IMPOSTA)|
|SfBWithTeamsCollab<sup>2</sup>|Bate-papos e chamadas de entrada são roteadas para Skype para negócios|Skype para negócios apenas|Os usuários finais podem iniciar chamadas e chats do Skype para negócios e apenas agendar Skype para reuniões de negócios. Eles também podem usar os canais em equipes. (AINDA NÃO IMPOSTA)|
|SfBWithTeamsCollabAndMeetings<sup>3</sup>|Bate-papos e chamadas de entrada são roteadas para Skype para negócios|Somente as equipes|Os usuários finais podem iniciar chamadas e bate-papos do Skype para negócios somente e somente agendem reuniões de equipes. Eles também podem usar os canais em equipes. (AINDA NÃO IMPOSTA)|
|TeamsOnly|Bate-papos e chamadas de entrada são roteadas para equipes|Somente as equipes|Os usuários finais podem iniciar chamadas e chats de equipes. Skype para negócios só está disponível para participar de reuniões.|
|Herdado|Roteamento baseado em TeamsInteropPolicy|Sem impacto|Não há impacto. Este um modo temporário para facilitar a transição entre TeamsInteropPolicy e TeamsUpgradePolicy. Quando a transição for concluída, esse modo será removido. |
|||||

**Observações:**

<sup>1</sup> para obter detalhes sobre a chamada de PSTN, consulte a tabela no final deste documento.

<sup>2</sup> SfBWithTeamsCollab não é ainda exposta na experiência do usuário admin porque ele atualmente se comporta não diferente SfBOnly modo. Quando é entregue a experiência do cliente, esse modo estará disponível.

<sup>3</sup> SfBWithTeamsCollabAndMeetings ainda não está disponível. 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: gerenciamento migração e coexistência

TeamsUpgradePolicy agora expõe três propriedades. As propriedades principais são modo e NotifySfbUsers. Ação é um parâmetro de legado e é totalmente redundante com a combinação de modo e NotifySfbUsers.
</br>
</br>
|Parâmetro|Tipo|Valores permitidos</br>(padrão em itálico)|Descrição|
|---|---|---|---|
|Modo|Enum|*Ilhas*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>Herdado|Indica o modo que deve ser executado no cliente. Se o modo = Legacy, componentes consumindo essa diretiva serão revertida para respeitar TeamsInteropPolicy. Isso é para auxiliar na transição para o novo esquema conforme componentes que anteriormente cumpridas TeamsInteropPolicy são atualizados para honram TeamsUpgradePolicy.</br>Modo = TeamsOnly é o equivalente da ação = atualização.|
|NotifySfbUsers|Bool|*Falso* ou true|Indica se deseja mostrar um banner no Skype para cliente corporativos informando que o usuário que equipes breve substituirá Skype para negócios. Ele não pode ser true se o modo = TeamsOnly. Este é o equivalente a ação = Notify.|
|Ação|Enum|*None*, notificar, atualização|Este é um parâmetro de legado que eventualmente será removido, porque ele é redundante com a combinação de modo e NotifySfbUsers. |
|||||

As equipes fornece todas as instâncias relevantes do TeamsUpgradePolicy via políticas internas, somente leitura. Portanto, obter apenas e Grant cmdlets estão disponíveis. As instâncias internas estão listadas abaixo.
</br>
</br>
|Identidade |Modo|NotifySfbUsers|Ação|Comentários|
|---|---|---|---|---|
|Ilhas|Ilhas|Falso|Nenhum||
|IslandsWithNotify|Ilhas|Verdadeiro|Notificar||
|SfBOnly|SfBOnly|Falso|Nenhum|No momento, esse modo é efetivamente o mesmo cliente preferencial da configuração = SfB. No futuro, esperamos que isso restringe a funcionalidade de equipes.|
|SfBOnlyWithNotify|SfBOnly|Verdadeiro|Notificar|No momento, esse modo é efetivamente o mesmo cliente preferencial da configuração = SfB. No futuro, esperamos que isso restringe a funcionalidade de equipes.|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Falso|Nenhum|Esse modo existe na camada do PowerShell, mas ainda não está exposto na experiência do usuário admin. Da perspectiva de roteamento, isso é igual ao modo de SfBOnly. Quando TeamsAppPolicy estiver disponível, isso permitirá que apenas os canais no app equipes.|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|Verdadeiro|Notificar|Esse modo existe na camada do PowerShell, mas ainda não está exposto na experiência do usuário admin. Da perspectiva de roteamento, isso é igual ao modo de SfBOnly. Quando TeamsAppPolicy estiver disponível, isso permitirá que apenas os canais no app equipes.|
|UpgradeToTeams|TeamsOnly|Falso|Atualizar|Use este modo para atualizar os usuários para equipes e evitar que o bate-papo, chamadas e agendamento de reuniões no Skype para negócios.|
|Global|Herdado|Falso|Nenhum|O modo eventualmente será atualizado para ilhas.|
|NoUpgrade|Herdado|Falso|Nenhum|Esta instância eventualmente será desativada.|
|NotifyForTeams|Herdado|Verdadeiro|Notificar|Esta instância eventualmente será desativada.|
||||||

Essas instâncias de política podem ser concedidas a usuários individuais ou em uma base de todo o inquilino. Por exemplo:
- Para atualizar um usuário ($SipAddress) para equipes, conceda a instância de "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Para atualizar o locatário inteiro, omita o parâmetro identity do comando grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

### <a name="important"></a>IMPORTANTE!
Componentes que anteriormente cumpridas TeamsInteropPolicy estão no processo que está sendo atualizado para honram TeamsUpgradePolicy. Durante a transição, gerenciamento dessas duas políticas deve ser coordenado conforme especificado abaixo. Observe que a atualização recente portal moderno automaticamente concede ambos dessas políticas corretamente quando você seleciona um modo de coexistência.
</br>
</br>
|Se você conceder a uma instância de TeamsUpgradePolicy</br>com este valor de modo …|… Conceda essa instância do TeamsInteropPolicy|
|---|---|
|Ilhas|`DisallowOverrideCallingDefaultChatDefault`|
|SfBOnly, SfBWithTeamsCollab,</br>SfBWithTeamsCollabAndMeetings|`DisallowOverrideCallingSfbChatSfb`|
|TeamsOnly |`DisallowOverrideCallingTeamsChatTeams`|
|||

## <a name="teamsinteroppolicy-to-be-retired"></a>TeamsInteropPolicy para ser retirado 

Conforme descrito anteriormente, TeamsInteropPolicy será substituído pelos TeamsUpgradePolicy. Até que essa transição seja concluída, apenas as três instâncias específicas do TeamsInteropPolicy listadas a seguir são suportadas. Em cada caso, o valor da CallingDefaultClient corresponde ao valor do ChatDefaultClient e AllowEndUserClientOverride é sempre false. 
</br>
</br>
**Instâncias com suporte do TeamsInteropPolicy antes de aposentadoria**
|Identidade |AllowEndUserClientOverride|CallingDefaultClient|ChatDefaultClient|
|---|---|---|---|
|`DisallowOverrideCallingDefaultChatDefault`|Falso|Padrão|Padrão|
|`DisallowOverrideCallingSfbChatSfb`|Falso|Sfb|Sfb|
|`DisallowOverrideCallingTeamsChatTeams`|Falso|Microsoft Teams|Microsoft Teams|
|||||

Use a seguinte sintaxe do cmdlet, onde $policy é um dos valores acima da identidade:`Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

## <a name="federation-considerations"></a>Considerações de Federação

A federação de equipes para outro usuário usando o Skype para negócios requer o usuário equipes hospedados online Skype para negócios. Eventualmente, as equipes que os usuários hospedados no Skype para negócios local será capazes de estabelecer uma federação com outros usuários de equipes.

Depois que o suporte à Federação é habilitado, TeamsUpgradePolicy (juntamente com TeamsInteropPolicy durante a transição) rege roteamento para chamadas e chats federados de entrada. Para facilitar a outras organizações que iniciam comunicações federadas com usuários em sua organização, é recomendável escolher um modo que especificamente roteia um para Skype para negócios ou equipes, em vez de ilhas.
</br>
|Para rotear chamadas e chats para …|Conceder a uma instância de TeamsUpgradePolicy</br> com um desses modos|E conceder essa instância do TeamsInteropPolicy|
|---|---|---|
|Skype for Business|SfBOnly, SfBWithTeamsCollab, </br>SfBWithTeamsCollabAndMeetings|`DisallowOverrideCallingSfbChatSfb`|
|Microsoft Teams|TeamsOnly |`DisallowOverrideCallingTeamsChatTeams`|
||||

## <a name="completing-the-transition-to-mode-management"></a>Conclusão da transição para o gerenciamento de modo

Posteriormente este ano, a Microsoft planeja introduzir um tipo de política novos, TeamsAppPolicy, para controlar quais partes do cliente de equipes estão habilitados (por exemplo, mensagens Instantâneas, reuniões, bate-papo, canais). Quando a nova política para habilitar/desabilitar as cargas de trabalho em equipes se torna disponível, TeamsUpgradePolicy será atualizado para que, quando um administrador tenta conceder uma instância de TeamsUpgradePolicy a um usuário, ele verificará primeiro para garantir que TeamsAppPolicy esteja corretamente configurado para o modo desejado. Caso contrário, o grant falhará com um erro que explica como a outra diretiva deve ser definida pela primeira vez. 

Até TeamsAppPolicy se tornar disponível, TeamsUpgradePolicy essencialmente rege o roteamento de chamadas e a chats, bem como o agendamento de reuniões (conforme exposto por meio de suplementos do Outlook). Porque o comportamento dos clientes de equipes ainda não está no lugar, nem todos os modos estão habilitados no Portal moderno. Da perspectiva de roteamento, os modos de SfBOnly, SfBWithTeamsCollab e SfBWithTeamsCollabAndMeetings são idênticos. 

## <a name="action-required-for-organizations-that-have-already-used-teamsinteroppolicy"></a>Ação necessária para as organizações que já tem usado o TeamsInteropPolicy

Para preparar para essas alterações futuras, os clientes devem fazer o seguinte:

1. Certifique-se de que os usuários com TeamsInteropPolicy são atribuídos apenas uma dessas três instâncias internas, para qual CallingDefaultClient = ChatDefaultClient e para qual AllowEndUserClientOverride = false. Essas instâncias são:
</br>
</br>
   |Identidade |AllowEndUserClientOverride |CallingDefaultClient|ChatDefaultClient|
   |---|---|---|---|
   |`DisallowOverrideCallingDefaultChatDefault`|Falso|Padrão|Padrão|
   |`DisallowOverrideCallingSfbChatSfb`|Falso|Sfb|Sfb|
   |`DisallowOverrideCallingTeamsChatTeams`|Falso|Microsoft Teams|Microsoft Teams|
   |||||

    Use a seguinte sintaxe do cmdlet, onde $policy é um dos valores acima da identidade:

    `Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

    **Microsoft solicita que os clientes atualizem suas diretivas por 30 de junho de 2018.** Um dia depois disso, a Microsoft removerá outras instâncias do TeamsInteropPolicy.</br> 
    ***As organizações que não atualizam a uma dessas instâncias eventualmente terão seus usuários automaticamente atualizados para uma dessas instâncias. Podemos obviamente preferem que os clientes fazem isso, para que você possa escolher o que é mais adequado para seus usuários.***

2. Se você personalizou a política global interna, desfazer isso. Sua política global deve ter os seguintes valores:
</br>
</br>
    |Parâmetro|Valor|
    |---|---|
    |`AllowEndUserClientOverride`|Falso|
    |`CallingDefaultClient`|Padrão|
    |`ChatDefaultClient`|Padrão|
    |||

    Se qualquer um dos valores são diferentes acima, execute o seguinte procedimento para remover quaisquer personalizações específicas locatários:

    `Grant-CsTeamsInteropPolicy -PolicyName $null`

## <a name="detailed-mode-descriptions"></a>Descrições de modo detalhado
</br>
</br>

|Modo|Explicação|
|---|---|
|**Ilhas**|Um único usuário executa ambos os Skype para negócios e equipes--lado a lado. Esse usuário:</br><ul><li>Pode iniciar o bate-papos e chamadas de VOIP em um dos Skype para equipes ou negócios do cliente. Observação: Usuários com Skype para negócios hospedados no local não é possível iniciar das equipes de acessar outra Skype para o usuário de negócios.<li>Recebe chamadas VOIP iniciadas no Skype para negócios por outro usuário em seu Skype para o cliente de negócios e bate-papo.<li>Recebe VOIP chamadas iniciadas no equipes por outro usuário em seu cliente de equipes.<li>Recebe chats iniciadas em equipes por outro usuário em:<ul><li>Skype para negócios fornecido o destinatário é hospedado online e nunca logado ao equipes<li>Equipes em todos os outros casos.</ul><li>Oferece a funcionalidade de PSTN, conforme observado abaixo:<ul><li>Se o usuário estiver hospedado no Skype para negócios local, chamadas PSTN são iniciadas e recebidas no Skype para negócios.<li>Se o usuário está hospedado online, o usuário tem o sistema telefônico, no qual caso o usuário:<ul><li>Inicia e recebe chamadas PSTN em equipes se o usuário estiver configurado para roteamento direto<li>Inicia e recebe chamadas PSTN em Skype para os negócios, se o usuário tiver MS chamar planejar ou conecta-se à rede PSTN por meio de um dos Skype para Business Edition do conector de nuvem ou uma implantação local do Skype para Business Server (voice híbrido)</ul></ul><li>Pode agendar reuniões em equipes ou Skype para negócios (e verá ambas plug-ins por padrão).<li>Podem ingressar em qualquer Skype para reunião de negócios ou equipes; a reunião será aberto no respectivo cliente.</ul>|
|**SfBOnly**|Um único usuário executa apenas Skype para negócios. Esse usuário:</br><ul><li>Pode iniciar o bate-papos e chamadas do Skype para negócios.<li>Recebe qualquer chat/chamada em seu Skype para o cliente de negócios, independentemente de onde for iniciado, a menos que o iniciador é um usuário de equipes com Skype para negócios hospedados no local. * <li>Pode agendar apenas Skype para reuniões de negócios, mas pode ingressar Skype para reuniões de negócios ou equipes. </br> *Usando Ilhas com usuários no local não é recomendado em combinação com outros usuários no modo de SfBOnly. Se um usuário de equipes com Skype para negócios hospedado no local inicia uma chamada ou converse com um usuário SfBOnly, o usuário SfBOnly é inalcançável e recebe um email.* de bate-papo/chamadas não atendidas|
|**SfBWithTeamsCollab**|Um único usuário executa ambos os Skype para negócios e equipes--lado a lado. Esse usuário:</br><ul><li>Tem a funcionalidade de um usuário no modo de SfBOnly.<li>As equipes tem habilitado somente para colaboração de grupo (canais); agendamento de bate-papo/chamada/reunião estão desabilitadas.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>(planejado)|Um único usuário executa ambos os Skype para negócios e equipes--lado a lado. Esse usuário:<ul><li>Tem o bate-papo e a funcionalidade de chamada do usuário no modo de SfBOnly.<li>As equipes tem habilitado para colaboração de grupo (canais); bate-papo e chamadas estão desabilitadas.<li>Pode agendar reuniões de equipes apenas, mas pode ingressar Skype para reuniões de negócios ou equipes.</ul>|
|**TeamsOnly**</br>(requer SfB Online residencial)|Um único usuário executa apenas equipes. Esse usuário:<ul><li>Recebe qualquer bate-papos e chamadas em seu cliente de equipes, independentemente de onde for iniciado.<li>Pode iniciar o bate-papos e chamadas de equipes.<li>Pode agendar reuniões em equipes, mas pode ingressar Skype para reuniões de negócios ou equipes.<li>Pode continuar a usar o Skype para telefones IP de negócios.</ul> |
|**Herdado**</br>(padrão)|Esse modo é usado durante a transição enquanto estamos encerrar TeamsInteropPolicy. Diferentes componentes do sistema serão atualizados para usar TeamsUpgradePolicy em momentos diferentes. Durante essa transição, os usuários com esse modo continuará honram o valor TeamsInteropPolicy existente. Isso permite uma experiência de usuário consistente, mesmo que diferentes componentes no serviço estejam atualizadas em momentos diferentes.|
|||

## <a name="summary-of-planned-functionality-changes-to-simplify-coexistence-and-migration"></a>Resumo das alterações de funcionalidade planejada para simplificar a coexistência e migração

Com base nos comentários forte de toque em clientes e outros usuários iniciais, Microsoft anunciado alterações planejadas em abril para simplificar a capacidade de gerenciamento e aumentar a satisfação do usuário final como organizações migrar do Skype para negócios às equipes. Essas alterações fornecerão uma experiência de usuário final de simplificado e mais previsível, usando um modelo de diretiva simplificada para o gerenciamento de atualização e interoperabilidade. As alterações descritas abaixo desse tipo serão implantadas incrementalmente nos próximos vários meses. Em um alto nível, há quatro alterações funcionais planejadas, descritas abaixo.
</br>
</br>
**Alterar #1: Não há mais sobreposição modalidades quando o cliente preferencial estiver definido**
|||
|---|---|
|**DECISÃO**|*Quando o cliente preferencial de um usuário estiver definido como "Equipes" ou "Sfb"*, um determinado modalidade (mensagens Instantâneas, agendar, chamar da reunião) só estará disponível e com suporte em um cliente (equipes ou Skype para negócios) para esse usuário. (*Cliente preferencial* refere-se para os parâmetros DefaultChatClient e DefaultCallingClient na TeamsInteropPolicy.) Somente quando o cliente preferencial é definido como "Default" (no futuro conhecido como "Modo ilhas") será uma determinado modalidade estar disponível e com suporte nos dois clientes. |
|**RACIOCÍNIO**|Os comentários consistente que recebemos são que os usuários estão confusos para um ou outro motivo ao tentar usar ambos os clientes com sobrepostos modalidades. É difícil prever e entender por que land de mensagens e chamadas em um cliente versus outro e presença pode ser falsos ou imprecisa.|
|**STATUS**|Isso é suportado para o modo = TeamsOnly. Suporte para outros modos estarão disponível nos próximos meses. |
|||

**ALTERAR #2: Unificar cliente preferencial para mensagens e de chamadas**
|||
|---|---|
|**DECISÃO**|Microsoft será unificar o gerenciamento de cliente preferencial para mensagens Instantâneas e a chamada. Especificamente, DefaultChatClient e DefaultCallingClient precisam ter o mesmo valor - ambos padrão (Ilhas), equipes, ou ambos os Skype para negócios.  |
|**RACIOCÍNIO**|Se eles não estão alinhados, presença em alguns casos será confuso e confusa. Além disso, iniciar uma chamada a partir de um existente chat poderia ser confusa, porque a chamada pode ir para um cliente diferente que o bate-papo existente. |
|**STATUS**|Essa alteração foi implementada na camada de política usando TeamsUpgradePolicy, bem como no administrador eu (portal moderno). No entanto, a transição ainda não está completa, portanto, os clientes também devem definir TeamsInteropPolicy. Os clientes só devem definir um as três instâncias com suporte do TeamsInteropPolicy, que são: DisallowOverrideCallingTeamsChatTeams, DisallowOverrideCallingDefaultChatDefault, DisallowOverrideCallingSfbChatSfb|
|||

**Alterar #3: Nenhuma mais usuário final opção de cliente preferencial**
|||
|---|---|
|**DECISÃO**|Os usuários finais não terá mais uma opção de cliente preferencial. (AllowEndUserClientOverride em TeamsInteropPolicy deve ser definida como false). O cliente preferencial será baseado no modo, que é definido com o administrador.|
|**RACIOCÍNIO**|Análise de dados de uso mostra que quase nenhum usuário defina esta. Eliminar essa opção simplifica a cenários de admin/assistência técnica e reduz a complexidade de engenharia. Finalmente, se o usuário final escolher um cliente preferencial diferente do que o administrador tiver configurado para roteamento de voz em uma organização com o Enterprise Voice, isso causaria uma experiência de usuário final confusas porque ele for resultar em VOIP e chamadas PSTN inicial em diferentes clientes.|
|**STATUS**|Essa alteração foi implementada na camada de política usando TeamsUpgradePolicy, bem como no administrador eu (Portal moderno). No entanto, a transição ainda não estiver concluída, para que clientes usando cmdlets também devem definir TeamsInteropPolicy como uma das três instâncias com suporte do TeamsInteropPolicy, todos os quais não permitir substituição.|
|||

**ALTERAÇÃO #4: Gerenciamento baseado no cliente "modo"**
|||
|---|---|
|**DECISÃO**|A Microsoft está apresentando o conceito de "modo" para gerenciar o comportamento dos clientes como organizações uso Skype for Business começar a adotar as equipes. Os administradores podem definir o modo em uma base por usuário, e o modo de um usuário direcionarão a funcionalidade para a qual está disponível no qual cliente, bem como onde chamadas e chats land. Admins gerenciará isso via o TeamsUpgradePolicy revisado, que foi atualizado para dar suporte ao modo. TeamsInteropPolicy eventualmente será preterido e removido, depois que todos os componentes foram atualizados para ler TeamsUpgradePolicy.|
|**RACIOCÍNIO**|Para simplificar a capacidade de gerenciamento e aumentar a satisfação do usuário final, migração e interoperabilidade serão gerenciados usando o "modo de coexistência usando TeamsUpgradePolicy. Seleção de modo do usuário orientará o roteamento de chamadas de entrada e de bate-papos e no qual cliente o usuário pode iniciar o bate-papos e chamadas ou agendar reuniões. Consolidação de TeamsUpgradePolicy e TeamsInteropPolicy também impede que configurações incorretas que pode resultar se essas duas diretivas não foram definidas de forma consistente. |
|**STATUS**|Toque em clientes ver agora três modos em UX. o Admin Como suporte para alteração #1 territórios, modos adicionais serão disponibilizados. SfBOnly modo atualmente impede que usuários usem equipes, mas ela será no futuro. |
|||


## <a name="related-topics"></a>Tópicos relacionados

[Get-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsinteroppolicy?view=skype-ps)

[Grant-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsinteroppolicy?view=skype-ps)

[Remove-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsinteroppolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[New-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
