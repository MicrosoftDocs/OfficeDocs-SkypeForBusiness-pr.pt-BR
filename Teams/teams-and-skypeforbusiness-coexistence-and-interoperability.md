---
title: Entender a coexistência e interoperabilidade do Skype para Teams da Microsoft e de negócios
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Detalhes do Skype para opções de coexistência de negócios e Teams da Microsoft e interoperabilidade entre equipes e Skype para negócios.
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd1d6c59b522db4cb60446d094465fc58db9cb7
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23865635"
---
![Estágios da atualização jornada, com ênfase no estágio a definição do projeto] (media/upgrade-banner-project-definition.png "Estágios da atualização jornada, com ênfase no estágio a definição do projeto")

Este artigo faz parte do estágio da sua atualização jornada definição do projeto, uma atividade que você concluir depois de criar uma equipe de projeto e coalition patrocínio e definir o escopo, metas e vision para o seu projeto. Antes de continuar, confirme que você tiver concluído as seguintes atividades:

-   [Inscrito seus participantes do projeto](upgrade-enlist-stakeholders.md)
-   [Definido o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Entender o Microsoft Teams e Skype para interoperabilidade e coexistência de negócios

Se sua organização usa Skype para negócios hoje e você pretende começar a usar as equipes junto com Skype para negócios — ou que você pretende iniciar a atualização para equipes — é importante entender como os dois aplicativos coexistirem, quando e como eles interoperam e como para Gerencie migração dos usuários até a sua atualização final do Skype para a equipes de negócios.

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistência de equipes e Skype para negócios

Além dos recursos de colaboração, equipes oferece o bate-papo, chamadas e capacidades de reunião. Dependendo de como você optar por implantar equipes, esses recursos podem sobrepor-se com os recursos fornecidos pelo Skype for Business para um determinado usuário. O modo padrão será executada equipes junto com Skype para negócios; No entanto, um usuário pode ser atribuído um dos vários modos de coexistência que foram projetados para garantir que esses recursos não se sobrepõem para esse usuário.

Recomendamos que você examine os modos de coexistência descritos a seguir para ajudar a determinar qual caminho é certo para sua organização.

> [!Important]
> Apresentando a nova tecnologia ou fazendo alterações em seu Skype existente, familiar para ambiente de negócios, oferecendo um excelentes novos benefícios comerciais, pode ser destrutivos para os usuários. Demore para avaliar a preparação do usuário e implementar um plano de treinamento e a comunicação antes de implementar qualquer uma das alterações descritas neste artigo. Além disso, recomendamos que você crie um piloto seu plano com um grupo selecionado de usuários antes de implementá-la em sua organização. 

### <a name="islands-mode"></a>Modo de ilhas

Por padrão, os usuários podem executar as equipes junto com Skype para negócios como duas soluções separadas que oferecem recursos similares e sobrepostos como bate-papo, chamadas e reuniões. Usuários de equipes também podem tirar proveito dos recursos de colaboração como equipes e canais, acesso a arquivos no Office 365 e aplicativos.

Neste modo de coexistência, chamado **Ilhas**, cada um dos aplicativos cliente opera como uma ilha separada. Skype para fala de negócios para Skype for Business e equipes conversa com equipes. Os usuários executar ambos os clientes e podem se comunicar nativamente no cliente do qual a comunicação foi iniciada. Sendo assim, não é necessário para interoperabilidade no modo de **Ilhas** .

> [!Tip]
> A maioria das organizações tendem a implantação em modo **Ilhas** . Se você planeja mover para equipes rapidamente e você não espera suportar a coexistência de long, é recomendável que usar o modo de **Ilhas** . 

### <a name="skype-for-business-only"></a>Skype para negócios apenas

Neste modo de coexistência, usuários permanecem no Skype para negócios — não às equipes — para bate-papo, reunião e chamando os recursos e eles não usam equipes para equipes e canais. Esse modo está disponível atualmente; No entanto, na implementação atual modalidades de equipes não sejam desativadas para o usuário automaticamente. Esse recurso é futuro. Enquanto isso, os administradores podem remover a licença de equipes para todos os usuários que precisam ficar em Skype para negócios como seu aplicativo de comunicação somente.

### <a name="teams-only-this-mode-is-rolling-out-starting-in-summer-2018"></a>As equipes apenas (esse modo é aplicação iniciada no verão 2018)

Assim que sua organização está pronta para alguns ou todos os usuários usem equipes como seu única ferramenta de comunicação e colaboração, você pode atualizar esses usuários para o modo de **equipes apenas** .

Um usuário de **equipes apenas** só pode usar o Skype para o cliente de negócios para ingressar Skype existente para reuniões de negócios ou reuniões em Skype for Business que foram organizadas por usuários não atualizado ou parceiros externos. Um usuário atualizado pode continuar a se comunicar com outros usuários na organização que ainda estejam usando Skype para negócios usando os recursos de interoperabilidade entre equipes e Skype para negócios; No entanto, um usuário atualizado não é possível iniciar uma Skype para negócios bate-papo, chamada ou reunião.

![Skype para cliente corporativos em execução em um modo especial depois que o usuário é atualizado como um usuário somente equipes] (media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype para cliente corporativos em execução em um modo especial depois que o usuário é atualizado como um usuário somente equipes")

### <a name="skype-for-business-with-teams-collaboration-this-mode-is-upcoming"></a>Skype for Business com colaboração de equipes (esse modo é futuro)

Use este modo apresentar equipes em seu ambiente enquanto você continuar a aproveitar seus investimentos existentes no Skype para negócios. Neste modo, você deixar Skype para negócios inalterado com bate-papo, chamadas e capacidades de reunião, e você adicionar recursos de colaboração de equipes — equipes e canais, o acesso a arquivos no Office 365 e aplicativos.

### <a name="skype-for-business-with-teams-collaboration-and-meetings-this-mode-is-upcoming"></a>Skype for Business com colaboração de equipes e reuniões (esse modo é futuro)

Use este modo de coexistência para acelerar a disponibilidade das equipes de recursos em sua organização, além dos seus recursos de colaboração da reunião, permitindo que os usuários para aproveitar a excelente qualidade, novos recursos como transcrição e conversão e suporte para reuniões em navegadores.

Junto com usando equipes para equipes e baseada no canais de conversas neste modo, os usuários iniciam usando equipes para agendar e conduzir suas reuniões. Bate-papos privadas e voz e chamadas de vídeo, permanecem no Skype para negócios. Esse modo de coexistência é especialmente útil para usuários no Skype para negócios local implantações que tem o enterprise voice, que são provavelmente levar algum tempo para ser atualizada para equipes

> [!Note]
> Quando implantado em modos de coexistência específico, equipes e Skype para negócios podem [interoperar](#interoperability-of-teams-and-skype-for-business), permitindo que os usuários conversar com e chamadas entre si e garantir que o communications permaneçam fluida em toda a organização durante sua atualização jornada às equipes. Modos de coexistência regem interoperabilidade. O modo de coexistência do receptor determina se a interoperabilidade estará disponível. Por exemplo, se o receptor estiver em um modo no qual o bate-papo só está disponível em um cliente (digamos, equipes), interoperabilidade de bate-papo geralmente será disponível no caso do iniciador usa outro cliente (no caso, Skype para negócios) para iniciar o bate-papo. Por outro lado, se o receptor estiver em um modo no qual o chat está disponível nos dois clientes, interoperabilidade não estarão disponível para o bate-papo — e a mensagem será recebida pelo receptor no mesmo cliente no qual o iniciador iniciado o bate-papo.

Para obter mais detalhes sobre modos de coexistência, pré-requisitos e gerenciamento, consulte [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](https://aka.ms/SkypeToTeams-Interop) e [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Ponto de decisão|<ul><li>Quais mode(s) coexistência melhor atendem às necessidades de sua organização e dos usuários?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próxima etapa|<ul><li>Escolha a melhor abordagem para sua jornada de atualização.</li></ul>|


## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidade de equipes e Skype para negócios

Interoperabilidade é a capacidade para equipes e Skype para usuários comerciais na mesma organização se comunicarem através de equipes e Skype para negócios.

### <a name="native-interop-and-interop-escalation"></a>Escalonamento de interoperabilidade e interoperabilidade nativo

Existem dois tipos de interoperabilidade experiências: escalonamento nativo e interoperabilidade.

-   Uma experiência de _interoperabilidade nativa_ ocorre no cliente do que o usuário está usando no momento. Um usuário terão o Skype para cliente de negócios, a outra em equipes. Uma experiência de interoperabilidade nativa não usá-las para outro cliente para comunicar-se de que os usuários poderão conduzir sua conversa no cliente está usando no momento. As experiências de interoperabilidade nativas são um chat e a chamada.
-   Uma experiência de _escalonamento de interoperabilidade_ significa que, como parte do ajudando os usuários a executar uma ação avançada (por exemplo, compartilhamento de sua área de trabalho), o serviço pode facilitar a criação de uma reunião e continuar a experiência em que a reunião. A reunião é criada na plataforma do iniciador da ação. O usuário ou usuários que não estão nessa plataforma receber reunião ingressar coordenadas e ingressem na reunião (após a comutação clientes).

### <a name="native-interop-experiences"></a>Experiências de interoperabilidade nativas

Dependendo dos modos de coexistência atribuídos aos usuários (conforme descrito acima), as seguintes experiências de interoperabilidade nativo estão disponíveis:

-   Skype para usuários comerciais puder conversar entrevistas individuais com usuários de equipes e vice-versa. Um chat interoperabilidade deve passar por um gateway de interoperabilidade que faz parte das equipes de serviços na nuvem (e, portanto, só existe online). Interoperabilidade chats estão em texto sem formatação: rich text e emoticons não são suportados. Os usuários em equipes são notificados de que a conversa é uma conversa de interoperabilidade; uma notificação semelhante para Skype para usuários comerciais será fornecida em breve.
![Experiência de equipes de chat de interoperabilidade] (media/Interop_chat_experience_from_Teams.png "Experiência de equipes de chat de interoperabilidade")
-   Skype para usuários comerciais pode tornar pessoal durante chamadas de voz e vídeos para usuários de equipes e vice-versa.
![Interoperabilidade chamar a experiência de equipes] (media/Interop_calling_experience_from_Teams.png "Interoperabilidade chamar a experiência de equipes")

> [!Important]
> Experiências de interoperabilidade com uma implantação local do Skype para a empresa exigem que o ambiente local está no modo de híbrido com Skype do Office 365 para empresas. Para obter detalhes, consulte as [orientações de interoperabilidade e migração](https://aka.ms/SkypeToTeams-Interop).

Estas experiências interoperabilidade estão disponíveis para usuários que têm um dos seguintes modos de coexistência atribuída: **Skype for Business com colaboração de equipes**, **Skype for Business com reuniões e colaboração de equipes**, apenas **Skype para negócios **, ou **equipes apenas**.


### <a name="native-interop-experience-limitations"></a>Limitações de experiência de interoperabilidade nativo

Alguns recursos não estão disponíveis para o bate-papo interoperabilidade e a experiência de chamada interoperabilidade entre equipes e Skype para negócios:

-   Redução, o conjunto completo de emoticon e RTF não são suportados da equipes ou Skype para negócios. Outros recursos nativos da caixa de redação em bate-papos de equipes não são suportados.
-   Não há suporte para compartilhamento (área de trabalho ou compartilhamento de aplicativo) entre equipes e Skype para negócios de tela.
-   Agrupe chats (conversas com vários participantes) em equipes só podem incluir os participantes que estejam usando equipes.
-   Conversas de mensagens Instantâneas de vários participantes (chats de grupo) no Skype para negócios só podem incluir a participantes que estejam usando Skype para negócios.
-   Escalonando uma em andamento-a-ponto chamada de voz ou vídeo a uma chamada de vários participantes envolvendo equipes e Skype para usuários comerciais não é suportado.
-   Transferência de chats de duas partes de arquivos ou anexo de arquivo em bate-papos grupo das equipes de Skype para a empresa — e vice-versa — não são suportados.
-   Não há nenhuma interoperabilidade com Skype para o Chat persistente de negócios.

Para obter todas estas limitações (exceto para Chat persistente), uma solução possível é para um usuário para iniciar uma reunião e convidar outro usuário para fazer sua junção. Essa solução alternativa é a base para interoperabilidade escalonamento.

> [!Important]
> O que é iniciado conforme um chat simple (IM) rapidamente pode escalar para uma chamada ou uma reunião ad hoc. Podemos entender o que esses cenários são essenciais para a experiência do usuário e a usabilidade e podemos está evoluindo continuamente experiências interoperabilidade entre Skype para usuários empresariais e equipes. Verifique novamente as informações mais atualizadas.

Após revisar neste artigo, consulte [Escolher sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [migração e orientações de interoperabilidade](https://aka.ms/SkypeToTeams-Interop)e [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) para obter detalhes de implementação.
