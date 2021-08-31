---
title: Consulte, altere e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba como atribuir uma ID de conferência a um usuário no Skype for Business Online e quais os parâmetros de IDs de conferência devem ser. '
ms.openlocfilehash: a400536050ea22d4f841e3b401e30c3c14729093
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727998"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Visualizar e redefinir uma ID de conferência atribuída a um usuário no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Para obter informações sobre IDs de conferência do usuário no Microsoft Teams, consulte Exibir e redefinir uma [ID](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)de conferência atribuída a um usuário em Microsoft Teams .

Uma ID de conferência é atribuída automaticamente a um usuário Skype for Business quando está configurada para Audioconferência no Microsoft 365 ou Office 365 e usa a Microsoft como provedor de audioconferência. A ID da conferência atribuída é enviada no convite da reunião quando a reunião é agendada. Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva.

Embora uma ID de conferência seja criada e atribuída automaticamente a um usuário, pode haver momentos em que um usuário não deseja usá-la e você deseja defini-la como um determinado número, ou quando seus usuários não puderem se lembrar ou perderem a ID da conferência. Você pode usar o Skype for Business **de** administração e Windows PowerShell para exibir, alterar e redefinir a ID da conferência.

Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN. Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Visualizar e redefinir as IDs de conferências

### <a name="to-view-the-conference-id"></a>Para exibir a ID da conferência

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração**

Você pode exibir sua ID de conferência e enviá-la aos usuários.

1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business**.

3. Em **Centro de administração do Skype for Business**> **Audioconferências** > **Usuários**, selecione o usuário que necessita da ID da conferência.

4. Na página Ação, procure em **ID da conferência**.

    > [!TIP]
    > Você pode enviar todas as informações de conferência para o usuário em um email que inclui a ID da conferência e  números de telefone de áudio clicando no link Enviar informações de conferência por **email** depois de selecionar o usuário na página Usuários.

**Usando Windows PowerShell**

Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário. Para fazer isso, execute:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Consulte [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) para saber mais sobre o cmdlet.


### <a name="to-reset-the-conference-id"></a>Para redefinir a ID da conferência

É possível redefinir uma ID de conferência para um usuário se, por exemplo, ele a esquecer.

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração**

1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business**.

3. No centro **de Skype for Business de** administração Usuários de Audioconferência , no painel Ação em ID da >    >  Conferência, clique em **Redefinir**. 

4. Na janela **Redefinir iD** da conferência? clique em **Sim**. A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Usando Windows PowerShell**

Usando o Windows PowerShell Para fazer isso, execute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

   > [!IMPORTANT]
   >  Depois que uma nova ID de conferência é criada ou uma é redefinida, a ID de conferência antiga não pode ser usada pelos chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites. Os usuários podem usar o Skype for Business de Migração de Reunião para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar a ferramenta, consulte: Meeting [Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), Skype for Business [Online, Meeting Migration Tool (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype for Business Online, Meeting Migration Tool (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079).

- Consulte [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) para saber mais sobre o cmdlet.

- A ID da conferência deve atender ao comprimento em dígitos definidos na ponte de audioconferência. Não é possível usar caracteres alfabéticos ou especiais em IDs de conferência; somente números podem ser usados.

- A ID da conferência para todos os usuários de audioconferência será de 9 dígitos por padrão, e o número de dígitos não pode ser alterado.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
