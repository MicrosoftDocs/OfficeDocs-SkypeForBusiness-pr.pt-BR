---
title: Habilitar ou desabilitar o envio de emails quando a alteração de configurações de conferência de áudio nos Teams da Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a habilitar ou desabilitar Skype enviem emails para usuários quando configurações como o pin é alterado ou as alterações de número de conferência padrão no Microsoft Teams. '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892498"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Habilitar ou desabilitar o envio de emails quando a alteração de configurações de conferência de áudio nos Teams da Microsoft

Os usuários são notificados automaticamente por email quando estiverem habilitados para conferência de áudio. Pode haver momentos, no entanto, quando você deseja reduzir o número de emails que serão enviadas aos usuários do Microsoft Teams. Nesses casos, você pode desabilitar o envio de email.
  
Se você desabilitar o envio de emails, emails de conferência de áudio não serão enviadas aos seus usuários, incluindo emails para quando os usuários estão habilitados ou desabilitados para conferências de áudio, quando o seu PIN é redefinido e quando as alterações no número de telefone a ID de conferência e a conferência padrão .
  
Aqui está um exemplo de email enviada aos usuários quando eles estão habilitados para conferência de áudio:
  
![Email de conferência de áudio](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quando os emails são enviados para seus usuários?

- Há vários emails que serão enviadas aos usuários em sua organização depois que eles estão habilitados para conferência de áudio:
    
  - Quando uma licença de **Conferência de áudio** é atribuída a eles.
    
  - Quando você redefinir manualmente os serviços de audioconferência PIN do usuário.
    
  - Quando você redefine manualmente o ID de conferência do usuário.
    
  - Quando a licença de **Conferência de áudio** seja removida deles.
    
  - Quando o provedor de serviços de audioconferência de um usuário for alterado da Microsoft para outro provedor ou **Nenhum**.
    
  - Quando o provedor de serviços de audioconferência de um usuário é alterado para Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar ou desabilitar o email que está sendo enviado a usuários

Você pode usar o Microsoft Teams ou o Windows PowerShell para habilitar ou desabilitar o email enviado aos usuários.

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**
1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**. 

3. No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de discagem**.

4. Clique em **Salvar**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Usando o Windows PowerShell**
  
Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.

    
## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
  
## <a name="related-topics"></a>Tópicos relacionados

[Emails enviados aos usuários ao alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


