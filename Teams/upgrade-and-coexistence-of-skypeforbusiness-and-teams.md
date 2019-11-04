---
title: Atualização do Microsoft Teams do Skype for Business | Modos, coexistência
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen, bjwhalen
description: Detalhes das opções e modos de coexistência do Skype for Business e do Microsoft Teams e de upgrade para o Teams do Skype for Business com cenários de exemplo.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5de243402cd5694b2e4a498f7ff7650cd8f49f4a
ms.sourcegitcommit: 2e005b335b1566c99b93fc311498702838466324
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2019
ms.locfileid: "37931639"
---
![Atualize o diagrama de jornada, enfatizando o estágio de definição do projeto](media/upgrade-banner-project-definition.png "Estágios da jornada da atualização, com ênfase no estágio de definição do projeto")

Este artigo faz parte do estágio de definição do projeto da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Escolher a jornada da atualização do Skype for Business para o Teams

Como cliente existente do Skype for Business, sua transição completa para o Microsoft Teams pode levar algum tempo. No entanto, você pode começar a concretizar o valor do teams hoje, permitindo que seus usuários usem o Microsoft Teams juntamente com o Skype for Business. Como há alguns recursos sobrepostos entre os dois aplicativos, recomendamos que você revise os modos de coexistência e atualização disponíveis para ajudar a determinar qual caminho é ideal para a sua organização. Por exemplo, você pode optar por habilitar todas as cargas de trabalho em ambas as soluções sem interoperabilidade. Ou, você pode decidir gerenciar a experiência do usuário, introduzindo gradualmente os recursos do teams ou direcionando grupos de usuários para obter recursos de seleção, até que a sua organização esteja pronta para fazer a atualização de todos para o Microsoft Teams. Use o resultado do seu piloto para ajudar a avaliar a jornada de atualização certa para a sua organização.

> [!IMPORTANT]
> O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte. Para maximizar a concretização de benefícios e garantir que sua organização tenha tempo adequado para implementar a sua atualização, recomendamos que você comece sua jornada ao Microsoft Teams hoje mesmo.

Este artigo descreve os vários modos que permitem que você gerencie quais modalidades do Skype for Business e do teams estão disponíveis para seus usuários. Assim como em qualquer implantação, recomendamos que você denomine [o plano pretendido](pilot-essentials.md) com um grupo de usuários selecionado antes de atualizar sua organização para o Teams. Lembre-se de que introduzir nova tecnologia pode causar interrupções para os usuários. Reserve algum tempo para avaliar a prontidão do usuário e implementar um plano de comunicação e treinamento antes de implementar qualquer um dos modos descritos aqui.

> [!TIP]
> Junte-se aos workshops interativos e ativos nos quais compartilharemos orientação, práticas recomendadas e recursos projetados para iniciar o planejamento e a implementação da atualização.
>
>Ingresse no [plano da sessão de atualização](https://aka.ms/SkypeToTeamsPlanning) primeiro para começar.


## <a name="upgrade-journey-building-blocks"></a>Atualizar blocos de construção de viagem

Para preparar formalmente sua organização para o seu Journey to Teams, você precisa começar a planejar os cenários de atualização que, eventualmente, permitirão que sua organização adote o Teams como sua única solução de comunicação e colaboração.

Para ajudar a orientar seu processo de tomada de decisões, familiarize-se com os vários modos, conceitos e terminologia relevantes para a atualização do Skype for Business para o Teams. Para obter mais informações, consulte [Microsoft Teams e coexistência e interoperabilidade do Skype for Business](https://aka.ms/SkypeToTeams-Coexist)

Um usuário migrado para o Microsoft Teams não usa mais um cliente Skype for Business, exceto para ingressar em uma reunião hospedada no Skype for Business. Todos os chats recebidos e chamadas entram no cliente das equipes do usuário, independentemente de o remetente usar o Microsoft Teams ou o Skype for Business. Qualquer reunião nova organizada pelo usuário atualizado será agendada como reuniões de equipe. Se o usuário tentar usar o cliente Skype for Business, a iniciação de chats e chamadas será bloqueada<sup>1</sup>. No entanto, o usuário pode (e deve) ainda usar o cliente Skype for Business para ingressar em reuniões para as quais foram convidados.

Os administradores gerenciam a transição para o Microsoft Teams usando o conceito de [Mode](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes), que é uma propriedade de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Um usuário que foi migrado para o Teams, conforme descrito acima, está no modo "TeamsOnly". Para uma organização que está migrando para o Microsoft Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly.

Há dois métodos para migrar uma organização existente com o Skype for Business (seja online ou local) para o Microsoft Teams:

- **Método de recursos sobrepostos** (usando o modo de ilhas): os usuários em uma organização existente do Skype for Business são introduzidos para o Teams, para que eles possam usar os dois clientes lado a lado durante uma fase de transição. Durante esse período, a maioria dos recursos do Microsoft Teams está disponível para eles. O modo dessa configuração é chamado de ilhas, e esse é o modo padrão de qualquer organização existente com o Skype for Business. Depois que a organização estiver pronta, o administrador move os usuários para o modo TeamsOnly.
- **Selecione o método de funcionalidades** (usando um ou mais dos modos do Skype for Business): o administrador gerencia a transição (do Skype for Business para o Teams) de recursos de chat, chamadas e agendamento de reunião para os usuários de sua organização. Cada uma dessas funções está disponível no Skype for Business ou no Teams, mas não ambos. Os administradores usam o TeamsUpgradePolicy para controlar quando mudar essa funcionalidade para o Microsoft Teams para seus usuários. Os usuários que ainda não estão no modo TeamsOnly continuam a usar o Skype for Business para chat e chamadas, e os dois conjuntos de usuários podem se comunicar por meio da funcionalidade de interoperabilidade. Os administradores gerenciam a transição migrando progressivamente mais usuários para o modo TeamsOnly.

<sup>1</sup> Os clientes Skype for Business mais antigos que foram enviados antes do 2017 não obedecem ao TeamsUpgradePolicy. Certifique-se de que você esteja usando o cliente Skype for Business mais recente disponível em seu canal do Office.

Veja a seguir os principais fatores para ajudar a decidir o caminho apropriado para a sua organização. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Método de recursos sobrepostos (usando o modo de ilhas)

Com o método de recursos sobrepostos, os usuários podem usar o Microsoft Teams e clientes do Skype for Business para chats, chamadas de VoIP e reuniões. Nesse método, as chamadas de chat e VOIP em equipes são focadas na organização, enquanto o Skype for Business permite chamadas de chat e VOIP/PSTN com organizações externas (se estiverem definidas). As reuniões podem ser agendadas e assistidas em ambos os produtos.

Ao usar o método de recursos sobrepostos, o tráfego de comunicação do Skype for Business e do teams permanece separado (mesmo para o mesmo usuário) e os dois clientes diferentes nunca se comunicam uns com os outros (para usuários da mesma organização). As experiências do usuário são baseadas na configuração do destinatário. Por exemplo, suponha que o usuário do destinatário A esteja usando este método de atualização:

- A comunicação iniciada do cliente Skype for Business de outro usuário sempre chegará ao cliente Skype for Business do usuário A.
- A comunicação iniciada do cliente do teams a partir de um *usuário na mesma organização* sempre chegará ao cliente do teams do usuário a.
- A comunicação iniciada do cliente do teams a partir de um *usuário em uma organização externa* sempre chegará ao cliente Skype for Business do usuário a.

Se você tiver atribuído uma licença do Office 365 a seus usuários, essa será a experiência de atualização padrão para a sua organização. Quando você atribui uma licença do Office 365, as duas equipes e licenças do Skype for Business online são atribuídas por padrão. <sup>2</sup>

Para que esse método funcione de maneira eficaz, todos os usuários devem executar ambos os clientes simultaneamente. Chats recebidos e chamadas de dentro da organização para um usuário no modo de ilhas podem ser divididos no cliente do Skype for Business ou do Teams, e isso não está sob o controle do destinatário. Depende do cliente que o remetente usa para iniciar a comunicação. Se o remetente e o destinatário estiverem em organizações diferentes, as chamadas recebidas e chats para um usuário no modo ilhas sempre chegam no cliente Skype for Business.

Por exemplo, se um destinatário do modo de ilhas estiver conectado ao Skype for Business, mas não a equipes, e alguém a partir do Teams, o destinatário do modo de ilhas não verá a mensagem (mas, eventualmente, receberá um email informando que perdeu uma mensagem no Teams). Da mesma forma, se um usuário estiver executando o Microsoft Teams, mas não o Skype for Business, e alguém receber o usuário do Skype for Business, o usuário não verá esse chat. O comportamento em cada um desses casos é semelhante para fazer chamadas. Se os usuários não executarem ambos os clientes, poderão levar a frustração facilmente.

A presença também funciona independentemente do Teams e do Skype for Business usando este método de atualização. Isso significa que outros usuários podem ver Estados de presença diferentes para o usuário A, dependendo de qual cliente ele usa. Para obter mais detalhes, consulte [presença](upgrade-to-Teams-on-prem-overview.md#presence).

- Outros usuários, ao usar o Teams, verão a presença com base na atividade do usuário A no Teams.
- Para outros usuários, ao usar o Skype for Business, você verá a presença com base na atividade do usuário A no Skype for Business.

Quando estiver pronto para atualizar os usuários para o modo TeamsOnly, você pode atualizar os usuários individualmente ou pode atualizar o locatário inteiro de uma só vez usando a política<sup>3</sup>de todo o locatário. Depois que um usuário é atualizado para o modo TeamsOnly, ele recebe todos os chats e chamadas recebidos no Teams.

No entanto, os destinatários sem atualização no modo de ilhas podem continuar a receber chats e chamadas de um usuário do TeamsOnly em seus clientes do Skype for Business ou do teams. Para conversas existentes, o usuário do TeamsOnly responderá ao cliente no qual o remetente iniciou o chat ou uma chamada. 

Para novas conversas do ponto de vista do usuário do TeamsOnly, o chat ou a chamada sempre vai para o cliente das equipes de usuários do modo de ilhas. Isso ocorre porque o cliente do teams mantém threads de conversa separados para comunicação entre equipes e equipes para Skype para empresas, mesmo para o mesmo usuário. Para saber mais, consulte [conversas de equipe – interoperabilidade versus threads nativos](upgrade-to-Teams-on-prem-overview.md#teams-conversations---interop-versus-native-threads).

A tabela a seguir resume a experiência do teams para o modo de ilhas e o modo TeamsOnly:

| Experiência do teams | No modo de ilhas | No modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chats recebidos e chamadas recebidas em:|  Teams ou Skype for Business | Teams |
| Chamadas PSTN recebidas em: | Skype for Business <br>(Não há suporte para o uso da funcionalidade PSTN em Teams no modo de ilhas.)    | Teams |   
 |Presença  | A presença no Skype for Business e no Teams é independente. Os usuários podem ver Estados diferentes para o mesmo usuário ilhas, dependendo de qual cliente ele usa. | A presença baseia-se apenas na atividade do usuário no Teams. Todos os outros usuários, independentemente de qual cliente usa, veja essa presença. | 
 | Agendamento de reunião   | Os usuários podem agendar reuniões em qualquer um dos grupos ou no Skype for Business. Eles verão ambos os suplementos no Outlook. |   Os usuários agendam somente reuniões no Teams. Somente o suplemento Teams está disponível no Outlook. | 

A tabela a seguir resume os prós e os contras de usar o método de recursos sobrepostos para migrar sua organização para o Teams.

| Profissionais ti     |       Desvantagens |
| :------------------ | :---------------- |
| Permite a adoção rápida dentro de uma organização.| Potencial para confusão pelo usuário final porque há dois clientes com funcionalidade semelhante, mas interfaces do usuário diferentes. Além disso, eles não têm controle sobre qual cliente os chats/chamadas de entrada chegam. |
| Permite que os usuários aprendam e se familiarizem com o Microsoft Teams e ainda tenham acesso completo ao Skype for Business. | Potencial para insatisfação do usuário final devido a mensagens perdidas se o usuário não estiver executando ambos os clientes.|
| Esforço de administração mínima para começar a usar o Microsoft Teams. | Pode ser um desafio para "sair do modo de ilhas" e mudar para o modo TeamsOnly se os usuários e aqueles com quem se comunicam regularmente não estiverem usando o Teams de forma inativa.|
|Permite que os usuários aproveitem recursos para melhorar o trabalho em equipe que não está disponível no Skype for Business.| Um usuário que estiver usando o Skype for Business no local e em equipes não poderá se comunicar de equipes com outro usuário que esteja usando o Skype for Business no local, mas não tenha equipes.  |

<sup>2</sup> Isso é verdadeiro mesmo que o usuário seja hospedado no Skype for Business Server. Não importa se o usuário está hospedado no local ou online, deixe a licença do Skype for Business online habilitada, pois ela é necessária no momento para a funcionalidade completa do teams.

<sup>3</sup> Observe que a migração de reuniões do Skype for Business para reuniões de equipe é disparada somente ao aplicar TeamsUpgradePolicy a usuários individuais, e não a cada locatário. Consulte [migração de reunião](upgrade-to-Teams-on-prem-overview.md#meeting-migration) para obter detalhes.

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Selecionar método de funcionalidades (usando os modos Skype for Business)

Algumas organizações podem optar por oferecer aos usuários finais uma experiência mais previsível à medida que sua organização faz a transição do Skype for Business para o Teams. Nesse modelo, os administradores de ti usam um dos modos do Skype for Business no TeamsUpgradePolicy para designar explicitamente quais recursos permanecem no Skype for Business antes da migração para o modo TeamsOnly. Como estão prontos para deslocar as funcionalidades selecionadas para o modo TeamsOnly, o administrador atualiza o modo para os usuários TeamsOnly. Durante esta transição:

- Os administradores têm opções para habilitar certos recursos de equipes para os usuários enquanto mantêm recursos de chat e chamadas no Skype for Business antes que os usuários se movimentem para a experiência do TeamsOnly. A administração pode permitir recursos de colaboração de equipes ou reuniões do teams + recursos de colaboração.
- Os usuários que ainda estão no Skype for Business recebem todos os chats e chamadas recebidos no cliente Skype for Business, independentemente de se a comunicação se originou das equipes do outro usuário ou do cliente Skype for Business. Além disso, para esses usuários do Skype for Business, a funcionalidade de chamadas e de chat no cliente do teams é desativada para evitar a confusão do usuário final e garantir o roteamento e a presença adequados.
- Os usuários no modo TeamsOnly recebem todos os chats e chamadas de entrada no cliente e a presença de suas equipes, independentemente de onde a comunicação se originou de: equipes, Skype for Business ou qualquer tipo de usuário federado.

Ao contrário do método de recursos sobrepostos, no método selecionar funcionalidades, os usuários que usam o Skype for Business podem se comunicar com os usuários do TeamsOnly. A comunicação entre um usuário do usuário do Skype for Business e do teams é conhecida como [interoperabilidade](upgrade-to-Teams-on-prem-overview.md#interoperability) ou "interoperabilidade". A comunicação de interoperabilidade é possível em uma base de um-para-um para chats e chamadas entre um usuário no Skype for Business e outro usuário no Teams. Além disso, os usuários convidados sempre podem participar de uma reunião do Skype for Business ou do Teams, mas devem usar um cliente que corresponda ao tipo de reunião. Para obter mais informações, consulte [reuniões](upgrade-to-Teams-on-prem-overview.md#meetings).

Para os usuários em um método de seleção de recursos, a presença de um usuário é consistente independentemente do cliente usado pelo outro usuário. Se o usuário estiver em um dos modos do Skype for Business, todos os outros usuários verão a presença com base na atividade do usuário no Skype for Business. Da mesma forma, se um usuário estiver no modo TeamsOnly, todos os outros usuários verão presença com base na atividade do usuário no Microsoft Teams. Para obter detalhes, consulte [presença](upgrade-to-Teams-on-prem-overview.md#presence).

Para uma organização que optou por seguir o método de seleção de funcionalidades, o administrador deve alterar o modo de todo o locatário das ilhas para o modo de coexistência do Skype for Business adequado (SfbWithTeamsCollab ou SfBWithTeamsCollabAndMeetings).  

Os convidados experiências do usuário respeitarão o modo de coexistência atribuído ao locatário. Se você definir um modo Skype for Business no nível do locatário, os convidados não poderão conversar, ligar ou mostrar sua presença. Para saber mais, leia [Acesso de convidados no Teams](guest-access.md).

Quando o modo muda de ilhas para SfbWithTeamsCollab, um usuário que nunca usou o Teams não verá nenhuma diferença em como usar o Skype for Business. No entanto, caso o usuário comece a usar o Microsoft Teams, eles só serão expostos a funcionalidades como o Teams & Channel e os arquivos. O chat, as chamadas e o agendamento de reuniões não estarão disponíveis no Teams, pois o administrador já tinha o Skype for Business designado (por enquanto), como o cliente desejado para essas funções.

> [!NOTE]
> Quando o usuário altera de ilhas para um dos modos do Skype for Business, o cliente do teams de qualquer outro usuário que se comunica com o usuário A precisa saber que o modo de um usuário foi alterado para que ele possa encaminhar a comunicação ao cliente apropriado para o usuário A. Para qualquer usuário que já tenha estabelecido conversas nativas entre equipes e equipes com o usuário A, pode levar algum tempo para que os clientes de equipes de outros usuários estejam cientes da mudança de modo das ilhas para qualquer modo do Skype for Business. Quando os administradores estiverem prontos, poderão deslocar o chat, as chamadas e o agendamento de reuniões para um determinado usuário ao Teams ao mesmo tempo atualizando o modo do usuário para TeamsOnly.

Como alternativa, o administrador pode primeiro deslocar somente o agendamento da reunião para o Microsoft Teams, enquanto deixa as funções de chat e chamadas no Skype for Business usando o modo SfBWithTeamsCollabAndMeetings. Esse modo permite que as organizações façam a transição para o Microsoft Teams para reuniões--se os usuários ainda não estiverem prontos para serem movidos para o modo TeamsOnly (por exemplo, você ainda não está pronto para migrar a funcionalidade PSTN existente). Esse cenário de transição é conhecido como [reuniões primeiro](meetings-first.md).


|Experiência do teams  |No modo SfBWithTeamsCollab |No modo SfBWithTeamsCollabAndMeetings |No modo TeamsOnly  |
|---------|---------|---------|---------|
|Chats recebidos e chamadas VOIP de usuários de sua organização receberam:     | Skype for Business        | Skype for Business       | Teams        |
|Chamadas PSTN recebidas em:     | Skype for Business        |Skype for Business         | Teams        |
|Presença     | Skype for Business        |Skype for Business         | Teams        |
|Agendamento de reunião     | Skype for Business         | Teams        | Microsoft Teams        |


A tabela a seguir resume os prós e os contras do uso dos modos Skype for Business como uma etapa de transição em direção ao modo TeamsOnly.

| Profissionais ti     |       Desvantagens |
| :------------------ | :---------------- |
| Roteamento previsível para o usuário final. Todas as chamadas e chats se esterram no Skype for Business ou nas equipes (mas não em ambos), com base na seleção de administradores.|As conversas de interoperabilidade não têm suporte para Rich Text, compartilhamento de arquivos e compartilhamento de tela. Isso pode ser útil para aproveitar a funcionalidade reunir agora para iniciar uma reunião. |
|Pode reduzir a confusão do usuário final porque uma determinada funcionalidade está disponível apenas em um cliente. | Os usuários não têm acesso ao Microsoft Teams para atividades comuns realizadas no Skype for Business, como chat e chamadas à frente da atualização para o TeamsOnly.|
|O administrador aumentou o controle sobre o conjunto de recursos disponíveis para os usuários durante a transição do Skype for Business para o Teams. | |
| Permite que uma organização Use equipes para reuniões, mesmo se ainda não estiver pronta para se mover completamente para o modo TeamsOnly.||
|A presença de um determinado usuário visto por outras pessoas é a mesma, independentemente do cliente usado.||

## <a name="summary-of-upgrade-methods"></a>Resumo dos métodos de atualização
A tabela a seguir resume os métodos de atualização:


|Recursos sobrepostos (usando o modo de ilhas)  |Funcionalidades selecionadas (usando os modos Skype for Business)  |
|---------|---------|
|Antes de ser atualizada para o TeamsOnly, os usuários devem executar os dois clientes simultaneamente, já que chats recebidos e chamadas podem chegar em qualquer um dos clientes.     | Chats e chamadas só se esterram em um cliente, com base no modo do destinatário. Os usuários não atualizados podem executar ambos os clientes, mas não há sobreposição funcional (chamadas e chats não estão disponíveis no Teams).         |
|Permite que os administradores introduzam funcionalidades sobrepostas (chat, reuniões, chamadas de VOIP) no Skype for Business e em equipes para usuários finais, além de novos recursos (equipes e canais) no Teams.     | Permite que os administradores introduzam a funcionalidade de seleção do teams para usuários finais (equipes e canais), sem fornecer a mesma funcionalidade que também existe no Skype for Business.        |
|A interoperabilidade entre o Skype for Business e o Teams não existe enquanto ambos os usuários estiverem no modo de ilhas.      |A interoperabilidade é necessária para a comunicação entre os usuários do Skype for Business e do teams.         |

> [!NOTE]
> Se você não conseguir seguir os métodos compatíveis para migrar os usuários do Skype for Business Server para o Teams, é possível fazer a transição dos usuários para o Microsoft Teams, removendo o Skype for Business Server e todos os atributos de usuário relacionados no Active Directory. Após a limpeza dos atributos do Azure Active Directory dos usuários, os atributos do servidor do Skype for Business e os registros DNS foram reapontados para o Office 365, seria possível licenciar os usuários do Office 365 e atualizá-los para o Microsoft Teams. 

> [!IMPORTANT]
> Com a migração de substituição, os dados de contatos e dados de reuniões não serão migrados do ambiente local para o Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Ponto de decisão</td><td><ul> Qual viagem de atualização é adequada para as necessidades comerciais da sua organização?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Próxima etapa</td><td><ul> Identificar seu modelo de implantação atual, cenários de uso, e as principais considerações para a sua organização informarão ao Journey to Teams mais adequados para a sua organização.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Ponto de decisão</td><td><ul> Qual cenário de atualização é aplicável à sua organização?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul> Decida a linha do tempo da viagem de atualização de sua organização com base nas solicitações de mensagens, reuniões e chamadas para empresas.<br><br> Decida o trabalho adicional necessário para concluir a viagem de atualização.<br><br></ul></td></tr>
</table>

Depois de escolher a melhor viagem de atualização para sua organização, [realize a atualização para o Microsoft Teams](https://aka.ms/SkypeToTeams-Upgrade).
