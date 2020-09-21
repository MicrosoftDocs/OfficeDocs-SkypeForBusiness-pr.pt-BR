---
title: Coexistência com o Microsoft Teams e o Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualização do Skype for Business para o Teams-coexistência
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c5993611a383ee9b7040dfa4b74dae1b392253f
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955958"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>Coexistência com o Microsoft Teams e o Skype for Business

Este artigo resume o comportamento que pode ser experiente ao executar o cliente do Microsoft Teams e do Skype for Business na mesma organização, independentemente do modo de exibição e do método de atualização usado:

- [Reuniões](#meetings)
- [Interoperabilidade](#interoperability)
- [Conversas de equipes – interoperabilidade versus threads nativos](#teams-conversations---interop-versus-native-threads)
- [Presença](#presence)
- [Federação](#federation)
- [Contatos](#contacts)



## <a name="meetings"></a>Reuniões

Seja qual for o seu modo, os usuários sempre podem ingressar em qualquer tipo de reunião ao qual sejam convidados, seja o Skype for Business ou Teams.  No entanto, os usuários devem ingressar na reunião com um cliente correspondente que corresponda ao tipo de reunião:

- Se a reunião for uma reunião do Teams, todos os participantes (sejam TeamsOnly, Ilhas ou usuários do Skype for Business) usarão o cliente do teams para ingressar na reunião. Se o Microsoft Teams não estiver instalado, o usuário será encaminhado à Web, durante a tentativa de ingressar em uma reunião.

- Se a reunião for uma reunião do Skype for Business, todos os participantes (sejam TeamsOnly, Ilhas ou usuários do Skype for Business) usarão o cliente Skype for Business para ingressar na reunião. Se o cliente Skype for Business não estiver instalado, o usuário será direcionado à Web para participar pelo aplicativo de reunião do Skype.

Ao organizar reuniões, o tipo de reunião que é agendado baseia-se no modo do organizador, como mostrado na tabela a seguir:

| Modo do organizador    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Todas as reuniões agendadas no Teams. O suplemento Skype for Business não está disponível no Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Todas as reuniões agendadas no Skype for Business. O suplemento de equipe não está disponível no Outlook. | 
| Ilhas | Por padrão, as reuniões podem ser agendadas no Skype for Business ou no Teams. Os dois suplementos estão disponíveis no Outlook. No entanto, você pode exigir que os usuários nas ilhas sempre agendem reuniões no Teams, atribuindo a elas uma instância de TeamsMeetingPolicy com PreferredMeetingProviderForIslandsMode = Teams.| 


## <a name="interoperability"></a>Interoperabilidade

O Teams é compatível com a interoperabilidade ("interoperabilidade") com o Skype for Business em determinados cenários. A comunicação por interoperabilidade se refere a um chat ou uma chamada entre um usuário do Skype for Business e um usuário do teams.  A comunicação de interoperabilidade só é possível entre dois usuários; Não há suporte para chats/chamadas de vários participantes ou para adicionar outros usuários.

Um chat ou chamada interoperabilidade entre dois usuários é criado quando cada uma das seguintes opções é verdadeira:

- Um usuário está usando o Microsoft Teams e o outro está usando o Skype for Business.

- O modo do destinatário da comunicação inicial não é as ilhas (caso contrário, a comunicação se esterraria no mesmo cliente) se ambos os usuários estiverem na mesma organização. Em cenários federados, o usuário de envio está usando o Teams e o destinatário não está no modo TeamsOnly. 

- O usuário do teams também não tem uma conta do Skype for Business hospedada no local. 

Na comunicação de interoperabilidade, o chat somente é de texto sem formatação. Além disso, o compartilhamento de arquivos e o compartilhamento de tela não são possíveis *no chat de interoperabilidade*. No entanto, os usuários em uma conversa de interoperabilidade podem facilmente alcançar compartilhamento de arquivos e/ou telas criando uma reunião sob demanda, a partir do chat de interoperabilidade, conforme descrito abaixo:

- Se o usuário do teams tentar compartilhar a tela, uma reunião de equipes sob demanda será criada automaticamente e um link de convite para essa reunião será enviado ao cliente do usuário do Skype for Business. Ao clicar no link, o usuário do Skype for Business abrirá o Teams e ingressará na reunião. Os dois usuários estão agora em uma reunião do Teams e podem compartilhar conforme necessário.

- Se o usuário do Skype for Business estiver usando um cliente do 2018 ou posterior e tentar compartilhar qualquer conteúdo, uma reunião do Skype for Business por demanda será criada automaticamente e um link de convite para essa reunião será enviado ao cliente do usuário da equipe. Ao clicar no link, o usuário do teams tentará ingressar na reunião do Skype for Business. Se o usuário do teams tiver o cliente Skype for Business instalado, ele será aberto e o usuário será solicitado a entrar (se ainda não tiver entrado).  Se o usuário do Teams não tiver o cliente Skype for Business instalado, o usuário será solicitado a usar a versão da Web. Depois que os dois usuários estiverem conectados, eles estão em uma reunião do Skype for Business e podem compartilhar conforme necessário.

## <a name="teams-conversations---interop-versus-native-threads"></a>Conversas de equipes – interoperabilidade versus threads nativos

Como as comunicações de interoperabilidade não são compatíveis com todos os recursos da conversa de equipes nativas, o cliente das equipes mantém threads de conversa separados para comunicações entre equipes e equipes para Skype para empresas. Essas conversas são renderizadas de forma diferente na interface do usuário: os threads de interoperabilidade podem ser diferenciados de um thread regular de equipes nativas por:

- Falta de controles para Rich Text, compartilhamento de arquivo/tela, incapacidade de adicionar usuários.
- Uma modificação no ícone do usuário de destino, mostrando um "S" para o Skype for Business.

Essas diferenças são mostradas nas seguintes capturas de tela:

Uma conversa entre equipes nativas com o teste G3 do usuário

![Diagrama mostrando uma conversa de equipes nativas para equipes](media/teams-upgrade-native-thread.png)

Uma conversa de interoperabilidade com o mesmo teste G3 do usuário

![Diagrama mostrando uma conversa entre equipes de interoperabilidade para equipes](media/teams-upgrade-interop-thread.png)

Após a criação de um thread de conversa, o tipo nunca muda. Uma vez criado, um thread de interoperabilidade no Teams sempre direcionará para o cliente Skype for Business do usuário de destino. Um thread nativo sempre direcionará para o cliente das equipes do usuário de destino.  Se o modo de um usuário do destinatário for alterado, os threads existentes do usuário não funcionarão mais e uma nota será exibida nesse chat com um link para iniciar uma nova conversa nativa, como mostra a captura de tela a seguir.


![Diagrama mostrando um chat com usuário atualizado do Skype for Business](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>Presença

A presença de um determinado usuário baseia-se na atividade do usuário no serviço por meio do cliente. A presença é publicada para que outros usuários vejam.  O Skype for Business e o Teams são serviços separados com clientes separados, portanto, cada serviço tem seu próprio estado de presença para um usuário.   Também há sincronização entre os serviços de presença no Teams e no Skype for Business online.  Isso permite que um serviço publique a presença do usuário a partir do outro serviço, se necessário. 

O comportamento de publicação de presença é baseado no modo do usuário. Há três casos básicos:

- Se um usuário estiver no modo TeamsOnly, todos os outros usuários verão a presença do teams para esse usuário, independentemente do cliente usado.

- Se um usuário estiver em qualquer um dos modos do Skype for Business, todos os outros usuários verão a presença do Skype for Business para esse usuário, independentemente do cliente usado.

- Se um usuário estiver no modo de ilhas, a presença publicada no Skype for Business e nas equipes será independente, portanto, a presença mostrada para os usuários dentro da mesma organização dependerá do cliente do outro usuário. Os usuários de organizações federadas verão a presença desse usuário com base em suas atividades do Skype for Business, pois o tráfego federado para um usuário do modo de ilhas de ilhas chega no Skype for Business.

Por exemplo, suponha que o usuário A esteja no modo de ilhas. Se o usuário A estiver ativo no Teams, mas não estiver conectado ao Skype for Business, outros usuários veriam o usuário A como ativo do cliente de suas equipes, mas no cliente do Skype for Business, eles verão o usuário A como offline. Isso ocorre por design, pois o usuário A não pode ser acessado se não estiver executando o cliente. 


## <a name="federation"></a>Federação

A Federação do teams para outro usuário usando o Skype for Business exige que o usuário do teams seja hospedado online no Skype for Business. TeamsUpgradePolicy determina o roteamento para chamadas e conversas federadas e de entrada. O comportamento de roteamento federado é o mesmo para cenários de mesmo locatário, exceto no modo de Ilhas. Quando os destinatários estiverem no modo de Ilhas:

- Chats e chamadas iniciadas do teams Land no Skype for Business se o destinatário estiver em um locatário federado.
- Chats e chamadas iniciados a partir do Teams são recebidos no Teams se o destinatário estiver no mesmo locatário.
- Chats e chamadas iniciados pelo Skype for Business sempre se esterram no Skype for Business.

Um chat federado pode ser um thread nativo ou um thread de interoperabilidade. Consulte [conversas de equipe---interoperabilidade-versus-threads-nativo](#teams-conversations---interop-versus-native-threads).

- Se o receptor e o remetente estiverem no modo de atualização do TeamsOnly, a conversa será uma experiência de chat nativa que inclui todos os recursos avançados de mensagens e chamadas. Para saber mais, leia [experiência de chat nativo para usuários externos (federados) no Teams](native-chat-for-external-users.md). 

- Se algum dos participantes da conversa não estiver no modo de atualização do TeamsOnly, a conversa permanecerá interoperabilidade com mensagens somente texto. A interface do usuário expõe chats federados de maneira semelhante aos mesmos threads de interoperabilidade do locatário, exceto que há uma observação indicando que o usuário é externo.

Para obter mais detalhes, consulte [gerenciar o acesso externo no Microsoft Teams](manage-external-access.md) e [a experiência de chat nativo para usuários externos (federados) no Teams](native-chat-for-external-users.md).

## <a name="contacts"></a>Contatos

O Teams e o Skype for Business têm listas separadas de contatos. Isso significa que adições de contato, remoção e modificações feitas em um sistema não são sincronizadas com o outro sistema. No entanto, os contatos do Skype for Business são copiados automaticamente para o Microsoft Teams quando ocorrem dois eventos específicos: 

- Para qualquer usuário do Skype for Business Online, na primeira vez que fizer logon no Microsoft Teams, os contatos do Skype for Business serão copiados para o Microsoft Teams.  Esse comportamento não está disponível para usuários com uma conta local no Skype for Business Server.  

- Depois que um usuário for atualizado para o TeamsOnly (por meio da atribuição de TeamsUpgradePolicy ou via move-CsUser-MoveToTeams), da próxima vez que um usuário fizer logon no Microsoft Teams, os contatos existentes no Skype for Business serão mesclados com contatos existentes já presentes no Microsoft Teams. Esse comportamento ocorre se a conta do Skype for Business do usuário for hospedada no local ou online. 

Em ambos os casos, a transferência de contatos do Skype for Business para o Microsoft Teams é assíncrona, por isso pode ser um número de minutos para que os contatos sejam exibidos no Microsoft Teams. Os dois eventos acima são o que aciona a cópia.  

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

