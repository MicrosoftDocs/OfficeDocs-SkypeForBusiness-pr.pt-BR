---
title: Compreender Microsoft Teams e Skype for Business coexistência e interoperabilidade
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Detalhes das Skype for Business e Microsoft Teams de coexistência e a interoperabilidade resultante entre Skype for Business e Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: f76fa8a527de5cc56d6ae1d2f6a657bf702d9b35
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824670"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Compreender Microsoft Teams e Skype for Business coexistência e interoperabilidade

![Atualize o diagrama de jornada, enfatizando o estágio Project Definição.](media/upgrade-banner-project-definition.png "Etapas da jornada de atualização, com ênfase no estágio de Definição do Projeto")

Este artigo faz parte do estágio de Definição do Projeto da sua jornada de atualização. Conclua depois de criar uma coligação de patrocinadores e equipe de projeto e definir o escopo, as metas e o plano do seu projeto. Antes de prosseguir, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)

Se sua organização usa o Skype for Business hoje e você está começando a usar o Teams juntamente com o Skype for Business, ou você está começando a atualizar para o Teams, é importante entender como os dois aplicativos coexistem, quando e como eles interoperam e como gerenciar a migração dos usuários até a atualização final do Skype for Business para Teams.

> [!Tip]
> Assista à sessão a seguir para saber mais sobre [Coexistência e Interoperabilidade.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> Além disso, você pode se juntar a nós para workshops interativos e ao vivo nos quais compartilharemos orientações, práticas recomendadas e recursos projetados para iniciar o planejamento e a implementação da atualização.
>
> Para começar, participe primeiro da sessão de [Planejamento da atualização](./upgrade-workshops-landing-page.yml).

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Coexistência de Teams e Skype for Business visão geral

As seções a seguir descrevem os modos de coexistência disponíveis quando você decide atualizar para Teams e os recursos que cada modo oferece. Além disso, descrevemos a interoperabilidade (interoperabilidade) que ocorre entre usuários em clientes do Skype-for-Business e usuários em clientes Teams e como a interoperabilidade é afetada pelo modo de coexistência escolhido.

Teams oferece recursos de colaboração, chat, chamada e recursos de reunião. Dependendo de como você optar por implantar Teams, esses recursos podem se sobrepor aos recursos fornecidos pelo Skype for Business para um determinado usuário. O modo padrão é executar Teams com Skype for Business com os recursos sobrepostas. No entanto, um usuário pode ser atribuído a um dos vários modos de coexistência (também conhecidos como modos de atualização) que foram projetados para garantir que esses recursos não se sobreponham a esse usuário (nesse caso, a interoperabilidade entre o Teams e o Skype for Business está disponível). Por exemplo, se você tiver ativos Skype for Business Server locais significativos com uma implantação de Enterprise Voice complexa, mas quiser que seus usuários aproveitem reuniões modernas o mais rapidamente possível, talvez você queira avaliar [Reuniões Primeiro](meetings-first.md) como um caminho alternativo.

Recomendamos que você revise os seguintes modos de coexistência para ajudar a determinar qual caminho é o certo para sua organização.

> [!Important]
> Os modos de coexistência continuam a existir após a aposentadoria do Skype for Business Online, no entanto, os usuários que estão online só podem ter um modo do TeamsOnly. Não é mais possível atribuir qualquer modo diferente do TeamsOnly a um usuário que está em casa online.  Como foi o caso antes da ress reforma do Skype for Business Online, os usuários que estão no local podem ser atribuídos a qualquer modo diferente do *TeamsOnly*.

### <a name="islands-mode"></a>Modo ilhas

Por padrão, os usuários podem executar Teams com Skype for Business como duas soluções separadas que oferecem recursos semelhantes e sobrepostos. Os recursos incluem presença, chat, chamada e reuniões. Teams usuários também podem tirar proveito de novos recursos de colaboração, como equipes e canais, acesso a arquivos em Microsoft 365 e aplicativos.

Nesse modo de coexistência, chamado **Ilhas**, cada um dos aplicativos cliente opera como uma ilha separada. Skype for Business conversa com Skype for Business e Teams conversa com Teams. Espera-se que os usuários executem os dois clientes o tempo todo e possam se comunicar de forma nativa no cliente a partir do qual a comunicação foi iniciada. Como tal, não há necessidade de interoperabilidade no **modo Ilhas.**

Para evitar uma experiência confusa ou Skype for Business, o Skype for Business lida com as seguintes integrações que não são manipuladas no modo Teams **Islands:**

- Comunicações externas (federadas).
- Serviços de voz e aplicativos de voz PSTN, Office integração.
- Controles HID para dispositivos USB.
- Várias outras integrações.  

Sistema de Telefonia há suporte no Teams no **modo Ilhas.** **O modo** Ilhas não dá suporte Enterprise Voice cliente é Skype for Business.

> [!Important]
> No **modo Ilhas,** todas as mensagens e chamadas de usuários federados (pessoas de fora da sua organização) são entregues Skype for Business. Depois de atualizar para o **modo Somente Teams,** todas as mensagens e chamadas de fora da sua organização serão entregues Teams.

### <a name="teams-only"></a>Teams Somente

Um **Teams usuário** somente (também  chamado de usuário atualizado) tem acesso a todos os recursos no Teams. Eles podem reter o cliente Skype for Business para ingressar em reuniões Skype for Business que tenham sido organizadas por usuários não atualizados ou terceiros externos. Um usuário atualizado pode continuar a se comunicar com outros usuários na organização que ainda estão usando o Skype for Business usando os recursos de interoperabilidade  entre o Teams e o Skype for Business (desde que os usuários Skype for Business não estão no modo Ilhas). No entanto, um usuário atualizado não pode iniciar um Skype for Business chat, chamada ou reunião.

Assim que sua organização estiver pronta para que alguns ou todos os usuários usem o Teams como sua única ferramenta de comunicação e colaboração, atualize esses usuários para o modo Somente **Teams.** Se você estiver atualizando do modo **Ilhas,** recomendamos que você primeiro satura Teams adoção em toda a sua organização antes de iniciar o processo de atualização. Essa adoção evita cenários de comunicação quebrados devido ao **modo Ilhas** não fornecer interoperabilidade.

Quando no **Teams modo Somente,** Teams é o aplicativo padrão para o protocolo SIP/Tel. Os links no cartão de visita de um usuário Outlook para chamada ou chat serão tratados por Teams.

Para considerações adicionais sobre como mover **para o modo somente** Teams, consulte Teams [considerações do modo Only.](teams-only-mode-considerations.md)

![Captura de tela Teams mensagem de confirmação.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business cliente em execução em um modo especial depois que o usuário é atualizado como um usuário somente Teams usuário")

### <a name="skype-for-business-only"></a>Somente Skype for Business

Nesse modo de coexistência, os usuários permanecem em Skype for Business— não Teams — para recursos de chat, reunião e chamada, e eles não usam o Teams para equipes e canais. Esse modo está disponível hoje; no entanto, na implementação atual, as equipes e canais não são automaticamente desligados para o usuário. Isso pode ser feito usando a política de Instalação de Aplicativos para ocultar equipes e arquivos.

Esse modo pode ser usado antes de iniciar uma implantação gerenciada de Teams para impedir que os usuários começam a usar Teams antes de ter preparação criada. Esse modo também é uma maneira de habilitar a participação autenticada em reuniões Teams para Skype for Business usuários, desde que os usuários sejam licenciados para Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business com Teams Colaboração

Use este modo para apresentar Teams ambiente enquanto você continua a usar seu investimento existente em Skype for Business. Deixe Skype for Business inalterado para os recursos de chat, chamada e reunião. Adicione Teams de colaboração:

- Teams e canais.
- Acesso a arquivos em Microsoft 365 ou Office 365.
- Aplicativos. Teams comunicações — chat privado, chamada e reuniões de agendamento.

Teams chat privado, chamada e reuniões de agendamento estão desligadas por padrão neste modo.

As organizações com um ponto de partida do Skype for Business Server local ou  híbrido devem considerar esse modo como uma alternativa ao modo Ilhas se quiserem dar aos seus usuários interoperabilidade e previsibilidade para suas  comunicações, bem como ter uma linha do tempo previsível para sua atualização para Teams (em vez de depender da saturação de adoção no modo Ilhas).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business com Teams colaboração e reuniões, também conhecidas como Reuniões Primeiro

Use esse modo de coexistência para acelerar a disponibilidade de recursos Teams de reunião e colaboração em sua organização. O modo de coexistência permite que os usuários aproveitem a experiência superior Teams reuniões:

- Ótima qualidade.
- Transcrição e tradução.
- Desfocado em segundo plano.
- Experiência superior do usuário em todas as plataformas, incluindo dispositivos móveis e navegadores.

Além de usar Teams para equipes e conversas baseadas em canais nesse modo, os usuários usarão o Teams para agendar e conduzir suas reuniões. Chat privado e chamada permanecem no Skype for Business. Teams e Skype for Business se beneficiam de uma variedade de recursos "melhor juntos", como reconciliação de presença, resuspensão/reter automática e suporte a dispositivo HID em ambos os aplicativos. É possível ocultar equipes e canais, se desejado, usando a política de Configuração de Aplicativos.

Esse modo de coexistência é especialmente útil para organizações com Skype for Business implantações locais com Enterprise Voice. Essas organizações provavelmente levarão algum tempo para atualizar para Teams e querem se beneficiar das reuniões Teams superiores assim que possível.

> [!TIP]
> Para ajudar a identificar o modo de atualização recomendado com base nos recursos que você deseja habilitar no Teams enquanto o Skype for Business ainda estiver em uso, aproveite o Skype para Teams [Assistente de](https://aka.ms/SkypeToTeamsWizard)Atualização.

Para obter mais informações sobre modos de coexistência, pré-requisitos e gerenciamento, consulte Diretrizes de migração e [interoperabilidade](./migration-interop-guidance-for-teams-with-skype.md) para organizações que usam Teams em conjunto com Skype for Business e Configurando suas configurações de [coexistência](./setting-your-coexistence-and-upgrade-settings.md)e atualização.

|Ícone do ponto de decisão |Definição de ícone |Descrição |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Ponto de decisão|<ul><li>Quais modos de coexistência melhor se ajustam às necessidades da sua organização e dos usuários?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Próxima etapa|<ul><li>Escolha a melhor abordagem para sua jornada de atualização.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidade de Teams e Skype for Business

Interoperabilidade é a capacidade de Teams e Skype for Business usuários na mesma organização se comunicarem entre Teams e Skype for Business.

A interoperabilidade é governada pelo modo de coexistência (também conhecido como modo de atualização) do receptor. Não há interoperabilidade quando o receptor está no **modo Ilhas.**

> [!Note]
> Quando implantado em qualquer modo de coexistência, exceto **Ilhas,** Teams e Skype for Business podem [interoperar,](#interoperability-of-teams-and-skype-for-business)permitindo que os usuários conversem e liguem entre si e garantindo que as comunicações permaneçam fluidas em toda a sua organização durante sua jornada de atualização para Teams. Os modos de coexistência governam a interoperabilidade. O modo de coexistência do receptor determina se a interoperabilidade estará disponível. Por exemplo, se o receptor estiver em um modo no qual o chat só está disponível em um cliente (por exemplo, Teams), a interoperabilidade de chat geralmente estará disponível caso o iniciador use o outro cliente (nesse caso, Skype for Business) para iniciar o chat. Por outro lado, se o receptor estiver no modo no qual o chat está disponível em ambos os clientes (modo Ilhas), a interoperabilidade não estará disponível para o chat. A mensagem será recebida pelo receptor no mesmo cliente no qual o iniciador iniciou o chat. Portanto, a comunicação adequada **no modo Ilhas** requer Teams saturação de adoção; ou seja, todos os usuários ativamente usando e monitorando ambos os clientes.

> [!Note]
> **Para ter a experiência de coexistência mais recente, a versão do cliente deve ser o cliente mais recente disponível no canal de implantação Office usuário.**

#### <a name="native-interop-and-interop-escalation"></a>Escalonamento de interop e interop nativo

Há dois tipos de experiências de interop: escalonamento nativo e interop.

- Uma _experiência de interop_ nativa ocorre no cliente que o usuário está usando no momento. Um usuário estará no cliente Skype for Business, o outro no Teams. Uma experiência de interop nativa não os levará a outro cliente para se comunicar. Os usuários poderão conduzir sua conversa no cliente que estão usando no momento. As experiências de interop nativas são chat e chamada de um para um.
- Uma experiência de _escalonamento_ de interop significa que, como parte de ajudar os usuários a executar uma ação avançada (como compartilhar sua área de trabalho), o cliente facilita a criação de uma reunião na qual os usuários podem participar para continuar a experiência nessa reunião. A reunião é criada na plataforma do iniciador da ação. O usuário ou os usuários que não estão nessa plataforma recebem um link de junção de reunião. Ao clicar neste link, eles são ingressos na reunião em um cliente compatível (navegador, aplicativo Web ou cliente completo, dependendo da configuração). O escalonamento de Skype for Business requer um cliente recente. A escalonamento de interop Teams agora está disponível. Ambos têm suporte em experiências de interoperabilidade no locatário e para locatários de comunicação federada.

#### <a name="native-interop-experiences"></a>Experiências de interop nativas

Dependendo dos modos de coexistência atribuídos aos usuários (conforme descrito anteriormente), as seguintes experiências de interopção nativas estão disponíveis:

Skype for Business usuários podem conversar um a um com Teams usuários e vice-versa. Um chat de interop precisa passar por um gateway de interop que faz parte Teams serviços de nuvem (e, portanto, só existe online). Os chats de interop são texto sem texto: não há suporte para rich text e emoticons. Os usuários Teams e em Skype for Business são notificados de que a conversa é uma conversa de interop.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business os usuários podem fazer chamadas de voz e vídeo um para Teams usuários, e Teams os usuários podem fazer o mesmo.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> As experiências de interopção com uma implantação local de Skype for Business exigem que o ambiente local está no modo híbrido com Teams. Para obter detalhes, [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

Essas experiências de interopção estão disponíveis para e entre usuários que têm um dos seguintes modos de coexistência atribuídos: Skype for Business com colaboração **do Teams**, Skype for Business com colaboração e reuniões do **Teams,** **Skype for Business Somente** Skype for Business , ou **Teams Somente**. Não há interoperabilidade para os usuários no **modo Ilhas.**

#### <a name="native-interop-experience-limitations"></a>Limitações da experiência de interop nativa

Devido à diferença de protocolos e tecnologia, não é possível dar suporte a todos os recursos de forma nativa. Especificamente, os seguintes recursos não estão disponíveis:

- Markdown, rich text e o conjunto emoticon completo não são suportados de Teams ou Skype for Business. Outros recursos nativos da caixa de redação Teams chats não são suportados.
- O compartilhamento de tela (área de trabalho ou compartilhamento de aplicativos) entre Teams e Skype for Business não tem suporte nativo. No entanto, ele é suportado por meio de escalonamento de interop.
- Chats em grupo (conversas de várias partes) no Teams podem incluir apenas participantes que estão usando Teams.
- As conversas de IM de várias partes (chats de grupo) no Skype for Business podem incluir apenas participantes que estão usando Skype for Business. No entanto, a escalonamento de interop para várias partes está disponível Skype for Business.
- A escalada de uma chamada de voz ou vídeo ponto a ponto em andamento para uma chamada de várias partes envolvendo usuários Teams e Skype for Business não tem suporte.
- Não há suporte para transferência de arquivos para chats de duas partes ou anexo de arquivo em chats de grupo, de Teams para Skype for Business e vice-versa.
- Não há interoperabilidade com Skype for Business Chat Persistente.

Para todas essas limitações (exceto para Chat Persistente), uma solução alternativa possível é que um usuário inicie uma reunião e convide o outro usuário a participar dela.

Essa solução alternativa é a base para escalonamento de interop. Em particular, o compartilhamento de tela e a escalonamento para várias partes não podem ser alcançados de forma nativa, mas são suportados por meio de escalonamento de interop.

#### <a name="interop-escalation-experiences"></a>Experiências de escalonamento de interop

A escalonamento de interop consiste em complementar os recursos nativos de interop com escalonamentos gerenciados para reuniões. As reuniões oferecem experiências ricas disponíveis para qualquer pessoa, independentemente de qual cliente eles tenham.

Quando a escalonamento de interop é disparada pelo usuário Teams, uma reunião Teams é criada. Quando ele é acionado pelo usuário Skype for Business, uma reunião Skype for Business é criada. Em ambos os casos, a reunião criada é uma **reunião reunir agora,** que não se reflete no calendário do usuário.

A outra parte recebe o link de junção de reunião por meio de chat de interop e inspeções clicando nesse link. Se o Skype for Business tiver uma conta Teams e for convidado pelo Teams usuário, ele ingressará na reunião autenticada. Caso contrário, eles ingressarão como participantes anônimos. Por outro lado, os usuários Teams quase sempre têm uma conta Skype for Business e um cliente Skype for Business que podem usar para ingressar em uma reunião do Skype for Business como um participante autenticado, mas também podem ingressar como participantes anônimos, por exemplo, usando o aplicativo Reunião do Skype.

Depois que as partes ingressarem na reunião, elas poderão conduzir qualquer atividade suportada em reuniões, como compartilhamento de área de trabalho ou conteúdo, compartilhamento ou transferência de arquivos, adição de outros participantes e assim por diante.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalonamento de interop de Skype for Business

A escalonamento de interop e interop do Skype for Business foi atualizada na com build de julho de 2019 do C2R mensal. Anteriormente, Skype for Business não tinha conhecimento antecipado de que a parte remota estava usando Teams. Ele apenas suou que a partir da sinalização recebida após uma sessão ter sido estabelecida.

Quando a sinalização indicava que a resposta veio (ou por meio) do gateway de interop, ela exibiria a barra de negócios amarela (faixa) indicando que a outra parte não estava usando Skype for Business. Com a evolução do nosso serviço, isso resultou em falsos positivos em que os usuários do Skype for Business veriam a barra de negócios quando estavam conectados ao Serviço do Caixa postal na Nuvem ou a outros serviços de voz na nuvem, em vez de a um usuário Teams **Somente** de usuário.

Para evitar esses falsos positivos, o serviço de presença agora está informando o cliente Skype for Business quando a outra parte é Teams **usuário** real. Isso permite que Skype for Business esteja ciente de que ele precisa criar uma conversa de interop antes de ela ter sido criada, e a janela de conversa para ser específica para a interop.

![Captura de tela Teams mensagem para criar uma conversa de interop com um Skype for Business usuário.](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Se o Skype for Business quiser compartilhar sua área de trabalho, por exemplo, ele será informado de que iniciaremos uma reunião e guiaremos as etapas.

![Captura de tela Teams mensagem para iniciar a reunião com um Teams usuário.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Enquanto isso, o Teams usuário recebe uma mensagem de chat de entrada com o link para a reunião e é orientado a ingressar.

Essa escalada para uma reunião Skype for Business está disponível para chamadas e chats federados entre locatários e inter locatários. Ele está on por padrão e não há nenhuma configuração que o administrador tenha que provisionar.

#### <a name="interop-escalation-from-teams"></a>Escalonamento de interop de Teams

A escalonamento de Teams para uma reunião de Teams agora está disponível quando o usuário do Teams seleciona o botão de compartilhamento de área de trabalho em um thread de interop no locatário com um usuário Skype for Business ou em um thread de federação de interop entre locatários. A escalonamento de interop é suportada a partir de uma conversa de chat 1:1 ou de uma chamada 1:1.

O recurso é suportado no cliente de área de trabalho do Teams para Windows, no cliente de área de trabalho do Teams para Mac e no cliente web do Teams em navegadores em que há suporte para compartilhamento de conteúdo, enquanto se comunica com qualquer versão do cliente Skype for Business.

Em threads de interoperabilidade e em threads de interoperabilidade de federação, o usuário Teams agora tem os controles (botão) para iniciar o compartilhamento de conteúdo. Quando o Teams o usuário seleciona o botão, ele é apresentado com um menu adicional que informa que para compartilhar conteúdo, ele precisará iniciar uma reunião de Teams.

Se os usuários estavam em uma chamada, o menu também avisa que a chamada atual entre Teams e Skype for Business será encerrada à medida que eles são colocados em uma reunião Teams. Se escolherem, poderão avisar o usuário Skype for Business antes de aceitar.

![Captura de tela Teams mensagem para compartilhar a reunião com um Skype for Business usuário.](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Após a aceitação, eles são colocados na Teams reunião; eles devem começar a compartilhar da bandeja de compartilhamento na reunião.

Enquanto isso, o Skype for Business usuário recebe uma mensagem de chat de entrada com o link para a reunião e é orientado a ingressar.

Essa escalada para uma reunião Teams está disponível para chamadas e chats federados entre locatários e inter locatários. Ele está on por padrão e não há nenhuma configuração que o administrador tenha que provisionar. No entanto, ele será desligado para o usuário se o administrador ``-AllowPrivateMeetNow`` se configura ``CsTeamsMeetingPolicy`` como ``$false`` .

Depois de revisar este artigo, consulte Choose your [upgrade journey](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), Migration [and interoperability guidance](./migration-interop-guidance-for-teams-with-skype.md), [Coexistence with Skype for Business](coexistence-chat-calls-presence.md), and Setting your [coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) for implementation details. Também recomendamos o seguinte vídeo: [Vídeo: Gerenciar Coexistência e Interoperabilidade entre SfB e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Detalhes técnicos sobre Teams e Skype for Business coexistência

As seções a seguir resumem o comportamento que pode ser experimentado ao executar clientes Teams e Skype for Business na mesma organização, independentemente de qual modo e qual método de atualização é usado:

- [Reuniões](#meetings)
- [Interoperabilidade](#interoperability)
- [Threads de conversa interop versus nativo](#interop-versus-native-conversation-threads)
- [Presença](#presence)
- [Federação](#federation)
- [Contatos](#contacts)

### <a name="meetings"></a>Reuniões

Independentemente do modo, os usuários sempre podem participar de qualquer tipo de reunião para a qual são convidados, seja Skype for Business ou Teams.  No entanto, os usuários devem ingressar na reunião com um cliente correspondente que corresponda ao tipo de reunião:

- Se a reunião for uma reunião Teams, todos os participantes (sejam usuários do TeamsOnly, Ilhas ou Skype for Business) usarão o cliente Teams para ingressar na reunião. Se Teams não estiver instalado, o usuário será direcionado para a Web, ao tentar ingressar em uma reunião.

- Se a reunião for uma reunião Skype for Business, todos os participantes (sejam usuários do TeamsOnly, Ilhas ou Skype for Business) usarão o cliente Skype for Business para ingressar na reunião. Se o Skype for Business cliente não estiver instalado, o usuário será direcionado para a Web para ingressar por meio do Reunião do Skype App.

Ao organizar reuniões, o tipo de reunião agendado se baseia no modo do organizador, conforme mostrado na tabela a seguir:

| Modo de organizador    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Todas as reuniões agendadas em Teams. Skype for Business o complemento não está disponível no Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Todas as reuniões agendadas em Skype for Business. Teams o complemento não está disponível no Outlook. | 
| Ilhas | Por padrão, as reuniões podem ser agendadas Skype for Business ou Teams. Ambos os complementos estão disponíveis em Outlook. No entanto, opcionalmente, você pode exigir que os usuários em Ilhas sempre agendem reuniões no Teams atribuindo a eles uma instância do TeamsMeetingPolicy com PreferredMeetingProviderForIslandsMode=Teams.| 


### <a name="interoperability"></a>Interoperabilidade

Conforme descrito acima em [Interoperabilidade](#interoperability-of-teams-and-skype-for-business)de Teams e Skype for Business , Teams oferece suporte à interoperabilidade com Skype for Business em determinados cenários. A comunicação de interop refere-se a um chat ou chamada entre um usuário Skype for Business e um Teams usuário.  A comunicação de interop só é possível entre dois usuários; Não há suporte para chat/chamada de vários usuários ou a adição de usuários adicionais.

Um chat de interop ou chamada entre dois usuários é criado quando cada um dos seguintes são verdadeiros:

- Um usuário está usando Teams e o outro está usando Skype for Business.

- O modo do destinatário da comunicação inicial não é Ilhas (caso contrário, a comunicação pousaria no mesmo cliente) se ambos os usuários estão na mesma organização. Em cenários federados, o usuário de envio está usando Teams e o destinatário não está no modo TeamsOnly. 

- O Teams usuário não tem também uma conta Skype for Business no local.

Na comunicação de interop, o chat é somente texto sem texto. Além disso, o compartilhamento de arquivos e o compartilhamento de tela não são *possíveis no chat de interop propriamente dito*. No entanto, os usuários em uma conversa de interop podem facilmente obter compartilhamento de arquivo e/ou tela criando uma reunião sob demanda, de dentro do chat de interop, conforme descrito abaixo:

- Se o usuário Teams tentar compartilhar sua tela, uma reunião de Teams sob demanda será criada automaticamente e um link de convite para essa reunião será enviado para o cliente Skype for Business usuário do Skype for Business. Ao clicar no link, o Skype for Business usuário abrirá Teams e ingressará na reunião. Os dois usuários agora estão em uma reunião Teams e podem compartilhar conforme necessário.

- Se o usuário Skype for Business estiver usando um cliente de 2018 ou posterior e tentar compartilhar qualquer conteúdo, uma reunião de Skype for Business sob demanda será criada automaticamente e um link de convite para essa reunião será enviado para o cliente do usuário Teams. Ao clicar no link, o Teams usuário tentará ingressar na reunião Skype for Business. Se o Teams tiver o cliente Skype for Business instalado, ele será aberto e o usuário será solicitado a entrar (caso ainda não tenha feito logor).  Se o Teams usuário não tiver o cliente Skype for Business instalado, o usuário será solicitado a usar a versão da Web. Depois que ambos os usuários são assinados, eles estão em uma reunião Skype for Business e podem compartilhar conforme necessário.

### <a name="interop-versus-native-conversation-threads"></a>Threads de conversa interop versus nativo

Como as comunicações de interop não suportam todos os recursos da conversa Teams nativa, o cliente Teams mantém threads de conversa separados para a comunicação Teams-para-Teams e Teams-para-Skype for Business. Essas conversas são renderizadas de forma diferente na interface do usuário: os threads de interop podem ser diferenciados de um thread Teams nativo regular por:

- Falta de controles para texto rico, compartilhamento de arquivo/tela, incapacidade de adicionar usuários.
- Uma modificação no ícone do usuário de destino, mostrando um "S" para Skype for Business.

Essas diferenças são mostradas nas capturas de tela a seguir:

Uma conversa Teams para Teams com User G3 Test

![Diagrama mostrando uma conversa Teams para Teams nativa.](media/teams-upgrade-native-thread.png)

Uma conversa de interop com o mesmo Teste de Usuário G3

![Diagrama mostrando uma conversa Teams para Teams interopção.](media/teams-upgrade-interop-thread.png)

Depois que um thread de conversa é criado, seu tipo nunca muda. Depois de criado, um thread de Teams sempre será roteado para o cliente de Skype for Business do usuário de destino. Um thread nativo sempre será roteado para o cliente de Teams do usuário de destino.  Se o modo do usuário do destinatário mudar, os threads de Teams existentes para esse usuário não funcionarão mais e uma observação será exibida nesse chat com um link para iniciar uma nova conversa nativa, conforme mostrado na captura de tela a seguir.

![Diagrama mostrando um chat com o usuário Skype for Business atualizado.](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Presença

A presença de um determinado usuário baseia-se na atividade do usuário no serviço por meio do cliente. Em seguida, a presença é publicada para que outros usuários vejam.  Skype for Business e Teams são serviços separados com clientes separados, portanto, cada serviço tem seu próprio estado de presença para um usuário.   Também há sincronização entre os serviços de presença no Teams e no Skype for Business Online.  Isso permite que um serviço publique a presença do usuário do outro serviço, se necessário. 

O comportamento de publicação de presença é baseado no modo do usuário. Há três casos básicos:

- Se um usuário estiver no modo TeamsOnly, todos os outros usuários verão Teams presença desse usuário, independentemente de qual cliente eles usam.

- Se um usuário estiver em qualquer um dos modos Skype for Business, todos os outros usuários verão Skype for Business presença desse usuário, independentemente de qual cliente ele use.

- Se um usuário estiver no modo Ilhas, a presença publicada no Skype for Business e Teams são independentes, portanto, a presença mostrada aos usuários dentro da mesma organização dependerá do cliente do outro usuário. Os usuários em organizações federadas verão a presença desse usuário com base em suas atividades Skype for Business, já que o tráfego federado para um usuário do modo Ilhas chega Skype for Business.

Por exemplo, suponha que o Usuário A está no modo Ilhas. Se o Usuário A estiver ativo no Teams, mas não estiver Skype for Business, outros usuários verão o Usuário A como ativo a partir de seu cliente Teams, mas em seu cliente Skype for Business eles veriam o Usuário A como offline. Isso é por design, já que o Usuário A não pode ser atingido se não estiver executando o cliente. 


### <a name="federation"></a>Federação

A federação de Teams para outro usuário usando Skype for Business requer que o usuário Teams para estar em casa online Skype for Business. TeamsUpgradePolicy determina o roteamento para chamadas e conversas federadas e de entrada. O comportamento de roteamento federado é o mesmo para cenários de mesmo locatário, exceto no modo de Ilhas. Quando os destinatários estiverem no modo de Ilhas:

- Chats e chamadas iniciadas Teams em Skype for Business se o destinatário estiver em um locatário federado.
- Chats e chamadas iniciados a partir do Teams são recebidos no Teams se o destinatário estiver no mesmo locatário.
- Chats e chamadas iniciadas Skype for Business sempre são Skype for Business.

Um chat federado pode ser um thread nativo ou um thread de interop. Consulte [Interop versus native conversation threads](#interop-versus-native-conversation-threads).

- Se o receptor e o remetente estão no modo de atualização do TeamsOnly, a conversa será uma experiência de chat nativa que inclui todos os recursos avançados de mensagens e chamada. Para saber mais, leia [Experiência de chat nativa para usuários externos (federados) no Teams](native-chat-for-external-users.md). 

- Se um dos participantes da conversa não estiver no modo de atualização do TeamsOnly, a conversa permanecerá uma experiência de interop com mensagens somente texto. A interface do usuário expõe chats federados de maneira semelhante a threads de interop de mesmo locatário, exceto que há uma observação indicando que o usuário é externo.

Para obter mais detalhes, consulte [Manage external access in Microsoft Teams](manage-external-access.md) and Native chat experience for external [(federated) users in Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Contatos

Teams e Skype for Business têm listas separadas de contatos. Isso significa que as adições de contato, remoção e modificações feitas em um sistema não são sincronizadas com o outro sistema. No entanto, os contatos do Skype for Business são copiados automaticamente para Teams quando ocorrem dois eventos específicos: 

- Para qualquer usuário Skype for Business Online, na primeira vez que fizer logoff no Teams, os contatos do Skype for Business serão copiados para Teams.  Esse comportamento não está disponível para usuários com uma conta local no Skype for Business Server.  

- Depois que um usuário for atualizado para o TeamsOnly (por meio da atribuição do TeamsUpgradePolicy ou por meio do Move-CsUser -MoveToTeams), na próxima vez que um usuário entrar no Teams, os contatos existentes no Skype for Business serão mesclados com contatos existentes já no Teams. Esse comportamento acontece se o usuário foi movido para o TeamsOnly de local ou online. 

Em ambos os casos, a transferência de contatos do Skype for Business para Teams é assíncrona, portanto, pode levar alguns minutos para que os contatos apareçam Teams. Os dois eventos acima são o que disparam a cópia.  

### <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
