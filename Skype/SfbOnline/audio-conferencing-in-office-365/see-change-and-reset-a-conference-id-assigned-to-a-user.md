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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: 42aa17866c286c5d57fa3cd4962ecf6a16e2438a
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a>Consulte, alterar e redefina um ID de conferência atribuído a um usuário

Uma ID de conferência é atribuída automaticamente a um Skype para usuário de negócios ou Microsoft Teams quando eles estiverem configurados para conferência de áudio no Office 365 e usarem o Microsoft como um provedor de serviços de audioconferência. A ID de conferência atribuída pode ser estáticos ou dinâmicos e é enviada no convite da reunião, quando a reunião foi agendada.
  
IDs estáticas são usadas quando as pessoas na sua organização não desejam Lembre-se de um número aleatório; eles podem selecionar um certo número ou use um que seja fácil de lembrar. Se IDs de conferência dinâmicas estiverem sendo usadas, cada reunião agendada por um usuário terá uma ID de conferência exclusiva atribuída. Se você deseja atribuir dinâmico em vez de conferência estática IDs, [acesse aqui](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Embora uma ID de conferência estática será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número, ou quando os usuários não conseguir se lembrar ou tem perdido sua ID de conferência. Você pode usar o **Skype para centro de administração de negócios** e do Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.
  
Um email será enviado ao usuário com a ID de conferência e os números de telefone de conferência de áudio padrão, ou se você redefinir o ID de conferência um email diferente será enviado que incluírem o ID de conferência, mas não um PIN.
  
## <a name="view-and-change-conference-ids"></a>Exibir e alterar as IDs de conferência

### <a name="to-view-the-conference-id"></a>Para exibir a ID de conferência

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

    Consulte [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) para saber mais sobre o cmdlet.
    
### <a name="to-assign-or-change-the-conference-id"></a>Para atribuir ou alterar a ID de conferência

Você pode atribuir ou alterar um ID de conferência para um usuário se, por exemplo, alguém uma ID de conferência que é fácil de lembrar.

  > [!NOTE]
  > O Skype para centro de administração de negócios não pode ser usado para editar uma ID de conferência que foi criada automaticamente, mas você pode usar o Windows PowerShell para editar ou alterar uma ID de conferência que você definiu. 
     
Para editar ou alterar a ID de conferência para um usuário, execute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > Uma ID de conferência deve conter 7 dígitos, e você não pode alterá-lo no Skype para centro de administração de negócios ou usando o Windows PowerShell. 
  
### <a name="to-reset-the-conference-id"></a>Para redefinir o ID de conferência

Você pode redefinir uma ID de conferência para um usuário se, por exemplo, caso eles tenha esquecido.
  
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

