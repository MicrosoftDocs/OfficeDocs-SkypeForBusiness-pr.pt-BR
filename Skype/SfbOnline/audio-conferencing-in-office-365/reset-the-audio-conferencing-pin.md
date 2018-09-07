---
title: Redefinir o PIN de Audioconferência no Skype for Business Online
mms.author: tonysmit
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Descubra o que você deve saber sobre PINs e como redefini-los no Skype for Business Online. '
ms.openlocfilehash: 57431b51607f963f6dbd6da688e9bf7bd2758b53
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854291"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Redefinir o PIN de Audioconferência no Skype for Business Online

> [!Note]
> Para obter informações sobre a redefinição de PINs de Audioconferência no Microsoft Teams, consulte [Redefinir o PIN de Audioconferência no Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Um PIN é um código formado por números que são criados para cada usuário do Skype for Business que esteja habilitado para serviços de audioconferência. Os PINs de audioconferência são usados pelos organizadores da reunião para identificar que eles são os organizadores e permitir que eles iniciem uma reunião usando o telefone. Caso usem o aplicativo do Skype for Business para iniciar a reunião, o PIN não será necessário. Se os usuários esquecerem o PIN e não conseguirem encontrá-lo no e-mail que foi enviado quando eles foram habilitados para a audioconferência, um administrador poderá redefinir o PIN dos usuários ou redefinir seu próprio PIN.
  
As reuniões podem ser iniciadas quando um usuário autenticado participa usando o aplicativo do Skype for Business ou quando o organizador participa com seu PIN usando o telefone. Se a reunião exigir um PIN para ser iniciada, os usuários que entrarem por telefone serão colocados no lobby e esperarão ouvindo música até que a reunião seja iniciada. Se o organizador de uma reunião não exigir um PIN para iniciar a reunião por telefone, os chamadores não precisarão fornecer um PIN para participar.
  
## <a name="reset-a-users-pin"></a>Redefinir o PIN de um usuário

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá até o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação à esquerda, clique em **Audioconferência**.
    
3. Clique em **Usuários** e selecione o usuário cujo PIN você deseja redefinir.
    
4. No painel de Ação, em **PIN**, clique em **Redefinir**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Faça com que um usuário redefina seu próprio PIN

Um usuário pode redefinir um PIN usando a opção **Redefinir PIN** na página **Conferência discada** . Essa página pode ser acessada de três formas:

* Em um navegador, vá até [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* No Skype for Business, clique na seta **Mostrar Menu** ao lado de **Opções** e, em seguida, clique em **Ferramentas** > **Configurações de conferência discada**.
* No Skype for Business, clique em **Opções**, depois em **Encaminhamento de chamadas** no menu à esquerda e na seção **Mais configurações de chamadas** , clique em **Editar configurações online**. 

## <a name="what-else-should-you-know-about-pins"></a>O que mais você deve saber sobre PINs?

- Por motivos de segurança, o PIN só é mostrado para o administrador em uma ocasião: quando o PIN é redefinido. Depois que o PIN for redefinido por um administrador, ele será listado como *********** no **centro de administração do Skype for Business**  e nos resultados quando usarem o comando Get-CsCsOnlineDialInConfencingUser no Windows PowerShell.
    
- O envio automático de e-mails para usuários é ativado por padrão e os usuários receberão um e-mail com o PIN quando estiverem habilitados para audioconferência ou quando o PIN for redefinido. Entretanto, se você tiver desabilitado o envio automático de emails, o email de redefinição de PIN não será enviado para o usuário e você precisará enviar manualmente as informações de PIN para o usuário.
    
- Quando uma reunião for iniciada, todos os usuários do lobby serão conectados automaticamente. Por exemplo, se dois participantes tentarem participar de uma reunião antes que ela seja iniciada, eles serão colocados no lobby e esperarão ouvindo música. Quando o organizador da reunião participar usando o PIN por telefone, a reunião será iniciada e os participantes do lobby entrarão na reunião.
    
- A configuração padrão é não permitir que uma reunião seja iniciada por autores de chamadas anônimos.
    
- Quando você habilita um usuário para audioconferências, por padrão, ele recebe emails que incluem informações da conferência e seu PIN. O usuário deve ter uma caixa de correio do Office 365 porque, quando um PIN é redefinido, um novo PIN será enviado ao usuário por email para o endereço SMTP principal (alias) definido para o usuário.
    
- Quando você configura serviços de audioconferência, você pode definir os dígitos que são necessários para os PINs em sua organização. PINs podem ter de 4 a 12 dígitos - o padrão são 5 dígitos. Se você alterar a configuração do tamanho do PIN, a configuração será aplicada somente aos PINs recém-gerados e não será aplicada à configuração do PIN para usuários existentes que estejam habilitados para audioconferência. Consulte [Definir o tamanho do PIN para reuniões de Audioconferência](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Por padrão, o email será definido como o endereço SMTP principal do Office 365 do usuário. Você pode enviar um email para um endereço que não seja do Office 365, como um endereço de email do Hotmail ou do MSN. Você pode substituir o endereço de email padrão usando o Windows PowerShell. Isso é útil se os usuários não tiverem uma caixa de correio do Exchange no Office 365.
    
- Para substituir o endereço de usuário padrão para o qual o email é enviado, o administrador do locatário pode usar o seguinte cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". O parâmetro SendEmail é obrigatório para substituir o endereço de email do usuário.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Você pode definir o PIN do Amos Marble executando:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens de velocidade, simplicidade e produtividade em comparação ao uso exclusivo do centro de administração do Office 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir a ID de conferência de um usuário](reset-a-conference-id-for-a-user.md)
