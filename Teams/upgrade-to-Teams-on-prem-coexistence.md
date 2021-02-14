---
title: Coexistência com o Microsoft Teams e o Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualizar do Skype for Business para o Teams - Coexistência
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0690af8226f3f992dcc12f68c6135c953eb043f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533608"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>Coexistência com o Teams e o Skype for Business

Este artigo resume o comportamento que pode ser experimentado ao executar clientes do Teams e do Skype for Business na mesma organização, independentemente do modo e do método de atualização usado:

- [Reuniões](#meetings)
- [Interoperabilidade](#interoperability)
- [Conversas do Teams -Interop versus threads nativos](#teams-conversations---interop-versus-native-threads)
- [Presença](#presence)
- [Federação](#federation)
- [Contatos](#contacts)



## <a name="meetings"></a>Reuniões

Independentemente do modo, os usuários sempre podem ingressar em qualquer tipo de reunião para o qual são convidados, seja o Skype for Business ou o Teams.  No entanto, os usuários devem ingressar na reunião com um cliente correspondente que corresponda ao tipo de reunião:

- Se a reunião for uma reunião do Teams, todos os participantes (sejam usuários do TeamsOnly, Islands ou Skype for Business) usam o cliente do Teams para ingressar na reunião. Se o Teams não estiver instalado, o usuário será direcionado para a Web ao tentar ingressar em uma reunião.

- Se a reunião for uma reunião do Skype for Business, todos os participantes (sejam usuários do TeamsOnly, Islands ou Skype for Business) usam o cliente Skype for Business para ingressar na reunião. Se o cliente Skype for Business não estiver instalado, o usuário será direcionado para a Web para ingressar por meio do aplicativo reunião do Skype.

Ao organizar reuniões, o tipo de reunião que é agendado se baseia no modo do organizador, conforme mostrado na tabela a seguir:

| Modo de organizador    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Todas as reuniões agendadas no Teams. O complemento Skype for Business não está disponível no Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Todas as reuniões agendadas no Skype for Business. O add-in do Teams não está disponível no Outlook. | 
| Ilhas | Por padrão, as reuniões podem ser agendadas no Skype for Business ou no Teams. Ambos os complementos estão disponíveis no Outlook. No entanto, opcionalmente, você pode exigir que os usuários em Ilhas sempre agendem reuniões no Teams atribuindo a eles uma instância do TeamsMeetingPolicy com o PreferredMeetingProviderForIslandsMode=Teams.| 


## <a name="interoperability"></a>Interoperabilidade

O Teams dá suporte à interoperabilidade ("interop") com o Skype for Business em determinados cenários. A comunicação interop refere-se a um chat ou chamada entre um usuário do Skype for Business e um usuário do Teams.  A comunicação interop só é possível entre dois usuários; Não há suporte para chat/chamada de vários usuários ou adição de usuários adicionais.

Um chat interop ou chamada entre dois usuários é criado quando cada um dos seguintes é verdadeiro:

- Um usuário está usando o Teams e o outro está usando o Skype for Business.

- O modo do destinatário da comunicação inicial não é Ilhas (caso contrário, a comunicação entraria no mesmo cliente) se ambos os usuários estão na mesma organização. Em cenários federados, o usuário de envio está usando o Teams e o destinatário não está no modo TeamsOnly. 

- O usuário do Teams NÃO tem também uma conta do Skype for Business no local. 

Dentro da comunicação interop, o chat é somente texto sem texto. Além disso, o compartilhamento de arquivos e o compartilhamento de tela não são possíveis *no chat interop propriamente dito.* No entanto, os usuários em uma conversa interop podem facilmente obter arquivos e/ou compartilhamento de tela criando uma reunião sob demanda, a partir do chat interop, conforme descrito abaixo:

- Se o usuário do Teams tentar compartilhar sua tela, uma reunião do Teams sob demanda será criada automaticamente e um link de convite para essa reunião será enviado para o cliente do usuário do Skype for Business. Ao clicar no link, o usuário do Skype for Business abrirá o Teams e ingressará na reunião. Os dois usuários agora estão em uma reunião do Teams e podem compartilhar conforme necessário.

- Se o usuário do Skype for Business estiver usando um cliente de 2018 ou posterior e tentar compartilhar qualquer conteúdo, uma reunião sob demanda do Skype for Business será criada automaticamente e um link de convite para essa reunião será enviado para o cliente do usuário do Teams. Ao clicar no link, o usuário do Teams tentará ingressar na reunião do Skype for Business. Se o usuário do Teams tiver o cliente Skype for Business instalado, ele será aberto e o usuário será solicitado a entrar (se ainda não tiver feito logo in).  Se o usuário do Teams não tiver o cliente Skype for Business instalado, o usuário será solicitado a usar a versão da Web. Depois que os dois usuários estão dentro, eles estão em uma reunião do Skype for Business e podem compartilhar conforme necessário.

## <a name="teams-conversations---interop-versus-native-threads"></a>Conversas do Teams - Interop versus threads nativos

Como as comunicações interop não são suportadas por todos os recursos de conversas nativas do Teams, o cliente do Teams mantém threads de conversa separados para as comunicações do Teams para o Teams e do Teams para o Skype for Business. Essas conversas são renderizadas de forma diferente na interface do usuário: threads interop podem ser diferenciados de um thread nativo regular do Teams por:

- Falta de controles para rich text, compartilhamento de arquivo/tela, incapacidade de adicionar usuários.
- Uma modificação no ícone do usuário de destino, mostrando um "S" para o Skype for Business.

Essas diferenças são mostradas nas seguintes capturas de tela:

Uma conversa nativa do Teams para Teams com o Teste do Usuário G3

![Diagrama mostrando uma conversa nativa do Teams para o Teams](media/teams-upgrade-native-thread.png)

Uma conversa interop com o mesmo Teste de Usuário G3

![Diagrama mostrando uma conversa interop do Teams para o Teams](media/teams-upgrade-interop-thread.png)

Depois que um thread de conversa é criado, seu tipo nunca muda. Depois de criado, um thread interop no Teams sempre será roteada para o cliente Skype for Business do usuário de destino. Um thread nativo sempre será roteada para o cliente do Teams do usuário de destino.  Se o modo do usuário do destinatário mudar, os threads existentes do Teams para esse usuário não funcionarão mais e uma anotação será exibida nesse chat com um link para iniciar uma nova conversa nativa, conforme mostrado na captura de tela a seguir.


![Diagrama mostrando um chat com usuário atualizado do Skype for Business](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>Presença

A presença de um determinado usuário se baseia na atividade do usuário no serviço por meio do cliente. A presença é publicada para que outros usuários vejam.  O Skype for Business e o Teams são serviços separados com clientes separados, portanto, cada serviço tem seu próprio estado de presença para um usuário.   Também há sincronização entre os serviços de presença no Teams e no Skype for Business Online.  Isso permite que um serviço publique potencialmente a presença do usuário do outro serviço, se necessário. 

O comportamento de publicação de presença se baseia no modo do usuário. Há três casos básicos:

- Se um usuário estiver no modo TeamsOnly, todos os outros usuários verão a presença do Teams para esse usuário, independentemente de qual cliente usar.

- Se um usuário estiver em qualquer um dos modos do Skype for Business, todos os outros usuários verão a presença do Skype for Business para esse usuário, independentemente de qual cliente usar.

- Se um usuário estiver no modo Ilhas, a presença publicada no Skype for Business e no Teams será independente, portanto, a presença mostrada aos usuários dentro da mesma organização dependerá do cliente do outro usuário. Os usuários em organizações federadas verão a presença desse usuário com base em suas atividades do Skype for Business, uma vez que o tráfego federado para um usuário do modo Ilhas chega ao Skype for Business.

Por exemplo, suponha que o Usuário A está no modo Ilhas. Se o Usuário A estiver ativo no Teams, mas não estiver dentro do Skype for Business, outros usuários verão o Usuário A como ativo a partir de seu cliente do Teams, mas no cliente Skype for Business verão o Usuário A como offline. Isso acontece por design, pois o Usuário A não poderá ser atingido se ele não estiver executando o cliente. 


## <a name="federation"></a>Federação

A federação do Teams para outro usuário que usa o Skype for Business exige que o usuário do Teams seja instalado online no Skype for Business. TeamsUpgradePolicy determina o roteamento para chamadas e conversas federadas e de entrada. O comportamento de roteamento federado é o mesmo para cenários de mesmo locatário, exceto no modo de Ilhas. Quando os destinatários estiverem no modo de Ilhas:

- Chats e chamadas iniciadas a partir do Teams entrarão no Skype for Business se o destinatário estiver em um locatário federado.
- Chats e chamadas iniciados a partir do Teams são recebidos no Teams se o destinatário estiver no mesmo locatário.
- Chats e chamadas iniciadas a partir do Skype for Business sempre estão no Skype for Business.

Um chat federado pode ser um thread nativo ou um thread interop. Consulte [Conversas do Teams ---interop-versus-native-threads.](#teams-conversations---interop-versus-native-threads)

- Se o destinatário e o remetente estão no modo de atualização do TeamsOnly, a conversa será uma experiência de chat nativa que inclui todos os recursos avançados de mensagens e chamada. Para saber mais, leia [a experiência de chat nativo para usuários externos (federados) no Teams.](native-chat-for-external-users.md) 

- Se um dos participantes da conversa não estiver no modo de atualização do TeamsOnly, a conversa permanecerá uma experiência interop com mensagens somente de texto. A interface do usuário expõe os chats federados de maneira semelhante aos threads interop do mesmo locatário, exceto que há uma anotação indicando que o usuário é externo.

Para obter mais detalhes, consulte [Gerenciar o acesso externo no Microsoft Teams](manage-external-access.md) e experiência de chat nativo para usuários [externos (federados) no Teams.](native-chat-for-external-users.md)

## <a name="contacts"></a>Contatos

O Teams e o Skype for Business têm listas separadas de contatos. Isso significa que as adições, remoção e modificações de contatos feitas em um sistema não são sincronizadas com o outro sistema. No entanto, os contatos do Skype for Business são copiados automaticamente para o Teams quando ocorrem dois eventos específicos: 

- Para qualquer usuário do Skype for Business Online, na primeira vez que fizer logoff no Teams, os contatos do Skype for Business serão copiados para o Teams.  Esse comportamento não está disponível para usuários com uma conta local no Skype for Business Server.  

- Depois que um usuário for atualizado para o TeamsOnly (por meio da atribuição do TeamsUpgradePolicy ou via Move-CsUser -MoveToTeams), na próxima vez que um usuário entrar no Teams, os contatos existentes no Skype for Business serão mesclados com os contatos existentes que já estão no Teams. Esse comportamento acontece se a Conta do Skype for Business do usuário está no local ou online. 

Em ambos os casos, a transferência de contatos do Skype for Business para o Teams é assíncrona, portanto, pode levar alguns minutos para que os contatos sejam exibidos no Teams. Os dois eventos acima são o que desencadeia a cópia.  

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

