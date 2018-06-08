---
title: Consulte, alterar e redefina um ID de conferência atribuído a um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: eccbcd31add14026d2b5f3a57348ae5d6f1db2a5
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703400"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user"></a>Visualizar e redefinir uma ID de conferência atribuída a um usuário

Uma ID de conferência é atribuída automaticamente a um Skype para usuário de negócios ou Microsoft Teams quando eles estiverem configurados para conferência de áudio no Office 365 e usarem o Microsoft como um provedor de serviços de audioconferência. A ID de conferência atribuída é enviada no convite da reunião, quando a reunião foi agendada. Cada reunião que um usuário agenda será obtido atribuída uma ID de conferência exclusivas. 
  
Embora uma ID de conferência será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número, ou quando os usuários não conseguir se lembrar ou tem perdido sua ID de conferência. Você pode usar o **Skype para centro de administração de negócios** e do Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.
  
Um email será enviado ao usuário com a ID de conferência e os números de telefone de conferência de áudio padrão, ou se você redefinir o ID de conferência um email diferente será enviado que incluírem o ID de conferência, mas não um PIN. Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user.md). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Visualizar e redefinir as IDs de conferência

### <a name="to-view-the-conference-id"></a>Para exibir a ID de conferência

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, procure em **ID da conferência**.

    > [!TIP]
    > Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de áudio clicando no link **Enviar informações de conferência no email** .
  
Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário. Para fazer isso, execute:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

Você pode exibir sua ID de conferência e enviá-la aos usuários.
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**> **audioconferências** > **usuários**, selecione o usuário que necessidades ID de conferência.
    
4. Na página ação, procure em **ID da conferência**.
    
    > [!TIP]
    > Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de áudio clicando no link **Enviar informações de conferência via email** depois de selecionar o usuário na página **usuários** .

Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário. Para fazer isso, execute:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a>Para redefinir o ID de conferência

Você pode redefinir uma ID de conferência para um usuário se, por exemplo, caso eles tenha esquecido.
  
![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, clique em **Redefinir ID de conferência**.

4. Na janela **Redefinir ID de conferência** , clique em **Redefinir**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
    
    Você pode redefinir a ID de conferência para um usuário usando o Windows PowerShell. Para fazer isso, execute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**> **audioconferências** > **usuários**, no painel de ação em **ID da conferência**, clique em **Redefinir**.
    
4. No **Redefinir ID de conferência?** janela, clique em **Sim**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
    
    Você pode redefinir a ID de conferência para um usuário usando o Windows PowerShell. Para fazer isso, execute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

   > [!IMPORTANT]
   >  Depois que uma nova ID de conferência é criada ou um é redefinido, o ID de conferência antigos não pode ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites. Os usuários podem usar o Skype para ferramenta de migração de reunião de negócios para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar a ferramenta, consulte: [Ferramenta de atualização de reunião para Skype para negócios e Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negócios Online, a ferramenta de migração de reunião (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype para negócios Online, a ferramenta de migração de reunião (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
- Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.
    
- A ID de conferência deve atender a duração em dígitos, defina a ponte de conferência de áudio. Você não pode usar caracteres alfabéticos ou especiais de conferência IDs; somente números podem ser usados.
    
- O ID de conferência para todos os usuários de serviços de audioconferência será 7 dígitos por padrão, e o número de dígitos não pode ser alterado.
    
    
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

