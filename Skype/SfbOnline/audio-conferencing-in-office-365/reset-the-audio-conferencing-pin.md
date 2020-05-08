---
title: Redefinir o PIN da conferência de áudio no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Saiba o que você deve saber sobre PINs e como redefini-los no Skype for Business online. '
ms.openlocfilehash: 21e2742653e72919df0647c0539fdb335585cc84
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164690"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Redefinir o PIN da conferência de áudio no Skype for Business Online

> [!Note]
> Para obter informações sobre a redefinição de PINs de Audioconferência no Microsoft Teams, consulte [Redefinir o PIN de Audioconferência no Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing. Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone. If they use the Skype for Business app to start the meeting, a PIN isn't required. If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.
  
Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone. When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts. If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.
  
## <a name="reset-a-users-pin"></a>Redefinir o PIN de um usuário

1. Entre com sua conta corporativa ou de estudante.
    
2. Vá para o centro de administração > **Skype for Business**e, no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários**, selecione o usuário para o qual você deseja redefinir o PIN.
    
4. No painel Ação, em **PIN**, clique em **Redefinir**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Faça com que um usuário redefina seu próprio PIN

A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page. This page can be accessed in one of three ways:

* Em um navegador, vá até [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* No Skype for Business, clique na seta **Mostrar Menu** ao lado de **Opções** e, em seguida, clique em **Ferramentas** > **Configurações de conferência discada**.
* No Skype for Business, clique em **Opções**, depois em **Encaminhamento de chamadas** no menu à esquerda e na seção **Mais configurações de chamadas** , clique em **Editar configurações online**. 

## <a name="what-else-should-you-know-about-pins"></a>O que mais você deve saber sobre PINs?

- For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset. After the PIN is reset by an administrator, the PIN will be listed as *********** in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.
    
- Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.
    
- Quando uma reunião for iniciada, todos os usuários do lobby serão conectados automaticamente. Por exemplo, se dois participantes tentarem participar de uma reunião antes que ela seja iniciada, eles serão colocados no lobby e esperarão ouvindo música. Quando o organizador da reunião participar usando o PIN por telefone, a reunião será iniciada e os participantes do lobby entrarão na reunião.
    
- A configuração padrão é não permitir que uma reunião seja iniciada por chamadores anônimos.
    
- Por padrão, quando você habilita um usuário para videoconferência, ele recebe emails que incluem informações de conferência e seu PIN. O usuário deve ter uma caixa de correio do Microsoft 365 ou do Office 365, porque quando um PIN é redefinido, um novo PIN será enviado ao usuário em um email para o endereço SMTP principal (alias) definido para o usuário.
    
- When you set up audio conferencing, you set the digits that are required for the PINs in your organization. PINs can be from 4 to 12 digits - the default is 5. If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing. See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- O email por padrão será definido como o endereço SMTP principal do Microsoft 365 ou do Office 365 do usuário. Você pode enviar um email para um endereço que não seja do Microsoft 365 ou não do Office 365, como um endereço de email do hotmail ou do MSN. Você pode substituir o endereço de email padrão usando o Windows PowerShell. Isso é útil se os usuários não têm uma caixa de correio do Exchange no Microsoft 365 ou no Office 365.
    
- To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". The SendEmail parameter is required to override the email address of the user.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Você pode definir o PIN de Amos Marble com:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- O Windows PowerShell é tudo sobre o gerenciamento de usuários e o que os usuários podem fazer ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas para fazer. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configurações para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos tópicos a seguir:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir a ID de conferência de um usuário](reset-a-conference-id-for-a-user.md)
