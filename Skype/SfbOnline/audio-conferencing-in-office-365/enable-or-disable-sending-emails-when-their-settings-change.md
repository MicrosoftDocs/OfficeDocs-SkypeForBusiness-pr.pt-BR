---
title: Habilitar ou desabilitar o envio de emails quando as configurações de AudioConferência mudarem no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 681a02fd410c008f46ad7906c5963660df668a89
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164260"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Habilitar ou desabilitar o envio de emails quando as configurações de AudioConferência mudarem no Skype for Business Online

> [!Note]
> Se você quiser habilitar ou desabilitar o envio de emails no Microsoft Teams, consulte Habilitar ou desabilitar o envio de emails quando as configurações [de Audioconferência mudarem no Microsoft Teams.](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)

Os usuários são notificados automaticamente por email quando estão habilitados para Audioconferência. No entanto, pode haver ocasiões em que você queira reduzir o número de emails enviados para usuários do Skype for Business. Nesses casos, você pode desabilitar o envio de emails.
  
Se você desabilitar o envio de emails, os emails de Audioconferência não serão enviados para seus usuários, incluindo emails para quando os usuários estão habilitados ou desabilitados para audioconferência, quando o PIN é redefinido e quando a ID de conferência e o número de telefone de conferência padrão mudam.
  
Aqui está um exemplo de email que é enviado aos usuários quando eles estão habilitados para Audioconferência:
  
![Email de audioconferência](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quando os emails são enviados para seus usuários?

- Há vários emails enviados para os usuários em sua organização depois que eles são habilitados para audioconferência:
    
  - Quando uma **licença de Audioconferência** é atribuída a eles.
    
  - Quando você redefine manualmente o PIN de audioconferência do usuário.
    
  - Quando você redefine manualmente o ID de conferência do usuário.
    
  - Quando a **licença de Audioconferência** é removida delas.
    
  - Quando o provedor de audioconferência de um usuário é alterado da Microsoft para outro provedor ou **Nenhum.**
    
  - Quando o provedor de audioconferência de um usuário é alterado para a Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar ou desabilitar o envio de emails aos usuários

Você pode usar o Centro de administração do Skype for Business ou o Windows PowerShell para habilitar ou desabilitar os emails enviados aos usuários.

 
![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**
    
1. No Centro **de administração do Skype for Business,** na navegação à esquerda, clique em **Audioconferência.**
    
2. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.
    
3. Clique em **Salvar**.
    
    > [!TIP]
    > Você também pode enviar emails para um usuário com as configurações de audioconferência indo para Usuários de Audioconferência, selecionando o usuário e clicando em Enviar informações de conferência  >   **por email.**  Se você fizer isso, um email será enviado que inclua apenas a ID de conferência e o número de telefone de conferência, mas não o PIN.  Consulte [Enviar um email para um usuário com suas informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md) para obter mais informações.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Usando o Windows PowerShell**
  
- Execute o seguinte para desabilitar o envio de emails: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Para ajuda com esse cmdlet, consulte [Set-CsOnlineDialInConferencingTenantSettings.](https://go.microsoft.com/fwlink/?LinkId=715757)
    
## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Quando emails automáticos são desabilitados, você ainda pode disparar manualmente o envio de um email com a ID de conferência e o número de telefone usando o Centro de administração do Skype for Business. No entanto, se você fizer isso, o PIN não será incluído. Se você quiser redefinir o PIN de audioconferência e o envio de emails estiver desabilitado, será necessário enviá-lo para o usuário de outra maneira.
    
- O envio de emails a seus usuários pode ser desabilitado usando o Centro de administração do Skype for Business ou o Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Você pode usar esses cmdlets para economizar tempo ou automatizar isso.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o Microsoft 365 ou o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Emails enviados para os usuários quando suas configurações de Audioconferência mudarem](emails-sent-to-users-when-their-settings-change.md)

[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md)


