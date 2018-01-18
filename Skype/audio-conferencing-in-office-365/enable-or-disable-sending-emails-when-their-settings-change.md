---
title: "Habilitar ou desabilitar o envio de emails ao alteram suas configurações"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4efabf42f7253d89b37282103a3046cf7b2b0d26
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio

Os usuários são notificados automaticamente por email quando estiverem habilitados para conferência de áudio. Pode haver momentos, entretanto, quando você deseja reduzir o número de emails que são enviadas para Skype para usuário Teams da Microsoft e de negócios. Nesses casos, você pode desabilitar o envio de email.
  
Se você desabilitar o envio de emails, emails de conferência de áudio não serão enviadas aos seus usuários, incluindo emails para quando os usuários estão habilitados ou desabilitados para conferências de áudio, quando o seu PIN é redefinido e quando as alterações no número de telefone a ID de conferência e a conferência padrão .
  
Aqui está um exemplo de email enviada aos usuários quando eles estão habilitados para conferência de áudio:
  
![Email de conferência de áudio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quando os emails são enviados para seus usuários?

- Há vários emails que serão enviadas aos usuários em sua organização depois que eles estão habilitados para conferência de áudio:
    
  - Quando uma licença de **Conferência de áudio** é atribuída a eles.
    
  - Quando você redefinir manualmente os serviços de audioconferência PIN do usuário.
    
  - Quando você redefine manualmente a ID de conferência do usuário.
    
  - Quando a licença de **Conferência de áudio** seja removida deles.
    
  - Quando o provedor de serviços de audioconferência de um usuário for alterado da Microsoft para outro provedor ou **Nenhum**.
    
  - Quando o provedor de serviços de audioconferência de um usuário é alterado para Microsoft.
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar ou desabilitar o email que está sendo enviado a usuários

Você pode usar o Skype para centro de administração de negócios ou o Windows PowerShell para habilitar ou desabilitar o email enviado aos usuários.
  
 **Usando o Skype para o Centro de administração de negócios**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype para os negócios**e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Na página **configurações de ponte da Microsoft** , marque ou desmarque a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.
    
4. Clique em **Salvar**.
    
    > [!TIP]
    > Você também pode enviar email a um usuário com as configurações de serviços de audioconferência indo para **conferência de áudio** > **usuários**, selecionando o usuário e, em seguida, clicando em **Enviar informações de conferência via email**.  Se fizer isso, será enviado um email que inclui somente o ID de conferência e o número de telefone de conferência, mas não o PIN.  Para obter mais informações, consulte [Enviar um email a um usuário com as informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
 **Usando o Windows PowerShell**
  
- Execute o seguinte procedimento para desabilitar o envio de emails: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Para obter ajuda com este cmdlet, consulte [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Quando emails automáticas estão desabilitadas, você pode acionar ainda manualmente enviar um email com o número de telefone e a ID de conferência usando o Skype para o Centro de administração de negócios. No entanto, se você fizer isso, o PIN não será incluído. Se você deseja redefinir o PIN de conferência de áudio e enviando e-mails estiver desabilitado, você precisará enviá-la ao usuário em outra forma.
    
- Por padrão, o remetente dos e-mails será do Office 365, mas você pode alterar o endereço de email e usando o Windows PowerShell de nome de exibição e também usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
    > [!NOTE]
    >  Se você deseja alterar as informações de endereço de email, será necessário certificar-se de que as políticas de email de entrada do seu ambiente permitem emails provenientes de personalizado especificado do endereço.
  
  - Digite o endereço de email no parâmetro  _SendEmailFromAddress_.
    
  - Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.
    
  - Defina o parâmetro _SendEmailOverride_ como _True_.
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- O envio de emails a seus usuários pode ser desabilitado usando o Centro de administração do Skype for Business ou o Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Você pode usar esses cmdlets para economizar tempo ou automatizar isso.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Como usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Como usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Emails enviados aos usuários ao alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change.md)

[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md)

[Configurar a Audioconferência para o Skype for Business e o Microsoft Teams](set-up-audio-conferencing.md)

