---
title: Enviar um e-mail para um usuário com suas informações de audioconferência no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envie aos sus usuários um e-mail com as informações da audioconferência no Microsoft Teams.
ms.openlocfilehash: 3b1cb1eb4fcf654a4ab3d3cb227416b0cf700817
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347460"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Enviar um e-mail para um usuário com suas informações de audioconferência no Microsoft Teams

Em alguns casos, talvez seja necessário usuários Teams Microsoft a enviar-lhes suas informações de conferência de áudio. Você pode fazer isso clicando em **Enviar informações de conferência via email** sob as propriedades de um usuário. Quando você envia este email, ele irá conter todas as informações de conferência de áudio, incluindo:
  
- O número de telefone ou de discagem da conferência para o usuário.
    
- O ID de conferência do usuário.
    
   
Aqui está um exemplo do e-mail que é enviado:
  
![E-mail para conferência de discagem](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um e-mail com as informações da audioconferência para um usuário

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-and-skype-for-business-admin-center"></a>![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) Usando equipes da Microsoft e Skype para Business Admin Center

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, clique em **Enviar informações de conferência no email**.


## <a name="what-else-should-you-know-about-this-email"></a>O que mais devo saber sobre esse email?

- Há vários emails que serão enviadas aos usuários em sua organização depois que eles estão habilitados para conferência de áudio:
    
  - Quando uma licença de **Conferência de áudio** é atribuída a eles.
    
  - Quando você redefinir manualmente os serviços de audioconferência PIN do usuário.
    
  - Quando você redefine manualmente o ID de conferência do usuário.
    
  - Quando uma licença de **Conferência de áudio** seja removida deles.
    
  - Quando o provedor de serviços de audioconferência para um usuário mudou da Microsoft para outro provedor ou **Nenhum**.
    
  - Quando o provedor de serviços de audioconferência para um usuário é alterado para Microsoft.
    
- Por padrão, o remetente dos e-mails será do Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell. Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
