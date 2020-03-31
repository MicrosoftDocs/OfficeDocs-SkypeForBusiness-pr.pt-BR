---
title: Gerenciar políticas de mensagens no Teams
ms.author: lolaj
author: lolajacobsen
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
description: Saiba mais sobre as políticas de mensagens e como elas podem ser usadas para controlar as mensagens de chat no Teams.
ms.openlocfilehash: 476fd2cf77b7ec57a0279d71b614dc50395b3023
ms.sourcegitcommit: 62969bd1c3a74412aa692709d497b8c6c5992c5c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2020
ms.locfileid: "43059405"
---
# <a name="manage-messaging-policies-in-teams"></a>Gerenciar políticas de mensagens no Teams

<!--- Add zone marker here--->

As políticas de mensagens são usadas para controlar quais recursos de mensagens de chat e canal estão disponíveis para usuários no Microsoft Teams. Você pode usar a política padrão que é criada automaticamente ou criar uma ou mais políticas de mensagens personalizadas para pessoas em sua organização. Depois de criar uma política, você pode atribuí-la a um usuário ou grupo de usuários da organização.

Por padrão, uma política denominada Global (padrão toda a organização) é criada. Por padrão, todos os usuários da organização recebem a atribuição dessa política de mensagens. Você pode fazer alterações nessa política ou criar uma ou mais políticas personalizadas e atribuir usuários a elas. Quando cria uma política personalizada, você pode permitir ou impedir que certos recursos fiquem disponíveis para seus usuários e atribuí-la a um ou mais usuários que precisarão que essas configurações sejam aplicadas a eles. 

## <a name="change-or-create-a-messaging-policy"></a>Alterar ou criar uma política de mensagens

Você pode gerenciar facilmente as políticas de mensagens no centro de administração do Microsoft Teams (https://admin.teams.microsoft.com) entrando com credenciais de administrador e escolhendo **Políticas de mensagens** no painel de navegação esquerdo. Para editar a política de mensagens padrão existente para sua organização, escolha a linha **Global (padrão em toda a organização)** e faça as alterações. Para criar uma nova política de mensagens personalizada, escolha **Nova política**, dê um nome à nova política e escolha as configurações. Escolha **Salvar** quando terminar.

Por exemplo, digamos que você queira garantir que as mensagens enviadas não sejam excluídas ou alteradas. Você criaria uma nova política personalizada chamada "Reter mensagens enviadas" e desativaria as seguintes configurações:

- Os proprietários podem excluir as mensagens enviadas
- Os usuários podem excluir as mensagens enviadas
- Os usuários podem editar as mensagens enviadas

Em seguida, atribua a política aos usuários.

> [!NOTE] 
> Um usuário só pode ter uma política de mensagem atribuída por vez.
 
## <a name="assign-a-messaging-policy-to-a-user"></a>Atribuir uma política mensagens a um usuário

Se você criar uma política de mensagens personalizada, ela só estará ativa para um usuário se a política estiver atribuída a ele. Para atribuir uma política personalizada a um usuário, vá para o centro de administração do Microsoft Teams, escolha **Usuários** no painel de navegação à esquerda e escolha o usuário ao qual você deseja atribuir a política. Na página do usuário, escolha **Editar** ao lado de **Políticas atribuídas**. Em seguida, no painel **Editar políticas de usuário**, em **Política de mensagens**, escolha a política de mensagens na lista suspensa e marque **Salvar**. Você também pode editar as configurações na lista de usuários. Para fazer isso, escolha o usuário clicando à esquerda do nome de exibição do usuário. Escolha **Editar configurações**. Em seguida, no painel **Editar configurações**, em **Política de mensagens**, escolha a política na lista suspensa e marque **Salvar**.

Se você estiver aplicando uma política a mais de um usuário, escolha cada um deles clicando à esquerda do nome do usuário e, em seguida, escolha **Editar configurações**. No painel **Editar configurações**, em **Política de mensagens**, escolha a política na lista suspensa e marque **Salvar**.

Você também pode atribuir uma política de mensagens a um ou mais usuários da seguinte maneira:

1. Vá para **Centro de administração do Microsoft Teams** > **Políticas de mensagens**.
2. Escolha a política clicando à esquerda do nome da política.
3. Escolha **Gerenciar usuários**.
4. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar os usuários, escolha **Salvar**.

> [!NOTE]
> Você não pode excluir uma política se usuários estiverem atribuídos a ela. Primeiro, você deve atribuir uma política diferente a todos os usuários afetados. em seguida, é possível excluir a política original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configurações da política de mensagens

Use as configurações a seguir para alterar a política de mensagens globais ou criar uma nova política personalizada:

- **Os proprietários podem excluir as mensagens enviadas**  Use essa configuração para permitir que os proprietários excluam mensagens que os usuários enviaram por chat.
- **Os usuários podem excluir as mensagens enviadas** Use essa configuração para permitir que os usuários excluam mensagens que eles enviaram por chat.
- **Os usuários podem editar as mensagens enviadas** Use essa configuração para permitir que os usuários editem mensagens que eles enviaram por chat.
- **Confirmações de leitura** Os recibos de leitura permitem que o remetente de uma mensagem de chat seja notificado quando a mensagem foi lida pelo destinatário em chats individuais e em grupo de 20 pessoas ou menos. Os recibos de leitura de mensagens realizam a remoção sem ter a certeza se uma mensagem foi lida e melhoram a comunicação da equipe. Observe que as confirmações de leitura não são capturadas nos relatórios de descoberta eletrônica.  
    - **Controlado pelo usuário** Isso significa que os usuários decidem se desejam ATIVAR ou DESATIVAR os recibos de leitura. A configuração padrão dentro do aplicativo está ATIVA. Os usuários podem DESATIVÁ-LA. 
    - **Ativado para todos** Isso significa que todos os locatários terão o recurso ATIVADO, sem opção para desativá-lo. Lembre-se de que, ao usar a configuração **Ativado para todos**, a única maneira de definir recibos para todos os locatários é ter apenas uma política de mensagens para todos os locatários (a política padrão denominada "Global - para toda a organização padrão") ou fazer com que todas as políticas de mensagens no locatário usem as mesmas configurações para recibos. O recurso de confirmações de leitura é mais eficaz quando o recurso está habilitado como **Ativado para todos**.
    - **Desativado para todos** Isso significa que o recurso está desabilitado e ninguém no locatário tem confirmações de leitura, nem pode habilitá-lo. 
<a name="bkchat"> </a>

- **Chat**  Habilite essa configuração se quiser que os usuários da organização possam usar o aplicativo do Teams para conversar com outras pessoas.
- **Usar Giphys em conversas**  Se você habilitar essa opção, os usuários poderão incluir Giphys em conversas de chat com outras pessoas. O Giphy é um mecanismo de pesquisa e banco de dados online que permite aos usuários pesquisar e compartilhar arquivos GIF animados. Cada Giphy recebe uma classificação de conteúdo.
- **Classificação de conteúdo Giphy** 
    - **Sem restrições** Isso significa que os usuários poderão inserir qualquer Giphy em chats independentemente da classificação de conteúdo.
    - **Moderado**  Isso significa que seus usuários poderão inserir Giphys em chats, mas o conteúdo adulto será moderadamente restringido.
    - **Estrito**  Isso significa que seus usuários poderão inserir Giphys em chats, mas o conteúdo adulto será estritamente restringido.
- **Usar memes em conversas** Se você habilitar essa opção, os usuários poderão incluir Memes em conversas de chat com outras pessoas. 
- **Usar Figurinhas em conversas** Se você habilitar essa opção, os usuários poderão incluir Figurinhas em conversas de chat com outras pessoas.
- **Permitir visualizações de URLs** Use essa configuração para ativar ou desativar a visualização automática de URLs nas mensagens.
- **Permitir que os usuários traduzam mensagens** Ative essa configuração para permitir que os usuários traduzam automaticamente as mensagens do Teams para o idioma especificado pelas configurações de idioma pessoal do Office 365.
- **Permitir leitura avançada na exibição de mensagens** Ative essa configuração para permitir que os usuários exibam mensagens na Leitura Avançada da Microsoft. A Leitura Avançada é uma ferramenta de aprendizagem que fornece uma experiência de leitura em tela inteira para aumentar a legibilidade do texto.
- **Enviar mensagens urgentes usando as notificações de prioridade** Se você ativar isso, os usuários poderão enviar uma mensagem que usa notificações de prioridade. As notificações de prioridade notificam os usuários a cada dois minutos por um período de 20 minutos ou até que as mensagens sejam captadas e lidas pelo destinatário maximizando a probabilidade de que a mensagem seja captada e atendida em tempo hábil.   [!INCLUDE [pri-message-offer](includes/pri-message-offer.md)]
- **Criação de mensagens de áudio** 
  > [!Important]
  > Mensagens de áudio não são capturadas em relatórios de descoberta eletrônica. 
    - **Permitido em chats e canais** Isso significa que os usuários podem deixar mensagens de áudio nos chats e nos canais.
    - **Permitido em apenas chats** Isso significa que os usuários podem deixar mensagens de áudio nos chats, mas nos canais.
    - **Desabilitado** Isso significa que os usuários não podem criar mensagens de áudio em chats ou canais.  
- **Em dispositivos móveis, exibir canais favoritos acima dos chats recentes** Habilite essa configuração para mover canais favoritos para a parte superior da tela de um dispositivo móvel de modo que o usuário não precise rolar para encontrá-los. 
- **Permitir que um usuário remova usuários de um chat em grupo** Habilite essa configuração para permitir que um usuário remova outros usuários de um chat em grupo. Esse recurso permite que você continue um chat com um grupo menor de pessoas sem perder o histórico do chat.

> [!NOTE]
> Algumas dessas configurações, como o Giphys, também podem ser configuradas no nível da equipe pelos proprietários da equipe e no nível do canal privado pelos proprietários do canal privado.

### <a name="related-topics"></a>Tópicos relacionados
[Políticas de reunião no Teams](meeting-policies-in-teams.md)
