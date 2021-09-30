---
title: Habilitar ou desabilitar o envio de emails quando as configurações de Audioconferência mudarem no Skype for Business Online
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 9deb04e418d00171375aec34ca873a89c8a31cdf
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011725"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Habilitar ou desabilitar o envio de emails quando as configurações de Audioconferência mudarem no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Se você deseja habilitar ou desabilitar o envio de emails Microsoft Teams, consulte Habilitar ou desabilitar o envio de emails quando as configurações de [Audioconferência](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)mudarem em Microsoft Teams .

Os usuários são automaticamente notificados por email quando estão habilitados para Audioconferência. No entanto, pode haver momentos em que você deseja reduzir o número de emails enviados para Skype for Business usuários. Nesses casos, você pode desabilitar o envio de emails.
  
Se você desabilitar o envio de emails, os emails de Audioconferência não serão enviados para seus usuários, incluindo emails para quando os usuários estão habilitados ou desabilitados para a audioconferência, quando o PIN é redefinido e quando a ID da conferência e o número de telefone de conferência padrão são trocados.
  
Aqui está um exemplo do email que é enviado aos usuários quando eles estão habilitados para Audioconferência:
  
![Email de audioconferência.](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quando os emails são enviados para seus usuários?

- Há vários emails enviados aos usuários em sua organização depois que eles são habilitados para audioconferência:
    
  - Quando uma **licença de Audioconferência** é atribuída a eles.
    
  - Quando você redefine manualmente o PIN de audioconferência do usuário.
    
  - Quando você redefine manualmente o ID de conferência do usuário.
    
  - Quando a **licença de Audioconferência** é removida delas.
    
  - Quando o provedor de audioconferência de um usuário é alterado da Microsoft para outro provedor ou **Nenhum**.
    
  - Quando o provedor de audioconferência de um usuário é alterado para a Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar ou desabilitar o envio de emails aos usuários

Você pode usar o Skype for Business de administração ou Windows PowerShell para habilitar ou desabilitar emails enviados aos usuários.

 
![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração**
    
1. No centro **Skype for Business de** administração , na navegação à esquerda, clique **em Audioconferência**.
    
2. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.
    
3. Clique em **Salvar**.
    
    > [!TIP]
    > Você também pode enviar emails para um usuário com as configurações de audioconferência indo para **Usuários** de Audioconferência, selecionando o usuário e clicando em Enviar informações de conferência  >   **por email**.  Se você fizer isso, um email será enviado que inclui apenas a ID da conferência e o número de telefone de conferência, mas não o PIN.  Confira [Enviar um email para um usuário com suas informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md) para obter mais informações.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Usando Windows PowerShell**
  
- Execute o seguinte para desabilitar o envio de emails: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Para ajudar com esse cmdlet, consulte [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).
    
## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Quando emails automáticos são desabilitados, você ainda pode disparar manualmente o envio de um email com a ID da conferência e o número de telefone usando o centro de administração Skype for Business de conferência. No entanto, se você fizer isso, o PIN não será incluído. Se você quiser redefinir o PIN de audioconferência e o envio de emails estiver desabilitado, você precisará enviá-lo para o usuário de outra maneira.
    
- O envio de emails a seus usuários pode ser desabilitado usando o Centro de administração do Skype for Business ou o Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Você pode usar esses cmdlets para economizar tempo ou automatizar isso.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que é suportado apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em Baixar e instalar o módulo [Teams PowerShell](https://go.microsoft.com/fwlink/?LinkId=294688)(.. /set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Emails enviados aos usuários quando suas configurações de Audioconferência mudam](emails-sent-to-users-when-their-settings-change.md)

[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md)
