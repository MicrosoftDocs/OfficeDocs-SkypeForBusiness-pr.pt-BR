---
title: Compreender a coexistência e a interoperabilidade do Microsoft Teams e do Skype for Business
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Detalhes das opções de coexistência do Skype for Business e do Microsoft Teams e a interoperabilidade resultante entre o Skype for Business e o Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 430c64fed77412ca555048adf3cf5e323fa20856
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397586"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Compreender a coexistência e a interoperabilidade do Microsoft Teams e do Skype for Business

![Diagrama da jornada de atualização, enfatizando o estágio de Definição do Projeto](media/upgrade-banner-project-definition.png "Etapas da jornada de atualização, com ênfase no estágio de Definição do Projeto")

Este artigo faz parte do estágio de Definição do Projeto da sua jornada de atualização. Conclua depois de criar uma coligação de patrocinadores e equipe de projeto e definir o escopo, as metas e o plano do seu projeto. Antes de prosseguir, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)

Se sua organização usa o Skype for Business hoje e você está começando a usar o Teams juntamente com o Skype for Business ou você está começando a atualizar para o Teams, é importante entender como os dois aplicativos coexistem, quando e como eles interoperam e como gerenciar a migração dos usuários até sua eventual atualização do Skype for Business para o Teams.

> [!Tip]
> Assista à sessão a seguir para saber mais sobre [Coexistência e Interoperabilidade.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> Além disso, você pode se juntar a nós para workshops interativos e ao vivo nos quais compartilharemos orientações, práticas recomendadas e recursos projetados para iniciar o planejamento e a implementação da atualização.
>
> Para começar, participe primeiro da sessão de [Planejamento da atualização](https://aka.ms/SkypeToTeamsPlanning).

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Coexistência do Teams e visão geral do Skype for Business

As seções a seguir descrevem os modos de coexistência disponíveis quando você decide atualizar para o Teams e os recursos que cada modo oferece. Além disso, descrevemos a interoperabilidade (interoperabilidade) que ocorre entre usuários em clientes do Skype-for-Business e usuários em clientes do Teams e como a interoperabilidade é afetada pelo modo de coexistência escolhido.

 O Teams oferece recursos de colaboração, chat, chamada e recursos de reunião. Dependendo de como você optar por implantar o Teams, esses recursos podem se sobrepor aos recursos fornecidos pelo Skype for Business para um determinado usuário. O modo padrão é executar o Teams juntamente com o Skype for Business com os recursos sobrepostas. No entanto, um usuário pode ser atribuído a um dos vários modos de coexistência (também conhecidos como modos de atualização) que foram projetados para garantir que esses recursos não se sobreponham a esse usuário (nesse caso, a interoperabilidade entre o Teams e o Skype for Business está disponível). Por exemplo, se você tiver ativos locais significativos do Skype for Business Server com uma implantação Enterprise Voice complexa, mas quiser que os usuários aproveitem reuniões modernas o mais rapidamente possível, talvez você queira avaliar [Reuniões Primeiro](meetings-first.md) como um caminho alternativo.

Recomendamos que você revise os seguintes modos de coexistência para ajudar a determinar qual caminho é o certo para sua organização.

> [!Important]
> Introduzir nova tecnologia ou fazer alterações no seu ambiente existente e familiar do Skype for Business, ao mesmo tempo em que fornece grandes novos benefícios para os negócios, pode ser prejudicial para os usuários. Leve tempo para avaliar a preparação do usuário e implementar um plano de comunicação e treinamento antes de implementar qualquer uma das alterações descritas neste artigo. Além disso, recomendamos que você pilote seu plano com um grupo selecionado de usuários antes de implementá-lo em toda a sua organização.

### <a name="islands-mode"></a>Modo ilhas

Por padrão, os usuários podem executar o Teams juntamente com o Skype for Business como duas soluções separadas que oferecem recursos semelhantes e sobrepostos. Os recursos incluem presença, chat, chamada e reuniões. Os usuários do Teams também podem aproveitar novos recursos de colaboração, como equipes e canais, acesso a arquivos no Microsoft 365 ou Office 365 e aplicativos.

Nesse modo de coexistência, chamado **Ilhas**, cada um dos aplicativos cliente opera como uma ilha separada. O Skype for Business conversa com o Skype for Business e o Teams conversa com o Teams. Espera-se que os usuários executem os dois clientes o tempo todo e possam se comunicar de forma nativa no cliente a partir do qual a comunicação foi iniciada. Como tal, não há necessidade de interoperabilidade no **modo Ilhas.**

Para evitar uma experiência confusa ou regressiva do Skype for Business, o Skype for Business lida com as seguintes integrações que não são manipuladas no modo ilhas **do** Teams:

- Comunicações externas (federadas).
- Serviços de voz e aplicativos de voz PSTN, integração com o Office.
- Controles HID para dispositivos USB.
- Várias outras integrações.  

O Sistema de Telefonia não tem suporte no modo Teams in **Islands.** **O** modo de ilhas não dá suporte Enterprise Voice cliente é o Skype for Business.

> [!Important]
> No **modo Ilhas,** todas as mensagens e chamadas de usuários federados (pessoas de fora da sua organização) são entregues ao Skype for Business. Depois de atualizar para o modo **Somente equipes,** todas as mensagens e chamadas de fora da sua organização são entregues ao Teams.

> [!Tip]
> O caminho recomendado para os clientes do  Skype for Business Online é começar com o modo de Ilhas padrão, impulsionar a saturação de adoção do Teams na organização e, em seguida, mudar para o modo **Teams Only** rapidamente. Os clientes locais e híbridos, especialmente os complexos, podem se beneficiar da implantação  do modo de Colaboração do **Skype for Business** com o Teams como ponto de  partida, em vez do modo Ilhas, e de lá para o modo Skype for Business com Colaboração e Reuniões do **Teams** (ou seja, Reuniões Primeiro), se apropriado, e para o modo Somente equipes quando a organização estiver pronta para adotar o Teams.

### <a name="teams-only"></a>Somente equipes

Um **usuário do Teams Only** (também chamado de *usuário* atualizado) tem acesso a todos os recursos no Teams. Eles podem manter o cliente skype for Business para participar de reuniões no Skype for Business que foram organizadas por usuários não atualizados ou terceiros externos. Um usuário atualizado pode continuar a se comunicar com outros usuários na organização que ainda estão usando o Skype for Business usando  os recursos de interoperabilidade entre o Teams e o Skype for Business (desde que os usuários do Skype for Business não estão no modo Ilhas). No entanto, um usuário atualizado não pode iniciar um chat, chamada ou reunião do Skype for Business.

Assim que sua organização estiver pronta para que alguns ou todos os usuários usem o Teams como sua única ferramenta de comunicação e colaboração, atualize esses usuários para o modo **Somente do Teams.** Se você estiver atualizando do modo **Ilhas,** recomendamos que você primeiro satura a adoção do Teams em toda a sua organização antes de iniciar o processo de atualização. Essa adoção evita cenários de comunicação quebrados devido ao **modo Ilhas** não fornecer interoperabilidade.

Quando no **modo Somente Equipes,** o Teams é o aplicativo padrão para o protocolo SIP/Tel. Os links no cartão de visita de um usuário no Outlook para chamada ou chat serão manipulados pelo Teams.

Para considerações adicionais sobre como mudar para **o modo Somente equipes,** consulte Considerações sobre o modo Somente [do Teams.](teams-only-mode-considerations.md)

![Captura de tela da mensagem de confirmação do Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Cliente skype for Business em execução em um modo especial depois que o usuário é atualizado como um usuário somente do Teams")

### <a name="skype-for-business-only"></a>Somente Skype for Business

Nesse modo de coexistência, os usuários permanecem no Skype for Business, não no Teams, para recursos de chat, reunião e chamadas, e eles não usam o Teams para equipes e canais. Esse modo está disponível hoje; no entanto, na implementação atual, as equipes e canais não são automaticamente desligados para o usuário. Isso pode ser feito usando a política de Instalação de Aplicativos para ocultar equipes e arquivos.

Esse modo pode ser usado antes de iniciar uma implantação gerenciada do Teams para impedir que os usuários começam a usar o Teams antes de terem preparação criada. Esse modo também é uma maneira de habilitar a participação autenticada em reuniões do Teams para usuários do Skype for Business, desde que os usuários sejam licenciados para o Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business com Colaboração do Teams

Use esse modo para introduzir o Teams em seu ambiente enquanto você continua a usar seu investimento existente no Skype for Business. Deixe o Skype for Business inalterado para os recursos de chat, chamada e reunião. Adicionar recursos de colaboração do Teams:

- Equipes e canais.
- Acesso a arquivos no Microsoft 365 ou Office 365.
- Aplicativos. Recursos de comunicações do Teams — chat privado, chamada e reuniões de agendamento.

Por padrão, as reuniões privadas de chat, chamada e agendamento do Teams estão desligadas neste modo.

As organizações com um ponto de partida do Skype for Business  Server local ou híbrido devem considerar esse modo como uma alternativa ao modo Ilhas se quiserem dar aos seus usuários interoperabilidade  e previsibilidade para suas comunicações, bem como ter uma linha do tempo previsível para sua atualização para o Teams (em vez de depender da saturação de adoção no modo Ilhas).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business com Colaboração e Reuniões do Teams, também conhecido como Reuniões Primeiro

Use esse modo de coexistência para acelerar a disponibilidade dos recursos de reunião e colaboração do Teams em sua organização. O modo de coexistência permite que seus usuários aproveitem a experiência superior de reuniões do Teams:

- Ótima qualidade.
- Transcrição e tradução.
- Desfocado em segundo plano.
- Experiência superior do usuário em todas as plataformas, incluindo dispositivos móveis e navegadores.

Além de usar o Teams para equipes e conversas baseadas em canais nesse modo, os usuários usarão o Teams para agendar e conduzir suas reuniões. O chat privado e a chamada permanecem no Skype for Business. O Teams e o Skype for Business se beneficiam de uma variedade de recursos "melhor juntos", como reconciliação de presença, reter/reter automática e suporte a dispositivo HID em ambos os aplicativos. É possível ocultar equipes e canais, se desejado, usando a política de Configuração de Aplicativos.

Esse modo de coexistência é especialmente útil para organizações com implantações locais do Skype for Business com Enterprise Voice. Essas organizações provavelmente levarão algum tempo para atualizar para o Teams e querem se beneficiar das reuniões superiores do Teams assim que possível.

> [!TIP]
> Para ajudar a identificar o modo de atualização recomendado com base nos recursos que você deseja habilitar no Teams enquanto o Skype for Business ainda estiver em uso, aproveite o Assistente de Atualização do [Skype para o Teams.](https://aka.ms/SkypeToTeamsWizard)

Para obter mais informações sobre modos de coexistência, pré-requisitos e gerenciamento, consulte Diretrizes de migração e [interoperabilidade](https://aka.ms/SkypeToTeams-Interop) para organizações que usam o Teams em conjunto com o Skype for Business e Definindo suas configurações de [coexistência](https://aka.ms/SkypeToTeams-SetCoexistence)e atualização.

|Ícone do ponto de decisão |Definição de ícone |Descrição |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Ponto de decisão|<ul><li>Quais modos de coexistência melhor se ajustam às necessidades da sua organização e dos usuários?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Próxima etapa|<ul><li>Escolha a melhor abordagem para sua jornada de atualização.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidade do Teams e Skype for Business

Interoperabilidade é a capacidade dos usuários do Teams e do Skype for Business na mesma organização se comunicarem entre o Teams e o Skype for Business.

A interoperabilidade é governada pelo modo de coexistência (também conhecido como modo de atualização) do receptor. Não há interoperabilidade quando o receptor está no **modo Ilhas.**

> [!Note]
> Quando implantado em qualquer modo de coexistência, exceto **ilhas,** o Teams e o Skype for Business podem [interoperar,](#interoperability-of-teams-and-skype-for-business)permitindo que os usuários conversem e liguem entre si e garantindo que as comunicações permaneçam fluidas em toda a sua organização durante sua jornada de atualização para o Teams. Os modos de coexistência governam a interoperabilidade. O modo de coexistência do receptor determina se a interoperabilidade estará disponível. Por exemplo, se o receptor estiver em um modo no qual o chat só está disponível em um cliente (por exemplo, Teams), a interoperabilidade de chat geralmente estará disponível caso o iniciador use o outro cliente (nesse caso, Skype for Business) para iniciar o chat. Por outro lado, se o receptor estiver no modo no qual o chat está disponível em ambos os clientes (modo Ilhas), a interoperabilidade não estará disponível para o chat. A mensagem será recebida pelo receptor no mesmo cliente no qual o iniciador iniciou o chat. Portanto, a comunicação adequada no **modo Ilhas** requer saturação de adoção do Teams; ou seja, todos os usuários ativamente usando e monitorando ambos os clientes.

> [!Note]
> **Para ter a experiência de coexistência mais recente, a versão do cliente deve ser o cliente mais recente disponível no canal de implantação do Office do usuário.**

#### <a name="native-interop-and-interop-escalation"></a>Escalonamento de interop e interop nativo

Há dois tipos de experiências de interop: escalonamento nativo e interop.

- Uma _experiência de interop_ nativa ocorre no cliente que o usuário está usando no momento. Um usuário estará no cliente Skype for Business, o outro no Teams. Uma experiência de interop nativa não os levará a outro cliente para se comunicar. Os usuários poderão conduzir sua conversa no cliente que estão usando no momento. As experiências de interop nativas são chat e chamada de um para um.
- Uma experiência de _escalonamento_ de interop significa que, como parte de ajudar os usuários a executar uma ação avançada (como compartilhar sua área de trabalho), o cliente facilita a criação de uma reunião na qual os usuários podem participar para continuar a experiência nessa reunião. A reunião é criada na plataforma do iniciador da ação. O usuário ou os usuários que não estão nessa plataforma recebem um link de junção de reunião. Ao clicar neste link, eles são ingressos na reunião em um cliente compatível (navegador, aplicativo Web ou cliente completo, dependendo da configuração). A escalonamento de interop do Skype for Business requer um cliente recente. A escalonamento de interop do Teams agora está disponível. Ambos têm suporte em experiências de interoperabilidade no locatário e para locatários de comunicação federada.

#### <a name="native-interop-experiences"></a>Experiências de interop nativas

Dependendo dos modos de coexistência atribuídos aos usuários (conforme descrito anteriormente), as seguintes experiências de interopção nativas estão disponíveis:

Os usuários do Skype for Business podem conversar um a um com usuários do Teams e vice-versa. Um chat de interop precisa passar por um gateway de interop que faz parte dos serviços de nuvem do Teams (e, portanto, só existe online). Os chats de interop são texto sem texto: não há suporte para rich text e emoticons. Os usuários no Teams e no Skype for Business são notificados de que a conversa é uma conversa de interop.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Os usuários do Skype for Business podem fazer chamadas de voz e vídeo para usuários do Teams, e os usuários do Teams podem fazer o mesmo.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> As experiências de interopção com uma implantação local do Skype for Business exigem que o ambiente local está em modo híbrido com o Microsoft 365 ou o Office 365 Skype for Business. Para obter detalhes, consulte [Diretrizes de migração e interoperabilidade.](https://aka.ms/SkypeToTeams-Interop)

Essas experiências de interop estão disponíveis para e entre usuários que têm um dos seguintes modos de coexistência atribuídos: Skype for Business com Colaboração **do Teams,** Skype for Business com Colaboração e reuniões do **Teams,** **Skype for Business Only** ou Teams **Only**. Não há interoperabilidade para os usuários no **modo Ilhas.**

#### <a name="native-interop-experience-limitations"></a>Limitações da experiência de interop nativa

Devido à diferença de protocolos e tecnologia, não é possível dar suporte a todos os recursos de forma nativa. Especificamente, os seguintes recursos não estão disponíveis:

- Markdown, rich text e o conjunto emoticon completo não têm suporte do Teams ou do Skype for Business. Outros recursos nativos da caixa de redação em chats do Teams não são suportados.
- O compartilhamento de tela (área de trabalho ou compartilhamento de aplicativos) entre o Teams e o Skype for Business não tem suporte nativo. No entanto, ele é suportado por meio de escalonamento de interop.
- Os chats em grupo (conversas de várias partes) no Teams só podem incluir participantes que estão usando o Teams.
- As conversas de IM de várias partes (chats em grupo) no Skype for Business só podem incluir participantes que estão usando o Skype for Business. No entanto, a escalonamento de interop para várias partes está disponível no Skype for Business.
- Não há suporte para a escalada de uma chamada de voz ou vídeo ponto a ponto em uma chamada de várias partes envolvendo usuários do Teams e do Skype for Business.
- Não há suporte para transferência de arquivos para chats de duas partes ou anexo de arquivo em chats de grupo do Teams para o Skype for Business e vice-versa.
- Não há interoperabilidade com o Chat Persistente do Skype for Business.

Para todas essas limitações (exceto para Chat Persistente), uma solução alternativa possível é que um usuário inicie uma reunião e convide o outro usuário a participar dela.

Essa solução alternativa é a base para escalonamento de interop. Em particular, o compartilhamento de tela e a escalonamento para várias partes não podem ser alcançados de forma nativa, mas são suportados por meio de escalonamento de interop.

#### <a name="interop-escalation-experiences"></a>Experiências de escalonamento de interop

A escalonamento de interop consiste em complementar os recursos nativos de interop com escalonamentos gerenciados para reuniões. As reuniões oferecem experiências ricas disponíveis para qualquer pessoa, independentemente de qual cliente eles tenham.

Quando a escalonamento de interop é disparada pelo usuário do Teams, uma reunião do Teams é criada. Quando ele é acionado pelo usuário do Skype for Business, uma reunião do Skype for Business é criada. Em ambos os casos, a reunião criada é uma **reunião Reunir agora,** que não se reflete no calendário do usuário.

A outra parte recebe o link de junção de reunião por meio de chat de interop e inspeções clicando nesse link. Se o usuário do Skype for Business tiver uma conta do Teams e for convidado pelo usuário do Teams, ele ingressará na reunião autenticada. Caso contrário, eles ingressarão como participantes anônimos. Por outro lado, os usuários do Teams quase sempre têm uma conta do Skype for Business e um cliente do Skype for Business que podem usar para ingressar em uma reunião do Skype for Business como um participante autenticado, mas também podem ingressar como participantes anônimos, por exemplo, usando o Aplicativo de Reunião do Skype.

Depois que as partes ingressarem na reunião, elas poderão conduzir qualquer atividade suportada em reuniões, como compartilhamento de área de trabalho ou conteúdo, compartilhamento ou transferência de arquivos, adição de outros participantes e assim por diante.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalonamento de interop do Skype for Business

A escalonamento de interop e interop do Skype for Business foi atualizada no build de julho de 2019 do C2R mensal. Anteriormente, o Skype for Business não tinha conhecimento antecipado de que a parte remota estava usando o Teams. Ele apenas suou que a partir da sinalização recebida após uma sessão ter sido estabelecida.

Quando a sinalização indicava que a resposta veio (ou por meio) do gateway de interop, ela exibiria a barra de negócios amarela (faixa) indicando que a outra parte não estava usando o Skype for Business. Com a evolução do nosso serviço, isso resultou em falsos positivos em que os usuários do Skype for Business veriam a barra de negócios quando estavam conectados ao Serviço de Caixa Postal na Nuvem ou a outros serviços de voz na nuvem, em vez de a um usuário real do **Teams Only.**

Para evitar esses falsos positivos, o serviço de presença agora está informando o cliente do Skype for Business quando a outra parte é um **usuário real somente do Teams.** Isso permite que o Skype for Business esteja ciente de que ele precisa criar uma conversa de interop antes de ela ter sido criada e que a janela de conversa seja específica para a interop.

![Captura de tela da mensagem do Teams para criar uma conversa de interop com um usuário do Skype for Business](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Se o usuário do Skype for Business quiser compartilhar sua área de trabalho, por exemplo, ele será informado de que iniciaremos uma reunião e guiaremos as etapas.

![Captura de tela da mensagem do Teams para iniciar a reunião com um usuário do Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Enquanto isso, o usuário do Teams recebe uma mensagem de chat de entrada com o link para a reunião e é orientado a ingressar.

Essa escalada para uma reunião do Skype for Business está disponível para chamadas e chats federados entre locatários e inter locatários. Ele está on por padrão e não há nenhuma configuração que o administrador tenha que provisionar.

#### <a name="interop-escalation-from-teams"></a>Escalonamento de interop do Teams

A escalonamento de interop do Teams para uma reunião do Teams agora está disponível quando o usuário do Teams seleciona o botão de compartilhamento de área de trabalho em um thread de interop no locatário com um usuário do Skype for Business ou em um thread de federação de interop entre locatários. A escalonamento de interop é suportada a partir de uma conversa de chat 1:1 ou de uma chamada 1:1.

A funcionalidade é suportada no cliente de área de trabalho do Teams para Windows, no cliente de área de trabalho do Teams para Mac e no cliente Web do Teams em navegadores em que há suporte para compartilhamento de conteúdo, enquanto se comunica com qualquer versão do cliente do Skype for Business.

Em threads de interoperabilidade e em threads de interoperabilidade de federação, o usuário do Teams agora tem os controles (botão) para iniciar o compartilhamento de conteúdo. Quando o usuário do Teams seleciona o botão, ele é apresentado com um menu adicional que informa que para compartilhar conteúdo, ele precisará iniciar uma reunião do Teams.

Se os usuários estavam em uma chamada, o menu também avisa que a chamada atual entre o Teams e o Skype for Business será encerrada à medida que eles são colocados em uma reunião do Teams. Se escolherem, poderão avisar o usuário do Skype for Business antes de aceitar.

![Captura de tela da mensagem do Teams para compartilhar reunião com um usuário do Skype for Business](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Após a aceitação, eles são colocados na reunião do Teams; eles devem começar a compartilhar da bandeja de compartilhamento na reunião.

Enquanto isso, o usuário do Skype for Business recebe uma mensagem de chat de entrada com o link para a reunião e é orientado a ingressar.

Essa escalada para uma reunião do Teams está disponível para chamadas e chats federados entre locatários e inter locatários. Ele está on por padrão e não há nenhuma configuração que o administrador tenha que provisionar. No entanto, ele será desligado para o usuário se o administrador ``-AllowPrivateMeetNow`` se configura ``CsTeamsMeetingPolicy`` como ``$false`` .

Depois de revisar este artigo, consulte Choose your [upgrade journey](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), Migration [and interoperability guidance](https://aka.ms/SkypeToTeams-Interop), [Coexistence with Skype for Business](coexistence-chat-calls-presence.md), and Setting your [coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) for implementation details. Também recomendamos o seguinte vídeo: [Vídeo: Gerenciar Coexistência e Interoperabilidade entre SfB e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Detalhes técnicos da coexistência do Teams e do Skype for Business

As seções a seguir resumem o comportamento que pode ser experimentado ao executar clientes do Teams e do Skype for Business na mesma organização, independentemente do modo e do método de atualização usado:

- [Reuniões](#meetings)
- [Interoperabilidade](#interoperability)
- [Threads de conversa do Teams-Interop versus threads nativos](#teams-conversations---interop-versus-native-threads)
- [Presença](#presence)
- [Federação](#federation)
- [Contatos](#contacts)



### <a name="meetings"></a>Reuniões

Independentemente do modo, os usuários sempre podem participar de qualquer tipo de reunião para a qual são convidados, seja o Skype for Business ou o Teams.  No entanto, os usuários devem ingressar na reunião com um cliente correspondente que corresponda ao tipo de reunião:

- Se a reunião for uma reunião do Teams, todos os participantes (sejam usuários do TeamsOnly, Ilhas ou Skype for Business) usarão o cliente do Teams para ingressar na reunião. Se o Teams não estiver instalado, o usuário será direcionado para a Web, ao tentar ingressar em uma reunião.

- Se a reunião for uma reunião do Skype for Business, todos os participantes (sejam usuários do TeamsOnly, Islands ou Skype for Business) usarão o cliente skype for Business para ingressar na reunião. Se o cliente skype for Business não estiver instalado, o usuário será direcionado para a Web para ingressar por meio do Aplicativo de Reunião do Skype.

Ao organizar reuniões, o tipo de reunião agendado baseia-se no modo do organizador, conforme mostrado na tabela a seguir:

| Modo de organizador    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Todas as reuniões agendadas no Teams. O complemento do Skype for Business não está disponível no Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Todas as reuniões agendadas no Skype for Business. O add-in do Teams não está disponível no Outlook. | 
| Ilhas | Por padrão, as reuniões podem ser agendadas no Skype for Business ou no Teams. Ambos os complementos estão disponíveis no Outlook. No entanto, opcionalmente, você pode exigir que os usuários em Ilhas sempre agendem reuniões no Teams atribuindo a eles uma instância do TeamsMeetingPolicy com PreferredMeetingProviderForIslandsMode=Teams.| 


### <a name="interoperability"></a>Interoperabilidade

Conforme descrito acima em Interoperabilidade do Teams e [skype for Business,](#interoperability-of-teams-and-skype-for-business)o Teams dá suporte à interoperabilidade com o Skype for Business em determinados cenários. A comunicação de interop refere-se a um chat ou chamada entre um usuário do Skype for Business e um usuário do Teams.  A comunicação de interop só é possível entre dois usuários; Não há suporte para chat/chamada de vários usuários ou a adição de usuários adicionais.

Um chat de interop ou chamada entre dois usuários é criado quando cada um dos seguintes são verdadeiros:

- Um usuário está usando o Teams e o outro está usando o Skype for Business.

- O modo do destinatário da comunicação inicial não é Ilhas (caso contrário, a comunicação pousaria no mesmo cliente) se ambos os usuários estão na mesma organização. Em cenários federados, o usuário de envio está usando o Teams e o destinatário não está no modo TeamsOnly. 

- O usuário do Teams NÃO também tem uma conta do Skype for Business no local.

Na comunicação de interop, o chat é somente texto sem texto. Além disso, o compartilhamento de arquivos e o compartilhamento de tela não são *possíveis no chat de interop propriamente dito*. No entanto, os usuários em uma conversa de interop podem facilmente obter compartilhamento de arquivo e/ou tela criando uma reunião sob demanda, de dentro do chat de interop, conforme descrito abaixo:

- Se o usuário do Teams tentar compartilhar sua tela, uma reunião do Teams sob demanda será criada automaticamente e um link de convite para essa reunião será enviado para o cliente do usuário do Skype for Business. Ao clicar no link, o usuário do Skype for Business abrirá o Teams e ingressará na reunião. Os dois usuários agora estão em uma reunião do Teams e podem compartilhar conforme necessário.

- Se o usuário do Skype for Business estiver usando um cliente de 2018 ou posterior e tentar compartilhar qualquer conteúdo, uma reunião do Skype for Business sob demanda será criada automaticamente e um link de convite para essa reunião será enviado para o cliente do usuário do Teams. Ao clicar no link, o usuário do Teams tentará ingressar na reunião do Skype for Business. Se o usuário do Teams tiver o cliente skype for Business instalado, ele será aberto e o usuário será solicitado a entrar (se ainda não tiver feito logor).  Se o usuário do Teams não tiver o cliente skype for Business instalado, o usuário será solicitado a usar a versão da Web. Depois que ambos os usuários estão assinados, eles estão em uma reunião do Skype for Business e podem compartilhar conforme necessário.

### <a name="teams-conversation-threads---interop-versus-native-threads"></a>Threads de conversa do Teams - Interop versus threads nativos

Como as comunicações de interop não suportam todos os recursos da conversa nativa do Teams, o cliente do Teams mantém threads de conversa separados para comunicação do Teams para o Teams e do Teams para o Skype for Business. Essas conversas são renderizadas de forma diferente na interface do usuário: os threads de interop podem ser diferenciados de um thread regular nativo do Teams por:

- Falta de controles para texto rico, compartilhamento de arquivo/tela, incapacidade de adicionar usuários.
- Uma modificação no ícone do usuário de destino, mostrando um "S" para Skype for Business.

Essas diferenças são mostradas nas capturas de tela a seguir:

Uma conversa nativa do Teams para o Teams com o Teste do Usuário G3

![Diagrama mostrando uma conversa nativa do Teams para o Teams](media/teams-upgrade-native-thread.png)

Uma conversa de interop com o mesmo Teste de Usuário G3

![Diagrama mostrando uma conversa entre equipes e equipes](media/teams-upgrade-interop-thread.png)

Depois que um thread de conversa é criado, seu tipo nunca muda. Depois de criado, um thread de interop no Teams sempre será roteada para o cliente skype for Business do usuário de destino. Um thread nativo sempre será roteada para o cliente teams do usuário de destino.  Se o modo do usuário do destinatário mudar, os threads existentes do Teams para esse usuário não funcionarão mais e uma observação será exibida nesse chat com um link para iniciar uma nova conversa nativa, conforme mostrado na captura de tela a seguir.

![Diagrama mostrando um chat com usuário atualizado do Skype for Business](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Presença

A presença de um determinado usuário baseia-se na atividade do usuário no serviço por meio do cliente. Em seguida, a presença é publicada para que outros usuários vejam.  O Skype for Business e o Teams são serviços separados com clientes separados, portanto, cada serviço tem seu próprio estado de presença para um usuário.   Também há sincronização entre os serviços de presença no Teams e no Skype for Business Online.  Isso permite que um serviço publique a presença do usuário do outro serviço, se necessário. 

O comportamento de publicação de presença é baseado no modo do usuário. Há três casos básicos:

- Se um usuário estiver no modo TeamsOnly, todos os outros usuários verão a presença do Teams para esse usuário, independentemente do cliente usado.

- Se um usuário estiver em qualquer um dos modos do Skype for Business, todos os outros usuários verão a presença do Skype for Business para esse usuário, independentemente do cliente usado.

- Se um usuário estiver no modo Ilhas, a presença publicada no Skype for Business e no Teams será independente, portanto, a presença mostrada aos usuários dentro da mesma organização dependerá do cliente do outro usuário. Os usuários em organizações federadas verão a presença desse usuário com base em suas atividades do Skype for Business, já que o tráfego federado para um usuário do modo Ilhas chega ao Skype for Business.

Por exemplo, suponha que o Usuário A está no modo Ilhas. Se o Usuário A estiver ativo no Teams, mas não estiver no Skype for Business, outros usuários verão o Usuário A como ativo do cliente do Teams, mas em seu cliente skype for Business, eles veriam o Usuário A como offline. Isso é por design, já que o Usuário A não pode ser atingido se não estiver executando o cliente. 


### <a name="federation"></a>Federação

A federação do Teams para outro usuário que usa o Skype for Business exige que o usuário do Teams seja instalado online no Skype for Business. TeamsUpgradePolicy determina o roteamento para chamadas e conversas federadas e de entrada. O comportamento de roteamento federado é o mesmo para cenários de mesmo locatário, exceto no modo de Ilhas. Quando os destinatários estiverem no modo de Ilhas:

- Chats e chamadas iniciadas a partir do Teams aterram no Skype for Business se o destinatário estiver em um locatário federado.
- Chats e chamadas iniciados a partir do Teams são recebidos no Teams se o destinatário estiver no mesmo locatário.
- Chats e chamadas iniciadas pelo Skype for Business sempre estão no Skype for Business.

Um chat federado pode ser um thread nativo ou um thread de interop. Consulte [Teams Conversations ---interop-versus-native-threads](#teams-conversations---interop-versus-native-threads).

- Se o receptor e o remetente estão no modo de atualização do TeamsOnly, a conversa será uma experiência de chat nativa que inclui todos os recursos avançados de mensagens e chamada. Para saber mais, leia [Experiência de chat nativa para usuários externos (federados) no Teams](native-chat-for-external-users.md). 

- Se um dos participantes da conversa não estiver no modo de atualização do TeamsOnly, a conversa permanecerá uma experiência de interop com mensagens somente texto. A interface do usuário expõe chats federados de maneira semelhante a threads de interop de mesmo locatário, exceto que há uma observação indicando que o usuário é externo.

Para obter mais detalhes, consulte [Manage external access in Microsoft Teams](manage-external-access.md) and Native chat experience for external [(federated) users in Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Contatos

O Teams e o Skype for Business têm listas separadas de contatos. Isso significa que as adições de contato, remoção e modificações feitas em um sistema não são sincronizadas com o outro sistema. No entanto, os contatos do Skype for Business são copiados automaticamente para o Teams quando ocorrem dois eventos específicos: 

- Para qualquer usuário do Skype for Business Online, na primeira vez que fizer logoff no Teams, os contatos do Skype for Business serão copiados para o Teams.  Esse comportamento não está disponível para usuários com uma conta local no Skype for Business Server.  

- Depois que um usuário for atualizado para o TeamsOnly (por meio da atribuição do TeamsUpgradePolicy ou por meio do Move-CsUser -MoveToTeams), na próxima vez que um usuário entrar no Teams, os contatos existentes no Skype for Business serão mesclados com contatos existentes já no Teams. Esse comportamento acontece se a Conta do Skype for Business do usuário está em casa no local ou online. 

Em ambos os casos, a transferência de contatos do Skype for Business para o Teams é assíncrona, portanto, pode levar alguns minutos para que os contatos apareçam no Teams. Os dois eventos acima são o que disparam a cópia.  

### <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
