---
title: Emails enviados aos usuários quando suas configurações mudam no Skype for Business Online
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba mais sobre quais informações são enviadas automaticamente aos usuários por email quando suas configurações de conferência discada mudarem no Skype for Business Online. '
ms.openlocfilehash: b33fc6176d4103125432ebe0896ccab34e8fe269
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728030"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Emails enviados aos usuários quando suas configurações mudam no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Se você estiver procurando informações [automáticas](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)de email no Microsoft Teams, consulte Emails enviados aos usuários quando suas configurações mudarem em Microsoft Teams .

Os emails serão enviados automaticamente para usuários habilitados para [Audioconferência](set-up-audio-conferencing.md) usando a Microsoft como provedor de audioconferência.
  
Por padrão, há quatro tipos de email que serão enviados aos usuários habilitados para Audioconferência. No entanto, se você quiser limitar o número de emails enviados aos usuários, poderá desativar. A audioconferência Microsoft 365 ou Office 365 enviará emails para o email dos usuários quando:
  
- **Uma licença de Audioconferência é atribuída a eles ou quando você está alterando o provedor de audioconferência para a Microsoft.**
    
     Este email inclui a ID da conferência, o número de telefone de conferência padrão para as reuniões, o PIN de audioconferência para o usuário e as instruções e o link para usar a Ferramenta de Atualização de Reunião do Skype for Business Online usada para atualizar reuniões existentes para o usuário. Consulte [Atribuir Skype for Business licenças ou](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) Atribuir à Microsoft como provedor de [audioconferência.](assign-microsoft-as-the-audio-conferencing-provider.md)
    
    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar [IDs dinâmicas de Audioconferência em sua organização.](./reset-a-conference-id-for-a-user.md) 
  
    Aqui está um exemplo desse email:
    
     ![Skype for Business Verificar Licença.](../images/audio-conferencing-user-enabled.png)
  
    Você pode saber mais sobre as licenças do Skype for Business em [Licenciamento de complementos do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **A ID de conferência ou número de telefone de conferência padrão de um usuário for alterado.**
    
    Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário. Mas esse email não inclui o PIN de audioconferência do usuário. Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar [IDs dinâmicas de Audioconferência em sua organização.](./reset-a-conference-id-for-a-user.md) 
  
    Aqui está um exemplo desse email:
    
     ![As informações sobre conferência discada foram alteradas.](../images/audio-conferencing-info-change.png)
  
- **O PIN de audioconferência de um usuário é redefinido.**
    
    Este email contém o PIN de audioconferência do organizador, a ID de conferência existente e o número de telefone de conferência padrão para o usuário. Consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar [IDs dinâmicas de Audioconferência em sua organização.](./reset-a-conference-id-for-a-user.md) 
  
    Aqui está um exemplo desse email:
    
     ![PIN para conferência discada alterado.](../images/audio-conferencing-pin-has-changed.png)
  
- **A licença de um usuário é removida ou quando o provedor de audioconferência muda da Microsoft para outro provedor ou Nenhum.**
    
    Isso acontece quando a licença de **Audioconferência** é removida de um usuário ou ao alterar o provedor de audioconferência de um usuário da Microsoft para um provedor de audioconferência de terceiros ou ao definir o provedor como **Nenhum**. Este email contém as instruções e informações para o usuário usar Skype for Business Ferramenta de Atualização de Reunião Online para remover informações específicas de audioconferência, como o número de telefone de conferência padrão ou a ID de conferência.
    
    Consulte [Atribuir ou remover licenças para Microsoft 365 Apps para Pequenos e Médios negócios](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Aqui está um exemplo desse email:
    
     ![A conferência discada está desativada.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Alterar as mensagens de email enviadas a eles

Você pode fazer alterações no email que é enviado automaticamente aos usuários, incluindo o endereço de email e o nome de exibição incluído nas informações de contato *From.* Por padrão, o remetente dos emails será de Microsoft 365 ou Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10)) Para fazer alterações no endereço de email que está enviando o email para os usuários, você deve:
  
- Digite o endereço de email no parâmetro  _SendEmailFromAddress_.
    
- Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.
    
- De definir  _o parâmetro SendEmailOverride_ como  _True_.
    
Você pode fazer alterações no email enviado aos usuários, como o endereço de email de onde o email é enviado e o nome de exibição do email, executando:
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Se você quiser alterar as informações de endereço de email, você precisa se certificar de que as políticas de email de entrada do seu ambiente permitem emails que vêm do endereço personalizado especificado. Se você decidir substituir as informações de contato *De,* verifique se os emails são enviados corretamente aos usuários. Você pode fazer isso testando isso com um usuário em sua organização.
  
Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) para gerenciar outras configurações para sua organização, incluindo email.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>E se você não quiser que eles recebam emails?

Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença. Nesse caso, a ID da conferência, o número de telefone de conferência padrão e, o mais importante, o PIN de audioconferência não serão enviados ao usuário. Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.
  
Por padrão, os emails serão enviados para seus usuários, mas se você quiser impedir que eles recebam emails para audioconferência, você pode usar o centro de administração Skype for Business ou Windows PowerShell. 
 
![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png)  **Usando o Skype for Business de administração**
    
1. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Configurações** de ponte da Microsoft de audioconferência.  >  
    
2. Na página **Configurações de ponte da Microsoft,** selecione ou desempure Enviar emails automaticamente aos usuários se suas configurações de **audioconferência mudarem**. 
    
3. Clique em **Salvar**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Usando Windows PowerShell**
  
1. Execute os seguintes procedimentos para desabilitar o envio de email a todos os seus usuários:
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) para gerenciar outras configurações para sua organização, incluindo email.
  
## <a name="what-else-should-you-know-about-this-email"></a>O que mais devo saber sobre esse email?

- Para mais informações sobre como habilitar e desabilitar o envio de emails para seus usuários, consulte [Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Às vezes, os usuários perdem suas informações de áudio e você precisa ser capaz de enviar todas as informações de áudio para eles. Você pode fazer isso usando o centro de administração Skype for Business e clicando em Enviar informações de conferência por **email** nas propriedades de audioconferência para um usuário. Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md). No entanto, essas informações não incluem o PIN de audioconferência.
    
    Este é um exemplo de email que será enviado a eles:
    
     ![Email de conferência discado.](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Por padrão, o remetente dos emails será de Microsoft 365 ou Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md)
