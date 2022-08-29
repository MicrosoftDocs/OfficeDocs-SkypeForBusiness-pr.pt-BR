---
title: Gerenciar políticas de reunião no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Aprenda a gerenciar as configurações das políticas de reunião no Teams e a usá-las para controlar os recursos disponíveis para os participantes da reunião nas reuniões agendadas pelos usuários.
ms.openlocfilehash: 99c84f6c0dfcbd20824a90af49739eace200ecd2
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396542"
---
# <a name="manage-meeting-policies-in-microsoft-teams"></a>Gerenciar políticas de reunião no Microsoft Teams

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

As políticas de reunião são usadas para controlar os recursos disponibilizados para os participantes de reuniões programadas pelos usuários de sua organização. Você pode usar a política global (padrão em toda a organização) criada automaticamente ou criar e atribuir políticas personalizadas.  Você gerencia as políticas de reunião no Centro de Administração do Microsoft Teams ou usando o [PowerShell](teams-powershell-overview.md).

> [!NOTE]
> Para obter informações sobre como usar as funções para gerenciar as permissões de apresentadores e participantes da reunião, confira [funções em uma reunião no Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Você pode implementar políticas das seguintes maneiras, o que afeta a experiência da reunião para os usuários antes, durante, ou depois de uma reunião.

|Tipo de implementação  |Descrição  |
|---------|---------|
|Por organizador    |Ao implementar uma política por organizador, todos os participantes da reunião herdam a política do organizador. Por exemplo, **Admitir pessoas automaticamente** é uma política por organizador e controla se os usuários entram na reunião diretamente ou se esperam o lobby das reuniões agendadas pelo usuário que recebeu a política.          |
|Por usuário    |Ao implementar uma política por usuário, somente a política por usuário se aplica à restrições de certos recursos para o organizador e/ou os participantes da reunião. Por exemplo, **reunir agora em canais** é uma política por usuário.     |
|Por organizador e por usuário     |Ao implementar uma combinação de uma política por organizador e por usuário, alguns recursos são restritos para os participantes da reunião com base em sua política e a política do organizador. Por exemplo, **a gravação na** nuvem é uma política por organizador e por usuário. Ative essa configuração para permitir que o organizador da reunião e os participantes iniciem e interrompam uma gravação.

Você pode editar as configurações na política global ou criar e atribuir uma ou mais políticas personalizadas. Os usuários terão a política global, a menos que você crie e atribua uma política personalizada.

> [!NOTE]
> O botão detalhes da reunião estará disponível se um usuário tiver as licenças de conferência de áudio habilitadas ou se o usuário permitir a conferência de áudio, caso contrário, os detalhes da reunião não estarão disponíveis.

## <a name="create-a-custom-meeting-policy"></a>Criar uma política de reunião personalizada

1. Na barra de navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Reuniões** > **Políticas de Reunião**.
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política. O nome não pode conter caracteres especiais ou ter mais de 64 caracteres.
4. Escolha as configurações que deseja.
5. Clique em **Salvar**.

Por exemplo, digamos que você tenha um grupo de usuários e queira limitar a quantidade de largura de banda que a reunião exigiria. Você criaria uma nova política personalizada chamada "Largura de banda limitada" e desativaria as seguintes configurações:

Em **Áudio e vídeo**:

- Desative a gravação na nuvem.
- Desative o vídeo IP.

Em **Compartilhamento de conteúdo**:

- Desative o modo de compartilhamento de tela.
- Desative o Quadro de Comunicações.
- Desative anotações compartilhadas.

Em seguida, atribua a política aos usuários.

Este vídeo mostra as etapas para criar e atribuir uma política de reunião personalizada a um usuário (ou usuários).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53Wv0?autoplay=false]

## <a name="edit-a-meeting-policy"></a>Editar uma política de retenção

Você pode editar a política global e as políticas personalizadas que criar.

1. Na barra de navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Reuniões** > **Políticas de Reunião**.
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. A partir daqui, faça as alterações desejadas.
4. Clique em **Salvar**.

> [!NOTE]
> Um usuário pode receber apenas uma política de reunião por vez.

Este vídeo mostra as etapas para editar uma política de reunião padrão em toda a organização.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53MoG?autoplay=false]

## <a name="assign-a-meeting-policy-to-users"></a>Atribuir uma política de reunião aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> Você não pode excluir uma política se usuários estiverem atribuídos a ela. Primeiro, você deve atribuir uma política diferente a todos os usuários afetados. em seguida, é possível excluir a política original.

## <a name="meeting-policy-settings"></a>Configurações de política de reunião

Ao selecionar uma política existente na página de **Políticas de reunião** ou selecionar **Adicionar** para adicionar uma nova política, você pode definir as configurações para o seguinte.

- [Geral](meeting-policies-in-teams-general.md)
- [Áudio e vídeo](meeting-policies-audio-and-video.md)
- [Gravação & transcrição](meetings-policies-recording-and-transcription.md)
- [Compartilhamento de conteúdo](meeting-policies-content-sharing.md)
- [Participantes e convidados](meeting-policies-participants-and-guests.md)

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)
- [Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários](meeting-policies-restricted-anonymous-access.md)
