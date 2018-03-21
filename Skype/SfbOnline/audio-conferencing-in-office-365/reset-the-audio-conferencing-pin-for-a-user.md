---
title: "Redefinir o PIN de conferência de áudio para um usuário"
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Find out what you should know about PINs and how to reset them for your users. '
ms.openlocfilehash: 2244e23c1eed616ba5bf4832e634e7a796dfd8b7
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="reset-the-audio-conferencing-pin-for-a-user"></a>Redefinir o PIN de conferência de áudio para um usuário

Um PIN é um código formado por números que são criados para cada Skype para usuário Teams da Microsoft e de negócios que esteja habilitado para serviços de audioconferência. PINs de conferência de áudio são usados pelo organizadores de reunião para identificar se eles são o organizador da reunião e permitir que eles se iniciar uma reunião por telefone. Se eles usarem o Skype para aplicativo de negócios ou Teams da Microsoft para iniciar a reunião, um PIN não é exigido. Se os usuários se esquecer seu PIN e eles não é possível encontrá-lo no email que foi enviado para acessá-los quando eles foram habilitados para conferência de áudio, o administrador precisará redefinir seu PIN. Um usuário não pode redefinir o próprio PIN.
  
Reuniões podem ser iniciados quando um usuário autenticado que ingressa usando um Skype para aplicativo de negócios ou Microsoft Teams ou quando o organizador ingressa com seu PIN por telefone. Se a reunião exigir um PIN para ser iniciada, os usuários que entrarem por telefone serão colocados no lobby e esperarão ouvindo música até que a reunião seja iniciada. Se o organizador de uma reunião não exigir um PIN para iniciar a reunião por telefone, os chamadores não precisarão fornecer um PIN para participar.
  
## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype para os negócios**e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários**, selecione o usuário que você deseja redefinir o PIN para.
    
4. No painel de ações, em **PIN**, clique em **Redefinir**.
    
## <a name="what-else-should-you-know-about-pins"></a>O que mais você deve saber sobre PINs?

- Por motivos de segurança, o PIN só é mostrado para o administrador em uma ocasião: quando o PIN é redefinido. Depois que o PIN é redefinido por um administrador, o PIN será listado como * * * no **Skype para centro de administração de negócios** e nos resultados da quando utilizarem a Get-CsCsOnlineDialInConfencingUser no Windows PowerShell.
    
- Automaticamente enviando emails para usuários é habilitado por padrão e os usuários receberão um email com o PIN quando elas são habilitadas para conferência de áudio ou quando o PIN ser redefinido. Mas, se você desabilitou automaticamente enviando e-mails, um email de redefinição PIN não será enviado a um usuário e você terá que enviar manualmente as informações de PIN para o usuário.
    
- Quando uma reunião for iniciada, todos os usuários do lobby serão conectados automaticamente. Por exemplo, se dois participantes tentarem participar de uma reunião antes que ela seja iniciada, eles serão colocados no lobby e esperarão ouvindo música. Quando o organizador da reunião participar usando o PIN por telefone, a reunião será iniciada e os participantes do lobby entrarão na reunião.
    
- A configuração padrão para não permitir uma reunião ser iniciado por chamadores anônimos.
    
- Quando você habilita um usuário para conferência de áudio, por padrão, eles são enviados emails que incluem informações de conferência e o PIN. O usuário deve ter uma caixa de correio do Office 365, como quando um PIN é redefinido, um novo PIN será enviado ao usuário no email para seu endereço SMTP principal (alias) que está definido para o usuário.
    
- Quando você configura serviços de audioconferência, você pode definir os dígitos que são necessários para os PINs em sua organização. PINs podem ter somente de 4 a 12 dígitos, o padrão é 5. Se você alterar a configuração de tamanho PIN, a configuração é aplicada apenas ao PINs recentemente gerados e não será aplicada à configuração de PIN para usuários existentes que estão habilitados para conferência de áudio. Consulte [definir o comprimento do PIN para reuniões de conferência de áudio](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- O email por padrão será definido para o endereço SMTP principal do Office 365 do usuário. Você pode enviar um email para um endereço de não - Office 365, como uma conta do Hotmail ou o endereço de email do MSN. Você pode substituir o endereço de email padrão usando o Windows PowerShell. Isso é útil se os usuários não possuem uma caixa de correio do Exchange no Office 365.
    
- Para substituir o endereço do usuário padrão onde o email é enviado, o administrador proprietário pode usar o seguinte cmdlet: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - EnviarEmail - SendEmailToAddress "u@hotmail.com". O parâmetro EnviarEmail é necessário para substituir o endereço de email do usuário.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Você pode definir o PIN de Amos Marble com:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir a ID de conferência de um usuário](reset-a-conference-id-for-a-user.md)
