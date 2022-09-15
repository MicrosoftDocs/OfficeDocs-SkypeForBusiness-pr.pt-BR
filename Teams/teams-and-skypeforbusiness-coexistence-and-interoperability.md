---
title: Entender o Microsoft Teams e Skype for Business coexistência e interoperabilidade
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Detalhes das Skype for Business e as opções de coexistência do Microsoft Teams e a interoperabilidade resultante entre o Skype for Business e o Teams.
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
ms.openlocfilehash: b2a83a0ec3b93f44da5f22e0423ff6199f2ce0c5
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705850"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Entender o Microsoft Teams e Skype for Business coexistência e interoperabilidade

![Diagrama de jornada de atualização, enfatizando o estágio de Definição do Projeto.](media/upgrade-banner-project-definition.png "Etapas da jornada de atualização, com ênfase no estágio de Definição do Projeto")

Este artigo faz parte do estágio de Definição do Projeto da sua jornada de atualização. Conclua depois de criar uma coligação de patrocínio e equipe de projetos e definir o escopo, as metas e o plano do seu projeto. Antes de continuar, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)

Se sua organização usa o Skype for Business hoje e você está começando a usar o Teams junto com o Skype for Business , ou você está começando a atualizar para o Teams, é importante entender como os dois aplicativos coexistem, quando e como eles interoperam e como gerenciar a migração dos usuários até sua eventual atualização do Skype for Business ao Teams.

> [!Tip]
> Assista à sessão a seguir para saber mais sobre [coexistência e interoperabilidade](https://aka.ms/teams-upgrade-coexistence-interop).
>
> Além disso, você pode se juntar a nós para workshops ao vivo e interativos nos quais compartilharemos diretrizes, práticas recomendadas e recursos projetados para iniciar o planejamento e a implementação da atualização.
>
> Para começar, participe primeiro da sessão de [Planejamento da atualização](./upgrade-workshops-landing-page.yml).

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Coexistência do Teams e Skype for Business visão geral

Desde a desativação do Skype for Business Online, todos os usuários em uma organização online pura (ou seja, uma organização que não tem uma implantação local do Skype for Business) têm um modo de coexistência do TeamsOnly. O modo TeamsOnly garante que os usuários tenham funcionalidade total do Teams. No entanto, as organizações com uma implantação local do Skype for Business Server podem ter usuários que ainda estão hospedados no local; esses usuários não podem ser TeamsOnly. Os usuários com uma conta de Skype for Business Server local podem ter qualquer modo de coexistência *diferente do TeamsOnly.* As seções a seguir descrevem os modos de coexistência que estão disponíveis antes de você decidir atualizar o Skype for Business usuários locais para o TeamsOnly e os recursos que cada modo oferece. Além disso, as seções descrevem a interoperabilidade (interoperabilidade) que ocorre entre usuários em clientes do Skype for Business e usuários em clientes do Teams e como a interoperabilidade é afetada pelo modo de coexistência escolhido.

O Teams oferece recursos de colaboração, chat, chamadas e recursos de reunião.  A funcionalidade de chat, chamada e reunião também estava historicamente disponível no Skype for Business. Dependendo da configuração escolhida ao fornecer o Teams, esses recursos podem se sobrepor aos recursos fornecidos pelo Skype for Business para um determinado usuário. O modo de coexistência padrão para usuários locais é Ilhas. O modo Ilhas permite que o usuário execute o Teams junto Skype for Business com funcionalidade semelhante disponível em ambos os clientes; ou seja, os recursos se sobrepõem. No entanto, um usuário pode receber outros modos de coexistência para evitar que esse recurso se sobreponha ao usuário, caso em que a interoperabilidade entre o Teams e o Skype for Business está disponível. Por exemplo, se você tiver Skype for Business Server ativos locais significativos com uma implantação complexa do Enterprise Voice, mas quiser que os usuários aproveitem reuniões modernas o mais rápido possível, talvez você queira avaliar o uso do Skype for Business com o modo de Colaboração e Reuniões do Teams, também conhecido como Reuniões [ Em primeiro lugar.](meetings-first.md)

Recomendamos que você examine os seguintes modos de coexistência para ajudar a determinar qual caminho é ideal para sua organização.

> [!Important]
> Os modos de coexistência continuam a existir após a desativação do Skype for Business Online, no entanto, os usuários hospedados online só podem ter um modo do TeamsOnly. Não é mais possível atribuir nenhum modo diferente do TeamsOnly a um usuário hospedado online.  Como era o caso antes da desativação do Skype for Business Online, os usuários hospedados no local podem receber qualquer modo diferente *do TeamsOnly*.


### <a name="teams-only"></a>Somente Equipes

**Somente o Teams** é o único modo disponível para usuários online puros. Um usuário somente do **Teams** (no passado, às vezes chamado  de usuário atualizado) tem acesso a todos os recursos no Teams e pode continuar a se comunicar com qualquer outro usuário (na mesma organização ou externa) que ainda usam o Skype for Business (desde que os usuários do Skype for Business não estão no modo Ilhas). **Somente os usuários do Teams** recebem chats e chamadas recebidos no Teams e também agendam reuniões no Teams. Eles não podem iniciar chats ou chamadas ou agendar reuniões em Skype for Business. 

Somente os usuários do **Teams** podem reter o cliente Skype for Business para ingressar em qualquer reunião do Skype for Business que já tenham ou possam receber no futuro (ou seja, de partes externas ou, possivelmente, de usuários Skype for Business Server locais em sua própria organização). *No entanto, depois que a Microsoft remover a infraestrutura do Skype for Business Online para um determinado usuário do Teams, somente os usuários do Teams poderão ingressar Skype for Business reuniões anonimamente.* Após 30 de junho de 2022, os usuários recém-criados do TeamsOnly não serão mais provisionados com a infraestrutura Skype for Business Online. Se esses usuários forem convidados para uma reunião Skype for Business, eles precisarão ingressar anonimamente. Após outubro de 2022, os usuários movidos do local para a nuvem (ou seja, eles se tornam TeamsOnly) não serão mais provisionados com a infraestrutura do Skype for Business Online.  Se esses usuários forem convidados para uma reunião Skype for Business, eles também precisarão ingressar anonimamente.

Assim que sua organização estiver pronta para que alguns ou todos os usuários usem o Teams como sua única ferramenta de comunicação e colaboração, atualize esses usuários para o modo **Somente Teams.** Se você estiver atualizando do modo **Ilhas** , recomendamos primeiro saturar a adoção do Teams em toda a organização antes de iniciar o processo de atualização. Essa adoção evita cenários de comunicação desfeitos devido ao **modo Ilhas** não fornecer interoperabilidade.

No modo **Somente Teams** , o Teams é o aplicativo padrão para o protocolo SIP/Tel. Os links no cartão de visita de um usuário no Outlook para chamadas ou chats serão tratados pelo Teams.

Para obter considerações adicionais sobre como mudar para o **modo Somente Equipes** , consulte considerações sobre o [modo Somente Equipes](teams-only-mode-considerations.md).

![Captura de tela da mensagem de confirmação do Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business cliente em execução em um modo especial depois que o usuário é atualizado como um usuário somente do Teams")


### <a name="islands-mode"></a>Modo de ilhas

No **modo Ilhas**, os usuários podem executar o Teams Skype for Business como duas soluções separadas que fornecem recursos semelhantes e sobrepostos. Os recursos incluem presença, chat, chamadas e reuniões. Os usuários do Teams também podem aproveitar os novos recursos de colaboração, como equipes e canais, acesso a arquivos no Microsoft 365 e aplicativos.

Nesse modo de coexistência, cada um dos aplicativos cliente opera como uma ilha separada. Skype for Business conversa com o Skype for Business e o Teams conversa com o Teams. Espera-se que os usuários executem ambos os clientes o tempo todo e possam se comunicar nativamente no cliente do qual a comunicação foi iniciada. Dessa forma, não há necessidade de interoperabilidade no **modo Ilhas** .

Para evitar uma experiência Skype for Business confusa ou regredida, o Skype for Business lida com as seguintes integrações que não são tratadas no modo ilhas **do** Teams:

- Comunicações externas (federadas).
- Serviços de voz PSTN e aplicativos de voz, integração do Office.
- Controles HID para dispositivos USB.
- Várias outras integrações.

Telefonia do Microsoft Teams sistema não é compatível com o Teams **no modo Ilhas**. 

> [!Important]
>  - No **modo** Ilhas, todas as mensagens e chamadas de usuários federados (pessoas de fora da sua organização) são entregues Skype for Business. Depois de atualizar para o modo **Somente Teams** , todas as mensagens e chamadas de fora da sua organização são entregues ao Teams.
>  - Talvez você queira exigir que os usuários das Ilhas sempre agendem reuniões no Teams atribuindo a eles uma instância do TeamsMeetingPolicy com PreferredMeetingProviderForIslandsMode=Teams. Isso garante que todos os usuários agendem reuniões usando o Teams, que dá suporte à entrada autenticada e ao ingresso na reunião para qualquer usuário na organização, independentemente de o usuário ser TeamsOnly ou ainda usar Skype for Business Server. Por outro lado, depois que a Microsoft desativar a infraestrutura herdada do Skype for Business Online para organizações híbridas a partir de outubro de 2022, os usuários do TeamsOnly só poderão ingressar em reuniões Skype for Business anonimamente.


### <a name="skype-for-business-only"></a>Somente Skype for Business

Nesse modo de coexistência, os usuários permanecem no Skype for Business — não no Teams — para recursos de chat, reunião e chamada, e não usam o Teams para equipes e canais. Esse modo está disponível atualmente; no entanto, na implementação atual, as equipes e os canais não são desativados automaticamente para o usuário. Isso pode ser feito usando a política de Configuração de Aplicativos para ocultar equipes e arquivos.

Esse modo pode ser usado antes de iniciar uma implantação gerenciada do Teams para impedir que os usuários comecem a usar o Teams antes de ter preparação criada. Esse modo também é uma maneira de habilitar a participação autenticada em reuniões do Teams para Skype for Business usuários, desde que os usuários sejam licenciados para o Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business colaboração do Teams

Use esse modo para introduzir o Teams em seu ambiente enquanto você continua usando seu investimento existente no Skype for Business. Deixe Skype for Business inalterados para os recursos de chat, chamada e reunião. Adicionar recursos de colaboração do Teams:

- Equipes e canais.
- Acesso a arquivos no Microsoft 365 ou Office 365.
- Aplicativos. Recursos de comunicações do Teams – chat privado, chamadas e agendamento de reuniões.

As reuniões privadas de chat, chamadas e agendamento de reuniões do Teams estão desativadas por padrão nesse modo.

As organizações que começam Skype for Business Server locais têm esse modo como alternativa ao modo Ilhas se quiserem  fornecer aos usuários interoperabilidade e previsibilidade para suas comunicações durante a migração. Esse modo também fornece uma linha do tempo previsível para sua atualização para o Teams (em vez de depender da saturação da adoção **no modo Ilhas** ).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business colaboração e reuniões do Teams, também conhecidas como Reuniões Primeiro

Nesse modo, a funcionalidade de chat privado e chamada permanece em Skype for Business enquanto o Teams é usado para agendar e conduzir reuniões, bem como para colaboração usando conversas baseadas em canais.  Esse modo de coexistência ajuda a acelerar a disponibilidade dos recursos de reunião e colaboração do Teams em sua organização e permite que os usuários aproveitem a experiência superior de reuniões do Teams:

- Ótima qualidade.
- Transcrição e tradução.
- Tela de fundo desfocada.
- Experiência de usuário superior em todas as plataformas, incluindo dispositivos móveis e navegadores.

O Teams e Skype for Business se beneficiam de uma variedade de recursos "melhores juntos", como reconciliação de presença, retenção/resuspensão automática e suporte a dispositivo HID em ambos os aplicativos. É possível ocultar equipes e canais, se desejado, usando a política de Configuração de Aplicativos do Teams.

Esse modo de coexistência é especialmente útil para organizações com Skype for Business implantações locais com Enterprise Voice. Essas organizações provavelmente levarão algum tempo para atualizar para o Teams e desejarão se beneficiar das reuniões superiores do Teams assim que possível.

> [!NOTE]
> A partir de outubro de 2022, esse modo é recomendado para todos os usuários locais que anteriormente foram atribuídos Skype for Business **Somente** ou Skype for Business com modos de Colaboração do **Teams**. Esse modo oferece a mesma funcionalidade que as outras duas, exceto que novas reuniões agendadas pelo usuário serão reuniões do Teams em vez de Skype for Business reuniões. Isso garante que os usuários agendem suas reuniões como reuniões do Teams, que dão suporte à entrada autenticada e ao ingresso na reunião para qualquer usuário na organização, independentemente de o usuário ser TeamsOnly ou ainda usar Skype for Business Server.  Por outro lado, à medida que a Microsoft desativa a infraestrutura herdada do Skype for Business Online, os usuários do TeamsOnly não poderão mais se autenticar ao ingressar em reuniões do Skype for Business, no entanto, eles ainda poderão ingressar anonimamente. Para obter detalhes, consulte [o que esperar após a desativação](skype-for-business-online-retirement.md#what-to-expect-post-retirement).

> [!TIP]
> Para ajudar a identificar o modo de atualização recomendado com base nos recursos que você deseja habilitar no Teams enquanto Skype for Business ainda está em uso, aproveite o Assistente de Atualização do [Skype para o Teams](https://aka.ms/SkypeToTeamsWizard).

Para obter mais informações sobre modos de coexistência, pré-requisitos e gerenciamento, consulte as diretrizes de migração e interoperabilidade para organizações que usam o Teams junto com [o Skype for Business](./migration-interop-guidance-for-teams-with-skype.md) e definindo suas configurações de [coexistência](./setting-your-coexistence-and-upgrade-settings.md) e atualização.

|Ícone do ponto de decisão |Definição de ícone |Descrição |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Ponto de decisão|<ul><li>Quais modos de coexistência melhor se ajustam às necessidades da sua organização e dos usuários?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Próxima etapa|<ul><li>Escolha a melhor abordagem para seu percurso de atualização.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidade do Teams e do Skype for Business

A interoperabilidade é a capacidade do Teams e Skype for Business usuários da mesma organização se comunicarem entre o Teams e o Skype for Business.

A interoperabilidade é regida pelo modo de coexistência (também conhecido como modo de atualização) do receptor. Não há interoperabilidade quando o receptor está no **modo Ilhas** .

> [!Note]
> Quando implantado em qualquer modo de coexistência **, exceto** ilhas, o Teams e o Skype for Business podem [interoperar](#interoperability-of-teams-and-skype-for-business), permitindo que os usuários conversem e liguem entre si e garantindo que as comunicações permaneçam fluidas em toda a sua organização durante a jornada de atualização para o Teams. Os modos de coexistência regem a interoperabilidade. O modo de coexistência do receptor determina se a interoperabilidade estará disponível. Por exemplo, se o receptor estiver em um modo no qual o chat só está disponível em um cliente (digamos, Teams), a interoperabilidade de chat geralmente estará disponível caso o iniciador use o outro cliente (nesse caso, Skype for Business) para iniciar o chat. Por outro lado, se o receptor estiver no modo no qual o chat está disponível em ambos os clientes (modo Ilhas), a interoperabilidade não estará disponível para o chat. A mensagem será recebida pelo receptor no mesmo cliente no qual o iniciador iniciou o chat. Portanto, a comunicação adequada no **modo Ilhas** requer saturação da adoção do Teams; ou seja, todos os usuários que usam e monitoram ativamente os dois clientes.

> [!Note]
> **Para ter a experiência de coexistência mais recente, a versão do cliente deve ser o cliente mais recente disponível no canal de implantação do Office do usuário.**

#### <a name="native-interop-and-interop-escalation"></a>Escalonamento de interoperabilidade e interoperabilidade nativo

Há dois tipos de experiências de interoperabilidade: escalonamento nativo e de interoperabilidade.

- Uma _experiência de interoperabilidade_ nativa ocorre no cliente que o usuário está usando no momento. Um usuário estará no Skype for Business cliente, o outro no Teams. Uma experiência de interoperabilidade nativa não os levará a outro cliente para se comunicar. Os usuários poderão conduzir a conversa no cliente que estão usando no momento. As experiências de interoperabilidade nativas são chat e chamada de um para um.
- Uma experiência de _escalonamento_ de interoperabilidade significa que, como parte de ajudar os usuários a executar uma ação avançada (como compartilhar sua área de trabalho), o cliente facilita a criação de uma reunião na qual os usuários podem ingressar para continuar a experiência nessa reunião. A reunião é criada na plataforma do iniciador da ação. O usuário ou os usuários que não estão nessa plataforma recebem um link de ingresso na reunião. Conforme eles clicam nesse link, eles são ingressados na reunião em um cliente compatível (navegador, aplicativo Web ou cliente completo, dependendo da configuração). O escalonamento de interoperabilidade Skype for Business requer um cliente recente. O escalonamento de interoperabilidade do Teams agora está disponível. Ambos têm suporte em experiências de interoperabilidade no locatário e para comunicação federada entre locatários.

#### <a name="native-interop-experiences"></a>Experiências de interoperabilidade nativas

Dependendo dos modos de coexistência atribuídos aos usuários (conforme descrito anteriormente), as seguintes experiências de interoperabilidade nativas estão disponíveis:

Skype for Business usuários podem conversar um contra um com os usuários do Teams e vice-versa. Um chat de interoperabilidade precisa passar por um gateway de interoperabilidade que faz parte dos serviços de nuvem do Teams (e, portanto, só existe online). Chats de interoperabilidade são texto sem formatação: rich text e emoticons não têm suporte. Os usuários no Teams e Skype for Business são notificados de que a conversa é uma conversa de interoperabilidade.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business usuários podem fazer chamadas de voz e vídeo individuais para usuários do Teams e os usuários do Teams podem fazer o mesmo.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> As experiências de interoperabilidade com uma implantação local Skype for Business exigem que o ambiente local esteja no modo híbrido com o Teams. Para obter detalhes, [configure a conectividade híbrida entre Skype for Business Server e o Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

Essas experiências de interoperabilidade estão disponíveis para e entre os usuários que têm um dos seguintes modos de coexistência atribuídos: **Skype for Business com Colaboração do Teams**, Skype for Business com Colaboração e reuniões do **Teams**, **somente Skype for Business** ou **Teams**. Não há interoperabilidade para usuários no **modo Ilhas** .

#### <a name="native-interop-experience-limitations"></a>Limitações da experiência de interoperabilidade nativa

Devido à diferença em protocolos e tecnologia, não é possível dar suporte a todos os recursos nativamente. Especificamente, os seguintes recursos não estão disponíveis:

- Markdown, rich text e o conjunto de emoticon completo não têm suporte do Teams ou Skype for Business. Não há suporte para outros recursos nativos da caixa de redação em chats do Teams.
- O compartilhamento de tela (compartilhamento de área de trabalho ou aplicativo) entre o Teams Skype for Business não tem suporte nativo. No entanto, ele tem suporte por meio do escalonamento de interoperabilidade.
- Chats em grupo (conversas de várias partes) no Teams só podem incluir participantes que estão usando o Teams.
- As conversas de mensagens instantâneas de várias partes (chats em grupo) Skype for Business podem incluir apenas os participantes que estão usando Skype for Business. No entanto, o escalonamento de interoperabilidade para várias partes está disponível Skype for Business.
- Não há suporte para o escalonamento de uma chamada de vídeo ou voz ponto a ponto em andamento para uma chamada de várias partes envolvendo o Teams e Skype for Business usuários.
- Não há suporte para a transferência de arquivos para chats de duas partes ou anexos de arquivo em chats em grupo, do Teams para o Skype for Business e vice-versa.
- Não há interoperabilidade com o Skype for Business Persistente.

Para todas essas limitações (exceto o Chat Persistente), uma solução alternativa possível é que um usuário inicie uma reunião e convide o outro usuário para ingressá-la.

Essa solução alternativa é a base para o escalonamento de interoperabilidade. Em particular, o compartilhamento de tela e o escalonamento para vários participantes não são acessíveis nativamente, mas têm suporte por meio do escalonamento de interoperabilidade.

#### <a name="interop-escalation-experiences"></a>Experiências de escalonamento de interoperabilidade

O escalonamento de interoperabilidade consiste em complementar os recursos de interoperabilidade nativos com escalonamentos gerenciados para reuniões. As reuniões oferecem experiências avançadas disponíveis para qualquer pessoa, independentemente de qual cliente eles têm.

Quando o escalonamento de interoperabilidade é disparado pelo usuário do Teams, uma reunião do Teams é criada. Quando ele é disparado pelo Skype for Business usuário, uma Skype for Business é criada. Em ambos os casos, a reunião criada é uma **reunião reunir** agora, o que não é refletido no calendário do usuário.

A outra parte recebe o link de ingresso na reunião por meio de chat de interoperabilidade e ingressa clicando nesse link. Se o Skype for Business usuário tiver uma conta do Teams e for convidado pelo usuário do Teams, ele ingressará na reunião autenticada. Caso contrário, eles ingressarão como um participante anônimo. Os usuários do Teams quase sempre têm uma conta do Skype for Business e um cliente do Skype for Business que podem usar para ingressar em uma reunião do Skype for Business como um participante autenticado, mas também podem ingressar como um participante anônimo, por exemplo, usando o aplicativo Reunião do Skype.

Depois que as partes tiverem ingressado na reunião, elas poderão realizar qualquer atividade com suporte em reuniões, como compartilhamento de área de trabalho ou conteúdo, compartilhamento ou transferência de arquivos, adição de outros participantes e assim por diante.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalonamento de interoperabilidade de Skype for Business

O escalonamento de interoperabilidade Skype for Business foi atualizado na compilação de julho de 2019 do C2R mensal. Anteriormente, Skype for Business não tinha conhecimento antecipado de que a parte remota estava usando o Teams. Ele só imaginou que a partir da sinalização recebida após uma sessão foi estabelecida.

Quando a sinalização indicou que a resposta veio (ou por meio) do gateway de interoperabilidade, ela exibiria a barra de negócios amarela (faixa) indicando que a outra parte não estava usando Skype for Business. Com a evolução do nosso serviço, isso resultou em falsos positivos em que os usuários do Skype for Business veriam a barra de negócios quando estavam conectados ao Serviço do Caixa postal na Nuvem ou a outros serviços de voz na nuvem, em vez de a um usuário real somente do **Teams**.

Para evitar falsos positivos, o serviço de presença agora está informando o cliente Skype for Business quando a outra parte é um usuário real **somente do Teams**. Isso permite Skype for Business criar uma conversa de interoperabilidade e a janela de conversa ser específica para interoperabilidade.

![Captura de tela da mensagem do Teams para criar uma conversa de interoperabilidade com um Skype for Business usuário.](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Se o Skype for Business quiser compartilhar sua área de trabalho, por exemplo, ele será informado de que iniciaremos uma reunião e serão orientados pelas etapas.

![Captura de tela da mensagem do Teams para iniciar a reunião com um usuário do Teams.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Enquanto isso, o usuário do Teams recebe uma mensagem de chat de entrada com o link para a reunião e é guiado para ingressar.

Esse escalonamento para uma Skype for Business está disponível para chamadas e chats federados entre locatários e entre locatários. Ele está ativado por padrão e não há nenhuma configuração que o administrador precisa provisionar.

#### <a name="interop-escalation-from-teams"></a>Escalonamento de interoperabilidade do Teams

O escalonamento de interoperabilidade do Teams para uma reunião do Teams agora está disponível quando o usuário do Teams seleciona o botão de compartilhamento de área de trabalho em um thread de interoperabilidade no locatário com um usuário do Skype for Business ou em um thread de federação de interoperabilidade entre locatários. O escalonamento de interoperabilidade é compatível com uma conversa de chat 1:1 ou de uma chamada 1:1.

A funcionalidade é compatível com o cliente da área de trabalho do Teams para Windows, no cliente da área de trabalho do Teams para Mac e no cliente Web do Teams em navegadores em que há suporte para compartilhamento de conteúdo, enquanto em comunicação com qualquer Skype for Business do cliente.

Em threads de interoperabilidade e em threads de interoperabilidade de federação, o usuário do Teams agora tem os controles (botão) para iniciar o compartilhamento de conteúdo. Quando o usuário do Teams seleciona o botão, ele é apresentado a um menu adicional que informa que, para compartilhar conteúdo, ele precisará iniciar uma reunião do Teams.

Se os usuários estiverem em uma chamada, o menu avisará que a chamada atual entre o Teams e o Skype for Business será encerrada à medida que eles forem colocados em uma reunião do Teams. Se escolherem, eles poderão avisar o Skype for Business usuário antes de aceitar.

![Captura de tela da mensagem do Teams para compartilhar a reunião com um Skype for Business usuário.](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Após a aceitação, eles são colocados na reunião do Teams; eles devem começar a compartilhar da bandeja de compartilhamento na reunião.

Enquanto isso, o Skype for Business usuário recebe uma mensagem de chat de entrada com o link para a reunião e é guiado para ingressar.

Esse escalonamento para uma reunião do Teams está disponível para chamadas e chats federados entre locatários e entre locatários. Ele está ativado por padrão e não há nenhuma configuração que o administrador precisa provisionar. No entanto, ele será desativado para o usuário se o administrador definir ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` como ``$false``.

Depois de examinar este artigo, confira Escolher o percurso de [atualização, as](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) diretrizes de [migração e interoperabilidade](./migration-interop-guidance-for-teams-with-skype.md), a [coexistência](coexistence-chat-calls-presence.md) com o Skype for Business e a definição das configurações de [coexistência](./setting-your-coexistence-and-upgrade-settings.md) e atualização para obter detalhes de implementação. Também recomendamos o seguinte vídeo: Vídeo [: Gerenciar coexistência e interoperabilidade entre o SfB e o Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Detalhes técnicos do Teams e Skype for Business coexistência

As seções a seguir resumem o comportamento que pode ser experimentado ao executar o Teams e Skype for Business clientes na mesma organização, independentemente do modo e do método de atualização usado:

- [Reuniões](#meetings)
- [Interoperabilidade](#interoperability)
- [Interoperabilidade versus threads de conversa nativos](#interop-versus-native-conversation-threads)
- [Presença](#presence)
- [Federação](#federation)
- [Contatos](#contacts)

### <a name="meetings"></a>Reuniões

Independentemente do modo, os usuários sempre podem ingressar em qualquer tipo de reunião para a qual forem convidados, seja Skype for Business ou Teams.  No entanto, os usuários devem ingressar na reunião com um cliente correspondente que corresponda ao tipo de reunião:

- Se a reunião for uma reunião do Teams, todos os participantes (sejam usuários do TeamsOnly, Islands ou Skype for Business) usarão o cliente do Teams para ingressar na reunião. Se o Teams não estiver instalado, o usuário será direcionado para a Web ao tentar ingressar em uma reunião.

- Se a reunião for uma reunião Skype for Business, todos os participantes (sejam usuários do TeamsOnly, Islands ou Skype for Business) usarão o cliente Skype for Business para ingressar na reunião. Se o Skype for Business cliente não estiver instalado, o usuário será direcionado para a Web para ingressar por meio do Reunião do Skype App. 

  Em alguns casos, os participantes no modo TeamsOnly só poderão ingressar em reuniões Skype for Business usando o Skype for Business Web App ou o Aplicativo reuniões do Skype como um usuário anônimo. Eventualmente, esse caso será verdadeiro para todos os usuários no modo TeamsOnly. Para obter mais informações, [consulte Skype for Business desativação online](skype-for-business-online-retirement.md#what-to-expect-post-retirement).

Ao organizar reuniões, o tipo de reunião agendado é baseado no modo do organizador, conforme mostrado na tabela a seguir:

| Modo de organizador    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings | Todas as reuniões agendadas no Teams. Skype for Business suplemento não está disponível no Outlook. |
| SfbWithTeamsCollab, SfbOnly | Todas as reuniões agendadas Skype for Business. O suplemento do Teams não está disponível no Outlook. Considere usar SfbWithTeamsCollabAndMeetings em vez disso, o que permite que todos os usuários, seja local ou TeamsOnly, usem o Teams para reuniões.|
| Ilhas | Por padrão, as reuniões podem ser agendadas no Skype for Business ou no Teams. Ambos os suplementos estão disponíveis no Outlook. No entanto, opcionalmente, você pode exigir que os usuários nas Ilhas sempre agendem reuniões no Teams atribuindo a eles uma instância do TeamsMeetingPolicy com PreferredMeetingProviderForIslandsMode=Teams.|

### <a name="interoperability"></a>Interoperabilidade

Conforme descrito acima em [Interoperabilidade do Teams e Skype for Business](#interoperability-of-teams-and-skype-for-business), o Teams dá suporte à interoperabilidade com Skype for Business em determinados cenários. A comunicação de interoperabilidade refere-se a um chat ou chamada entre um Skype for Business usuário e um usuário do Teams. A comunicação de interoperabilidade só é possível entre dois usuários; não há suporte para chat/chamada de várias partes ou adição de usuários adicionais.

Um chat de interoperabilidade ou chamada entre dois usuários é criado quando cada um dos seguintes é verdadeiro:

- Um usuário está usando o Teams e o outro está usando Skype for Business.

- O modo do destinatário da comunicação inicial não é Ilhas (caso contrário, a comunicação chegará no mesmo cliente) se ambos os usuários estão na mesma organização. Em cenários federados, o usuário de envio está usando o Teams e o destinatário não está no modo TeamsOnly.

- O usuário do Teams TAMBÉM NÃO tem Skype for Business conta local.

Dentro da comunicação de interoperabilidade, o chat é somente texto sem formatação. Além disso, o compartilhamento de arquivos e o compartilhamento de tela não são possíveis *no chat de interoperabilidade em si*. No entanto, os usuários em uma conversa de interoperabilidade podem facilmente obter o compartilhamento de arquivo e/ou tela criando uma reunião sob demanda, de dentro do chat de interoperabilidade, conforme descrito abaixo:

- Se o usuário do Teams tentar compartilhar sua tela, uma reunião do Teams sob demanda será criada automaticamente e um link de convite para essa reunião será enviado para o Skype for Business cliente do usuário. Ao clicar no link, o Skype for Business usuário abrirá o Teams e ingressará na reunião. Os dois usuários agora estão em uma reunião do Teams e podem compartilhar conforme necessário.

- Se o usuário do Skype for Business estiver usando um cliente de 2018 ou posterior e tentar compartilhar qualquer conteúdo, uma reunião do Skype for Business sob demanda será criada automaticamente e um link de convite para essa reunião será enviado para o cliente do usuário do Teams. Ao clicar no link, o usuário do Teams tentará ingressar na Skype for Business reunião. Se o usuário do Teams tiver o cliente Skype for Business instalado, ele será aberto e o usuário será solicitado a entrar (se ainda não tiver entrado).  Se o usuário do Teams não tiver o Skype for Business cliente instalado, o usuário será solicitado a usar a versão da Web. Depois que ambos os usuários estiverem conectados, eles estão em uma reunião Skype for Business e podem compartilhar conforme necessário.

### <a name="interop-versus-native-conversation-threads"></a>Interoperabilidade versus threads de conversa nativos

Como as comunicações de interoperabilidade não dão suporte a todos os recursos da conversa nativa do Teams, o cliente do Teams mantém threads de conversa separados para comunicação teams a teams e teams para Skype for Business. Essas conversas são renderizadas de forma diferente na interface do usuário: os threads de interoperabilidade podem ser diferenciados de um thread nativo regular do Teams:

- Falta de controles para rich text, compartilhamento de arquivo/tela, incapacidade de adicionar usuários.
- Uma modificação no ícone do usuário de destino, mostrando um "S" para Skype for Business.

Essas diferenças são mostradas nas capturas de tela a seguir:

Uma conversa nativa do Teams para o Teams com o Teste do Usuário G3

![Diagrama mostrando uma conversa nativa do Teams para o Teams.](media/teams-upgrade-native-thread.png)

Uma conversa de interoperabilidade com o mesmo Teste do User G3

![Diagrama mostrando uma conversa entre equipes e equipes.](media/teams-upgrade-interop-thread.png)

Depois que um thread de conversa é criado, seu tipo nunca é alterado. Depois de criado, um thread de interoperabilidade no Teams sempre será roteado para o cliente de Skype for Business do usuário de destino. Um thread nativo sempre será roteado para o cliente do Teams do usuário de destino.  Se o modo de um usuário destinatário for alterado, os threads existentes do Teams para esse usuário não funcionarão mais e uma anotação será exibida nesse chat com um link para iniciar uma nova conversa nativa, conforme mostrado na captura de tela a seguir.

![Diagrama mostrando um chat com o Skype for Business usuário atualizado.](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Presença

A presença de um determinado usuário baseia-se na atividade do usuário no serviço por meio do cliente. Em seguida, a presença é publicada para que outros usuários vejam.  Skype for Business e o Teams são serviços separados com clientes separados, portanto, cada serviço tem seu próprio estado de presença para um usuário.   Também há sincronização entre os serviços de presença no Teams e no Skype for Business Online.  Isso permite que um serviço publique potencialmente a presença do usuário do outro serviço, se necessário.

O comportamento de publicação de presença é baseado no modo do usuário. Há três casos básicos:

- Se um usuário estiver no modo TeamsOnly, todos os outros usuários verão a presença do Teams para esse usuário, independentemente do cliente usado.

- Se um usuário estiver em qualquer um dos modos Skype for Business, todos os outros usuários verão Skype for Business presença desse usuário, independentemente do cliente usado.

- Se um usuário estiver no modo Ilhas, a presença publicada no Skype for Business e no Teams será independente, portanto, a presença mostrada aos usuários na mesma organização dependerá do cliente do outro usuário. Os usuários em organizações federadas verão a presença desse usuário com base em sua atividade Skype for Business, pois o tráfego federado para um usuário do modo Ilhas chega Skype for Business.

Por exemplo, suponha que o usuário A esteja no modo Ilhas. Se o Usuário A estiver ativo no Teams, mas não estiver conectado ao Skype for Business, outros usuários verão o Usuário A como ativo de seu cliente do Teams, mas no cliente do Skype for Business eles verão o Usuário A como offline. Isso ocorre por design, pois o Usuário A não poderá ser acessado se ele não estiver executando o cliente.


### <a name="federation"></a>Federação

A federação do Teams para outro usuário usando Skype for Business requer que o usuário do Teams esteja hospedado online no Skype for Business. TeamsUpgradePolicy determina o roteamento para chamadas e conversas federadas e de entrada. O comportamento de roteamento federado é o mesmo para cenários de mesmo locatário, exceto no modo de Ilhas. Quando os destinatários estiverem no modo de Ilhas:

- Chats e chamadas iniciadas do Teams Skype for Business se o destinatário estiver em um locatário federado.
- Chats e chamadas iniciados a partir do Teams são recebidos no Teams se o destinatário estiver no mesmo locatário.
- Chats e chamadas iniciadas Skype for Business sempre são Skype for Business.

Um chat federado pode ser um thread nativo ou um thread de interoperabilidade. Consulte [Interoperabilidade versus threads de conversa nativos](#interop-versus-native-conversation-threads).

- Se o destinatário e o remetente estão no modo de atualização do TeamsOnly, a conversa será uma experiência de chat nativa, que inclui todos os recursos avançados de mensagens e chamadas. Para saber mais, leia [a experiência de chat nativo para usuários externos (federados) no Teams](native-chat-for-external-users.md).

- Se um dos participantes da conversa não estiver no modo de atualização do TeamsOnly, a conversa permanecerá uma experiência de interoperabilidade com mensagens somente de texto. A interface do usuário expõe chats federados de maneira semelhante a threads de interoperabilidade de mesmo locatário, exceto que há uma observação indicando que o usuário é externo.

Para obter mais detalhes, consulte [Gerenciar o acesso externo no Microsoft Teams e](manage-external-access.md) experiência de [chat nativo para usuários externos (federados) no Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Contatos

As equipes Skype for Business têm listas separadas de contatos. Isso significa que as adições, remoção e modificações de contato feitas em um sistema não são sincronizadas com o outro sistema. No entanto, os contatos Skype for Business são copiados automaticamente para o Teams quando ocorrem dois eventos específicos:

- Para qualquer Skype for Business Online, na primeira vez que fizer logon no Teams, os contatos do Skype for Business serão copiados para o Teams. Esse comportamento não está disponível para usuários com uma conta local no Skype for Business Server.

- Depois que um usuário for atualizado para o TeamsOnly (por meio da atribuição de TeamsUpgradePolicy ou por meio de Move-CsUser -MoveToTeams), na próxima vez que um usuário fizer logon no Teams, os contatos existentes no Skype for Business serão mesclados com contatos existentes já no Teams. Esse comportamento ocorre se o usuário foi movido para o TeamsOnly do local ou online.

Em ambos os casos, a transferência de contatos do Skype for Business para o Teams é assíncrona, portanto, pode levar alguns minutos até que os contatos apareçam no Teams. Os dois eventos acima são o que dispara a cópia.

### <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Configurar a conectividade híbrida entre Skype for Business Server e o Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
