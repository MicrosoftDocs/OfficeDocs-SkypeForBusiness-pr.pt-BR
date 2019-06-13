---
title: Gerenciar políticas de mensagens no Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Saiba mais sobre as políticas de mensagens e como elas podem ser usadas para controlar as mensagens de chat no Microsoft Teams.
ms.openlocfilehash: dd636a0c8ab3b8acdad55e64e2460dcd87e38253
ms.sourcegitcommit: f5b6270e64752298687a1abff49da58acde8e107
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2019
ms.locfileid: "34912852"
---
# <a name="manage-messaging-policies-in-teams"></a>Gerenciar políticas de mensagens no Teams

<!--- Add zone marker here--->

As políticas de mensagens são usadas para controlar quais recursos de chat e mensagens de canal estão disponíveis para os usuários do Microsoft Teams. Você pode usar a política padrão criada automaticamente ou criar uma ou mais políticas de mensagens personalizadas para as pessoas em sua organização. Depois de criar uma política, você pode atribuí-la a um usuário ou grupo de usuários em sua organização.
Por padrão, uma política chamada global (padrão para toda a organização) é criada. Por padrão, todos os usuários de sua organização serão atribuídos a essa política de serviço. Você pode fazer alterações nessa política ou criar uma ou mais políticas personalizadas e atribuir usuários a elas. Quando você cria uma política personalizada, pode permitir ou impedir que determinados recursos sejam disponibilizados para seus usuários e, em seguida, atribuí-los a um ou mais usuários que precisarão das configurações aplicadas a eles. 

## <a name="change-or-create-a-messaging-policy"></a>Alterar ou criar uma política de mensagens

Você pode gerenciar facilmente as políticas de mensagens no centro de administração dohttp://admin.teams.microsoft.com) Microsoft Teams (entrando com credenciais de administrador e escolhendo **políticas de mensagens** no painel de navegação à esquerda. Para editar a política de mensagens padrão existente para sua organização, selecione a linha **global (padrão para toda** a organização) e faça as alterações. Para criar uma nova política de mensagens personalizada, selecione **nova política**, forneça um nome para a nova política e selecione as configurações. Escolha **salvar** quando terminar.

Por exemplo, digamos que você queira garantir que as mensagens enviadas não sejam excluídas ou alteradas. Você criaria uma nova política personalizada chamada "reter mensagens enviadas" e desativar as seguintes configurações:

- Os proprietários podem excluir mensagens enviadas
- Os usuários podem excluir mensagens enviadas
- Os usuários podem editar mensagens enviadas

Em seguida, atribua a política aos usuários.

> [!NOTE] 
> Um usuário só pode receber uma política de mensagens de cada vez.
 
## <a name="assign-a-messaging-policy-to-a-user"></a>Atribuir uma política de mensagens a um usuário

Se você criar uma política de mensagens personalizada, ela estará ativa somente para um usuário se a política for atribuída ao usuário. Para atribuir uma política personalizada a um usuário, vá para o centro de administração do Microsoft Teams, escolha **usuários** no painel de navegação à esquerda e selecione o usuário ao qual você deseja atribuir a política. Na página do usuário, escolha **Editar** ao lado de **políticas atribuídas**. Em seguida, no painel **Editar políticas do usuário** , em **política de mensagens**, selecione a política de mensagens na lista suspensa e selecione **salvar**. Você também pode editar as configurações da lista de usuários. Para fazer isso, selecione o usuário clicando à esquerda do nome para exibição do usuário. Selecione **Editar configurações**. Em seguida, no painel **Editar configurações** , em **política de mensagens**, selecione a política na lista suspensa e, em seguida, selecione **salvar**.

Se você estiver aplicando uma política a mais de um usuário, selecione cada um dos usuários clicando à esquerda do nome do usuário e selecione **Editar configurações**. No painel **Editar configurações** , em **política de mensagens**, selecione a política na lista suspensa e, em seguida, selecione **salvar**.

Você também pode atribuir uma política de mensagens a um ou mais usuários da seguinte maneira:

1. Vá para > **políticas de mensagens** **do centro de administração do Microsoft Teams**.
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **gerenciar usuários**.
4. No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e, em seguida, selecione **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar usuários, selecione **salvar**.

> [!NOTE]
> Você não pode excluir uma política se os usuários estiverem atribuídos a ela. Você deve primeiro atribuir uma política diferente para todos os usuários afetados e, em seguida, pode excluir a política original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configurações da política de mensagens

Use as configurações a seguir para alterar a política de mensagens globais ou criar uma nova política personalizada:

- Os **proprietários podem excluir mensagens enviadas**  Use esta configuração para permitir que os proprietários excluam mensagens que os usuários enviaram no chat.
- **Os usuários podem excluir mensagens enviadas** Use essa configuração para permitir que os usuários excluam mensagens enviadas por chat.
- **Os usuários podem editar mensagens enviadas** Use esta configuração para permitir que os usuários editem as mensagens que enviaram no chat.
- Confirmações de **leitura** Use esta configuração para especificar se as confirmações de leitura são controladas pelo usuário, ativadas para todos ou desativadas para todos. A configuração padrão é controlado pelo usuário. 
    - **Controlado pelo usuário** Isso significa que os usuários podem decidir se desejam ativar ou desativar as confirmações de leitura. A configuração padrão dentro do aplicativo está ATIVAda. Os usuários podem então desativá-lo.
    - **Ativado para todos** Isso significa que todos no locatário terão o recurso ativado sem opção para desativá-lo. 
    - **Desativado para todos** Isso significa que o recurso está desativado e ninguém no locatário tem recibos de leitura nem pode ativá-lo. 
<a name="bkchat"> </a>

- **Chat**  Ative essa configuração se quiser que os usuários em sua organização possam usar o aplicativo Teams para conversar com outras pessoas.
- **Usar o Giphys em conversas**  Se você ativar esta opção, os usuários poderão incluir o Giphys em conversas de chat com outras pessoas. O Giphy é um banco de dados online e um mecanismo de pesquisa que permite aos usuários procurar e compartilhar arquivos GIF animados. Cada Giphy é atribuído a uma classificação de conteúdo.
- **Classificação de conteúdo do Giphy** 
    - **Sem restrição** Isso significa que os usuários poderão inserir qualquer Giphy em chats, independentemente da classificação de conteúdo.
    - **Moderado**  Isso significa que os usuários poderão inserir Giphys em chats, mas serão moderadamente restritos ao conteúdo somente para adultos.
    - **Estrito**  Isso significa que os usuários poderão inserir Giphys em chats, mas serão estritamente restritos ao conteúdo somente para adultos.
- **Usar o memes em conversas** Se você ativar esta opção, os usuários poderão incluir o memes em conversas de chat com outras pessoas. 
- **Usar adesivos nas conversas** Se você ativar esta opção, os usuários poderão incluir adesivos em conversas de chat com outras pessoas.
- **Permitir visualizações de URL** Use essa configuração para ativar ou desativar a visualização automática de URL nas mensagens.
- **Permitir que os usuários traduzam mensagens** Ative essa configuração para permitir que os usuários traduzam mensagens de equipe automaticamente para o idioma especificado pelas configurações de idioma pessoal do Office 365.
- **Permitir leitura avançada para exibição de mensagens** Ative essa configuração para permitir que os usuários exibam mensagens na leitura avançada da Microsoft. Leitura avançada é uma ferramenta de aprendizagem que oferece uma experiência de leitura de tela inteira para aumentar a legibilidade do texto.
- **Os usuários podem enviar notificações de prioridade** Se você ativar isso, os usuários poderão enviar uma mensagem que usa notificações de prioridade. As notificações de prioridade notificam os usuários repetidamente por um período de 20 minutos ou até que as mensagens sejam retiradas e lidas pelo destinatário, maximizando a probabilidade de que a mensagem seja retirada e lidas em tempo hábil.   [!INCLUDE [pri-message-offer](includes/pri-message-offer.md)]
- **Criação de mensagem de voz** 
    - **Permitido em chats e canais** Isso significa que os usuários podem deixar mensagens de voz em chats e canais.
    - **Permitido somente em chats** Isso significa que os usuários podem deixar mensagens de voz em chats, mas não em canais.
    - **Desativado** Isso significa que os usuários não podem criar mensagens de voz em chats ou canais.  
- **Em dispositivos móveis, exiba os canais favoritos acima dos chats recentes** Habilite essa configuração para mover os canais favoritos para a parte superior da tela do dispositivo móvel para que um usuário não precise rolar para localizá-los. 
- **Permitir que um usuário remova usuários de um chat em grupo** Ative essa configuração para permitir que um usuário remova outros usuários de um chat em grupo. Esse recurso permite que você continue um chat com um grupo menor de pessoas sem perder o histórico de chats.

### <a name="related-topics"></a>Tópicos relacionados
[Políticas de reunião no Teams](meeting-policies-in-teams.md)
