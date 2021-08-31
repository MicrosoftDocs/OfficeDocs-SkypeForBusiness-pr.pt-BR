---
title: Enviar um email para um usuário com sua Audioconferência no Skype for Business Online
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Envie um email aos usuários com suas informações de audioconferência no Skype for Business Online.
ms.openlocfilehash: 428ff78fe501200ef9607a03d76c034007517cf0
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727670"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Enviar um email para um usuário com suas informações de Audioconferência no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Para obter informações sobre como enviar informações de Audioconferência aos usuários no Microsoft Teams, consulte Enviar um email para um usuário com suas informações de [Audioconferência no Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

Às Skype for Business os usuários podem precisar que você envie suas informações de Audioconferência. Você pode fazer isso usando o centro de administração **Skype for Business** e clicando em Enviar informações de conferência por **email** sob as propriedades de um usuário. Quando você enviar esse email, ele conterá todas as informações de audioconferência, incluindo:
  
- O número de telefone ou de discagem da conferência para o usuário.
    
- A ID de conferência do usuário.
    
   
Veja um exemplo do email enviado:
  
![Email de conferência discado.](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com informações de audioconferência para um usuário

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Audioconferência,** clique **em Enviar informações de conferência no email**.

1. Entre com sua conta de trabalho ou de estudante.
    
2. Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique **em Audioconferência**.
    
3. Clique **em Usuários** e selecione o usuário.
    
4. No painel Ação, clique em **Enviar informações da conferência por email**.
    
> [!TIP]
> Você também pode enviar emails para o usuário com as configurações de audioconferência editando as propriedades do usuário e clicando em **Audioconferência** Enviar informações de conferência  >  **por email**. 

## <a name="what-else-should-you-know-about-this-email"></a>O que mais devo saber sobre esse email?

- Há vários emails enviados aos usuários em sua organização depois que eles são habilitados para audioconferência:
    
  - Quando uma **licença de Audioconferência** é atribuída a eles.
    
  - Quando você redefine manualmente o PIN de audioconferência do usuário.
    
  - Quando você redefine manualmente o ID de conferência do usuário.
    
  - Quando uma **licença de Audioconferência** é removida delas.
    
  - Quando o provedor de audioconferência para um usuário é alterado da Microsoft para outro provedor ou **Nenhum**.
    
  - Quando o provedor de audioconferência para um usuário é alterado para a Microsoft.
    
- Por padrão, o remetente dos emails será de Microsoft 365 ou Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Para fazer alterações no endereço de email que está enviando o email para os usuários, você deve:
    
  - Insira o endereço de email no parâmetro SendEmailFromAddress.
    
  - Defina o parâmetro SendEmailOverride como Verdadeiro.
    
  - Insira o nome de exibição de email no parâmetro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > [!OBSERVAçãO] Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado definido. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
    Para enviar um email para o usuário com suas informações de audioconferência, execute o seguinte:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
