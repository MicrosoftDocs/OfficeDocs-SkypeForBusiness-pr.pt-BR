---
title: Ver, alterar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba como atribuir uma ID de conferência a um usuário no Skype for Business Online e quais devem ser os parâmetros de IDs de conferência. '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643601"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Visualizar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online

> [!Note]
> Para obter informações sobre IDs de conferência de usuário no Microsoft Teams, consulte Exibir e redefinir uma ID de conferência atribuída a um usuário [no Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

Uma ID de conferência é atribuída automaticamente a um usuário do Skype for Business quando está configurada para Audioconferência no Microsoft 365 ou no Office 365 e usa a Microsoft como provedor de audioconferência. A ID de conferência atribuída é enviada no convite da reunião quando a reunião está agendada. Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva.

Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.

An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Visualizar e redefinir as IDs de conferências

### <a name="to-view-the-conference-id"></a>Para exibir a ID de conferência

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

Você pode exibir sua ID de conferência e enviá-la aos usuários.

1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business.**

3. Em **Centro de administração do Skype for Business**> **Audioconferências** > **Usuários**, selecione o usuário que necessita da ID da conferência.

4. Na página Ação, procure em **ID da conferência**.

    > [!TIP]
    > Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e  os números de telefone de áudio clicando nas informações de conferência Enviar por **email** depois de selecionar o usuário na página Usuários.

**Usando o Windows PowerShell**

You can use Windows PowerShell to view the conference ID for a user. To do so, run:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Consulte [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) para saber mais sobre o cmdlet.


### <a name="to-reset-the-conference-id"></a>Para redefinir a ID de conferência

É possível redefinir uma ID de conferência para um usuário se, por exemplo, ele a esquecer.

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business.**

3. No Centro **de administração do Skype for Business,** usuários de >  **audioconferência,** no painel Ação em ID de  >   **Conferência,** clique em **Redefinir.**

4. Na janela **Redefinir ID de conferência?** clique em **Sim.** A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Usando o Windows PowerShell**

Usando o Windows PowerShell Para fazer isso, execute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

   > [!IMPORTANT]
   >  Depois que uma nova ID de conferência é criada ou uma é redefinida, a ID de conferência antiga não pode ser usada pelos chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites. Os usuários podem usar a Ferramenta de Migração de Reunião do Skype for Business para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar a ferramenta, confira: Ferramenta de Atualização de Reunião do Skype for Business e [do Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype for Business Online, Ferramenta de Migração de Reuniões [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)e Skype for Business Online, Ferramenta de Migração de Reunião [(32 bits).](https://www.microsoft.com/download/details.aspx?id=54079)

- Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.

- A ID de conferência deve atender ao comprimento em dígitos definido na ponte de audioconferência. Você não pode usar caracteres alfabéticos ou especiais em IDs de conferência; somente números podem ser usados.

- A ID de conferência para todos os seus usuários de audioconferência terá 9 dígitos por padrão e o número de dígitos não poderá ser alterado.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Por que você precisa usar o Microsoft 365 ou o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar Audioconferência no Microsoft 365 ou no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

