---
title: Enviar um e-mail para um usuário com suas informações de audioconferência no Microsoft Teams
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
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envie aos sus usuários um e-mail com as informações da audioconferência no Microsoft Teams.
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892088"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Enviar um e-mail para um usuário com suas informações de audioconferência no Microsoft Teams

Às vezes, os usuários do Microsoft Teams podem precisar que você envie as informações da audioconferência. É possível fazer isso clicando em **Enviar informações de conferência por e-mail** nas propriedades de um usuário. O e-mail enviado conterá todas as informações da audioconferência, incluindo:
  
- O número de telefone ou de discagem da conferência para o usuário.
    
- O ID de conferência do usuário.
    
   
Aqui está um exemplo do e-mail que é enviado:
  
![E-mail para conferência de discagem](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um e-mail com as informações da audioconferência para um usuário

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Em **Audioconferência**, clique em **Enviar informações da conferência por e-mail**.


## <a name="what-else-should-you-know-about-this-email"></a>O que mais preciso saber sobre esse e-mail?

- Vários e-mails são enviados aos usuários da sua organização depois que são habilitados para a audioconferência:
    
  - Quando uma licença de **Audioconferência** é atribuída a eles.
    
  - Quando você redefine manualmente o PIN de audioconferência do usuário.
    
  - Quando você redefine manualmente o ID de conferência do usuário.
    
  - quando uma licença de **Audioconferência** é removida deles.
    
  - Quando o provedor de audioconferência de um usuário é transferido da Microsoft para outro provedor ou **Nenhum**.
    
  - Quando o provedor de audioconferência de um usuário for transferido para a Microsoft.
    
- Por padrão, o remetente dos e-mails será do Office 365, mas é possível alterar o endereço de e-mail e o nome exibido usando o Windows PowerShell. Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
