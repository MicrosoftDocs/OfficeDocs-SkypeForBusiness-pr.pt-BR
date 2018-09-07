---
title: Consultar, alterar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como atribuir um ID de conferência a um usuário no Skype for Business Online e quais devem ser os parâmetros de IDs da conferência. '
ms.openlocfilehash: d47e188220f66e320289384c4fbe421328d8eca3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850181"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Visualizar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online

> [!Note]
> Para obter informações sobre IDs de conferência de usuários no Microsoft Teams, consulte [Exibir e redefinir um ID de conferência atribuído a um usuário no Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).

Um ID de conferência é atribuído automaticamente a um usuário do Skype for Business quando está configurado para Audioconferência no Office 365 e usa a Microsoft como o provedor de audioconferência. A ID de conferência atribuída é enviada no convite da reunião quando a reunião é agendada. Cada reunião programada por um usuário receberá um ID de conferência único.

Embora um ID de conferência seja criado e atribuído a um usuário automaticamente, podem existir ocasiões em que um usuário não deseje usá-lo e você precise configurá-lo para um determinado número, ou seus usuários não lembrem ou tenham perdido o ID da conferência. Você pode usar o **centro de administração do Skype for Business** e o Windows PowerShell para exibir, alterar e redefinir o ID da conferência.

Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN. Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Visualizar e redefinir as IDs de conferências

### <a name="to-view-the-conference-id"></a>Para exibir a ID da conferência

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**

Você pode exibir sua ID de conferência e enviá-la aos usuários.

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.

3. Em **Centro de administração do Skype for Business**> **Audioconferências** > **Usuários**, selecione o usuário que necessita da ID da conferência.

4. Na página Ação, procure em **ID da conferência**.

    > [!TIP]
    > Você pode enviar todas as informações da conferência para o usuário em um email que inclua a ID da conferência e os números de telefone de áudio clicando no link **Enviar informações da conferência via email** depois de selecionar o usuário na página **Usuários**.

**Usando o Windows PowerShell**

Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário. Para fazer isso, execute:

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a>Para redefinir a ID de conferência da reunião

É possível redefinir uma ID de conferência para um usuário se, por exemplo, ele a esquecer.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.

3. Em **Centro de administração do Skype for Business**> **Audioconferências** > **Usuários**, no painel Ação em **ID da conferência**, clique em **Redefinir**.

4. Na janela **Redefinir o ID da conferência?** , clique **Sim**. Uma ID de conferência será criada automaticamente e um email será enviado ao usuário com a nova ID da conferência.

**Usar o Windows PowerShell**

Usando o Windows PowerShell Para fazer isso, execute:

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

   > [!IMPORTANT]
   >  Depois que uma nova ID de conferência for criada ou for redefinida, a ID antiga não poderá ser usada pelos autores de chamadas. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites. Os usuários podem usar a Ferramenta de Migração de Reunião do Skype for Business para atualizar suas reuniões marcadas. Para ver como baixar, instalar e executar a ferramenta, consulte: [Ferramenta de Atualização de Reunião do Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Ferramenta de Migração de Reunião (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047) e [Skype for Business Online, Ferramenta de Migração de Reunião (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

- Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.

- A ID da conferência deve atender ao comprimento em dígitos definido na ponte de audioconferência. Não é possível usar letras e caracteres especiais nas IDs de conferência, somente números.

- Por padrão, a ID de conferência de todos os usuários da audioconferência é de sete dígitos e o número de dígitos não pode ser alterado.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

