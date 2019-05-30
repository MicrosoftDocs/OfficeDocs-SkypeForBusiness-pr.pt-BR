---
title: Habilitar ou desabilitar o envio de emails quando as configurações de conferência de áudio mudarem no Skype for Business Online
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: ac3f6b94f0ddb4410d89ecd95aef346eb32c9ff1
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494222"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Habilitar ou desabilitar o envio de emails quando as configurações de conferência de áudio mudarem no Skype for Business Online

> [!Note]
> Se você quiser habilitar ou desabilitar o envio de emails no Microsoft Teams, consulte [habilitar ou desabilitar o envio de emails quando as configurações de conferência de áudio mudarem no Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

Os usuários são notificados automaticamente por e-mail quando estão habilitados para videoconferências. No entanto, pode haver ocasiões em que você queira reduzir o número de emails enviados para os usuários do Skype for Business. Nesses casos, você pode desabilitar o envio de emails.
  
Se você desabilitar o envio de emails, os emails de audioconferência não serão enviados para seus usuários, incluindo emails para quando os usuários estiverem habilitados ou desabilitados para a conferência de áudio, quando o PIN for redefinido e quando a ID de conferência e o número de telefone de conferência padrão forem alterados .
  
Aqui está um exemplo do e-mail que é enviado aos usuários quando eles são habilitados para videoconferências:
  
![Email de audioconferência](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quando os emails são enviados para seus usuários?

- Há vários emails enviados para os usuários em sua organização após serem habilitados para conferências de áudio:
    
  - Quando uma licença de **conferência de áudio** é atribuída a ele.
    
  - Quando você redefine manualmente o PIN de audioconferência de áudio do usuário.
    
  - Quando você redefine manualmente o ID de conferência do usuário.
    
  - Quando a licença de **conferência de áudio** é removida.
    
  - Quando o provedor de audioconferência de um usuário for alterado da Microsoft para outro provedor ou **nenhum**.
    
  - Quando o provedor de audioconferência de um usuário for alterado para a Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar ou desabilitar o envio de emails para os usuários

Você pode usar o centro de administração do Skype for Business ou o Windows PowerShell para habilitar ou desabilitar o envio de emails para os usuários.

 
![Um ícone mostrando o logotipo](../images/sfb-logo-30x30.png) do Skype for Business **usando o centro de administração do Skype for Business**
    
1. No **centro de administração do Skype for Business**, no painel de navegação à esquerda, clique em **videoconferência de áudio**.
    
2. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.
    
3. Clique em **Salvar**.
    
    > [!TIP]
    > Você também pode enviar emails para um usuário com as configurações de videoconferência acessando**usuários**de **audioconferência** > , selecionando o usuário e clicando em **enviar informações de conferência por email**.  Se você fizer isso, será enviado um e-mail que inclui apenas a ID de conferência e o número de telefone de conferência, mas não o PIN.  Para obter mais informações, consulte [enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Usando o Windows PowerShell**
  
- Execute o seguinte para desabilitar o envio de emails: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Para obter ajuda com esse cmdlet, consulte [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Quando os emails automáticos estiverem desativados, você ainda poderá disparar manualmente o envio de um email com a ID de conferência e o número de telefone usando o centro de administração do Skype for Business. No entanto, se você fizer isso, o pino não será incluído. Se você quiser redefinir o PIN de audioconferência e enviar emails estiver desabilitado, será necessário enviá-lo para o usuário de outra maneira.
    
- O envio de emails a seus usuários pode ser desabilitado usando o Centro de administração do Skype for Business ou o Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Você pode usar esses cmdlets para economizar tempo ou automatizar isso.
    
  - [Get-Csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-Csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-Csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Office 365, como quando você está realizando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Emails enviados para os usuários quando as configurações de conferência de áudio mudam](emails-sent-to-users-when-their-settings-change.md)

[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md)


