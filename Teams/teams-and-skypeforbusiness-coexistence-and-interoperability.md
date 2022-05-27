---
title: Entender Microsoft Teams e Skype for Business coexistência e interoperabilidade
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Detalhes de Skype for Business e Microsoft Teams coexistência e a interoperabilidade resultante entre Skype for Business e Teams.
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
ms.openlocfilehash: 60ed33e1bbafe7fe5600edfa85c9f9d5a13432db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681422"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Entender Microsoft Teams e Skype for Business coexistência e interoperabilidade

![Diagrama de jornada de atualização, enfatizando o estágio Project definição.](media/upgrade-banner-project-definition.png "Etapas da jornada de atualização, com ênfase no estágio de Definição do Projeto")

Este artigo faz parte do estágio de Definição do Projeto da sua jornada de atualização. Conclua depois de criar uma coligação de patrocínio e equipe de projetos e definir o escopo, as metas e o plano do seu projeto. Antes de continuar, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)

Se sua organização usa o Skype for Business hoje e você está começando a usar o Teams junto com o Skype for Business ou você está começando a atualizar para o Teams, é importante entender como os dois aplicativos coexistem, quando e como eles interoperam e como gerenciar a migração dos usuários até a atualização eventual de Skype for Business para Teams.

> [!Tip]
> Assista à sessão a seguir para saber mais sobre [coexistência e interoperabilidade](https://aka.ms/teams-upgrade-coexistence-interop).
>
> Além disso, você pode se juntar a nós para workshops ao vivo e interativos nos quais compartilharemos diretrizes, práticas recomendadas e recursos projetados para iniciar o planejamento e a implementação da atualização.
>
> Para começar, participe primeiro da sessão de [Planejamento da atualização](./upgrade-workshops-landing-page.yml).

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Coexistência de Teams e Skype for Business visão geral

As seções a seguir descrevem os modos de coexistência que estão disponíveis quando você decide atualizar para o Teams e os recursos que cada modo oferece. Além disso, descrevemos a interoperabilidade (interoperabilidade) que ocorre entre usuários em clientes do Skype-for-Business e usuários em clientes do Teams e como a interoperabilidade é afetada pelo modo de coexistência escolhido.

Teams oferece funcionalidades de colaboração, chat, chamadas e recursos de reunião. Dependendo de como você optar por implantar Teams, esses recursos podem se sobrepor aos recursos fornecidos pelo Skype for Business para um determinado usuário. O modo padrão é executar Teams juntamente Skype for Business os recursos se sobrepõem. No entanto, um usuário pode receber um dos vários modos de coexistência (também conhecidos como modos de atualização) que foram projetados para garantir que esses recursos não se sobreponham a esse usuário (nesse caso, a interoperabilidade entre o Teams e o Skype for Business está disponível). Por exemplo, se você tiver ativos Skype for Business Server locais significativos com uma implantação complexa do Enterprise Voice, mas quiser que os usuários aproveitem reuniões modernas o mais rápido possível, talvez você queira avaliar [o Meetings First](meetings-first.md) como um caminho alternativo.

Recomendamos que você examine os seguintes modos de coexistência para ajudar a determinar qual caminho é ideal para sua organização.

> [!Important]
> Os modos de coexistência continuam a existir após a desativação do Skype for Business Online, no entanto, os usuários hospedados online só podem ter um modo do TeamsOnly. Não é mais possível atribuir nenhum modo diferente do TeamsOnly a um usuário hospedado online.  Como era o caso antes da desativação do Skype for Business Online, os usuários hospedados no local podem receber qualquer modo diferente *do TeamsOnly*.

### <a name="islands-mode"></a>Modo de ilhas

Por padrão, os usuários podem executar Teams juntamente com Skype for Business como duas soluções separadas que fornecem recursos semelhantes e sobrepostos. Os recursos incluem presença, chat, chamadas e reuniões. Teams usuários também podem aproveitar os novos recursos de colaboração, como equipes e canais, acesso a arquivos em Microsoft 365 e aplicativos.

Nesse modo de coexistência, chamado **Ilhas**, cada um dos aplicativos cliente opera como uma ilha separada. Skype for Business falar com Skype for Business, e Teams com Teams. Espera-se que os usuários executem ambos os clientes o tempo todo e possam se comunicar nativamente no cliente do qual a comunicação foi iniciada. Dessa forma, não há necessidade de interoperabilidade no **modo Ilhas** .

Para evitar uma experiência Skype for Business confusa ou regredida, o Skype for Business lida com as seguintes integrações que não são tratadas no modo Teams **Ilhas**:

- Comunicações externas (federadas).
- Serviços de voz PSTN e aplicativos de voz, Office integração.
- Controles HID para dispositivos USB.
- Várias outras integrações.

Sistema de Telefonia há suporte no modo Teams **ilhas**. **O** modo Ilhas não dá suporte Enterprise Voice cliente está Skype for Business.

> [!Important]
> No **modo** Ilhas, todas as mensagens e chamadas de usuários federados (pessoas de fora da sua organização) são entregues Skype for Business. Depois de atualizar para **o Teams somente**, todas as mensagens e chamadas de fora da sua organização são entregues Teams.

### <a name="teams-only"></a>Teams

Um **Teams único** usuário (também chamado *de* usuário atualizado) tem acesso a todos os recursos no Teams. Eles podem manter o cliente Skype for Business para ingressar em reuniões Skype for Business que foram organizadas por usuários não atualizados ou partes externas. Um usuário atualizado pode continuar a se comunicar com outros usuários na organização que ainda estão usando o Skype for Business usando os recursos de interoperabilidade entre o Teams e o Skype for Business (desde que os usuários do Skype for Business não estejam no modo Ilhas). No entanto, um usuário atualizado não pode iniciar um Skype for Business chat, chamada ou reunião.

Assim que sua organização estiver pronta para que alguns ou todos os usuários usem o Teams como sua única ferramenta de comunicação e colaboração, atualize esses usuários para o Teams **Somente**. Se você estiver atualizando do modo **Ilhas**, recomendamos que primeiro Teams adoção em toda a organização antes de iniciar o processo de atualização. Essa adoção evita cenários de comunicação desfeitos devido ao **modo Ilhas** não fornecer interoperabilidade.

Quando estiver **Teams modo Somente**, Teams é o aplicativo padrão para o protocolo SIP/Tel. Os links no cartão de visita de um usuário Outlook para chamadas ou chat serão tratados por Teams.

Para obter considerações adicionais sobre como **mudar para Teams modo** somente, [consulte Teams considerações sobre o modo somente](teams-only-mode-considerations.md).

![Captura de tela da Teams de confirmação.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business cliente em execução em um modo especial depois que o usuário é atualizado como Teams somente usuário")

### <a name="skype-for-business-only"></a>Somente Skype for Business

Nesse modo de coexistência, os usuários permanecem no Skype for Business, não no Teams, para recursos de chat, reunião e chamada, e não usam Teams para equipes e canais. Esse modo está disponível atualmente; no entanto, na implementação atual, as equipes e os canais não são desativados automaticamente para o usuário. Isso pode ser feito usando a política de Configuração de Aplicativos para ocultar equipes e arquivos.

Esse modo pode ser usado antes de iniciar uma implantação gerenciada do Teams para impedir que os usuários comecem a usar Teams antes de ter preparação criada. Esse modo também é uma maneira de habilitar a participação autenticada em reuniões Teams para Skype for Business usuários, desde que os usuários sejam licenciados para Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business com Teams Colaboração

Use esse modo para introduzir Teams em seu ambiente enquanto você continua a usar seu investimento existente no Skype for Business. Deixe Skype for Business inalterados para os recursos de chat, chamada e reunião. Adicione Teams de colaboração:

- Teams e canais.
- Acesso a arquivos em Microsoft 365 ou Office 365.
- Aplicativos. Teams comunicações — chat privado, chamadas e agendamento de reuniões.

Teams chat privado, chamadas e agendamento de reuniões estão desativados por padrão nesse modo.

As organizações com um ponto de partida do Skype for Business Server local ou híbrido devem considerar esse modo como uma alternativa ao modo  Ilhas se quiserem fornecer aos usuários interoperabilidade e previsibilidade para suas comunicações, bem como ter uma linha do tempo previsível para sua atualização para o Teams (em vez de depender da saturação da adoção no modo  Ilhas).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business com Teams colaboração e reuniões, também conhecidas como Meetings First

Use esse modo de coexistência para acelerar a disponibilidade de Teams recursos de colaboração e reunião em sua organização. O modo de coexistência permite que os usuários aproveitem a experiência superior Teams reuniões:

- Ótima qualidade.
- Transcrição e tradução.
- Tela de fundo desfocada.
- Experiência de usuário superior em todas as plataformas, incluindo dispositivos móveis e navegadores.

Além de usar Teams para conversas baseadas em equipes e canais nesse modo, os usuários usarão Teams para agendar e conduzir suas reuniões. Chat privado e chamada permanecem em Skype for Business. Teams e Skype for Business se beneficiam de uma variedade de recursos "melhores juntos", como reconciliação de presença, retenção/retenção automática e suporte a dispositivo HID em ambos os aplicativos. É possível ocultar equipes e canais, se desejado, usando a política de Configuração de Aplicativos.

Esse modo de coexistência é especialmente útil para organizações com Skype for Business implantações locais com Enterprise Voice. Essas organizações provavelmente levarão algum tempo para atualizar para o Teams e desejarão se beneficiar das reuniões Teams superiores assim que possível.

> [!TIP]
> Para ajudar a identificar o modo de atualização recomendado com base nos recursos que você deseja habilitar no Teams enquanto o Skype for Business ainda estiver em uso, aproveite o Skype para Teams [Atualização](https://aka.ms/SkypeToTeamsWizard).

Para obter mais informações sobre modos de coexistência, pré-requisitos e gerenciamento, consulte as diretrizes de migração e interoperabilidade para organizações que usam o Teams junto com [o Skype for Business e definindo](./migration-interop-guidance-for-teams-with-skype.md) suas configurações de [coexistência](./setting-your-coexistence-and-upgrade-settings.md) e atualização.

|Ícone do ponto de decisão |Definição de ícone |Descrição |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Ponto de decisão|<ul><li>Quais modos de coexistência melhor se ajustam às necessidades da sua organização e dos usuários?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Próxima etapa|<ul><li>Escolha a melhor abordagem para seu percurso de atualização.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidade de Teams e Skype for Business

A interoperabilidade é a capacidade de Teams e Skype for Business usuários na mesma organização se comunicarem entre Teams e Skype for Business.

A interoperabilidade é regida pelo modo de coexistência (também conhecido como modo de atualização) do receptor. Não há interoperabilidade quando o receptor está no **modo Ilhas** .

> [!Note]
> Quando implantado em qualquer modo de coexistência **, exceto** ilhas, o Teams e o Skype for Business podem [interoperar](#interoperability-of-teams-and-skype-for-business), permitindo que os usuários conversem e liguem entre si e garantindo que as comunicações permaneçam fluidas em toda a sua organização durante a jornada de atualização para Teams. Os modos de coexistência regem a interoperabilidade. O modo de coexistência do receptor determina se a interoperabilidade estará disponível. Por exemplo, se o receptor estiver em um modo no qual o chat só está disponível em um cliente (digamos, Teams), a interoperabilidade de chat geralmente estará disponível caso o iniciador use o outro cliente (nesse caso, Skype for Business) para iniciar o chat. Por outro lado, se o receptor estiver no modo no qual o chat está disponível em ambos os clientes (modo Ilhas), a interoperabilidade não estará disponível para o chat. A mensagem será recebida pelo receptor no mesmo cliente no qual o iniciador iniciou o chat. Portanto, a comunicação adequada no **modo Ilhas** requer Teams saturação da adoção; ou seja, todos os usuários que usam e monitoram ativamente ambos os clientes.

> [!Note]
> **Para ter a experiência de coexistência mais recente, a versão do cliente deve ser o cliente mais recente disponível no canal de implantação Office usuário.**

#### <a name="native-interop-and-interop-escalation"></a>Escalonamento de interoperabilidade e interoperabilidade nativo

Há dois tipos de experiências de interoperabilidade: escalonamento nativo e de interoperabilidade.

- Uma _experiência de interoperabilidade_ nativa ocorre no cliente que o usuário está usando no momento. Um usuário estará no Skype for Business cliente, o outro no Teams. Uma experiência de interoperabilidade nativa não os levará a outro cliente para se comunicar. Os usuários poderão conduzir a conversa no cliente que estão usando no momento. As experiências de interoperabilidade nativas são chat e chamada de um para um.
- Uma experiência de _escalonamento_ de interoperabilidade significa que, como parte de ajudar os usuários a executar uma ação avançada (como compartilhar sua área de trabalho), o cliente facilita a criação de uma reunião na qual os usuários podem ingressar para continuar a experiência nessa reunião. A reunião é criada na plataforma do iniciador da ação. O usuário ou os usuários que não estão nessa plataforma recebem um link de ingresso na reunião. Conforme eles clicam nesse link, eles são ingressados na reunião em um cliente compatível (navegador, aplicativo Web ou cliente completo, dependendo da configuração). O escalonamento de interoperabilidade Skype for Business requer um cliente recente. O escalonamento de interoperabilidade Teams agora está disponível. Ambos têm suporte em experiências de interoperabilidade no locatário e para comunicação federada entre locatários.

#### <a name="native-interop-experiences"></a>Experiências de interoperabilidade nativas

Dependendo dos modos de coexistência atribuídos aos usuários (conforme descrito anteriormente), as seguintes experiências de interoperabilidade nativas estão disponíveis:

Skype for Business usuários podem conversar um contra um com Teams usuários e vice-versa. Um chat de interoperabilidade precisa passar por um gateway de interoperabilidade que faz parte Teams serviços de nuvem (e, portanto, só existe online). Chats de interoperabilidade são texto sem formatação: rich text e emoticons não têm suporte. Os usuários Teams e no Skype for Business são notificados de que a conversa é uma conversa de interoperabilidade.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business usuários podem fazer chamadas de voz e vídeo individuais para Teams usuários e Teams usuários podem fazer o mesmo.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> As experiências de interoperabilidade com uma implantação local Skype for Business exigem que o ambiente local esteja no modo híbrido com Teams. Para obter detalhes, [configure a conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

Essas experiências de interoperabilidade estão disponíveis entre usuários que têm um dos seguintes modos de coexistência atribuídos: Skype for Business com colaboração do **Teams**, Skype for Business com colaboração e reuniões do **Teams****, Skype for Business Somente** ou **Teams.** Não há interoperabilidade para usuários no **modo Ilhas** .

#### <a name="native-interop-experience-limitations"></a>Limitações da experiência de interoperabilidade nativa

Devido à diferença em protocolos e tecnologia, não é possível dar suporte a todos os recursos nativamente. Especificamente, os seguintes recursos não estão disponíveis:

- Markdown, rich text e o conjunto de emoticon completo não têm suporte de Teams ou Skype for Business. Outros recursos nativos da caixa de redação Teams chats não têm suporte.
- O compartilhamento de tela (compartilhamento de área de trabalho ou aplicativo) entre Teams e Skype for Business não tem suporte nativo. No entanto, ele tem suporte por meio do escalonamento de interoperabilidade.
- Chats em grupo (conversas de várias partes) no Teams podem incluir apenas os participantes que estão usando Teams.
- As conversas de mensagens instantâneas de várias partes (chats em grupo) Skype for Business podem incluir apenas os participantes que estão usando Skype for Business. No entanto, o escalonamento de interoperabilidade para várias partes está disponível Skype for Business.
- Não há suporte para o escalonamento de uma chamada de voz ou vídeo ponto a ponto em andamento para uma chamada de várias partes envolvendo Teams e Skype for Business usuários.
- Não há suporte para a transferência de arquivos para chats de duas partes ou anexos de arquivo em chats em grupo, de Teams a Skype for Business e vice-versa.
- Não há interoperabilidade com o Skype for Business Persistente.

Para todas essas limitações (exceto o Chat Persistente), uma solução alternativa possível é que um usuário inicie uma reunião e convide o outro usuário para ingressá-la.

Essa solução alternativa é a base para o escalonamento de interoperabilidade. Em particular, o compartilhamento de tela e o escalonamento para vários participantes não são acessíveis nativamente, mas têm suporte por meio do escalonamento de interoperabilidade.

#### <a name="interop-escalation-experiences"></a>Experiências de escalonamento de interoperabilidade

O escalonamento de interoperabilidade consiste em complementar os recursos de interoperabilidade nativos com escalonamentos gerenciados para reuniões. As reuniões oferecem experiências avançadas disponíveis para qualquer pessoa, independentemente de qual cliente eles têm.

Quando o escalonamento de interoperabilidade é disparado pelo Teams usuário, uma Teams é criada. Quando ele é disparado pelo Skype for Business usuário, uma Skype for Business é criada. Em ambos os casos, a reunião criada é uma **reunião reunir agora** , o que não é refletido no calendário do usuário.

A outra parte recebe o link de ingresso na reunião por meio de chat de interoperabilidade e ingressa clicando nesse link. Se o Skype for Business tiver uma Teams e for convidado pelo Teams usuário, ele ingressará na reunião autenticada. Caso contrário, eles ingressarão como um participante anônimo. Por outro lado, Teams usuários quase sempre têm uma conta do Skype for Business e um cliente do Skype for Business que podem usar para ingressar em uma reunião do Skype for Business como um participante autenticado, mas também podem ingressar como um participante anônimo, por exemplo, usando o Reunião do Skype App.

Depois que as partes tiverem ingressado na reunião, elas poderão realizar qualquer atividade com suporte em reuniões, como compartilhamento de área de trabalho ou conteúdo, compartilhamento ou transferência de arquivos, adição de outros participantes e assim por diante.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalonamento de interoperabilidade de Skype for Business

O escalonamento de interoperabilidade Skype for Business foi atualizado na compilação de julho de 2019 do C2R mensal. Anteriormente, Skype for Business tinha conhecimento antecipado de que a parte remota estava usando Teams. Ele só imaginou que a partir da sinalização recebida após uma sessão foi estabelecida.

Quando a sinalização indicou que a resposta veio (ou por meio) do gateway de interoperabilidade, ela exibiria a barra de negócios amarela (faixa) indicando que a outra parte não estava usando Skype for Business. Com a evolução do nosso serviço, isso resultou em falsos positivos em que os usuários do Skype for Business veriam a barra de negócios quando estavam conectados ao Serviço do Caixa postal na Nuvem ou a outros serviços de voz na nuvem, em vez de a um usuário Teams **Único** real.

Para evitar esses falsos positivos, o serviço de presença agora está informando o cliente Skype for Business quando a outra parte é Teams **usuário** real. Isso permite que Skype for Business esteja ciente de que precisa criar uma conversa de interoperabilidade antes de ela ter sido criada e que a janela de conversa seja específica para interoperabilidade.

![Captura de tela Teams mensagem para criar uma conversa de interoperabilidade com um Skype for Business usuário.](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Se o Skype for Business quiser compartilhar sua área de trabalho, por exemplo, ele será informado de que iniciaremos uma reunião e orientaremos pelas etapas.

![Captura de tela Teams mensagem para iniciar a reunião com um Teams usuário.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Enquanto isso, o Teams usuário recebe uma mensagem de chat de entrada com o link para a reunião e é guiado para ingressar.

Esse escalonamento para uma Skype for Business está disponível para chamadas e chats federados entre locatários e entre locatários. Ele está ativado por padrão e não há nenhuma configuração que o administrador precisa provisionar.

#### <a name="interop-escalation-from-teams"></a>Escalonamento de interoperabilidade de Teams

O escalonamento de interoperabilidade de Teams para uma reunião do Teams agora está disponível quando o usuário do Teams seleciona o botão de compartilhamento de área de trabalho em um thread de interoperabilidade no locatário com um usuário do Skype for Business ou em um thread de federação de interoperabilidade entre locatários. O escalonamento de interoperabilidade é compatível com uma conversa de chat 1:1 ou de uma chamada 1:1.

A funcionalidade é compatível com o cliente de área de trabalho do Teams para Windows, no cliente da área de trabalho do Teams para Mac e no cliente Web do Teams em navegadores em que há suporte para compartilhamento de conteúdo, durante a comunicação com qualquer versão do cliente do Skype for Business.

Em threads de interoperabilidade e em threads de interoperabilidade de federação, o Teams usuário agora tem os controles (botão) para iniciar o compartilhamento de conteúdo. Quando o Teams seleciona o botão, ele é apresentado a um menu adicional que informa que, para compartilhar conteúdo, ele precisará iniciar uma reunião Teams reunião.

Se os usuários estiverem em uma chamada, o menu também os avisará de que sua chamada atual entre Teams e Skype for Business será encerrada à medida que eles forem colocados em uma reunião Teams reunião. Se escolherem, eles poderão avisar o Skype for Business usuário antes de aceitar.

![Captura de tela Teams mensagem para compartilhar a reunião com um Skype for Business usuário.](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Após a aceitação, eles são colocados na reunião Teams; eles devem começar a compartilhar da bandeja de compartilhamento na reunião.

Enquanto isso, o Skype for Business usuário recebe uma mensagem de chat de entrada com o link para a reunião e é guiado para ingressar.

Esse escalonamento para uma Teams está disponível para chamadas e chats federados entre locatários e entre locatários. Ele está ativado por padrão e não há nenhuma configuração que o administrador precisa provisionar. No entanto, ele será desativado para o usuário se o administrador definir ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` como ``$false``.

Depois de examinar este artigo, confira Escolher o percurso de [atualização, as](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) diretrizes de [migração e interoperabilidade](./migration-interop-guidance-for-teams-with-skype.md), a [coexistência](coexistence-chat-calls-presence.md) com o Skype for Business e a definição das configurações de [coexistência](./setting-your-coexistence-and-upgrade-settings.md) e atualização para obter detalhes de implementação. Também recomendamos o seguinte vídeo: [Vídeo: Gerenciar coexistência e interoperabilidade entre SfB e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Detalhes técnicos de Teams e Skype for Business coexistência

As seções a seguir resumem o comportamento que pode ser experimentado ao executar clientes Teams e Skype for Business na mesma organização, independentemente de qual modo e qual método de atualização é usado:

- [Reuniões](#meetings)
- [Interoperabilidade](#interoperability)
- [Interoperabilidade versus threads de conversa nativos](#interop-versus-native-conversation-threads)
- [Presença](#presence)
- [Federação](#federation)
- [Contatos](#contacts)

### <a name="meetings"></a>Reuniões

Independentemente do modo, os usuários sempre podem ingressar em qualquer tipo de reunião para a qual são convidados, seja Skype for Business ou Teams.  No entanto, os usuários devem ingressar na reunião com um cliente correspondente que corresponda ao tipo de reunião:

- Se a reunião for uma Teams, todos os participantes (sejam usuários do TeamsOnly, Islands ou Skype for Business) usarão o cliente Teams para ingressar na reunião. Se Teams não estiver instalado, o usuário será direcionado para a Web, ao tentar ingressar em uma reunião.

- Se a reunião for uma Skype for Business, todos os participantes (sejam usuários do TeamsOnly, Islands ou Skype for Business) usarão o cliente Skype for Business para ingressar na reunião. Se o Skype for Business cliente não estiver instalado, o usuário será direcionado para a Web para ingressar por meio do Reunião do Skype App.

Ao organizar reuniões, o tipo de reunião agendado é baseado no modo do organizador, conforme mostrado na tabela a seguir:

| Modo de organizador    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings | Todas as reuniões agendadas Teams. Skype for Business suplemento não está disponível no Outlook. |
| SfbWithTeamsCollab, SfbOnly | Todas as reuniões agendadas Skype for Business. Teams suplemento não está disponível no Outlook. |
| Ilhas | Por padrão, as reuniões podem ser agendadas Skype for Business ou Teams. Ambos os suplementos estão disponíveis no Outlook. No entanto, opcionalmente, você pode exigir que os usuários em Ilhas sempre agendem reuniões no Teams atribuindo a eles uma instância do TeamsMeetingPolicy com PreferredMeetingProviderForIslandsMode=Teams.|

### <a name="interoperability"></a>Interoperabilidade

Conforme descrito acima em [Interoperabilidade de Teams e Skype for Business](#interoperability-of-teams-and-skype-for-business), o Teams dá suporte à interoperabilidade com Skype for Business em determinados cenários. A comunicação de interoperabilidade refere-se a um chat ou chamada entre um Skype for Business usuário e um Teams usuário.  A comunicação de interoperabilidade só é possível entre dois usuários; Não há suporte para chat/chamada de várias partes ou adição de usuários adicionais.

Um chat de interoperabilidade ou chamada entre dois usuários é criado quando cada um dos seguintes é verdadeiro:

- Um usuário está usando Teams e o outro está usando Skype for Business.

- O modo do destinatário da comunicação inicial é NOT Islands (caso contrário, a comunicação seria ressarmado no mesmo cliente) se ambos os usuários estão na mesma organização. Em cenários federados, o usuário de envio está usando Teams e o destinatário não está no modo TeamsOnly.

- O Teams usuário não tem também uma Skype for Business conta local.

Dentro da comunicação de interoperabilidade, o chat é somente texto sem formatação. Além disso, o compartilhamento de arquivos e o compartilhamento de tela não são *possíveis no chat de interoperabilidade em si*. No entanto, os usuários em uma conversa de interoperabilidade podem facilmente obter o compartilhamento de arquivo e/ou tela criando uma reunião sob demanda, de dentro do chat de interoperabilidade, conforme descrito abaixo:

- Se o Teams usuário tentar compartilhar sua tela, uma reunião de Teams sob demanda será criada automaticamente e um link de convite para essa reunião será enviado para o cliente Skype for Business usuário do Skype for Business. Ao clicar no link, o Skype for Business usuário abrirá Teams e ingressará na reunião. Os dois usuários agora estão em uma Teams e podem compartilhar conforme necessário.

- Se o usuário do Skype for Business estiver usando um cliente de 2018 ou posterior e tentar compartilhar qualquer conteúdo, uma reunião do Skype for Business sob demanda será criada automaticamente e um link de convite para essa reunião será enviado para o cliente do Teams. Ao clicar no link, o Teams usuário tentará ingressar na Skype for Business reunião. Se o Teams usuário tiver o cliente Skype for Business instalado, ele será aberto e o usuário será solicitado a entrar (se ainda não tiver entrado).  Se o Teams usuário não tiver o cliente Skype for Business instalado, o usuário será solicitado a usar a versão da Web. Depois que ambos os usuários estiverem conectados, eles estão em uma Skype for Business e podem compartilhar conforme necessário.

### <a name="interop-versus-native-conversation-threads"></a>Interoperabilidade versus threads de conversa nativos

Como as comunicações de interoperabilidade não dão suporte a todos os recursos da conversa Teams nativa, o cliente do Teams mantém threads de conversa separados para comunicação de Teams para Teams e Teams para Skype for Business. Essas conversas são renderizadas de forma diferente na interface do usuário: threads de interoperabilidade podem ser diferenciados de um thread Teams nativo regular por:

- Falta de controles para rich text, compartilhamento de arquivo/tela, incapacidade de adicionar usuários.
- Uma modificação no ícone do usuário de destino, mostrando um "S" para Skype for Business.

Essas diferenças são mostradas nas capturas de tela a seguir:

Uma conversa Teams para Teams com o Teste do Usuário G3

![Diagrama mostrando uma conversa Teams-a-Teams nativa.](media/teams-upgrade-native-thread.png)

Uma conversa de interoperabilidade com o mesmo Teste do User G3

![Diagrama mostrando uma conversa Teams de Teams de interoperabilidade.](media/teams-upgrade-interop-thread.png)

Depois que um thread de conversa é criado, seu tipo nunca é alterado. Depois de criado, um thread de interoperabilidade Teams sempre roteará para o cliente de Skype for Business destino. Um thread nativo sempre será roteado para o cliente de Teams do usuário de destino.  Se o modo de um usuário destinatário for alterado, os threads de Teams existentes para esse usuário não funcionarão mais e uma anotação será exibida nesse chat com um link para iniciar uma nova conversa nativa, conforme mostrado na captura de tela a seguir.

![Diagrama mostrando um chat com o Skype for Business usuário atualizado.](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Presença

A presença de um determinado usuário baseia-se na atividade do usuário no serviço por meio do cliente. Em seguida, a presença é publicada para que outros usuários vejam.  Skype for Business e Teams são serviços separados com clientes separados, portanto, cada serviço tem seu próprio estado de presença para um usuário.   Também há sincronização entre os serviços de presença no Teams e no Skype for Business Online.  Isso permite que um serviço publique potencialmente a presença do usuário do outro serviço, se necessário.

O comportamento de publicação de presença é baseado no modo do usuário. Há três casos básicos:

- Se um usuário estiver no modo TeamsOnly, todos os outros usuários verão Teams presença desse usuário, independentemente do cliente usado.

- Se um usuário estiver em qualquer um dos modos Skype for Business, todos os outros usuários verão Skype for Business presença desse usuário, independentemente do cliente usado.

- Se um usuário estiver no modo Ilhas, a presença publicada no Skype for Business e Teams será independente, portanto, a presença mostrada aos usuários na mesma organização dependerá do cliente do outro usuário. Os usuários em organizações federadas verão a presença desse usuário com base em sua atividade Skype for Business, pois o tráfego federado para um usuário do modo Ilhas chega Skype for Business.

Por exemplo, suponha que o usuário A esteja no modo Ilhas. Se o Usuário A estiver ativo no Teams, mas não estiver conectado ao Skype for Business, outros usuários verão o Usuário A como ativo do cliente do Teams, mas no cliente do Skype for Business eles verão o Usuário A como offline. Isso ocorre por design, pois o Usuário A não pode ser acessado se não estiver executando o cliente.


### <a name="federation"></a>Federação

A federação Teams outro usuário usando Skype for Business requer que o Teams esteja hospedado online no Skype for Business. TeamsUpgradePolicy determina o roteamento para chamadas e conversas federadas e de entrada. O comportamento de roteamento federado é o mesmo para cenários de mesmo locatário, exceto no modo de Ilhas. Quando os destinatários estiverem no modo de Ilhas:

- Chats e chamadas iniciadas Teams chegar Skype for Business se o destinatário estiver em um locatário federado.
- Chats e chamadas iniciados a partir do Teams são recebidos no Teams se o destinatário estiver no mesmo locatário.
- Chats e chamadas iniciadas Skype for Business sempre são Skype for Business.

Um chat federado pode ser um thread nativo ou um thread de interoperabilidade. Consulte [Interoperabilidade versus threads de conversa nativos](#interop-versus-native-conversation-threads).

- Se o destinatário e o remetente estão no modo de atualização do TeamsOnly, a conversa será uma experiência de chat nativa que inclui todos os recursos avançados de mensagens e chamadas. Para saber mais, leia [a experiência de chat nativo para usuários externos (federados) Teams](native-chat-for-external-users.md).

- Se um dos participantes da conversa não estiver no modo de atualização do TeamsOnly, a conversa permanecerá uma experiência de interoperabilidade com mensagens somente de texto. A interface do usuário expõe chats federados de maneira semelhante a threads de interoperabilidade de mesmo locatário, exceto que há uma observação indicando que o usuário é externo.

Para obter mais detalhes, consulte Gerenciar o acesso externo [Microsoft Teams](manage-external-access.md) e experiência de chat nativo para usuários externos [(federados) no Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Contatos

Teams e Skype for Business têm listas separadas de contatos. Isso significa que as adições, remoção e modificações de contato feitas em um sistema não são sincronizadas com o outro sistema. No entanto, os contatos Skype for Business são copiados automaticamente para Teams quando ocorrem dois eventos específicos:

- Para qualquer Skype for Business Online, na primeira vez que fizer logon no Teams, os contatos do Skype for Business serão copiados para Teams.  Esse comportamento não está disponível para usuários com uma conta local no Skype for Business Server.

- Depois que um usuário for atualizado para o TeamsOnly (por meio da atribuição de TeamsUpgradePolicy ou por meio de Move-CsUser -MoveToTeams), na próxima vez que um usuário fizer logon no Teams, os contatos existentes no Skype for Business serão mesclados com os contatos existentes já no Teams. Esse comportamento ocorre se o usuário foi movido para o TeamsOnly do local ou online.

Em ambos os casos, a transferência de contatos de Skype for Business para Teams é assíncrona, portanto, pode levar alguns minutos até que os contatos apareçam em Teams. Os dois eventos acima são o que dispara a cópia.

### <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Configurar a conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
