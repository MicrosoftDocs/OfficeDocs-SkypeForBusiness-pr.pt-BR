---
title: Gerenciar políticas de reunião
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 03/01/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Saiba como gerenciar as configurações de diretiva em equipes de reunião.
ms.openlocfilehash: f8f7e4bbf18fa96ebc8de3fd219945a06c05c0b3
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494081"
---
# <a name="manage-meeting-policies-in-teams"></a>Gerenciar políticas de reunião em equipes

::: zone target="docs"
Políticas de reunião são usadas para controlar os recursos disponíveis aos participantes para reuniões agendadas por usuários em sua organização da reunião. Depois de criar uma política e faça as alterações, você pode atribuir usa para a política. 

Por padrão, uma política de chamada Global (toda a organização padrão) é criada. Todos os usuários em sua organização serão atribuídos a política de reunião por padrão. Você pode fazer alterações para esta política ou criar uma ou mais políticas personalizadas e atribuir usuários a eles. Quando você cria uma política personalizada, você pode permitir ou impedir que certos recursos disponíveis para os usuários e atribuí-la a um ou mais usuários com as configurações aplicadas a eles. 

## <a name="change-or-create-a-meeting-policy"></a>Alterar ou criar uma política de reunião

Para alterar ou criar uma política de reunião, vá para **o Centro de administração do Microsoft equipes** > **reuniões** > **políticas de reunião**. Selecione uma política na lista ou selecione **nova política**. Escolher as configurações e selecione **Salvar**.

Por exemplo, digamos que você tem um monte de usuários e deseja limitar a quantidade de largura de banda que exigiria sua reunião. Crie uma nova política personalizada denominada "Largura de banda limitada" e desabilitar as configurações a seguir:

Em **áudio & vídeo**:
- Desative a nuvem de gravação
- Desativar vídeo IP permitidos

Em **compartilhamento de conteúdo**:
- Desabilitar o modo de compartilhamento de tela
- Desativar o quadro de comunicações
- Desativar anotações compartilhadas

Em seguida, atribua a política aos usuários.

> [!NOTE] 
> Um usuário pode ser atribuído a política de reunião de apenas um por vez. 

## <a name="assign-a-meeting-policy-to-a-user"></a>Atribuir uma política de reunião para um usuário

Para atribuir uma política, vá para **o Centro de administração do Microsoft equipes** > **usuários**. 
 
Se você estiver aplicando a política a um usuário, selecione o nome de exibição do usuário. Ao lado de **políticas atribuído**, selecione **Editar**. Em seguida, no painel **Editar políticas de usuário** , em **política de reunião**, selecione a política de reunião na lista suspensa e selecione **Salvar**. Você também pode editar as configurações da lista de usuários. Para fazer isso, selecione o usuário clicando à esquerda do nome para exibição do usuário. Selecione **Editar configurações**. Em seguida, no painel **Editar configurações** , em **política de reunião**, selecione a política na lista suspensa e selecione **Salvar**. 
 
Se você estiver aplicando uma política para mais de um usuário, selecione cada um dos usuários clicando à esquerda do nome de usuário e, em seguida, clique em **Editar configurações**. No painel **Editar configurações** , em **política de reunião**, selecione a política na lista suspensa e selecione **Salvar**.
 
Você também pode fazer isso indo para **o Centro de administração do Microsoft equipes** > **reuniões** >  **políticas de reunião**. Selecione a política e selecione **Gerenciar usuários**. No painel de **Gerenciar usuários** , procure o usuário por nome para exibição ou o usuário. Selecione o nome e selecione **Adicionar**. Quando terminar de adicionar usuários, selecione **Salvar**.

> [!NOTE] 
> Você não pode excluir uma política, se os usuários são atribuídos a ela. Você deve primeiro atribuir uma política diferente a todos os usuários afetados e, em seguida, você pode excluir a diretiva original.
 
 
## <a name="user-policy-settings"></a>Configurações de diretiva de usuário

Quando você seleciona uma política existente na página de **políticas de reunião** ou selecione **nova política** para adicionar uma nova diretiva, você pode configurar as configurações a seguir.

### <a name="new-meeting-policy-name-and-description"></a>Nova reunião política nome e descrição
   - **Nome** Este é o nome da política que aparecerão na página de **políticas de reunião** . Ele não pode conter caracteres especiais ou ter mais de 64 caracteres. Observe que você não pode alterar o nome da política de um existente.
   - **Descrição** Você pode colocar em uma descrição amigável para a política que você criar. Isso será útil se você deseja atribuir uma política a um grupo de usuários.
::: zone-end 

<a name="bkgeneral"> </a>
### <a name="general"></a>Geral
   - **Permitir reunir agora** Ativando isso permitirá que o recurso reunir agora esteja disponível aos usuários que ingressem em reuniões.
   - **Permitir que o suplemento do Outlook** Ativando isso permitirá que os usuários atribuídos à política tiver o suplemento Outlook disponível quando eles agendarem reuniões.
   - **Agendamento de reuniões de canal de permitir** Ativando isso permitirá que o agendamento de reuniões de canal.
   - **Permitir o agendamento de reuniões privadas** Ativando isso permitirá que os usuários que ingressem em uma reunião para agendar reuniões privadas.

<a name="bkaudioandvideo"> </a>

### <a name="audio--video"></a>Áudio & de vídeo
   - **Permitir transcrição** Se você ativar isso, transcrições da reunião estarão disponíveis aos usuários.
   - **Permitir nuvem de gravação** Ativando isso permitirá gravações seja salvo na nuvem.
   - **Permitir que o vídeo IP** Ativando isso permitirá que os vídeos IP durante as reuniões.
   - **(KBs) de taxa de bits de mídia** Você pode definir a taxa de bits para reuniões. O padrão é 50 MB.

<a name="bkcontentsharing"> </a>

### <a name="content-sharing"></a>Compartilhamento de conteúdo
   - **Modo de compartilhamento de tela** Você pode selecionar a modo de compartilhamento de tela. Esse será o tamanho da tela que será usado durante uma reunião que um usuário atribuído com a diretiva pode usar.
   - **Permitir que um participante dar ou solicitar o controle** Isso permite que todos os participantes em uma reunião dar e solicitar o controle de compartilhamento de tela.
   - **Permitir que um participante externo dar ou solicitar o controle** Isso permite que um participante externo (alguém não faz parte da sua organização) dar e solicitar o controle de uma reunião quando a tela está sendo compartilhada.
   - **Compartilhamento de PowerPoint permitir** Se você ativar isso, os usuários que agendem reuniões podem compartilhar apresentações de slide do PowerPoint durante uma reunião.
   - **Permitir quadro de comunicações** Se você ativar isso, o quadro de comunicações estarão disponível aos participantes da reunião durante uma reunião.
   - **Permitir anotações compartilhadas** Se você ativar isso, anotações compartilhadas estarão disponíveis aos participantes da reunião durante uma reunião.

<a name="bkparticipantsandguests"> </a>

### <a name="participants--guests"></a>Convidados que & participantes
   - **Permitir que os usuários anônimos para reuniões de iniciar** Se essa configuração estiver desativada, apenas uma pessoa que tiverem sido autenticados para a reunião com um aplicativo de equipes pode iniciar a reunião. Se ele estiver ativado, qualquer pessoa pode iniciar a reunião.
   - **Admitir automaticamente aos usuários** Se você desativar esse recurso, em seguida, os participantes da reunião serão deixados no lobby até que alguém inicia a reunião. Se ele estiver ativado, os participantes da reunião poderão ingressar na reunião automaticamente.

[Artigo completo](meeting-policies-in-teams.md)

### <a name="related-topics"></a>Tópicos relacionados
[Políticas de mensagens em equipes](messaging-policies-in-teams.md)