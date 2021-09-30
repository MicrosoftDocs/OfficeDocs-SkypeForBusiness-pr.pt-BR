---
title: Redefinir o PIN de Audioconferência no Skype for Business Online
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Descubra o que você deve saber sobre PINs e como redefini-los no Skype for Business Online. '
ms.openlocfilehash: c3e33655a5d92dbc24522611a1551c4240c4c228
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011925"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Redefinir o PIN de Audioconferência no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Para obter informações sobre a redefinição de PINs de Audioconferência no Microsoft Teams, consulte [Redefinir o PIN de Audioconferência no Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Um PIN é um código que é criado para cada Skype for Business usuário habilitado para audioconferência. Os PINs de audioconferência são usados pelos organizadores da reunião para identificar que eles são o organizador da reunião e permitir que eles iniciem uma reunião por telefone. Se eles usarem o Skype for Business para iniciar a reunião, um PIN não será necessário. Se os usuários esquecerem o PIN e não puderem encontrá-lo no email que foi enviado para eles quando eles foram habilitados para audioconferência, um administrador pode redefinir seu PIN ou pode redefinir seu próprio PIN.
  
As reuniões podem ser iniciadas quando um usuário autenticado ingressar usando o aplicativo Skype for Business ou quando o organizador ingressar com seu PIN pelo telefone. Se a reunião exigir um PIN para ser iniciada, os usuários que entrarem por telefone serão colocados no lobby e esperarão ouvindo música até que a reunião seja iniciada. Se o organizador de uma reunião não exigir um PIN para iniciar a reunião por telefone, os chamadores não precisarão fornecer um PIN para participar.
  
## <a name="reset-a-users-pin"></a>Redefinir o PIN de um usuário

1. Entre com sua conta de trabalho ou de estudante.
    
2. Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique **em Audioconferência**.
    
3. Clique em **Usuários**, selecione o usuário para o que você deseja redefinir o PIN.
    
4. No painel Ação, em **PIN,** clique em **Redefinir**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Faça com que um usuário redefina seu próprio PIN

Um usuário pode redefinir um PIN usando a opção **Redefinir PIN** na página **Conferência discada** . Essa página pode ser acessada de três formas:

* Em um navegador, vá até [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* No Skype for Business, clique na seta **Mostrar Menu** ao lado de **Opções** e, em seguida, clique em **Ferramentas** > **Configurações de conferência discada**.
* No Skype for Business, clique em **Opções**, depois em **Encaminhamento de chamadas** no menu à esquerda e na seção **Mais configurações de chamadas** , clique em **Editar configurações online**. 

## <a name="what-else-should-you-know-about-pins"></a>O que mais você deve saber sobre PINs?

- Por motivos de segurança, o PIN só é mostrado para o administrador em uma ocasião: quando o PIN é redefinido. Depois que o PIN for redefinido por um administrador, o PIN será listado como ********** no centro de administração do **Skype for Business** e nos resultados quando eles usarem Get-CsCsOnlineDialInConfencingUser no Windows PowerShell.
    
- O envio automático de emails para usuários está habilitado por padrão e os usuários receberão um email com seu PIN quando eles estão habilitados para audioconferência ou quando o PIN for redefinido. Mas se você tiver desabilitado o envio automático de emails, um email de redefinição de PIN não será enviado para um usuário e você terá que enviar manualmente as informações de PIN para o usuário.
    
- Quando uma reunião for iniciada, todos os usuários do lobby serão conectados automaticamente. Por exemplo, se dois participantes tentarem participar de uma reunião antes que ela seja iniciada, eles serão colocados no lobby e esperarão ouvindo música. Quando o organizador da reunião participar usando o PIN por telefone, a reunião será iniciada e os participantes do lobby entrarão na reunião.
    
- A configuração padrão é não permitir que uma reunião seja iniciada por chamadores anônimos.
    
- Quando você habilita um usuário para audioconferência, por padrão, eles são enviados emails que incluem informações de conferência e seu PIN. O usuário deve ter uma caixa de correio Microsoft 365 ou Office 365, pois quando um PIN for redefinido, um novo PIN será enviado para o usuário por email para seu endereço SMTP principal (alias) definido para o usuário.
    
- Quando você configura serviços de audioconferência, você pode definir os dígitos que são necessários para os PINs em sua organização. PINs podem ter somente de 4 a 12 dígitos, o padrão é 5. Se você alterar a configuração do tamanho do PIN, a configuração será aplicada somente aos PINs recém-gerados e não será aplicada à configuração do PIN para usuários existentes que estejam habilitados para audioconferência. Consulte [Definir o tamanho do PIN para reuniões de Audioconferência.](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)
    
- O email por padrão será definido como o endereço SMTP Microsoft 365 ou Office 365 SMTP principal do usuário. Você pode enviar um email para um endereço não Microsoft 365 ou não Office 365, como um endereço de email do Hotmail ou MSN. Você pode substituir o endereço de email padrão usando o Windows PowerShell. Isso será útil se os usuários não têm uma caixa de correio Exchange no Microsoft 365 ou Office 365.
    
- Para substituir o endereço de usuário padrão para o qual o email é enviado, o administrador do locatário pode usar o seguinte cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". O parâmetro SendEmail é necessário para substituir o endereço de email do usuário.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Você pode definir o PIN de Amos Marble com:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que é suportado apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em Baixar e instalar o módulo [Teams PowerShell](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir a ID de conferência de um usuário](reset-a-conference-id-for-a-user.md)
