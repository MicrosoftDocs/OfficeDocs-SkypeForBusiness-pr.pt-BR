---
title: Microsoft Teams | Atualização, modo de ilhas, política de interoperabilidade, somente
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Detalhes das opções de coexistência do Skype for Business e do Microsoft Teams e interoperabilidade entre o Skype for Business e o Teams.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c10a5fd2a1a172410a69362687146ba50cd69529
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344566"
---
![Estágios da jornada da atualização, com ênfase no estágio de definição do projeto] (media/upgrade-banner-project-definition.png "Estágios da jornada da atualização, com ênfase no estágio de definição do projeto")

Este artigo faz parte do estágio de definição do projeto da sua jornada de atualização, uma atividade que você preenche após criar um patrocínio de aliança e equipe de projeto e definir o escopo, metas e visão do seu projeto. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Listamos os participantes do projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business

Se a sua organização usa o Skype for Business hoje e você pretende começar a usar o Microsoft Teams juntamente com o Skype for Business — ou pretende começar a fazer a atualização para o Microsoft Teams, é importante entender como os dois aplicativos coexistem, quando e como eles interoperam e como gerenciar a migração dos usuários em relação à sua atualização eventual do Skype for Business para o Teams.

> [!Tip]
> Assista à sessão a seguir para saber mais sobre [coexistência e](https://aka.ms/teams-upgrade-coexistence-interop) interoperabilidade

## <a name="coexistence-of-teams-and-skype-for-business"></a>Coexistência de Teams e Skype for Business

Além dos recursos de colaboração, o Teams oferece recursos de chat, chamada e reunião. Dependendo de como você optar por implantar o Microsoft Teams, esses recursos ficarão sobrepostos com os recursos oferecidos pelo Skype for Business para um determinado usuário. O modo padrão é executar o Microsoft Teams juntamente com o Skype for Business; no entanto, um usuário pode receber um dos vários modos de coexistência projetados para garantir que esses recursos não se sobreponham a esse usuário.

Recomendamos que você revise os modos de coexistência discutidos abaixo para ajudar a determinar qual caminho é ideal para a sua organização.

> [!Important]
> Apresentar nova tecnologia ou fazer alterações em seu ambiente Skype for Business, familiar e, ao mesmo tempo em que oferece novos benefícios para os negócios, pode causar interrupções para os usuários. Reserve algum tempo para avaliar a prontidão do usuário e implementar um plano de comunicação e treinamento antes de implementar qualquer uma das alterações descritas neste artigo. Além disso, recomendamos enfaticamente que você pilote seu plano com um grupo de usuários selecionado antes de implementá-lo em toda a organização.

### <a name="islands-mode"></a>Modo de ilhas

Por padrão, os usuários podem executar o Microsoft Teams juntamente com o Skype for Business como duas soluções separadas que oferecem recursos semelhantes e sobrepostos, como chat, chamadas e reuniões. Os usuários do teams também podem tirar proveito dos recursos de colaboração, como equipes e canais, acesso a arquivos no Office 365 e aplicativos.

Nesse modo de coexistência, chamado de **ilhas**, cada um dos aplicativos cliente Opera como uma ilha separada. O Skype for Business conversa com o Skype for Business e o Teams conversa com o Microsoft Teams. Os usuários executam os dois clientes e podem se comunicar nativamente no cliente a partir do qual a comunicação foi iniciada. Assim, não há necessidade de interoperabilidade no modo de **ilhas** .

> [!Tip]
> O caminho recomendado para clientes do Skype for Business Online é começar com o modo de **ilhas** padrão, direcionar a saturação de adoção na organização e, em seguida, mover para o modo **somente Teams** rapidamente. Clientes locais e híbridos podem se beneficiar com a implantação do futuro **Skype for Business com** o modo de colaboração do teams como ponto de partida, em vez de ilhas, e o progresso de lá para o modo **somente de equipe** quando a organização está pronta para adotar Acompanhar.

### <a name="skype-for-business-only"></a>Somente Skype for Business

Nesse modo de coexistência, os usuários permanecem no Skype for Business, não nas equipes, para recursos de chat, reunião e chamadas, e não usam equipes para equipes e canais. Este modo está disponível hoje; no entanto, na implementação atual, as modalidades do Teams não são desativadas para o usuário automaticamente. Esta funcionalidade é próxima. No ínterim, os administradores podem remover a licença do teams para todos os usuários que precisam permanecer no Skype for Business como seu único aplicativo de comunicação.

### <a name="teams-only"></a>Somente equipes

Um usuário **somente** do teams pode usar o cliente Skype for Business para ingressar em reuniões existentes do Skype for Business ou reuniões no Skype for Business que foram organizadas por usuários não atualizados ou participantes externos. Um usuário atualizado pode continuar a se comunicar com outros usuários da organização que ainda estão usando o Skype for Business usando os recursos de interoperabilidade entre o Teams e o Skype for Business; no entanto, um usuário atualizado não pode iniciar um chat, chamada ou reunião do Skype for Business.

Assim que a sua organização estiver pronta para alguns ou todos os usuários usarem o Microsoft Teams como a única ferramenta de comunicação e colaboração, você poderá atualizar esses usuários para o modo **somente Teams** .

Para saber mais sobre como migrar para o modo somente equipes, consulte [Considerações sobre o modo](teams-only-mode-considerations.md)Microsoft Teams.

![Cliente do Skype for Business executado em um modo especial após o usuário ser atualizado como usuário do Microsoft Teams-only] (media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Cliente do Skype for Business executado em um modo especial após o usuário ser atualizado como usuário do Microsoft Teams-only")

### <a name="skype-for-business-with-teams-collaboration-this-mode-is-upcoming"></a>Skype for Business com colaboração do Teams (esse modo é próximo)

Use esse modo para apresentar as equipes do seu ambiente enquanto você continua a aproveitar o investimento existente no Skype for Business. Nesse modo, você deixa o Skype for Business inalterado com recursos de chat, chamada e reunião e adiciona recursos de colaboração de equipes — equipes e canais, acesso a arquivos no Office 365 e aplicativos. Organizações com ponto de partida do Skype for Business Server no local ou híbrido devem usar este modo em vez do modo de ilhas.

### <a name="skype-for-business-with-teams-collaboration-and-meetings-this-mode-is-upcoming"></a>Skype for Business com colaboração e reuniões do Teams (esse modo é próximo)

Use este modo de coexistência para acelerar a disponibilidade de recursos de reunião do teams em sua organização, além de seus recursos de colaboração, permitindo que os usuários aproveitem os novos recursos de qualidade, novos recursos como transcrição e Tradução e suporte para reuniões em navegadores.

Juntamente com o uso do teams para equipes e canais – conversas com base nesse modo, os usuários começam a usar o Microsoft Teams para agendar e conduzir suas reuniões. Chats privados, chamadas de voz e com vídeo, permanecem no Skype for Business. Esse modo de coexistência é especialmente útil para usuários nas implantações locais do Skype for Business que têm Enterprise Voice, que provavelmente levará algum tempo para serem atualizados para o Microsoft Teams, mas deseja se beneficiar das reuniões de equipes superiores.

> [!Note]
> Quando implantados em modos de coexistência específicos, o Teams [](#interoperability-of-teams-and-skype-for-business)e o Skype for Business podem interoperar, permitindo que os usuários conversem e liguem um ao outro e garantindo que as comunicações permaneçam fluindo para toda a sua organização durante a viagem de atualização para o Teams. Os modos de coexistência regem a interoperabilidade. O modo de coexistência do receptor determina se a interoperabilidade estará disponível. Por exemplo, se o destinatário estiver em um modo no qual o chat está disponível apenas em um cliente (digamos, equipes), a interoperabilidade de chat geralmente estará disponível para o caso de o iniciador usar o outro cliente (neste caso, o Skype for Business) para iniciar o chat. Por outro lado, se o receptor estiver em um modo no qual o chat está disponível nos dois clientes, a interoperabilidade não estará disponível para o chat, e a mensagem será recebida pelo receptor no mesmo cliente em que o iniciador iniciou o chat.

Para obter mais detalhes sobre modos de coexistência, pré-requisitos e gerenciamento, consulte [orientação de migração e interoperabilidade para organizações que usam o Skype for Business](https://aka.ms/SkypeToTeams-Interop) e [como configurar sua coexistência e configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence).

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Ponto de decisão|<ul><li>Quais são os modos de coexistência mais adequados para as necessidades da sua organização e dos usuários?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Próxima etapa|<ul><li>Escolha a melhor abordagem para a sua jornada de atualização.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilidade do Teams e do Skype for Business

Interoperabilidade é a capacidade para os usuários do Teams e do Skype for Business na mesma organização se comunicarem entre o Teams e o Skype for Business.

### <a name="native-interop-and-interop-escalation"></a>Escalonamento nativo e escalonamento de interoperabilidade

Há dois tipos de experiências de interoperabilidade: escalonamento nativo e interoperabilidade.

- Uma experiência de interoperabilidade _nativa_ ocorre no cliente que o usuário está usando no momento. Um usuário estará no cliente Skype for Business, o outro no Teams. Uma experiência de interoperabilidade nativa não vai levá-la para outro cliente para se comunicar, os usuários poderão conduzir a conversa no cliente que estiverem usando no momento. As experiências de interoperabilidade nativa são chat e chamadas de um-para-um.
- Uma experiência de _escalonamento_ de interoperabilidade significa que, como parte de ajudar os usuários a executar uma ação avançada (como compartilhar sua área de trabalho), o serviço pode facilitar a criação de uma reunião e continuar a experiência nessa reunião. A reunião é criada na plataforma do iniciador da ação. O usuário ou os usuários que não estão nessa plataforma recebem coordenadas de junção de reunião e entram na reunião (após a troca de clientes).

### <a name="native-interop-experiences"></a>Experiências de interoperabilidade nativa

Dependendo dos modos de coexistência atribuídos aos usuários (conforme descrito acima), as seguintes experiências de interoperabilidade nativa estão disponíveis:

- Os usuários do Skype for Business podem conversar com usuários do Microsoft Teams e vice-versa. Um chat de interoperabilidade precisa passar por um gateway de interoperabilidade que faz parte dos serviços de nuvem do Teams (e, portanto, só existe online). Chats de interoperabilidade são texto sem formatação: não há suporte para Rich Text e emoticons. Os usuários do teams são notificados de que a conversa é uma conversa de interoperabilidade; uma notificação semelhante para os usuários do Skype for Business será fornecida em breve.

![Experiência de chat de interoperabilidade do teams] (media/Interop_chat_experience_from_Teams.png "Experiência de chat de interoperabilidade do teams")

- Os usuários do Skype for Business podem fazer chamadas com voz e com vídeo individuais para usuários do Teams e vice-versa.

![Experiência de chamadas interoperabilidade do teams] (media/Interop_calling_experience_from_Teams.png "Experiência de chamadas interoperabilidade do teams")

> [!Important]
> As experiências de interoperabilidade com uma implantação local do Skype for Business exigem que o ambiente local esteja no modo híbrido com o Office 365 Skype for Business. Para obter detalhes, consulte [orientação de migração e](https://aka.ms/SkypeToTeams-Interop)interoperabilidade.

Essas experiências de interoperabilidade estão disponíveis para e entre os usuários que têm um dos seguintes modos de coexistência atribuídos: **Skype for Business com colaboração**do Teams, **Skype for Business com colaboração e reuniões**do Teams, **Skype para Somente para empresas**ou **equipes**. Não há interoperabilidade para os usuários no modo de ilhas.

### <a name="native-interop-experience-limitations"></a>Limitações da experiência de interoperabilidade nativa

Alguns recursos não estão disponíveis para o chat de interoperabilidade e a experiência de chamadas interoperabilidade entre o Teams e o Skype for Business:

- A redução, o Rich Text e o conjunto de emoticons completos não têm suporte do teams ou do Skype for Business. Outros recursos nativos da caixa de texto nos chats de equipe não têm suporte.
- Não há suporte para compartilhamento de tela (área de trabalho ou compartilhamento de aplicativos) entre o Microsoft Teams e o Skype for Business.
- Chats em grupo (conversas com vários participantes) no Teams só podem incluir participantes que estejam usando o Teams.
- Conversas de mensagens instantâneas de vários participantes (chats em grupo) no Skype for Business podem incluir somente participantes que estão usando o Skype for Business.
- Não há suporte para a expansão contínua de uma chamada de voz ou com vídeo em andamento para uma chamada de vários participantes que envolve o Microsoft Teams e os usuários do Skype for Business.
- A transferência de arquivos para chats de duas partes, ou anexo de arquivo em chats em grupo, do teams para o Skype for Business, e vice-versa, não são compatíveis.
- Não há interoperabilidade com o chat persistente do Skype for Business.

Para todas essas limitações (exceto para o chat persistente), uma possível solução é que um usuário inicie uma reunião e convide o outro usuário para ingressar nela. Essa solução alternativa é a base para o escalonamento de interoperabilidade.

> [!Important]
> O que começa como um chat simples (IM) pode ser rapidamente encaminhado para uma chamada ou para uma reunião ad hoc. Entendemos que esses cenários são essenciais para a usabilidade e a experiência do usuário, e estamos constantemente desenvolvendo experiências de interoperabilidade entre o Skype for Business e os usuários do teams. Verifique as informações mais atualizadas.

Depois de revisar este artigo, consulte [escolher a sua viagem de atualização, a](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) [orientação de migração e](https://aka.ms/SkypeToTeams-Interop)interoperabilidade, [a coexistência com o Skype for Business](coexistence-chat-calls-presence.md)e [a configuração de suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence) para implementação os.

## <a name="related-links"></a>Links relacionados

[Vídeo: gerenciar a coexistência e interoperabilidade entre o SfB e o Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
