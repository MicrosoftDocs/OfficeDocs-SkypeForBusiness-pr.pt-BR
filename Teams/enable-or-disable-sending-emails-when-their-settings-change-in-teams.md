---
title: Ativar ou desativar o envio de e-mails quando alterar configurações de audioconferência no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como ativar ou desativar o Skype de enviar e-mails para usuários quando configurações, como alterações de PIN ou o número de conferência padrão, são alteradas no Microsoft Teams. '
ms.openlocfilehash: 3e26a9e430d00f4759af8c6aecaf625bfd2d0abc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298863"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Ativar ou desativar o envio de e-mails quando alterar configurações de audioconferência no Microsoft Teams

Os usuários são notificados automaticamente por e-mail quando são habilitados para audioconferência. Pode haver ocasiões, no entanto, em que você deseja reduzir o número de e-mails enviados aos usuários do Microsoft Teams. Nesses casos, você pode desabilitar o envio de e-mails.
  
Se você desabilitar o envio de e-mails, nenhum e-mail de audioconferência será enviado para os usuários, incluindo e-mails notificando quando o usuário está habilitado ou desabilitado para audioconferência, quando o PIN é redefinido ou quando o número de telefone padrão e o ID de conferência são alterados.
  
Aqui está um exemplo de e-mail enviado aos usuários habilitados para audioconferência:
  
![E-mail de audioconferência](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quando os e-mails são enviados aos seus usuários?

- Vários e-mails são enviados aos usuários da sua organização depois que são habilitados para a audioconferência:
    
  - Quando uma licença de **Audioconferência** é atribuída a eles.
    
  - Quando você redefine manualmente o PIN de audioconferência do usuário.
    
  - Quando você redefine manualmente o ID de conferência do usuário.
    
  - Quando a licença de **Audioconferência** deles é removida.
    
  - Quando o provedor de audioconferência de um usuário é alterado da Microsoft para outro provedor ou para **Nenhum**.
    
  - Quando o provedor de audioconferência de um usuário é alterado para a Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar ou desabilitar o envio de e-mails para os usuários

É possível usar o Microsoft Teams ou o Windows PowerShell para habilitar ou desabilitar o envio de e-mails para os usuários.

![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**. 

3. No painel **Configurações de ponte**, habilite ou desabilite **Enviar e-mails aos usuários automaticamente de suas configurações de discagem forem alteradas**.

4. Clique em **Salvar**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Usar o Windows PowerShell**
  
Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.

    
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
  
## <a name="related-topics"></a>Tópicos relacionados

[E-mails enviados para os usuários quando suas configurações de Audioconferência são alteradas](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


