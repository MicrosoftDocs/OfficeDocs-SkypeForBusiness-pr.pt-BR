---
title: Enviar um email para um usuário com suas informações de discagem
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envie um email com suas informações de conferência de áudio para seus usuários.
ms.openlocfilehash: 28d3f83259033b5e587c299464a334710797e149
ms.sourcegitcommit: 411d59a92ad73555cf39d9c64822b24240b5af8a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2018
ms.locfileid: "20324119"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>Enviar um email para um usuário com suas informações de conferência de áudio

Em alguns casos, talvez seja necessário Skype para usuários corporativos ou Microsoft Teams a enviar-lhes suas informações de conferência de áudio. Você pode fazer isso usando o **Skype para centro de administração de negócios** e clicar em **Enviar informações de conferência via email** , sob as propriedades de um usuário. Quando você envia este email, ele irá conter todas as informações de conferência de áudio, incluindo:
  
- O número de telefone ou de discagem da conferência para o usuário.
    
- A ID de conferência do usuário.
    
   
Aqui está um exemplo do email que será enviado:
  
![Email para conferência discada](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com informações de conferência de áudio a um usuário

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, clique em **Enviar informações de conferência no email**.

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype para os negócios**e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários**e, em seguida, selecione o usuário.
    
4. No painel Ação, clique em **Enviar informações da conferência por email**.
    
> [!TIP]
> Você também pode enviar email para o usuário com as configurações de serviços de audioconferência editando as propriedades do usuário e, em seguida, clicando em **audioconferências** > **Enviar informações de conferência via email**. 

## <a name="what-else-should-you-know-about-this-email"></a>O que mais devo saber sobre esse email?

- Há vários emails que serão enviadas aos usuários em sua organização depois que eles estão habilitados para conferência de áudio:
    
  - Quando uma licença de **Conferência de áudio** é atribuída a eles.
    
  - Quando você redefinir manualmente os serviços de audioconferência PIN do usuário.
    
  - Quando você redefine manualmente o ID de conferência do usuário.
    
  - Quando uma licença de **Conferência de áudio** seja removida deles.
    
  - Quando o provedor de serviços de audioconferência para um usuário mudou da Microsoft para outro provedor ou **Nenhum**.
    
  - Quando o provedor de serviços de audioconferência para um usuário é alterado para Microsoft.
    
- Por padrão, o remetente dos e-mails será do Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Para fazer alterações para o endereço de email que está enviando email aos usuários, você deve:
    
  - Insira o endereço de email no parâmetro SendEmailFromAddress.
    
  - Defina o parâmetro SendEmailOverride como True.
    
  - Insira o nome de exibição do email no parâmetro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > [!OBSERVAçãO] Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado definido. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Para enviar um email para o usuário com suas informações de conferência de áudio, execute o seguinte:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. No Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar o trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
