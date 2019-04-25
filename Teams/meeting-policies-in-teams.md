---
title: Gerenciar políticas de reunião
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 04/18/2019
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
ms.openlocfilehash: 01d4ec8265c069d5fdbd6d8bb64ab89ec991956a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231810"
---
# <a name="manage-meeting-policies-in-teams"></a>Gerenciar políticas de reunião em equipes

::: zone target="docs"
Políticas de reunião são usadas para controlar os recursos disponíveis aos participantes para reuniões agendadas por usuários em sua organização da reunião. Depois de criar uma política e faça as alterações, você pode atribuir usuários à diretiva. 

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

## <a name="assign-a-meeting-policy-to-users"></a>Atribuir uma política de reunião aos usuários

Se você estiver aplicando a política a um usuário, selecione **os usuários** no painel de navegação à esquerda e clique em nome para exibição do usuário. Na página do usuário, ao lado de **políticas atribuído**, selecione **Editar**. Em seguida, no painel **Editar políticas de usuário** , em **política de reunião**, selecione a política de reunião na lista suspensa e selecione **Salvar**. Você também pode atribuir políticas da lista de usuários. Para fazer isso, selecione o usuário clicando à esquerda do nome para exibição do usuário. Selecione **Editar configurações**. Em seguida, no painel **Editar configurações** , em **política de reunião**, selecione a política na lista suspensa e selecione **Salvar**. 
 
Se você estiver aplicando uma política para mais de um usuário, selecione os **usuários** no painel de navegação à esquerda e selecione cada usuário clicando à esquerda do nome de usuário e, em seguida, clique em **Editar configurações**. No painel **Editar configurações** , em **política de reunião**, selecione a política na lista suspensa e, em seguida, selecione **Salvar**.
 
Você também pode atribuir uma política de reunião para um ou mais usuários da seguinte maneira:

1. Vá para **o Centro de administração do Microsoft equipes** > **reuniões** > **políticas de reunião**.
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **Gerenciar usuários**.
4. No painel de **Gerenciar usuários** , procure o usuário pelo nome de exibição ou nome de usuário, selecione o nome e selecione **Adicionar**. Repita essa etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar usuários, selecione **Salvar**.
 
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
   - **Permitir reunir agora no canais** Ativando isso permitirá que o recurso reunir agora esteja disponível aos usuários que ingressem em reuniões.
   - **Permitir que o suplemento do Outlook** Ativando isso permitirá que os usuários atribuídos à política tiver o suplemento Outlook disponível quando eles agendarem reuniões.
   - **Permitir agendamento de reuniões de canal** Ativando isso permitirá que o agendamento de reuniões de canal.
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
   - **Permitir que as pessoas que discam para iniciar uma reunião** Você pode ativar ou desativar se você quiser permitir que as pessoas que ainda não tenham sido autenticadas porque eles discaram usando seu telefone para iniciar uma reunião.
   - **Automaticamente admitir pessoas** Determina quais tipos de participantes serão automaticamente ser adicionado às reuniões organizadas pelo usuário. Defina **todos em sua organização** se você gostaria de reuniões, coloque cada usuário externo no lobby, mas permitir que todos os usuários na empresa para ingressar na reunião imediatamente. Defina isso para **todas as pessoas** se você gostaria de admitir usuários anônimos por padrão. Defina isso para **todos em sua organização e organizações federadas** , se você gostaria de reuniões para permitir que usuários federados ingressar como os usuários da sua empresa, mas colocar todos os outros usuários externos em um lobby.
   - **Permitir que usuários de discagem para ignoram o lobby** Você pode ativar ou desativar se quiser permitir que as pessoas que discou usando seu telefone ignoram o lobby e ingressar na reunião.
   - **Permitir que os organizadores para substituir as configurações de lobby** Ative esta configuração para permitir que os organizadores de reuniões desconsiderar as configurações de lobby para admitir usuários às reuniões.
   - **Permitir reunir agora nas reuniões privadas** Ative esta configuração para permitir que os participantes da reunião atender em particular via bate-papo antes de começa a reunião. 
   - **Habilitar legendas ao vivo** Habilite essa configuração para exibir as legendas em idiomas suportados durante uma reunião. 
   - **Permitir bate-papo em reuniões** Habilite essa configuração permitir o bate-papos durante uma reunião. Isso é útil se os usuários tem dúvidas ou deseja inserir um hiperlink ou uma nota durante uma discussão, mas não querem interromper a conversa.

[Artigo completo](meeting-policies-in-teams.md)

### <a name="related-topics"></a>Tópicos relacionados
[Políticas de mensagens em equipes](messaging-policies-in-teams.md)
