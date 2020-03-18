---
title: Microsoft Teams | Atualização, modo de ilhas, política de interoperabilidade, somente
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Detalhes das opções de coexistência do Skype for Business e do Microsoft Teams e interoperabilidade entre o Skype for Business e o Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef1c9d8fd9d30101fdd40dba5946dfefb324742c
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706651"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business

![Diagrama da jornada de atualização, enfatizando o estágio de Definição do Projeto](media/upgrade-banner-project-definition.png "Etapas da jornada de atualização, com ênfase no estágio de Definição do Projeto")

Este artigo faz parte do estágio de definição do projeto da sua jornada de atualização, uma atividade que você preenche após criar um patrocínio de aliança e equipe de projeto e definir o escopo, metas e visão do seu projeto. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)

Se sua organização usa o Skype for Business hoje e você está começando a usar o Microsoft Teams com o Skype for Business — ou está começando a fazer o upgrade para o Microsoft Teams, é importante entender como os dois aplicativos coexistem, quando e como eles interoperam e como gerenciar migração dos usuários em relação à sua eventual atualização do Skype for Business para o Teams.

> [!Tip]
> Assista à sessão a seguir para saber mais sobre [coexistência e interoperabilidade](https://aka.ms/teams-upgrade-coexistence-interop).
>
> Além disso, você pode participar de workshops interativos e ativos nos quais compartilharemos orientação, práticas recomendadas e recursos projetados para começar a fazer o planejamento e a implementação da atualização.
>
> Para começar, participe primeiro da sessão de [Planejamento da atualização](https://aka.ms/SkypeToTeamsPlanning).

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistência de Teams e Skype for Business

Além dos recursos de colaboração, o Teams oferece recursos de chat, chamada e reunião. Dependendo de como você opta por implantar o Microsoft Teams, esses recursos podem se sobrepor com os recursos fornecidos pelo Skype for Business para um usuário específico. O modo padrão é executar o Microsoft Teams juntamente com o Skype for Business com os recursos sobrepostos; no entanto, um usuário pode ser atribuído a um dos vários modos de coexistência (também conhecidos como modos de atualização) que foram projetados para garantir que esses recursos não se sobreponham a esse usuário (nesse caso, a interoperabilidade entre equipes e o Skype for Business está disponível). Por exemplo, se você tiver ativos significativos do Skype for Business Server com uma implantação complexa do Enterprise Voice, mas quiser que seus usuários aproveitem reuniões modernas o mais rápido possível, talvez queira avaliar as [reuniões primeiro](meetings-first.md) como um caminho alternativo.

Recomendamos que você revise os seguintes modos de coexistência para ajudar a determinar qual caminho é ideal para sua organização.

> [!Important]
> Apresentar nova tecnologia ou fazer alterações em seu ambiente Skype for Business, familiar e, ao mesmo tempo em que oferece novos benefícios para os negócios, pode causar interrupções para os usuários. Reserve algum tempo para avaliar a prontidão do usuário e implementar um plano de comunicação e treinamento antes de implementar qualquer uma das alterações descritas neste artigo. Além disso, recomendamos enfaticamente que você pilote seu plano com um grupo de usuários selecionado antes de implementá-lo em toda a organização.

### <a name="islands-mode"></a>Modo de ilhas

Por padrão, os usuários podem executar o Microsoft Teams juntamente com o Skype for Business como duas soluções separadas que oferecem recursos semelhantes e sobrepostos, como presença, chat, chamadas e reuniões. Os usuários do teams também podem aproveitar os novos recursos de colaboração, como equipes e canais, o acesso a arquivos no Office 365 e aplicativos.

Nesse modo de coexistência, chamado de **ilhas**, cada um dos aplicativos cliente Opera como uma ilha separada. O Skype for Business conversa com o Skype for Business e o Teams conversa com o Microsoft Teams. Espera-se que os usuários executem os dois clientes o tempo todo e possam se comunicar nativamente no cliente a partir do qual a comunicação foi iniciada. Assim, não há necessidade de interoperabilidade no modo de **ilhas** .

Para evitar uma experiência confusa ou inesperada do Skype for Business, comunicações externas (federadas), serviços de voz PSTN e aplicativos de voz, integração do Office, controles HID para dispositivos USB e várias outras integrações continuam a ser administradas pelo Skype for Business e não estão disponíveis no Microsoft Teams no modo de **ilhas** . O sistema telefônico não é compatível com o Microsoft Teams no modo de **ilhas** ; Nesse modo, o único cliente Enterprise Voice é o Skype for Business.

> [!Important]
> No modo **ilhas** , todas as mensagens e chamadas de usuários federados (pessoas de fora da sua organização) são entregues ao Skype for Business. Após a atualização para o modo **somente equipes** , todas as mensagens e chamadas de fora da sua organização serão entregues ao Teams.

> [!Tip]
> O caminho recomendado para clientes do Skype for Business Online é começar com o modo de **ilhas** padrão, orientar a saturação da adoção da equipe na organização e, em seguida, mover para o modo **somente Teams** rapidamente. Os clientes locais e híbridos, especialmente os complexos, podem se beneficiar de implantar o **Skype for Business com** o modo de colaboração do teams como ponto de partida, em vez do modo de **ilhas** e fazer o andamento de lá para o **Skype for Business com o modo de colaboração e reuniões do teams** (ou seja, reuniões primeiro), se for apropriado, e para o modo **somente** para empresas

### <a name="skype-for-business-only"></a>Somente Skype for Business

Nesse modo de coexistência, os usuários permanecem no Skype for Business, não nas equipes, para recursos de chat, reunião e chamadas, e não usam equipes para equipes e canais. Este modo está disponível hoje; no entanto, na implementação atual, as equipes e os canais não são desativados automaticamente para o usuário. Isso pode ser conseguido com o uso da política de permissão do aplicativo para ocultar equipes e canais.

Esse modo pode ser usado antes de iniciar uma implantação gerenciada do teams para impedir que os usuários comecem a usar o Microsoft Teams antes de ter uma prontidão interna, ou como uma maneira de habilitar a participação autenticada em reuniões de equipe para usuários do Skype for Business, contanto que os usuários estejam licenciado para Teams.

### <a name="teams-only"></a>Somente equipes


> [!IMPORTANT]
> Se você desinstalar o cliente do Skype for Business depois de mover um usuários para o modo **Somente Microsoft Teams**, a presença deixará de funcionar no Outlook e em outros aplicativos do Office. A presença funciona bem no Microsoft Teams. Solução alternativa: para ver a presença no Outlook (e em outros aplicativos do Office), o Skype for Business deve estar instalado, mesmo se você estiver executando o Microsoft Teams no modo **somente Teams** . A Microsoft está ciente desse problema e trabalhando para corrigi-lo.


Um usuário **somente para equipes** (também chamado de usuário *atualizado* ) tem acesso a todos os recursos do teams. Eles podem reter o cliente Skype for Business para ingressar em reuniões no Skype for Business que foram organizadas por usuários não atualizados ou parceiros externos. Um usuário atualizado pode continuar a se comunicar com outros usuários da organização que ainda estão usando o Skype for Business usando recursos de interoperabilidade entre o Teams e o Skype for Business (desde que esses usuários do Skype for Business não estejam no modo **ilhas** ). No entanto, um usuário atualizado não pode iniciar um chat, chamada ou reunião do Skype for Business.

Assim que a sua organização estiver pronta para alguns ou todos os usuários usarem o Microsoft Teams como a única ferramenta de comunicação e colaboração, você poderá atualizar esses usuários para o modo **somente Teams** . Se você estiver atualizando do modo de **ilhas** , aconselhamos que primeiro você saturasse a adoção da equipe em toda a organização antes de iniciar o processo de atualização. Isso evita cenários de comunicação desfeitas devido ao modo de **ilhas** que não fornecem interoperabilidade.

Para saber mais sobre como migrar para o modo **somente equipes** , consulte [Considerações sobre o modo Microsoft Teams](teams-only-mode-considerations.md).

![Captura de tela da mensagem de confirmação do teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Cliente do Skype for Business executado em um modo especial após o usuário ser atualizado como usuário do Microsoft Teams-only")

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business com colaboração em equipe

Use esse modo para apresentar as equipes do seu ambiente enquanto você continua a aproveitar o investimento existente no Skype for Business. Nesse modo, você deixa o Skype for Business inalterável para recursos de chat, chamada e reunião, e adiciona recursos de colaboração de equipes — equipes e canais, acesso a arquivos no Office 365 e aplicativos. Recursos de comunicação de equipes – reuniões privadas de chat, chamadas e agendamento são desativadas, por padrão, nesse modo.

Organizações com um ponto de partida do Skype for Business Server no local ou híbrido devem considerar esse modo como uma alternativa para o modo de **ilhas** se desejam oferecer aos usuários interoperabilidade e previsibilidade para suas comunicações, bem como ter uma linha do tempo previsível para a atualização para o Microsoft Teams (em oposição a depender da saturação de adoção no modo de **ilhas** ).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype para empresas com colaboração e reuniões do Teams, também conhecidas como reuniões primeiro

Use este modo de coexistência para acelerar a disponibilidade de recursos de reunião do teams em sua organização, além de seus recursos de colaboração, permitindo que os usuários aproveitem a experiência de reuniões de equipes superiores-excelente qualidade, recursos inovadores, como transcrição e tradução ou suavidade do plano de fundo, e experiência superior do usuário em todas as plataformas, incluindo dispositivos móveis e navegadores.

Juntamente com o uso do teams para equipes e canais – conversas com base nesse modo, os usuários usarão o Teams para agendar e conduzir suas reuniões. O chat e as chamadas particulares permanecem no Skype for Business. O Teams e o Skype for Business tiram proveito de uma variedade de recursos "aprimorados juntos", como reconciliação de presença, retenção automática/desbloqueio e suporte a dispositivo HID em ambos os aplicativos. Observe que é possível ocultar equipes e canais, se desejado, usando a política de permissões do aplicativo.

Esse modo de coexistência é especialmente útil para organizações com implantações locais do Skype for Business com o Enterprise Voice, que provavelmente levará algum tempo para fazer a atualização para o Microsoft Teams e gostaria de aproveitar as reuniões de equipes superiores o mais rápido possível.

> [!Note]
> Quando implantado em qualquer modo de coexistência, exceto as **ilhas**, Teams e Skype for Business podem [interoperar](#interoperability-of-teams-and-skype-for-business), permitindo que os usuários conversem e liguem e liguem-se e garantindo que as comunicações permaneçam fluindo para a sua organização durante a viagem de atualização para o Teams. Os modos de coexistência regem a interoperabilidade. O modo de coexistência do receptor determina se a interoperabilidade estará disponível. Por exemplo, se o destinatário estiver em um modo no qual o chat está disponível apenas em um cliente (digamos, equipes), a interoperabilidade de chat geralmente estará disponível para o caso de o iniciador usar o outro cliente (neste caso, o Skype for Business) para iniciar o chat. Por outro lado, se o receptor estiver no modo em que o chat está disponível nos dois clientes (modo de ilhas), a interoperabilidade não estará disponível para o chat. A mensagem será recebida pelo destinatário no mesmo cliente no qual o iniciador iniciou o chat. Portanto, a comunicação adequada no modo de **ilhas** requer saturação de adoção do teams; ou seja, todos os usuários que usam ativamente e monitoram os dois clientes.

> [!TIP]
> Para ajudar a identificar o modo de atualização recomendado com base nos recursos que você deseja habilitar no Teams enquanto o Skype for Business ainda está em uso, use o [Assistente de atualização do Skype to Teams](https://aka.ms/SkypeToTeamsWizard).

Para obter mais detalhes sobre modos de coexistência, pré-requisitos e gerenciamento, consulte [orientação de migração e interoperabilidade para organizações que usam o Skype for Business](https://aka.ms/SkypeToTeams-Interop) e [como configurar sua coexistência e configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence).

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Ponto de decisão|<ul><li>Quais são os modos de coexistência mais adequados para as necessidades da sua organização e dos usuários?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Próxima etapa|<ul><li>Escolha a melhor abordagem para a sua jornada de atualização.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidade do Teams e do Skype for Business

Interoperabilidade é a capacidade para os usuários do Teams e do Skype for Business na mesma organização se comunicarem entre o Teams e o Skype for Business.

A interoperabilidade é regida pelo modo de coexistência (também conhecido como modo de atualização) do receptor. Não há interoperabilidade quando o receptor está no modo de **ilhas** .

### <a name="native-interop-and-interop-escalation"></a>Escalonamento nativo e escalonamento de interoperabilidade

Há dois tipos de experiências de interoperabilidade: escalonamento nativo e interoperabilidade.

- Uma experiência de _interoperabilidade nativa_ ocorre no cliente que o usuário está usando no momento. Um usuário estará no cliente Skype for Business, o outro no Teams. Uma experiência de interoperabilidade nativa não vai levá-la para outro cliente para se comunicar, os usuários poderão conduzir a conversa no cliente que estiverem usando no momento. As experiências de interoperabilidade nativa são chat e chamadas de um-para-um.
- Uma experiência de _escalonamento de interoperabilidade_ significa que, como parte de ajudar os usuários a executar uma ação avançada (como o compartilhamento de área de trabalho), o cliente facilita a criação de uma reunião na qual os usuários podem ingressar para continuar a experiência nessa reunião. A reunião é criada na plataforma do iniciador da ação. O usuário ou os usuários que não estão nessa plataforma recebem um link de ingresso na reunião. Conforme clicam nesse link, eles são associados à reunião em um cliente compatível (navegador, aplicativo Web ou cliente completo, dependendo da configuração). O escalonamento de interoperabilidade do Skype for Business exige um cliente recente. O escalonamento de interoperabilidade do teams agora está disponível. Ambos são compatíveis com experiências de interoperabilidade no locatário e para os locatários de comunicação federada.

### <a name="native-interop-experiences"></a>Experiências de interoperabilidade nativa

Dependendo dos modos de coexistência atribuídos aos usuários (conforme descrito anteriormente), as seguintes experiências de interoperabilidade nativa estão disponíveis:

Os usuários do Skype for Business podem conversar com usuários do Microsoft Teams e vice-versa. Um chat de interoperabilidade precisa passar por um gateway de interoperabilidade que faz parte dos serviços de nuvem do Teams (e, portanto, só existe online). Chats de interoperabilidade são texto sem formatação: não há suporte para Rich Text e emoticons. Os usuários do Teams e do Skype for Business são notificados de que a conversa é uma conversa de interoperabilidade.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Os usuários do Skype for Business podem fazer chamadas com voz e com vídeo individuais para usuários do Teams e vice-versa.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> As experiências de interoperabilidade com uma implantação local do Skype for Business exigem que o ambiente local esteja no modo híbrido com o Office 365 Skype for Business. Para obter detalhes, consulte [orientação de migração e interoperabilidade](https://aka.ms/SkypeToTeams-Interop).

Essas experiências de interoperabilidade estão disponíveis para e entre os usuários que têm um dos seguintes modos de coexistência atribuídos: **Skype for Business com colaboração do teams**, **Skype para empresas com colaboração e reuniões do teams**, **somente para Skype for Business**ou somente para **equipes**. Não há interoperabilidade para os usuários no modo de **ilhas** .

### <a name="native-interop-experience-limitations"></a>Limitações da experiência de interoperabilidade nativa

Devido à diferença de protocolos e tecnologia, não é possível dar suporte a todos os recursos nativamente. Especificamente, os seguintes recursos não estão disponíveis:

- A redução, o Rich Text e o conjunto de emoticons completos não têm suporte do teams ou do Skype for Business. Outros recursos nativos da caixa de texto nos chats de equipe não têm suporte.
- O compartilhamento de tela (área de trabalho ou compartilhamento de aplicativos) entre o Microsoft Teams e o Skype for Business não tem suporte nativo. No entanto, ele é compatível com o escalonamento de interoperabilidade.
- Chats em grupo (conversas com vários participantes) no Teams só podem incluir participantes que estejam usando o Teams.
- Conversas de mensagens instantâneas de vários participantes (chats em grupo) no Skype for Business podem incluir somente participantes que estão usando o Skype for Business. No entanto, o escalonamento de interoperabilidade para vários participantes está disponível no Skype for Business.
- Não há suporte para a expansão contínua de uma chamada de voz ou com vídeo em andamento para uma chamada de vários participantes que envolve o Microsoft Teams e os usuários do Skype for Business.
- A transferência de arquivos para chats de duas partes, ou anexo de arquivo em chats em grupo, do teams para o Skype for Business, e vice-versa, não são compatíveis.
- Não há interoperabilidade com o chat persistente do Skype for Business.

Para todas essas limitações (exceto para o chat persistente), uma possível solução é que um usuário inicie uma reunião e convide o outro usuário para ingressar nela.

Essa solução alternativa é a base para o escalonamento de interoperabilidade. Em particular, o compartilhamento de tela e o escalonamento a vários participantes não são atingíveis nativamente, mas têm suporte por meio de escalonamento de interoperabilidade.

### <a name="interop-escalation-experiences"></a>Experiências de escalonamento de interoperabilidade

O escalonamento de interoperabilidade consiste em complementar os recursos de interoperabilidade nativa com escalonamentos gerenciados para reuniões. As reuniões oferecem experiências ricas disponíveis para qualquer pessoa, independentemente de qual cliente ele tem.

Quando o escalonamento de interoperabilidade é disparado pelo usuário do Teams, uma reunião do teams é criada. Quando ele é disparado pelo usuário do Skype for Business, é criada uma reunião do Skype for Business. Em ambos os casos, a reunião criada é uma reunião **reunir agora** , que não se reflete no calendário do usuário.
 
A outra parte recebe o link ingressar na reunião por meio de chat de interoperabilidade e junções clicando nesse link. Se o usuário do Skype for Business tiver uma conta do Teams e for convidado pelo usuário do Teams, ele entrará na reunião autenticada. Caso contrário, eles se juntarão como participantes anônimos. Por outro lado, os usuários do teams quase sempre têm uma conta do Skype for Business e um cliente do Skype for Business que podem usar para ingressar em uma reunião do Skype for Business como participante autenticado, mas também podem participar como um participante anônimo, por exemplo, usando o Skype Aplicativo de reunião.

Depois que os participantes ingressarem na reunião, poderão conduzir qualquer atividade com suporte em reuniões, como compartilhamento de área de trabalho ou de conteúdo, compartilhamento de arquivos ou transferência, adição de outros participantes e assim por diante.

#### <a name="interop-escalation-from-skype-for-business"></a>Escalonamento de interoperabilidade do Skype for Business

O escalonamento de interoperabilidade e interoperabilidade do Skype for Business foi atualizado na compilação de julho de 2019 de C2R mensal. Anteriormente, o Skype for Business não tinha reconhecimento antecipado de que a parte remota estava usando o Teams. Ele só surmised que da sinalização recebida após uma sessão ser estabelecida.

Quando a sinalização indicou que a resposta veio de (ou por) o gateway de interoperabilidade, ela exibiria a barra de negócios amarela (faixa), indicando que a outra pessoa não estava usando o Skype for Business. Com a evolução do nosso serviço, isso resultava em falsos positivos nos quais os usuários do Skype for Business veriam a barra de negócios quando estavam conectados ao serviço de correio de voz na nuvem ou outros serviços de voz em nuvem, em vez de um usuário **somente para equipes** reais.
 
Para evitar esses falsos positivos, o serviço de presença agora está informando o cliente Skype for Business quando a outra pessoa é uma **equipe apenas** um usuário real. Isso permite que o Skype for Business saiba que precisa criar uma conversa de interoperabilidade à sua volta e a janela de conversa para ser específica da interoperabilidade.

![Captura de tela da mensagem do teams para criar uma conversa de interoperabilidade com um usuário do Skype for Business](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Se o usuário do Skype for Business quiser compartilhar sua área de trabalho por exemplo, ele será informado de que vamos iniciar uma reunião e guiado pelas etapas.

![Captura de tela da mensagem do teams para começar a reunião com um usuário do teams](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Enquanto isso, o usuário do teams recebe uma mensagem de chat recebida com o link para a reunião e é guiado para ingressar.

Esse escalonamento para uma reunião do Skype for Business está disponível para interoperabilidade dentro do locatário e chamadas federadas e chats de locatário cruzado. Ele está ativado por padrão e não há nenhuma configuração que o administrador tenha para provisionar.

#### <a name="interop-escalation-from-teams"></a>Escalonamento de interoperabilidade do teams

O escalonamento de interoperabilidade do teams para uma reunião de equipes agora está disponível quando o usuário do teams seleciona o botão de compartilhamento de área de trabalho em um thread de interoperabilidade de locatário com um usuário do Skype for Business ou em um thread de Federação interoperabilidade de locatários. O escalonamento de interoperabilidade é oferecido por uma conversa de chat do 1:1 ou de uma chamada do 1:1.

A funcionalidade tem suporte no cliente da área de trabalho do teams para Windows, no cliente da área de trabalho do teams para Mac, e no cliente da Web do teams nos navegadores com suporte para compartilhamento de conteúdo durante a comunicação com qualquer versão de cliente do Skype for Business.

Em threads de interoperabilidade e em threads de interoperabilidade de Federação, o usuário do teams agora tem os controles (botão) para iniciar o compartilhamento de conteúdo. Quando o usuário do teams selecionar o botão, ele receberá um menu adicional informando que o conteúdo deve ser compartilhado, será necessário iniciar uma reunião do teams.

Se os usuários estavam em uma chamada, o menu também o alerta de que a sua chamada atual entre o Teams e o Skype for Business será encerrada à medida que eles forem colocados em uma reunião do teams. Se isso for feito, ele pode avisar o usuário do Skype for Business antes de aceitar.

![Captura de tela da mensagem do teams para compartilhar reuniões com um usuário do Skype for Business](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Mediante a aceitação, eles são colocados na reunião do teams; Eles devem começar a compartilhar da bandeja de compartilhamento na reunião.
 
Enquanto isso, o usuário do Skype for Business recebe uma mensagem de chat de entrada com o link para a reunião e é guiado para ingressar.

Esse escalonamento para uma reunião do teams está disponível para interoperabilidade dentro do locatário e chamadas federadas e chats de locatário cruzado. Ele está ativado por padrão e não há nenhuma configuração que o administrador tenha para provisionar. No entanto, ela é desativada para o usuário se ``-AllowPrivateMeetNow`` o ``CsTeamsMeetingPolicy`` administrador ``$false``definir como.

Depois de revisar este artigo, consulte [escolher a sua viagem de atualização, a](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) [orientação de migração e interoperabilidade](https://aka.ms/SkypeToTeams-Interop), [a coexistência com o Skype for Business](coexistence-chat-calls-presence.md)e [a configuração de seus parâmetros de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence) para obter detalhes sobre a implementação.

## <a name="related-links"></a>Links relacionados

[Vídeo: gerenciar a coexistência e interoperabilidade entre o SfB e o Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
