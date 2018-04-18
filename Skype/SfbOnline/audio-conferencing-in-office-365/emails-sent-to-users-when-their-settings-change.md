---
title: Emails enviados aos usuários ao alteram suas configurações
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. '
ms.openlocfilehash: df4e85dbe0549035984a518ad378307a41740fa9
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="emails-sent-to-users-when-their-settings-change"></a>Emails enviados aos usuários ao alteram suas configurações

Emails serão enviados automaticamente para usuários que estão [habilitados para conferência de áudio](set-up-audio-conferencing.md) usando o Microsoft como um provedor de serviços de audioconferência.
  
Por padrão, há quatro tipos de email que será enviada para os usuários habilitados para conferência de áudio. No entanto, se desejar limitar o número de emails enviados aos usuários, você pode desativá-lo. Serviços de audioconferência no Office 365 enviará o email para seus usuários de email quando:
  
- **Uma licença de conferência de áudio é atribuída a eles ou quando você estiver alterando o provedor de serviços de audioconferência à Microsoft.**
    
     Este email inclui o ID de conferência, o número de telefone de conferência padrão para as reuniões, os serviços de audioconferência PIN para o usuário e as instruções e link usar o Skype para negócios Online Meeting Update Tool que é usado para atualizar as reuniões existentes para o usuário. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [Atribuir Microsoft como um provedor de serviços de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar as [IDs de conferência de áudio dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aqui está um exemplo desse email:
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    Você pode encontrar mais informações sobre Skype para licenciamento de negócios, conferindo [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **A ID de conferência ou número de telefone de conferência padrão de um usuário for alterado.**
    
    Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário. Mas este email não inclui serviços de audioconferência PIN do usuário. Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar as [IDs de conferência de áudio dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aqui está um exemplo desse email:
    
     ![As informações sobre conferência discada foram alteradas.](../images/audio-conferencing-info-change.png)
  
- **O PIN de um usuário de serviços de audioconferência é redefinido.**
    
    Este email contém serviços de audioconferência do organizador PIN, o ID de conferência existente e número de telefone de conferência padrão para o usuário. Veja [Redefinir o PIN de conferência de áudio para um usuário](reset-the-audio-conferencing-pin-for-a-user.md).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar as [IDs de conferência de áudio dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aqui está um exemplo desse email:
    
     ![PIN para conferência discada alterado.](../images/audio-conferencing-pin-has-changed.png)
  
- **Uma licença de usuário é removida ou quando o provedor de serviços de audioconferência altera da Microsoft para outro provedor ou nenhum.**
    
    Isso acontece quando a licença de **Conferência de áudio** é removida de um usuário ou quando a alteração do provedor de serviços de audioconferência de um usuário da Microsoft a um provedor de serviços de audioconferência de terceiros ou ao configurar o provedor como **Nenhum**. Este email contém as instruções e informações para o usuário usar o Skype para ferramenta de atualização de Reunião Online comercial para remover informações específicas de conferência de áudio, como o padrão ID de conferência telefônica número ou conferência.
    
    Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Aqui está um exemplo desse email:
    
     ![A conferência discada está desativada.](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Alterar as mensagens de email enviadas a eles

Você pode fazer alterações para email que será enviado automaticamente aos usuários, incluindo o endereço de email e o nome de exibição que está incluído nas informações de contato *do* . Por padrão, o remetente dos e-mails será do Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Para fazer alterações para o endereço de email que está enviando email aos usuários, você deve:
  
- Digite o endereço de email no parâmetro  _SendEmailFromAddress_.
    
- Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.
    
- Defina o parâmetro _SendEmailOverride_ como _True_.
    
Você pode fazer alterações para o email enviado aos usuários, como o endereço de email que o email é enviado de e o nome de exibição para o email, executando:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Se você deseja alterar as informações de endereço de email, será necessário certificar-se de que as políticas de email de entrada do seu ambiente permitem emails provenientes de personalizado especificado do endereço. Se você decidir substituir as informações de contato *do* , você deve verificar se os emails corretamente serão enviados aos usuários. Você pode fazer isso testando isso com um usuário em sua organização.
  
Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo email.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>E se você não quiser que eles recebam emails?

Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença. Neste caso, o ID de conferência, padrão o número de telefone de conferência e, mais importante, o seu PIN de conferência de áudio não será enviada ao usuário. Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.
  
Por padrão, emails serão enviadas aos seus usuários, mas se desejar impedir a email de recebimento para conferência de áudio, você pode usar o Microsoft Teams, o Skype para o Centro de administração de negócios, ou o Windows PowerShell. 

**Usando equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **Configurações de ponte**. 

3. No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de discagem**.

4. Clique em **Aplicar**.
  
**Usando o Skype para o Centro de administração de negócios**
    
1. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
2. Na página **configurações de ponte da Microsoft** , marque ou desmarque **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**. 
    
3. Clique em **Salvar**. 
    
**Usando o Windows PowerShell**
  
1. Execute os seguintes procedimentos para desabilitar o envio de email a todos os seus usuários:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo email.
  
## <a name="what-else-should-you-know-about-this-email"></a>O que mais devo saber sobre esse email?

- Para mais informações sobre como habilitar e desabilitar o envio de emails para seus usuários, consulte [Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Em alguns casos, os usuários perderão suas informações de áudio e você precisa ser capaz de enviar-lhes todas as suas informações de áudio para acessá-los. Você pode fazer isso usando o Skype para centro de administração de negócios e clicar em **Enviar informações de conferência via email** , sob as propriedades de conferência de áudio para um usuário. Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md). No entanto, essas informações não incluem o PIN de conferência de áudio.
    
    Este é um exemplo de email que será enviado a eles:
    
     ![Email para conferência discada](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Por padrão, o remetente dos e-mails será do Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md)
