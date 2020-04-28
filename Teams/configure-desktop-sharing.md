---
title: Configurar o compartilhamento da área de trabalho no Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como configurar uma política de reunião para permitir que os usuários compartilhem suas áreas de trabalho nos chats ou reuniões do teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 955a642d2a2309ccbaf9f9d6280170a93a9179ae
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905893"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configurar o compartilhamento da área de trabalho no Microsoft Teams
============================================

O compartilhamento da área de trabalho permite que os usuários apresentem uma tela ou aplicativo durante uma reunião ou bate-papo. Os administradores podem configurar o compartilhamento de tela no Microsoft Teams para permitir que os usuários compartilhem uma tela inteira, um aplicativo ou um arquivo. Você pode permitir que os usuários deem ou solicitem controle, permitam o compartilhamento do PowerPoint, adicionem um quadro branco e permitam anotações compartilhadas. Você também pode configurar se usuários anônimos ou externos podem solicitar o controle da tela compartilhada.

Para configurar o compartilhamento de tela, crie uma nova política de reuniões e a atribua aos usuários que quer gerenciar.

**No [Centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/)**

1. Clique em **Reuniões** > **Políticas de reuniões**.

    ![Captura de tela exibindo as políticas das reuniões selecionadas](media/configure-desktop-sharing-image1.png)

2. Na página **Políticas de reunião**, clique em **Nova política**.

    ![Captura de tela exibindo a mensagem das políticas de reunião](media/configure-desktop-sharing-image2.png)

3. Atribua um título exclusivo à sua política e insira uma breve descrição.

4. Em **Compartilhamento de conteúdo**, escolha um **Modo de compartilhamento de tela** da lista suspensa:

   - **Tela inteira** – permite que os usuários compartilhem toda a área de trabalho.
   - **Aplicativo único** – permite que os usuários limitem o compartilhamento de tela a um único aplicativo ativo.
   - **Desabilitado** – desativa o compartilhamento de tela.

    ![Captura de tela exibindo as opções do modo de compartilhamento](media/configure-desktop-sharing-image3.png)

5. Ative ou desative as seguintes configurações:

    - **Permitir que um participante conceda ou solicite o controle** – permite que os membros da equipe conceda ou solicitem o controle da área de trabalho ou do aplicativo do apresentador.
    - **Permitir que um participante externo conceda ou solicite controle** – permite que convidados e usuários externos (federados) conceda ou solicitem controle da área de trabalho ou do aplicativo do apresentador.
    - **Permitir o compartilhamento do PowerPoint** - permite que os usuários criem reuniões que permitem que as apresentações do PowerPoint sejam carregadas e compartilhadas.
    - **Permitir quadro de comunicações** – permite que os usuários compartilhem um quadro de comunicações.
    - **Permitir anotações compartilhadas** – permite que os usuários façam anotações compartilhadas.

6. Clique em **Salvar**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Use o PowerShell para configurar a área de trabalho compartilhada

Você também pode usar o cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar o compartilhamento da área de trabalho. Use os seguintes parâmetros:

- Descrição
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Saiba mais sobre como usar o cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

