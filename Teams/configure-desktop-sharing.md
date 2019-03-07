---
title: Configurar o compartilhamento de área de trabalho no Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Configurar uma política de reunião para permitir que os usuários compartilhem suas áreas de trabalho em chats de equipes ou em reuniões
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 757f023d5f988e5a4f45c6274358aa51f3417ce0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464456"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configurar o compartilhamento de área de trabalho no Microsoft Teams
============================================

Compartilhamento da área de trabalho permite que os usuários apresentar uma tela ou app durante uma reunião ou bate-papo. Os administradores podem configurar Teams da Microsoft para permitir que usuários compartilhar uma tela inteira, um aplicativo ou um arquivo de compartilhamento de tela. Você pode permitir que usuários conceder ou solicitar o controle, permitir o compartilhamento do PowerPoint, adicione um quadro de comunicações e permitir anotações compartilhadas. Você também pode configurar se os usuários anônimos ou externos podem solicitar o controle da tela compartilhada.

Para configurar o compartilhamento de tela, você pode cria uma nova política de reuniões e atribuí-la para os usuários que você deseja gerenciar.

**No Centro de administração do Microsoft Teams**

1. Selecione **reuniões** > **políticas de reunião**.

    ![Selecione políticas de reunião](media/configure-desktop-sharing-image1.png)

2. Na página de **políticas de reunião** , selecione **nova política**.

    ![Selecione nova política](media/configure-desktop-sharing-image2.png)

3. Dê um título exclusivo de sua política e insira uma breve descrição.

4. Em **compartilhamento de conteúdo**, escolha um **modo de compartilhamento de tela** da lista suspensa:

   - **Tela inteira** – permite que os usuários compartilhar sua área de trabalho inteira.
   - **Único aplicativo** – permite que os usuários compartilhamento de tela do limite a um único aplicativo ativo.
   - **Desabilitado** – desativa o compartilhamento de tela.

    ![Escolha uma modo de compartilhamento de tela](media/configure-desktop-sharing-image3.png)

5. Ative ou desativar o as seguintes configurações:

    - **Permitir que um participante dar ou solicitar o controle** – permite que membros da equipe de conceder ou solicitar o controle da área de trabalho do apresentador ou aplicativo.
    - **Permitir que um participante externo dar ou solicitar o controle** – permite convidados e usuários (federados) externos dar ou solicitar o controle da área de trabalho ou do aplicativo do apresentador.
    - **Compartilhamento de PowerPoint permitir** - permite aos usuários criar reuniões que permitem apresentações do PowerPoint sejam carregados e compartilhados.
    - **Quadro de comunicações permitir** – permite que os usuários compartilhem um quadro de comunicações.
    - **Permitir anotações compartilhadas** – permite que os usuários façam anotações compartilhadas.

6. Clique em **Salvar**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Usar o PowerShell para configurar a área de trabalho compartilhada

Você também pode usar o cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar o compartilhamento da área de trabalho. Defina os seguintes parâmetros:

- Descrição
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Saiba mais sobre como usar o cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

