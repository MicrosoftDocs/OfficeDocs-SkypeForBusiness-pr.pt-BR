---
title: Configurar o compartilhamento de área de trabalho no Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Configurar uma política de reunião para permitir que os usuários compartilhem suas áreas de trabalho nos chats ou reuniões do teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99c6e2a5adb9d0f9a4b4e3f6f17b7484bda96a74
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516881"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configurar o compartilhamento de área de trabalho no Microsoft Teams
============================================

O compartilhamento de área de trabalho permite que os usuários apresentem uma tela ou um aplicativo durante uma reunião ou chat. Os administradores podem configurar o compartilhamento de tela no Microsoft Teams para permitir que os usuários compartilhem uma tela inteira, um aplicativo ou um arquivo. Você pode permitir que os usuários forneçam ou solicitem controle, permitam o compartilhamento do PowerPoint, adicionem um quadro de comunicações e permitam anotações compartilhadas. Você também pode configurar se usuários anônimos ou externos podem solicitar o controle da tela compartilhada.

Para configurar o compartilhamento de tela, crie uma nova política de reuniões e atribua-a aos usuários que você deseja gerenciar.

**No centro de administração do Microsoft Teams**

1. Selecionar **** > **as políticas de reunião**de reuniões.

    ![Captura de tela mostrando as políticas de reunião selecionadas](media/configure-desktop-sharing-image1.png)

2. Na página **políticas de reunião** , selecione **nova política**.

    ![Captura de tela mostrando a mensagem de políticas de reunião](media/configure-desktop-sharing-image2.png)

3. Dê à sua política um título exclusivo e insira uma breve descrição.

4. Em **compartilhamento de conteúdo**, escolha um **modo de compartilhamento de tela** na lista suspensa:

   - **Tela inteira** – permite que os usuários compartilhem toda a área de trabalho.
   - **Aplicativo único** – permite que os usuários limitem o compartilhamento de tela a um único aplicativo ativo.
   - **Desabilitado** – desativa o compartilhamento de tela.

    ![Captura de tela mostrando as opções do modo de compartilhamento](media/configure-desktop-sharing-image3.png)

5. Ativar ou desativar as seguintes configurações:

    - **Permitir que um participante conceda ou solicite o controle** – permite que os membros da equipe conceda ou solicitem o controle da área de trabalho ou do aplicativo do apresentador.
    - **Permitir que um participante externo conceda ou solicite controle** – permite que convidados e usuários externos (federados) conceda ou solicitem controle da área de trabalho ou do aplicativo do apresentador.
    - **Permitir compartilhamento do PowerPoint** -permite que os usuários criem reuniões que permitem que as apresentações do PowerPoint sejam carregadas e compartilhadas.
    - **Permitir quadro de comunicações** – permite que os usuários compartilhem um quadro de comunicações.
    - **Permitir anotações compartilhadas** – permite que os usuários façam anotações compartilhadas.

6. Clique em **Salvar**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Usar o PowerShell para configurar a área de trabalho compartilhada

Você também pode usar o cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar o compartilhamento da área de trabalho. Defina os seguintes parâmetros:

- Descrição
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Saiba mais sobre como usar o cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

