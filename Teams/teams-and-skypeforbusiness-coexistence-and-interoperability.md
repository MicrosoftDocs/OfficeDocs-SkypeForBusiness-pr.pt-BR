---
title: Interoperabilidade entre o Skype for Business e o Microsoft Teams
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
ms.openlocfilehash: ea8c313d74829c00532fa3310657879f94dc2e5d
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196425"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Compreender a coexistência e a interoperabilidade do Microsoft Teams e do Skype for Business

![Diagrama da jornada de atualização, enfatizando o estágio de Definição do Projeto](media/upgrade-banner-project-definition.png "Etapas da jornada de atualização, com ênfase no estágio de Definição do Projeto")

Este artigo faz parte da etapa Definição do Projeto da sua jornada de atualização, uma atividade que você conclui depois de criar uma conferência de apoio e equipe de projeto e definir o escopo, as metas e a visão do seu projeto. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)

Se a sua organização usa o Skype for Business hoje e você está começando a usar o Teams junto com o Skype for Business ( ou você está começando a atualizar para o Teams), é importante entender como os dois aplicativos coexistem, quando e como eles interoperam e como gerenciar a migração dos usuários até sua possível atualização do Skype for Business para o Teams.

> [!Tip]
> Assista à sessão a seguir para saber mais sobre [Coexistência e Interoperabilidade.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> Além disso, você pode participar de workshops interativos ao vivo, nos quais compartilharemos orientações, práticas recomendadas e recursos projetados para iniciar o planejamento e a implementação de atualizações.
>
> Para começar, participe primeiro da sessão de [Planejamento da atualização](https://aka.ms/SkypeToTeamsPlanning).

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistência do Teams e do Skype for Business

Além dos recursos de colaboração, o Teams oferece recursos de chat, chamada e reunião. Dependendo de como você optar por implantar o Teams, esses recursos podem se sobrepor aos recursos fornecidos pelo Skype for Business para um determinado usuário. O modo padrão é executar o Teams junto com o Skype for Business com os recursos sobrepostas; no entanto, um usuário pode ter um dos vários modos de coexistência (também conhecidos como modos de atualização) que foram projetados para garantir que esses recursos não se sobreponham a esse usuário (nesse caso, a interoperabilidade entre o Teams e o Skype for Business está disponível). Por exemplo, se você tiver ativos locais significativos do Skype for Business Server com uma implantação complexa do [](meetings-first.md) Enterprise Voice, mas quiser que os usuários aproveitem reuniões modernas o mais rapidamente possível, talvez você queira avaliar Reuniões Primeiro como um caminho alternativo.

Recomendamos que você revise os seguintes modos de coexistência para ajudar a determinar qual caminho é o certo para sua organização.

> [!Important]
> Apresentar novas tecnologias ou fazer alterações em seu ambiente existente e familiar do Skype for Business, ao mesmo tempo que fornece grandes benefícios para os novos negócios, pode ser prejudicial para os usuários. Leve algum tempo para avaliar a preparação do usuário e implementar um plano de comunicação e treinamento antes de implementar qualquer uma das alterações descritas neste artigo. Além disso, recomendamos que você pilote seu plano com um grupo de usuários selecionado antes de implementá-lo em toda a organização.

### <a name="islands-mode"></a>Modo ilhas

Por padrão, os usuários podem executar o Teams junto com o Skype for Business como duas soluções separadas que oferecem recursos semelhantes e sobrepostos, como presença, chat, chamadas e reuniões. Os usuários do Teams também podem aproveitar novos recursos de colaboração, como equipes e canais, acesso a arquivos no Microsoft 365 ou no Office 365 e aplicativos.

Nesse modo de coexistência, denominado **Ilhas,** cada um dos aplicativos cliente opera como uma ilha separada. O Skype for Business conversa com o Skype for Business e o Teams conversa com o Teams. Espera-se que os usuários executem os dois clientes o tempo todo e possam se comunicar de forma nativa no cliente a partir do qual a comunicação foi iniciada. Como tal, não há necessidade de interoperabilidade no **modo Ilhas.**

Para evitar uma experiência confusa ou regressada do Skype for Business, comunicações externas (federadas), serviços de voz PSTN e aplicativos de voz, integração do Office, controles HID para dispositivos USB e várias outras integrações continuam sendo tratadas pelo Skype for Business e não estão disponíveis no modo Teams em **Ilhas.** O Sistema telefônico não tem suporte no teams no **modo Ilhas;** nesse modo, o único cliente Enterprise Voice é o Skype for Business.

> [!Important]
> No **modo Ilhas,** todas as mensagens e chamadas de usuários federados (pessoas de fora da sua organização) são entregues no Skype for Business. Após a atualização para o modo **Somente equipes,** todas as mensagens e chamadas de fora da sua organização são entregues no Teams.

> [!Tip]
> O caminho recomendado para os clientes do  Skype for Business Online é começar com o  modo de Ilhas padrão, impulsionar a saturação da adoção do Teams na organização e ir rapidamente para o modo Somente equipes. Os clientes híbridos e locais, especialmente os complexos, podem se beneficiar da implantação  do modo colaboração do **Skype for Business** com o Teams como ponto de partida,  em vez do modo Ilhas, e avançar de lá para o Skype for Business com o modo de Colaboração e Reuniões do **Teams** (ou seja, Reuniões Primeiro), se apropriado, e para o modo Somente equipes quando a organização estiver pronta para adotar o Teams.

### <a name="teams-only"></a>Somente equipes

Um **usuário do Teams Somente** (também chamado de usuário atualizado) tem acesso a todos os recursos do Teams.  Eles podem manter o cliente Skype for Business para ingressar em reuniões no Skype for Business que tenham sido organizadas por usuários não atualizados ou partes externas. Um usuário atualizado pode continuar a se comunicar com outros usuários da organização que ainda usam o Skype for Business usando os  recursos de interoperabilidade entre o Teams e o Skype for Business (desde que esses usuários do Skype for Business não estão no modo Ilhas). No entanto, um usuário atualizado não pode iniciar um chat, chamada ou reunião do Skype for Business.

Assim que sua organização estiver pronta para que alguns ou todos os usuários usem  o Teams como sua única ferramenta de comunicação e colaboração, você poderá atualizar esses usuários para o modo Somente equipes. Se você estiver atualizando do modo **Ilhas,** recomendamos que primeiro saturar a adoção do Teams em toda a organização antes de iniciar o processo de atualização. Isso evita cenários de comunicação desfeitos devido ao **modo de Ilhas** não fornecer interoperabilidade.

No modo **Somente equipes,** o Teams é o aplicativo padrão para o protocolo SIP/Tel. Isso significa que os links no cartão de visita de um usuário no Outlook para chamada ou chat serão tratados pelo Teams.

Para considerações adicionais sobre como mover para o **modo Somente equipes,** consulte considerações sobre o modo [Somente equipes.](teams-only-mode-considerations.md)

![Captura de tela da mensagem de confirmação do Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Cliente Skype for Business em execução em um modo especial depois que o usuário é atualizado como um usuário somente do Teams")

### <a name="skype-for-business-only"></a>Somente Skype for Business

Nesse modo de coexistência, os usuários permanecem no Skype for Business, não no Teams, para recursos de chat, reunião e chamadas, e não usam o Teams para equipes e canais. Este modo está disponível hoje; no entanto, na implementação atual, as equipes e canais não são automaticamente desligados para o usuário. Isso pode ser feito usando a política de Configuração de Aplicativos para ocultar equipes e arquivos.

Esse modo pode ser usado antes de iniciar uma implantação gerenciada do Teams para impedir que os usuários começam a usar o Teams antes de terem uma preparação criada ou como uma maneira de habilitar a participação autenticada em reuniões do Teams para usuários do Skype for Business, desde que os usuários sejam licenciados para o Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business com Colaboração do Teams

Use esse modo para apresentar o Teams em seu ambiente enquanto você continua a aproveitar seu investimento existente no Skype for Business. Nesse modo, você deixa o Skype for Business inalterado para recursos de chat, chamadas e reuniões e adiciona recursos de colaboração do Teams: equipes e canais, acesso a arquivos no Microsoft 365 ou Office 365 e aplicativos. Os recursos de comunicação do Teams — chat privado, chamada e agendamento de reuniões — estão desligados por padrão nesse modo.

As organizações com um ponto de partida do Skype for Business  Server local ou híbrido devem considerar esse modo como uma alternativa ao modo Ilhas se quiserem dar aos usuários interoperabilidade e  previsibilidade de suas comunicações, além de ter uma linha do tempo previsível para sua atualização para o Teams (em vez de depender da saturação da adoção no modo Ilhas).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business com Colaboração e Reuniões do Teams, também conhecidos como Reuniões Primeiro

Use esse modo de coexistência para acelerar a disponibilidade dos recursos de reunião do Teams em sua organização, além de seus recursos de colaboração, permitindo que os usuários aproveitem a experiência de reuniões superiores do Teams com ótima qualidade, recursos inovadores, como transcrição e tradução ou desfocar a tela de fundo, além de uma experiência superior do usuário em todas as plataformas, incluindo dispositivos móveis e navegadores.

Além de usar o Teams para equipes e conversas baseadas em canais nesse modo, os usuários usarão o Teams para agendar e conduzir suas reuniões. O chat privado e as chamadas permanecem no Skype for Business. O Teams e o Skype for Business se beneficiam com uma variedade de recursos "melhores juntos", como reconciliação de presença, resuspensão/resuspensão automática e suporte a dispositivos HID em ambos os aplicativos. Observe que é possível ocultar equipes e canais se desejar usando a política de Configuração de Aplicativo.

Esse modo de coexistência é especialmente útil para organizações com implantações locais do Skype for Business com o Enterprise Voice, que provavelmente vão demorar um pouco para atualizar para o Teams e querem se beneficiar das reuniões superiores do Teams assim que possível.

> [!TIP]
> Para ajudar a identificar o modo de atualização recomendado com base nos recursos que você deseja habilitar no Teams enquanto o Skype for Business ainda estiver em uso, aproveite o Assistente de Atualização do Skype para [o Teams.](https://aka.ms/SkypeToTeamsWizard)

Para obter mais detalhes sobre modos de coexistência, pré-requisitos e gerenciamento, consulte as diretrizes de migração e [interoperabilidade](https://aka.ms/SkypeToTeams-Interop) para organizações que usam o Teams em conjunto com o Skype for Business e definindo suas configurações de [coexistência](https://aka.ms/SkypeToTeams-SetCoexistence)e atualização.

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Ponto de decisão|<ul><li>Quais modos de coexistência melhor se ajustam às necessidades da sua organização e dos usuários?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Próxima etapa|<ul><li>Escolha a melhor abordagem para sua jornada de atualização.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidade do Teams e do Skype for Business

Interoperabilidade é a capacidade de usuários do Teams e do Skype for Business na mesma organização se comunicarem entre o Teams e o Skype for Business.

A interoperabilidade é regida pelo modo de coexistência (também conhecido como modo de atualização) do receptor. Não há interoperabilidade quando o receptor está no **modo Ilhas.**

> [!Note]
> Quando implantado em qualquer modo de coexistência, exceto **ilhas,** o Teams e o Skype for Business podem [interoperar,](#interoperability-of-teams-and-skype-for-business)permitindo que os usuários conversem e liguem entre si e garantindo que as comunicações permaneçam fluidas em toda a organização durante sua jornada de atualização para o Teams. Os modos de coexistência regem a interoperabilidade. O modo de coexistência do receptor determina se a interoperabilidade estará disponível. Por exemplo, se o destinatário estiver em um modo no qual o chat só está disponível em um cliente (por exemplo, Teams), a interoperabilidade de chat geralmente estará disponível caso o iniciador use o outro cliente (nesse caso, Skype for Business) para iniciar o chat. Por outro lado, se o receptor estiver no modo no qual o chat está disponível em ambos os clientes (modo Ilhas), a interoperabilidade não estará disponível para o chat. A mensagem será recebida pelo destinatário no mesmo cliente no qual o iniciador iniciou o chat. Portanto, a comunicação adequada no **modo Ilhas** requer saturação da adoção do Teams; ou seja, todos os usuários que usam e monitoram ativamente os dois clientes.

> [!Note]
> **Para ter a experiência de coexistência mais recente, a versão do cliente deve ser o cliente mais recente disponível no canal de implantação do Office do usuário.**

### <a name="native-interop-and-interop-escalation"></a>Escala nativa interop e interop

Há dois tipos de experiências interop: escalação nativa e interop.

- Uma _experiência de interop_ nativa ocorre no cliente que o usuário está usando no momento. Um usuário estará no cliente Skype for Business, o outro no Teams. Uma experiência de interop nativa não os levará a outro cliente para se comunicar, os usuários poderão conduzir suas conversas no cliente que estão usando no momento. As experiências nativas de interop são chat e chamada entre duas pessoas.
- Uma _experiência de escalonamento interop_ significa que, como parte de ajudar os usuários a executar uma ação avançada (como compartilhar sua área de trabalho), o cliente facilita a criação de uma reunião em que os usuários podem ingressar para continuar a experiência nessa reunião. A reunião é criada na plataforma do iniciador da ação. O usuário ou os usuários que não estão nessa plataforma recebem um link de ingressar na reunião. Conforme eles clicam neste link, eles são ingressos na reunião em um cliente compatível (navegador, aplicativo Web ou cliente completo, dependendo da configuração). A escalonamento interop do Skype for Business requer um cliente recente. A escalação interop do Teams agora está disponível. Ambos são suportados em experiências de interoperabilidade no locatário e para locatários de comunicação federada.

### <a name="native-interop-experiences"></a>Experiências interop nativas

Dependendo dos modos de coexistência atribuídos aos usuários (conforme descrito anteriormente), as seguintes experiências nativas de interop estão disponíveis:

Os usuários do Skype for Business podem conversar entre duas pessoas com usuários do Teams e vice-versa. Um chat interop precisa passar por um gateway interop que faz parte dos serviços de nuvem do Teams (e, portanto, só existe online). Os chats interop são texto sem texto: rich text e emoticons não são suportados. Os usuários no Teams e no Skype for Business são notificados de que a conversa é uma conversa interop.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Os usuários do Skype for Business podem fazer chamadas de voz e vídeo entre duas pessoas para os usuários do Teams e vice-versa.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> As experiências de interopção com uma implantação local do Skype for Business exigem que o ambiente local está no modo híbrido com o Microsoft 365 ou o Office 365 Skype for Business. Para obter detalhes, consulte [as diretrizes de migração e interoperabilidade.](https://aka.ms/SkypeToTeams-Interop)

Essas experiências interop estão disponíveis para e entre usuários que têm um dos seguintes modos de coexistência atribuídos: Skype for Business com Colaboração do **Teams,** Skype for Business com Colaboração do Teams e **reuniões,** **Somente Skype for Business** ou Somente **Equipes.** Não há interoperabilidade para os usuários no **modo Ilhas.**

### <a name="native-interop-experience-limitations"></a>Limitações da experiência interop nativa

Devido à diferença nos protocolos e na tecnologia, não é possível dar suporte a todos os recursos de forma nativa. Especificamente, os seguintes recursos não estão disponíveis:

- A marcação, o rich text e o conjunto completo de emoticon não são suportados pelo Teams ou pelo Skype for Business. Outros recursos nativos da caixa de texto em chats do Teams não são suportados.
- O compartilhamento de tela (compartilhamento de área de trabalho ou aplicativo) entre o Teams e o Skype for Business não tem suporte nativo. No entanto, ele é suportado por meio de escalonamento interop.
- Os chats em grupo (conversas de várias partes) no Teams só podem incluir participantes que estão usando o Teams.
- Várias conversas de IM (chats em grupo) no Skype for Business só podem incluir participantes que estão usando o Skype for Business. No entanto, a escalonamento entre várias pessoas está disponível no Skype for Business.
- Não há suporte para o escalonamento de uma chamada de voz ou vídeo ponto a ponto em uma chamada de várias partes que envolva usuários do Teams e do Skype for Business.
- Não há suporte para transferência de arquivos para chats de duas pessoas ou anexos de arquivos em chats em grupo, do Teams para o Skype for Business e vice-versa.
- Não há interoperabilidade com o Chat Persistente do Skype for Business.

Para todas essas limitações (exceto o Chat Persistente), uma possível solução alternativa é um usuário iniciar uma reunião e convidar o outro usuário para participar dela.

Essa solução alternativa é a base para a escalonamento interop. Em particular, o compartilhamento de tela e a escalação para várias partes não podem ser alcançados na nativa, mas são suportados por meio de escalonamento interop.

### <a name="interop-escalation-experiences"></a>Interop experiências de escalonamento

A escalação interop consiste em complementar os recursos de interop nativos com escalonamentos gerenciados para reuniões. As reuniões oferecem experiências ricas disponíveis para qualquer pessoa, independentemente de qual cliente elas tenham.

Quando a escalação interop é disparada pelo usuário do Teams, uma reunião do Teams é criada. Quando ele é disparado pelo usuário do Skype for Business, uma reunião do Skype for Business é criada. Em ambos os casos, a reunião criada é **uma** reunião Reunir agora, que não se reflete no calendário do usuário.
 
A outra parte recebe o link de ingressar na reunião por meio de chat interop e in joins clicando nesse link. Se o usuário do Skype for Business tiver uma conta do Teams e for convidado pelo usuário do Teams, ele ingressará na reunião autenticado. Caso contrário, ele ingressará como um participante anônimo. Por outro lado, os usuários do Teams quase sempre têm uma conta do Skype for Business e um cliente do Skype for Business que podem usar para ingressar em uma reunião do Skype for Business como um participante autenticado, mas também podem ingressar como participantes anônimos, por exemplo, usando o aplicativo Reunião do Skype.

Depois que as partes ingressarem na reunião, poderão realizar qualquer atividade com suporte em reuniões, como compartilhamento de área de trabalho ou conteúdo, compartilhamento ou transferência de arquivos, adição de outros participantes e assim por diante.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalonamento interop do Skype for Business

A escala interop e interop do Skype for Business foi atualizada na com build mensal C2R de julho de 2019. Anteriormente, o Skype for Business não tinha reconhecimento antecipado de que a parte remota estava usando o Teams. Ele apenas suou que a partir da sinalização recebida após uma sessão ser estabelecida.

Quando a sinalização indicava que a resposta era de (ou por meio) do gateway de interop, ela exibia a barra de negócios amarela (faixa) indicando que a outra parte não estava usando o Skype for Business. Com a evolução do nosso serviço, isso resultou em falsos positivos em que os usuários do Skype for Business veriam a barra de negócios quando estavam conectados ao Serviço de Caixa Postal na Nuvem ou a outros serviços de voz na nuvem, em vez de a um usuário real do **Teams** Somente.
 
Para evitar esses falsos positivos, o serviço de presença agora informa o cliente Skype for Business quando a outra parte é um usuário real do **Teams.** Isso permite que o Skype for Business esteja ciente de que é necessário criar uma conversa interop antes de ela ter sido criada e a janela de conversa ser específica para interopção.

![Captura de tela da mensagem do Teams para criar uma conversa interop com um usuário do Skype for Business](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Se o usuário do Skype for Business quiser compartilhar sua área de trabalho, por exemplo, ele será informado de que iniciaremos uma reunião e orientaremos pelas etapas.

![Captura de tela da mensagem do Teams para iniciar uma reunião com um usuário do Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Enquanto isso, o usuário do Teams recebe uma mensagem de chat recebida com o link para a reunião e é orientado a ingressar.

Essa escalonamento para uma reunião do Skype for Business está disponível tanto para chamadas e chats federados entre locatários quanto entre locatários. Ele está por padrão e não há nenhuma configuração que o administrador tenha que provisionar.

#### <a name="interop-escalation-from-teams"></a>Escalonamento entre equipes

A escalonamento entre equipes para uma reunião do Teams agora está disponível quando o usuário do Teams seleciona o botão de compartilhamento de área de trabalho em uma conversa interop no locatário com um usuário do Skype for Business ou em um thread de federação interop entre locatários. A escalação entre duas pessoas tem suporte em uma conversa de chat 1:1 ou de uma chamada 1:1.

O recurso é suportado no cliente de área de trabalho do Teams para Windows, no cliente de área de trabalho do Teams para Mac e no cliente Web do Teams em navegadores em que há suporte para o compartilhamento de conteúdo, enquanto está em comunicação com qualquer versão do cliente Skype for Business.

Em threads de interoperabilidade e em threads de interoperabilidade de federação, o usuário do Teams agora tem os controles (botão) para iniciar o compartilhamento de conteúdo. Quando o usuário do Teams seleciona o botão, ele recebe um menu adicional que informa que, para compartilhar conteúdo, será necessário iniciar uma reunião do Teams.

Se os usuários estavam em uma chamada, o menu também os avisa que a chamada atual entre o Teams e o Skype for Business será encerrada à medida que eles são colocados em uma reunião do Teams. Se assim escolherem, eles poderão avisar o usuário do Skype for Business antes de aceitar.

![Captura de tela da mensagem do Teams para compartilhar reunião com um usuário do Skype for Business](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Após a aceitação, eles são colocados na reunião do Teams; eles devem começar a compartilhar a partir da bandeja de compartilhamento na reunião.
 
Enquanto isso, o usuário do Skype for Business recebe uma mensagem de chat recebida com o link para a reunião e é orientado a ingressar.

Essa escalonamento para uma reunião do Teams está disponível tanto para chamadas e chats federados entre locatários quanto entre locatários. Ele está por padrão e não há nenhuma configuração que o administrador tenha que provisionar. No entanto, ele será desabilitado para o usuário se o administrador ``-AllowPrivateMeetNow`` entrar ``CsTeamsMeetingPolicy`` em ``$false`` .

Depois de revisar este artigo, consulte Escolher sua jornada de [atualização,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)diretrizes de migração e [interoperabilidade,](https://aka.ms/SkypeToTeams-Interop) [Coexistência](coexistence-chat-calls-presence.md)com o Skype for Business e Definir suas configurações de [coexistência](https://aka.ms/SkypeToTeams-SetCoexistence) e atualização para os detalhes da implementação.

## <a name="related-links"></a>Links Relacionados

[Vídeo: Gerenciar coexistência e interoperabilidade entre o SfB e o Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
