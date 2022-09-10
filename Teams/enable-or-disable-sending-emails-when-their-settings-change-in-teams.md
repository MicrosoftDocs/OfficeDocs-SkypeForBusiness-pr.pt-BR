---
title: Email opções quando as configurações de Audioconferência são alteradas
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Saiba como habilitar ou desabilitar o Microsoft Teams de enviar emails aos usuários quando configurações como fixar alterações ou o número de conferência padrão mudar no Teams. '
ms.openlocfilehash: a5119d6f612ed083ac4e72ab52f6bb189af4c9d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642102"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Ativar ou desativar o envio de e-mails quando as configurações de audioconferência são alteradas no Microsoft Teams

Os usuários são notificados automaticamente por email quando estão habilitados para Audioconferência. No entanto, pode haver ocasiões em que você deseja reduzir o número de emails enviados aos usuários do Microsoft Teams. Nesses casos, você pode desabilitar o envio de emails.
  
Se você desabilitar o envio de emails, os emails de Audioconferência não serão enviados aos usuários, incluindo emails para quando os usuários estiverem habilitados ou desabilitados para audioconferência, quando o PIN for redefinido e quando a ID de conferência e o número de telefone de conferência padrão forem alterados.
  
Aqui está um exemplo do email que é enviado aos usuários quando eles estão habilitados para Audioconferência:
  
![Exemplo de uma mensagem de email de Audioconferência.](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quando os emails são enviados para seus usuários?

- Há vários emails que são enviados aos usuários em sua organização depois que eles são habilitados para audioconferência:

  - Quando uma **licença de Audioconferência** é atribuída a eles.

  - Quando você redefine manualmente o PIN de audioconferência do usuário.

  - Quando você redefine manualmente o ID de conferência do usuário.

  - Quando a **licença de Audioconferência** é removida delas.

  - Quando o provedor de audioconferência de um usuário é alterado da Microsoft para outro provedor ou **Nenhum**.

  - Quando o provedor de audioconferência de um usuário é alterado para a Microsoft.

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar ou desabilitar o envio de emails aos usuários

Você pode usar o Microsoft Teams ou Windows PowerShell para habilitar ou desabilitar emails enviados aos usuários.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.

2. Na parte superior da página **Pontes de** Conferência, clique em **Configurações de Ponte**.

3. No painel **configurações do Bridge** , habilite ou desabilite o envio automático de emails aos usuários se as configurações **de discagem mudarem**.

4. Clique em **Salvar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Usar o Windows PowerShell

Você também pode usar o módulo PowerShell do Microsoft Teams e executar:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Você pode usar [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) para gerenciar outras configurações para sua organização, incluindo email.

Consulte a [referência do PowerShell do Microsoft Teams](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a serem executadas. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="related-topics"></a>Tópicos relacionados

[Emails enviados aos usuários quando suas configurações de Audioconferência são alteradas](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Enviar um email para um usuário com suas informações de audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
