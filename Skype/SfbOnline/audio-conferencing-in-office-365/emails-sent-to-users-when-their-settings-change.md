---
title: Emails enviados para usuários quando as configurações forem alteradas no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Saiba quais informações são enviadas automaticamente para os usuários por e-mail quando as configurações de conferência discada forem alteradas no Skype for Business online. '
ms.openlocfilehash: acdc16a1af2666dcb84599fae31a910be83ac08f
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494282"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Emails enviados para usuários quando as configurações forem alteradas no Skype for Business Online

> [!Note]
> Se você estiver procurando por informações automáticas de email no Microsoft Teams, consulte [emails enviados para os usuários quando as configurações forem alteradas no Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).

Os emails serão enviados automaticamente para os usuários que estão [habilitados para conferência de áudio](set-up-audio-conferencing.md) usando a Microsoft como provedor de serviços de audioconferência.
  
Por padrão, há quatro tipos de email que serão enviados aos usuários que estão habilitados para videoconferências. No entanto, se quiser limitar o número de emails enviados para os usuários, você pode desativá-lo. A conferência de áudio no Office 365 enviará emails ao email dos usuários quando:
  
- **Uma licença de conferência de áudio é atribuída a eles ou quando você está alterando o provedor de serviços de audioconferência para a Microsoft.**
    
     Este e-mail inclui a ID de conferência, o número de telefone de conferência padrão para as reuniões, o PIN de audioconferência para o usuário e as instruções e o link para usar a ferramenta de atualização de reunião do Skype for Business online que é usada para atualizar reuniões existentes para o utilizador. Consulte [atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [atribuir a Microsoft como provedor de serviços de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar [IDs dinâmicas de audioconferência em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aqui está um exemplo desse email:
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    Você pode saber mais sobre as licenças do Skype for Business em [Licenciamento de complementos do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **A ID de conferência ou número de telefone de conferência padrão de um usuário for alterado.**
    
    Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário. Mas esse email não inclui o PIN de audioconferência do usuário. Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar [IDs dinâmicas de audioconferência em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aqui está um exemplo desse email:
    
     ![As informações sobre conferência discada foram alteradas.](../images/audio-conferencing-info-change.png)
  
- **O PIN de conferência de áudio de um usuário é redefinido.**
    
    Este e-mail contém o pino de audioconferência do organizador, a ID de conferência existente e o número de telefone de conferência padrão para o usuário. Consulte [redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar [IDs dinâmicas de audioconferência em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aqui está um exemplo desse email:
    
     ![PIN para conferência discada alterado.](../images/audio-conferencing-pin-has-changed.png)
  
- **A licença de um usuário é removida ou quando o provedor de serviços de audioconferência é alterado da Microsoft para outro provedor ou nenhum.**
    
    Isso acontece quando a licença de **conferência de áudio** é removida de um usuário ou ao alterar o provedor de serviços de audioconferência de um usuário da Microsoft para um provedor de serviços de audioconferência de terceiros ou quando o provedor é definido como **nenhum**. Este e-mail contém as instruções e informações para o usuário usar a ferramenta de atualização de reunião do Skype for Business online para remover informações específicas da conferência de áudio, como o número de telefone ou a ID de conferência padrão.
    
    Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Aqui está um exemplo desse email:
    
     ![A conferência discada está desativada.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Alterar as mensagens de email enviadas a eles

Você pode fazer alterações nos emails enviados automaticamente para os usuários, incluindo o endereço de email e o nome para exibição que está incluído nas informações *de contato do* remetente. Por padrão, o remetente dos emails será do Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) . Para fazer alterações no endereço de email que está enviando o email aos usuários, você deve:
  
- Digite o endereço de email no parâmetro  _SendEmailFromAddress_.
    
- Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.
    
- Defina o parâmetro _SendEmailOverride_ como _true_.
    
Você pode fazer alterações nos emails enviados para usuários, como o endereço de email do qual o email é enviado e o nome de exibição do email, executando:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Se você quiser alterar as informações do endereço de email, é preciso certificar-se de que as políticas de email de entrada do seu ambiente permitam os emails provenientes do endereço de especificado de personalizado. Se você decidir substituir as informações *de contato do* remetente, verifique se os emails são enviados corretamente para os usuários. Você pode fazer isso testando isso com um único usuário em sua organização.
  
Você pode usar o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações de sua organização, incluindo o email.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>E se você não quiser que eles recebam emails?

Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença. Nesse caso, a ID de conferência, o número de telefone de conferência padrão e, o mais importante, o PIN de audioconferência não será enviado ao usuário. Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.
  
Por padrão, os emails serão enviados aos seus usuários, mas se você quiser impedir que eles recebam emails para videoconferências, você pode usar o centro de administração do Skype for Business ou o Windows PowerShell. 
 
![Um ícone mostrando o logotipo](../images/sfb-logo-30x30.png)do Skype for Business**usando o centro de administração do Skype for Business**  
    
1. No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.
    
2. Na página **configurações da ponte da Microsoft** , marque ou desmarque **enviar emails automaticamente aos usuários se as configurações de conferência de áudio forem alteradas**. 
    
3. Clique em **Salvar**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Usando o Windows PowerShell**
  
1. Execute os seguintes procedimentos para desabilitar o envio de email a todos os seus usuários:
    
   ```
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

Você pode usar o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações de sua organização, incluindo o email.
  
## <a name="what-else-should-you-know-about-this-email"></a>O que mais devo saber sobre esse email?

- Para mais informações sobre como habilitar e desabilitar o envio de emails para seus usuários, consulte [Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Às vezes, os usuários perdem suas informações de áudio e você precisa ser capaz de enviar todas as informações de áudio para eles. Você pode fazer isso usando o centro de administração do Skype for Business e clicando em **enviar informações de conferência por e-mail** nas propriedades de audioconferência de áudio de um usuário. Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md). No entanto, essas informações não incluem o PIN de audioconferência.
    
    Este é um exemplo de email que será enviado a eles:
    
     ![Email para conferência discada](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Por padrão, o remetente dos emails será do Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
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

[Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md)
