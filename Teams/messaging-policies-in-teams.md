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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Saiba mais sobre as políticas de mensagens e como eles podem ser usados para controlar as equipes de mensagens de chat.
ms.openlocfilehash: f0dd52dac1bd2563a0ef5c500714ab63eeadf84d
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298449"
---
# <a name="manage-messaging-policies-in-teams"></a>Gerenciar políticas de mensagens no Teams

<!--- Add zone marker here--->

Políticas de mensagens são usadas para controlar quais recursos de mensagens de canal e de bate-papo estão disponíveis para usuários no Microsoft Teams. Você pode usar a política padrão que é criada automaticamente ou cria uma ou mais políticas de mensagens personalizadas para pessoas da sua organização. Depois de criar uma política, você pode atribuí-lo a um usuário ou grupo de usuários em sua organização.

Por padrão, uma política de chamada Global (toda a organização padrão) é criada. Todos os usuários em sua organização serão atribuídos essa política de mensagens por padrão. Você pode fazer alterações para esta política ou criar uma ou mais políticas personalizadas e atribuir usuários a eles. Quando você cria uma política personalizada, você pode permitir ou impedir que certos recursos disponíveis para os usuários e atribuí-la a um ou mais usuários que precisarem as configurações aplicadas a eles. 

## <a name="change-or-create-a-messaging-policy"></a>Alterar ou criar uma política de mensagens

Você pode gerenciar facilmente as políticas de mensagens no Centro de administração do Microsoft Teams (http://admin.teams.microsoft.com) por assinatura com credenciais de administrador e escolhendo **políticas de mensagens** no painel de navegação à esquerda. Para editar o padrão existente de mensagens de política para sua organização, selecione a linha **Global (padrão de toda a organização)** e faça suas alterações. Para criar uma nova política personalizada de mensagens, selecione **nova política**, nomeie a nova diretiva e selecione suas configurações. Escolha **Salvar** quando terminar.

Por exemplo, digamos que você deseja garantir que enviou mensagens não são excluídas ou alteradas. Crie uma nova política personalizada denominada "Reter mensagens enviada" e desativar as configurações a seguir:

- Os proprietários podem excluir as mensagens enviadas
- Os usuários podem excluir as mensagens enviadas
- Os usuários podem editar as mensagens enviadas

Em seguida, atribua a política aos usuários.

> [!NOTE] 
> Um usuário pode ser atribuído somente uma política de mensagens por vez.
 
## <a name="assign-a-messaging-policy-to-a-user"></a>Atribuir uma política de mensagens a um usuário

Se você criar uma política personalizada de mensagens, ele só será ativo para um usuário se a diretiva é atribuída ao usuário. Para atribuir uma política personalizada a um usuário, vá para o Centro de administração do Microsoft Teams, escolha **usuários** no painel de navegação à esquerda e selecione o usuário que você deseja atribuir a política. Na página do usuário, escolha **Editar** ao lado de **políticas atribuído**. Em seguida, no painel **Editar políticas de usuário** , em **política de mensagens**, selecione a política de mensagens na lista suspensa e selecione **Salvar**. Você também pode editar as configurações da lista de usuários. Para fazer isso, selecione o usuário clicando à esquerda do nome para exibição do usuário. Selecione **Editar configurações**. Em seguida, no painel **Editar configurações** , em **política de mensagens**, selecione a política na lista suspensa e selecione **Salvar**.

Se você estiver aplicando uma política para mais de um usuário, selecione cada um dos usuários clicando à esquerda do nome de usuário e selecione **Editar configurações**. No painel **Editar configurações** , em **política de mensagens**, selecione a política na lista suspensa e selecione **Salvar**.

Você também pode atribuir uma política de mensagens a um ou mais usuários da seguinte maneira:

1. Vá para **o Centro de administração do Microsoft equipes** > **políticas de mensagens**.
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **Gerenciar usuários**.
4. No painel de **Gerenciar usuários** , procure o usuário pelo nome de exibição ou nome de usuário, selecione o nome e selecione **Adicionar**. Repita essa etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar usuários, selecione **Salvar**.

> [!NOTE]
> Você não pode excluir uma política, se os usuários são atribuídos a ela. Você deve primeiro atribuir uma política diferente a todos os usuários afetados e, em seguida, você pode excluir a diretiva original.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Configurações de política de mensagens

Use as configurações a seguir para alterar a política global de mensagens ou criar uma nova política personalizada:

- **Os proprietários podem excluir as mensagens enviadas**  Use esta configuração para permitir que os proprietários excluir mensagens que os usuários enviada em bate-papo.
- **Os usuários podem excluir as mensagens enviadas** Use esta configuração para permitir que usuários excluir mensagens enviados por eles no bate-papo.
- **Os usuários podem editar as mensagens enviadas** Use esta configuração para permitir aos usuários editar as mensagens enviados por eles no bate-papo.
- **Confirmações de leitura** Use esta configuração para especificar se a notificação de leitura estão usuário controlados, habilitado para todas as pessoas ou desabilitado.
<a name="bkchat"> </a>

- **Bate-papo**  Ative esta configuração se quiser que os usuários em sua organização possam usar o aplicativo de equipes para conversar com outras pessoas.
- **Uso Giphys em conversas**  Se você ativar isso, os usuários podem incluir Giphys em conversas de bate-papo com outras pessoas. Giphy é um banco de dados online e o mecanismo de pesquisa que permite aos usuários pesquisar e compartilhar arquivos GIF animados. Cada Giphy é atribuída uma classificação de conteúdo.
- **Classificação de conteúdo Giphy** 
    - **Sem restrição** Isso significa que os usuários poderão inserir qualquer Giphy em bate-papos independentemente a classificação de conteúdo.
    - **Moderada**  Isso significa que os usuários serão capazes de inserir Giphys em bate-papos, mas serão restritos relativamente de conteúdo para adultos.
    - **Estrito**  Isso significa que os usuários serão capazes de inserir Giphys em bate-papos, mas serão restritos estritamente de conteúdo para adultos.
- **Uso Memes em conversas** Se você ativar isso, os usuários podem incluir Memes em conversas de bate-papo com outras pessoas. 
- **Adesivos de uso em conversas** Se você ativar isso, os usuários podem incluir adesivos em conversas de bate-papo com outras pessoas.
- **Visualizações de URL permitir** Use esta configuração para ativar automática URL pré-visualizar ativada ou desativada nas mensagens.
- **Permitir que os usuários para traduzir mensagens** Ative esta configuração para permitir que os usuários automaticamente traduzir mensagens de equipes para o idioma especificado por suas configurações de idioma pessoal para o Office 365.
- **Permitir imersivo leitor para a exibição de mensagens** Ative esta configuração para permitir que os usuários exibir mensagens no Microsoft Reader imersivo. Leitor imersivo é uma ferramenta de aprendizado que fornece uma experiência para aumentar a legibilidade do texto de leitura de tela inteira.
- **Os usuários podem enviar notificações de prioridade** Se você ativar isso, os usuários podem enviar uma mensagem que usa notificações de prioridade. Notificações de prioridade notificam os usuários repetidamente por um período de 20 minutos ou até que as mensagens são buscadas e lido pelo destinatário, maximizando a probabilidade de que a mensagem é buscada e tratada oportunamente.
- **Criação de mensagem de voz** 
    - **Permitidos em bate-papos e canais** Isso significa que os usuários podem deixar mensagens de voz em bate-papos e canais.
    - **Permitidos em bate-papos somente** Isso significa que os usuários podem deixar mensagens de voz em bate-papos, mas não no canais.
    - **Desabilitado** Isso significa que os usuários não podem criar mensagens de voz em bate-papos ou canais.  
- **Em dispositivos móveis, exibir canais favoritos acima chats recentes** Habilite essa configuração mover os canais favoritos na parte superior da tela do dispositivo móvel para que um usuário não precisa rolar para localizá-los. 
- **Permitir que um usuário para remover usuários de um bate-papo de grupo** Ative esta configuração para permitir que um usuário remova a outros usuários o chat de grupo. Esse recurso permite que você continuar um chat com um pequeno grupo de pessoas sem perder o histórico de chat.

### <a name="related-topics"></a>Tópicos relacionados
[Políticas de reunião em equipes](meeting-policies-in-teams.md)
