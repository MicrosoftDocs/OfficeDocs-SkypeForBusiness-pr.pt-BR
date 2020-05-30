---
title: Atualização do Skype for Business para o Microsoft Teams | Modos, Coexistência
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen, bjwhalen
description: Detalhes das opções e modos de coexistência do Skype for Business e do Microsoft Teams, além da jornadas de atualização do Skype for Business para o Microsoft Teams com exemplos de cenários.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6a1e54d677436b2441e9174cc265eb67b7664d2
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416741"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Escolha a jornada de atualização do Skype for Business para o Teams

![Diagrama da jornada de atualização, enfatizando o estágio de Definição do Projeto](media/upgrade-banner-project-definition.png "Etapas da jornada de atualização, com ênfase no estágio de Definição do Projeto")

Este artigo faz parte do estágio de Definição do Projeto da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)

Como um cliente existente do Skype for Business, sua transição completa para o Teams poderá levar algum tempo. Além disso, para começar a tirar proveito ainda hoje das vantagens do Microsoft Teams, você pode habilitá-lo juntamente com o Skype for Business. Como há alguns recursos sobrepostos entre os dois aplicativos, recomendamos que você revise os modos de coexistência e atualização disponíveis para ajudar a determinar qual caminho é ideal para a sua organização. Por exemplo, você pode optar por habilitar todas as cargas de trabalho nas duas soluções sem interoperabilidade. Ou então, você pode optar por gerenciar a experiência do usuário, introduzindo gradualmente os recursos do Teams ou direcionando grupos de usuários para os recursos selecionados, até que sua organização esteja pronta para atualizar todos para o Teams. Use o resultado do seu piloto para ajudar a determinar a melhor jornada de atualização para sua organização.

> [!IMPORTANT]
> O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams.

Esse artigo descreve os vários modos que lhe permitem gerenciar quais modalidades no Skype for Business e no Teams estarão disponíveis para seus usuários. Como em qualquer implantação, recomendamos que você [teste seu plano pretendido](pilot-essentials.md) com um grupo selecionado de usuários antes de atualizar sua organização para o Teams. Lembre-se de que a introdução de novas tecnologias pode causar problemas aos usuários. Reserve um tempo para avaliar a prontidão do usuário e implementar um plano de comunicação e treinamento antes de implementar qualquer um dos modos descritos aqui.

> [!TIP]
> Junte-se aos workshops interativos e ativos nos quais compartilharemos orientação, práticas recomendadas e recursos projetados para iniciar o planejamento e a implementação da atualização.
>
>Para começar, participe primeiro da sessão de [Planejamento da atualização](https://aka.ms/SkypeToTeamsPlanning).


## <a name="upgrade-journey-building-blocks"></a>Blocos de construção da jornada de atualização

Para preparar formalmente sua organização para a jornada para o Teams, você precisa começar a planejar os cenários de atualização que permitirão que sua organização adote totalmente o Teams como única solução de comunicação e colaboração.

Para lhe ajudar no processo de tomada de decisão, familiarize-se com os vários modos, conceitos e terminologia relevantes para a atualização do Skype for Business para o Teams. Para obter mais informações, confira [Coexistência e interoperabilidade do Microsoft Teams e do Skype for Business](https://aka.ms/SkypeToTeams-Coexist)

Um usuário que migrou para o Teams não usa mais um cliente do Skype for Business, exceto para ingressar em uma reunião hospedada no Skype for Business. Todos os chats recebidos e chamadas entram no cliente das equipes do usuário, independentemente de o remetente usar o Microsoft Teams ou o Skype for Business. Todas as novas reuniões organizadas pelo usuário atualizado serão agendadas como reuniões do Teams. Se o usuário tentar usar o cliente do Skype for Business, o início de chats e chamadas será bloqueado <sup>1</sup>. No entanto, o usuário ainda pode (e deve) usar o cliente do Skype for Business para ingressar nas reuniões que tenha sido convidado.

Os administradores gerenciam a transição para o Teams usando o conceito de [modo](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes), que é uma propriedade do [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Um usuário que foi migrado para o Teams, conforme descrito acima, está no modo "TeamsOnly". Para uma organização que esteja migrando para o Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly.

Há dois métodos para migrar uma organização existente com o Skype for Business (online ou local) para o Teams:

- **Método de recursos sobrepostos** (usando o modo de Uso Paralelo): os usuários de uma organização existente do Skype for Business são introduzidos ao Teams para que possam usar os dois clientes lado a lado durante uma fase de transição. Durante esse período, quase todas as funcionalidades do Teams estarão disponíveis para eles. O modo para essa configuração é referenciado como Uso Paralelo, e esse é o modo padrão para qualquer organização existente com o Skype for Business. Assim que a organização estiver pronta, o administrador moverá os usuários para o modo TeamsOnly.
- **Método de recursos selecionados** (usando um ou mais dos modos Skype for Business): o administrador gerencia a transição (do Skype for Business para as equipes) da funcionalidade de chat, chamadas e agendamento de reunião para os usuários da organização. Cada uma dessas funções está disponível no Skype for Business ou no Teams, mas não em ambas. Os administradores usam o TeamsUpgradePolicy para controlar quando mudar essa funcionalidade para o Teams dos seus usuários. Os usuários que ainda não estão no modo TeamsOnly continuarão a usar o Skype for Business para chats e chamadas, e os dois conjuntos de usuários poderão se comunicar por meio da funcionalidade de interoperabilidade. Os administradores gerenciam a transição migrando progressivamente mais usuários para o modo TeamsOnly.

<sup>1</sup>Clientes mais antigos do Skype for Business enviados antes de 2017 não obedecem ao TeamsUpgradePolicy. Verifique se você está usando o cliente do Skype for Business mais recente disponível no canal do Office.

A seguir estão os principais fatores que ajudarão a decidir o caminho apropriado para sua organização. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Método de recursos sobrepostos (usando o modo de Uso Paralelo)

Com o método de recursos sobrepostos, os usuários podem usar os clientes do Teams e do Skype for Business para chats, chamadas VoIP e reuniões. Nesse método, o chat e as chamadas VOIP no Teams são focadas na organização, enquanto o Skype for Business permite o chat e as chamadas VOIP/PSTN com organizações externas (se for configurado). As reuniões podem ser agendadas e assistidas nos dois produtos.

Ao usar o método de recursos sobrepostos, o tráfego de comunicação do Skype for Business e do Teams permanece separado (mesmo que seja para o mesmo usuário), e os dois clientes diferentes nunca se comunicam entre si (para usuários da mesma organização). As experiências do usuário são baseadas na configuração do destinatário. Por exemplo, suponha que o Usuário A do destinatário esteja usando esse método de atualização:

- A comunicação iniciada do cliente Skype for Business de outro usuário sempre chegará ao cliente Skype for Business do usuário A.
- A comunicação iniciada do cliente do teams a partir de um *usuário na mesma organização* sempre chegará ao cliente do teams do usuário a.
- A comunicação iniciada do cliente do teams a partir de um *usuário em uma organização externa* sempre chegará ao cliente Skype for Business do usuário a.

Se você atribuiu uma licença do Office 365 aos seus usuários, essa será a experiência de atualização padrão da sua organização. Quando você atribui uma licença do Office 365, as licenças do Teams e do Skype for Business Online são atribuídas por padrão.<sup>2</sup>

Para que esse método funcione efetivamente, todos os usuários devem executar ambos os clientes simultaneamente. Os chats e chamadas recebidos de dentro da organização para um usuário no modo de Uso Paralelo podem chegar ao cliente do Skype for Business ou do Teams, mas isso não está sob o controle do destinatário. Depende de qual cliente o remetente usa para iniciar a comunicação. Se o remetente e o destinatário estiverem em organizações diferentes, chamadas e chats recebidos para um usuário no modo de Uso Paralelo sempre chegam ao cliente do Skype for Business.

Por exemplo, se um destinatário do modo de Uso Paralelo estiver conectado ao Skype for Business, mas não ao Teams, e alguém enviar mensagens pelo Teams, o destinatário do modo de Uso Paralelo não verá a mensagem (mas, eventualmente, receberá um email informando que uma mensagem no Teams foi perdida). Da mesma forma, se um usuário estiver executando o Teams, mas não o Skype for Business, e alguém enviar mensagens a esse usuário pelo Skype for Business, o usuário não verá esse chat. O comportamento em cada um desses casos é semelhante para chamadas. Se os usuários não executarem ambos clientes, isso poderá terminar facilmente em frustração.

Usando esse método de atualização, a presença também funcionará de maneira independente entre o Teams e o Skype for Business. Isso significa que outros usuários podem ver estados diferentes de presença para o Usuário A, dependendo do cliente usado. Para saber mais, confira [Presença](upgrade-to-Teams-on-prem-overview.md#presence).

- Outros usuários, ao usar o Teams, verão a presença com base na atividade do usuário A no Teams.
- Para outros usuários, ao usar o Skype for Business, você verá a presença com base na atividade do usuário A no Skype for Business.

Assim que estiver pronto para atualizar os usuários para o modo TeamsOnly, você poderá atualizar os usuários individualmente ou atualizar todo o locatário de uma só vez usando a política do locatário<sup>3</sup>. Assim que um usuário é atualizado para o modo TeamsOnly, ele recebe todos os chats e chamadas recebidos no Teams.

No entanto, os destinatários não atualizados para o modo de Uso Paralelo poderão continuar recebendo chats e chamadas de um usuário do TeamsOnly nos clientes do Skype for Business ou do Teams. Para conversas existentes, o usuário do TeamsOnly responderá ao cliente do remetente que iniciou o chat ou a chamada. 

Para novas conversas do ponto de vista do usuário do TeamsOnly, o chat ou a chamada sempre vai para o cliente das equipes de usuários do modo de ilhas. Isso ocorre porque o cliente do Teams mantém threads de conversas separadas para comunicações de Teams para Teams e de Teams para Skype for Business, mesmo que seja para o mesmo usuário. Para saber mais, confira [Conversas do Teams – Interoperabilidade versus threads nativos](upgrade-to-Teams-on-prem-overview.md#teams-conversations---interop-versus-native-threads).

A tabela a seguir resume a experiência do Teams no modo de Uso Paralelo e no modo TeamsOnly:

| Experiência do Teams | No modo de Uso Paralelo | No modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chats e chamadas recebidos no:|  Teams ou Skype for Business | Teams |
| Chamadas PSTN recebidas em: | Skype for Business <br>(Não há suporte para o uso da funcionalidade PSTN no Teams no modo de Uso Paralelo.)     | Teams |   
 |Presença    | A presença no Skype for Business e no Teams é independente. Os usuários podem ver estados diferentes para o mesmo usuário de Uso Paralelo, dependendo do cliente usado. | A presença baseia-se apenas na atividade do usuário no Teams. Todos os outros usuários, independentemente de qual cliente usam, veem essa presença. | 
 | Agendamento de reunião    | Os usuários podem agendar reuniões no Teams ou no Skype for Business. Por padrão, eles verão ambos os suplementos no Outlook. Você pode definir uma política de reunião do teams para controlar se os usuários só podem usar o suplemento de reunião do Teams e os suplementos de reunião do Skype for Business (em**breve**). Para saber mais, consulte [definir o provedor de reunião para usuários no modo ilhas](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode). |     Os usuários só agendam reuniões no Teams. Somente o suplemento do Teams está disponível no Outlook. | 

A tabela a seguir resume os prós e os contras de usar o método de recursos sobrepostos para migrar sua organização para o Teams.

| Prós     |       Contras |
| :------------------ | :---------------- |
| Permite a adoção rápida dentro de uma organização.| Potencial para confundir o usuário final, porque há dois clientes com funcionalidade semelhante, mas interfaces de usuário diferentes. Além disso, eles não têm controle sobre em qual cliente chegarão os chats/chamadas recebidos. |
| Permite que os usuários aprendam e se familiarizem com o Teams enquanto ainda têm acesso total ao Skype for Business. | Potencial de insatisfação do usuário final devido a mensagens perdidas, caso o usuário não esteja executando ambos os clientes.|
| Esforço administrativo mínimo para começar a usar o Teams. | Pode ser um desafio para "sair do modo de ilhas" e mudar para o modo TeamsOnly se os usuários e aqueles com quem se comunicam regularmente não estiverem usando o Teams de forma inativa.|
|Permite que os usuários aproveitem os recursos para aprimorar o trabalho em equipe que não está disponível no Skype for Business.| Um usuário que esteja usando o Skype for Business no local e o Teams não poderá se comunicar do Teams com outro usuário que esteja usando o Skype for Business no local, mas não tenha o Teams.  |

<sup>2</sup>Isso é verdadeiro mesmo se o usuário estiver hospedado no local no Skype for Business Server. Se o usuário estiver hospedado no local ou online, deixe a licença do Skype for Business Online habilitada, pois atualmente ela é necessária para a funcionalidade completa do Teams.

<sup>3</sup>Observe que a migração de reuniões do Skype for Business para reuniões do Teams só é acionada ao aplicar o TeamsUpgradePolicy aos usuários individuais, e não por locatário. Para obter detalhes, confira [Migração de reunião](upgrade-to-Teams-on-prem-overview.md#meeting-migration).

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Método de recursos selecionados (usando os modos do Skype for Business)

Algumas organizações podem optar por fornecer aos usuários finais uma experiência mais previsível à medida que a organização faz a transição do Skype for Business para o Teams. Nesse modelo, os administradores de TI usam um dos modos do Skype for Business no TeamsUpgradePolicy para designar explicitamente quais recursos permanecem no Skype for Business antes de migrar para o modo TeamsOnly. Quando os usuários estiverem prontos para mudar os recursos selecionados para o modo TeamsOnly, o administrador atualizará o modo deles para o TeamsOnly. Durante a transição:

- Os administradores têm opções para habilitar determinados recursos do Teams para os usuários, mantendo os recursos de chat e chamadas no Skype for Business antes dos usuários migrarem para a experiência do TeamsOnly. A administração pode habilitar os recursos de colaboração do Teams ou os recursos de colaboração e reuniões do Teams.
- Os usuários que ainda estão no Skype for Business recebem todos os chats e chamadas recebidos no cliente Skype for Business, independentemente de se a comunicação se originou das equipes do outro usuário ou do cliente Skype for Business. Além disso, para os usuários do Skype for Business, a funcionalidade de chamada e chat no cliente do Teams está desabilitada para evitar que o usuário final se confunda, e garantir o roteamento e a presença apropriados.
- Os usuários no modo TeamsOnly recebem todos os chats e chamadas recebidos no cliente do Teams e a presença é fornecida pelo Teams, independentemente de onde a comunicação se originou: Teams, Skype for Business ou qualquer tipo de usuário federado.

Diferentemente do método de recursos sobrepostos, no método de recursos selecionados, os usuários do Skype for Business podem se comunicar com os usuários do TeamsOnly. A comunicação entre um usuário do usuário do Skype for Business e do teams é conhecida como [interoperabilidade](upgrade-to-Teams-on-prem-overview.md#interoperability) ou "interoperabilidade". A comunicação de interoperabilidade é possível bilateralmente para chats e chamadas entre um usuário no Skype for Business e outro usuário no Teams. Além disso, os usuários convidados sempre podem participar de uma reunião do Skype for Business ou do Teams; embora, devam usar um cliente que corresponda ao tipo de reunião. Para mais informações, confira [Reuniões](upgrade-to-Teams-on-prem-overview.md#meetings).

Para usuários em um método de recursos selecionados, a presença de um usuário é consistente, independentemente de qual cliente é usado pelo outro usuário. Se o usuário estiver em um dos modos do Skype for Business, todos os outros usuários verão a presença com base na atividade do usuário no Skype for Business. Da mesma forma, se um usuário estiver no modo TeamsOnly, todos os outros usuários verão presença com base na atividade do usuário no Microsoft Teams. Para obter detalhes, confira [Presença](upgrade-to-Teams-on-prem-overview.md#presence).

Para uma organização que optou por seguir o método de recursos selecionados, o administrador deve alterar o modo de todos os locatários de Uso Paralelo para o modo de coexistência apropriado do Skype for Business (SfbWithTeamsCollab ou SfBWithTeamsCollabAndMeetings).  

As experiências dos usuários convidados irão aderir ao modo de coexistência atribuído ao locatário. Se você definir um modo do Skype for Business no nível de locatário, os convidados não poderão usar o chat, fazer chamadas ou mostrar sua presença. Para saber mais, leia [Acesso de convidados no Teams](guest-access.md).

Quando o modo muda de Uso Paralelo para SfbWithTeamsCollab, um usuário que nunca usou o Teams não verá diferença na maneira como usa o Skype for Business. No entanto, se esse usuário começasse a usar o Teams, ele estaria exposto apenas a funcionalidades como Arquivos, Teams e Canal. O agendamento de chats, chamadas e reuniões não estaria disponível no Teams, pois o administrador (por enquanto) designou o Skype for Business como o cliente desejado para essas funções.

> [!NOTE]
> Quando o usuário altera de ilhas para um dos modos do Skype for Business, o cliente do teams de qualquer outro usuário que se comunica com o usuário A precisa saber que o modo de um usuário foi alterado para que ele possa encaminhar a comunicação ao cliente apropriado para o usuário A. Para qualquer usuário que já tenha estabelecido conversas nativas entre equipes e equipes com o usuário A, pode levar algum tempo para que os clientes de equipes de outros usuários estejam cientes da mudança de modo das ilhas para qualquer modo do Skype for Business. Quando os administradores estiverem prontos, poderão deslocar o chat, as chamadas e o agendamento de reuniões para um determinado usuário ao Teams ao mesmo tempo atualizando o modo do usuário para TeamsOnly.

Como alternativa, o administrador poderá primeiro mudar apenas o agendamento de reuniões para o Teams, deixando as funções de chats e chamadas no Skype for Business usando o modo SfBWithTeamsCollabAndMeetings. Esse modo permite que as organizações usem o Teams para reuniões; se os usuários ainda não estiverem prontos para mudar para o modo TeamsOnly (por exemplo, você ainda não está pronto para migrar a funcionalidade PSTN existente). Esse cenário de transição é conhecido como [Primeiro Reuniões](meetings-first.md).


|Experiência do Teams  |No modo SfBWithTeamsCollab |No modo SfBWithTeamsCollabAndMeetings |No modo TeamsOnly  |
|---------|---------|---------|---------|
|Chats e chamadas VOIP de usuários em sua organização recebidos em:     | Skype for Business        | Skype for Business       | Teams        |
|Chamadas PSTN recebidas em:     | Skype for Business        |Skype for Business         | Teams        |
|Presença     | Skype for Business        |Skype for Business         | Teams        |
|Agendamento de Reunião     | Skype for Business         | Microsoft Teams        | Teams        |


A tabela a seguir resume os prós e os contras do uso dos modos do Skype for Business como uma etapa de transição para o modo TeamsOnly.

| Prós     |       Contras |
| :------------------ | :---------------- |
| Roteamento previsível para o usuário final. Todas as chamadas e chats chegam ao Skype for Business ou Teams (mas não a ambos), com base na seleção do administrador.|As conversas de interoperabilidade não têm suporte para o compartilhamento de tela, compartilhamento de arquivos e rich text. Isso pode ser tratado, aproveitando a funcionalidade de Reunir Agora para iniciar uma reunião. |
|Poderá reduzir as chances de um usuário final se confundir, devido a uma determinada funcionalidade está disponível apenas em um cliente. | Os usuários não têm acesso ao Microsoft Teams para atividades comuns realizadas no Skype for Business, como chat e chamadas à frente da atualização para o TeamsOnly.|
|O administrador aumentou o controle sobre o conjunto de recursos disponíveis para os usuários durante a transição do Skype for Business para o Teams. | |
| Permite que uma organização use o Teams para reuniões, mesmo que ainda não esteja pronta para mudar inteiramente para o modo TeamsOnly.||
|A presença de um determinado usuário é a mesma, conforme visualizada por outros, independentemente do cliente usado.||

## <a name="summary-of-upgrade-methods"></a>Resumo dos métodos de atualização
A tabela a seguir resume os métodos de atualização:


|Recursos sobrepostos (usando o modo de Uso Paralelo)  |Recursos selecionados (usando os modos do Skype for Business)  |
|---------|---------|
|Antes de serem atualizados para o TeamsOnly, os usuários devem executar ambos os clientes simultaneamente, pois os chats e chamadas recebidos podem chegar a qualquer cliente.     | Chats e chamadas só se esterram em um cliente, com base no modo do destinatário. Usuários não atualizados podem executar ambos os clientes, mas não há sobreposição funcional (chamadas e chats não estão disponíveis no Teams).         |
|Permite que os administradores introduzam funcionalidades sobrepostas (chats, reuniões, chamadas VOIP) no Skype for Business e no Teams para usuários finais, bem como novos recursos (Teams e Canais) no Teams.     | Permite que os administradores introduzam a funcionalidade selecionada do Teams para usuários finais (Teams e Canais), sem fornecer a mesma funcionalidade que também existe no Skype for Business.        |
|A interoperabilidade entre o Skype for Business e o Teams não existe enquanto os dois usuários estão no modo de Uso Paralelo.      |A interoperabilidade é necessária para a comunicação entre usuários do Skype for Business e do Teams.         |

> [!NOTE]
> Caso não consiga seguir os métodos com suporte para migrar os usuários do Skype for Business Server para o Teams, seria possível fazer a transição dos usuários para o Teams removendo o Skype for Business Server e todos os atributos de usuário relacionados no Active Directory. Depois que atributos do Azure Active Directory dos usuários forem removidos dos atributos do Skype for Business Server e os registros DNS forem redirecionados para o Office 365, seria possível licenciar os usuários no Office 365 e atualizá-los para ao Teams. 

> [!IMPORTANT]
> Com a migração de substituição, os dados de contatos e de reuniões não serão migrados do ambiente local para o Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Ponto de decisão</td><td><ul> Qual jornada de atualização é adequada aos requisitos de negócios da sua organização?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Próxima etapa</td><td><ul> Identificar seu modelo de implantação atual, cenários de uso, e as principais considerações para a sua organização informarão ao Journey to Teams mais adequados para a sua organização.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Ponto de decisão</td><td><ul> Qual cenário de atualização é aplicável à sua organização?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul> Decida a linha do tempo da jornada de atualização da sua organização com base nos requisitos de mensagens, reuniões e chamadas de negócios.<br><br> Decida o trabalho adicional necessário para concluir a jornada de atualização.<br><br></ul></td></tr>
</table>

Depois de escolher a melhor viagem de atualização para sua organização, [realize a atualização para o Microsoft Teams](https://aka.ms/SkypeToTeams-Upgrade).
