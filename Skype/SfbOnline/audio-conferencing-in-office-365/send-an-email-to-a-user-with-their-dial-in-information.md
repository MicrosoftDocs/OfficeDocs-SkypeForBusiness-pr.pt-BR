---
title: Enviar um email para um usuário com sua videoconferência no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: Envie um email aos seus usuários com as informações de videoconferência no Skype for Business online.
ms.openlocfilehash: b499bfb4734d46a671ff4c236b354630f7e0a284
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776806"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Enviar um email para um usuário com suas informações de audioconferência no Skype for Business Online

> [!Note]
> Para obter informações sobre o envio de informações de videoconferência a usuários no Microsoft Teams, consulte [enviar um email para um usuário com suas informações de audioconferência no Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

Às vezes, os usuários do Skype for Business talvez precisem enviar suas informações de conferência de áudio. Você pode fazer isso usando o **centro de administração do Skype for Business** e clicando em **enviar informações de conferência por e-mail** nas propriedades de um usuário. Quando você enviar este e-mail, ele conterá todas as informações de audioconferência, incluindo:
  
- O número de telefone ou de discagem da conferência para o usuário.
    
- A ID de conferência do usuário.
    
   
Aqui está um exemplo do e-mail enviado:
  
![Email para conferência discada](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com as informações de conferência de áudio para um usuário

1. Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **conferência de áudio**, clique em **enviar informações de conferência por email**.

1. Entre com sua conta corporativa ou de estudante.
    
2. Vá para o centro de administração > **Skype for Business**e, no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários**e selecione o usuário.
    
4. No painel Ação, clique em **Enviar informações da conferência por email**.
    
> [!TIP]
> Você também pode enviar emails para o usuário com as configurações de videoconferência editando as propriedades do usuário e clicando em **videoconferências** > **enviar informações de conferência por e-mail**. 

## <a name="what-else-should-you-know-about-this-email"></a>O que mais devo saber sobre esse email?

- Há vários emails enviados para os usuários em sua organização após serem habilitados para conferências de áudio:
    
  - Quando uma licença de **conferência de áudio** é atribuída a ele.
    
  - Quando você redefine manualmente o PIN de audioconferência de áudio do usuário.
    
  - Quando você redefine manualmente o ID de conferência do usuário.
    
  - Quando uma licença de **conferência de áudio** é removida.
    
  - Quando o provedor de serviços de audioconferência de um usuário for alterado da Microsoft para outro provedor ou **nenhum**.
    
  - Quando o provedor de serviços de audioconferência de um usuário for alterado para a Microsoft.
    
- Por padrão, o remetente dos emails será do Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=708983) . Para fazer alterações no endereço de email que está enviando o email aos usuários, você deve:
    
  - Digite o endereço de email no parâmetro SendEmailFromAddress.
    
  - Defina o parâmetro SendEmailOverride como Verdadeiro.
    
  - Digite o nome de exibição do email no parâmetro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > [!OBSERVAçãO] Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado definido. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Para enviar um email para o usuário com as informações da conferência de áudio, execute o seguinte:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. No Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar o trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
