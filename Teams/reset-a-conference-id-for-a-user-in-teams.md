---
title: Redefinir o ID de conferência de um usuário no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Conheça as etapas para redefinir o ID de conferência de reunião de um usuário no Microsoft Teams e obtenha links para as ferramentas de atualização e migração da reunião. '
ms.openlocfilehash: a33ccf71d683fc7ae55011f502eda5182ed40268
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754701"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Redefinir o ID de conferência de um usuário no Microsoft Teams

Esse ID de conferência dinâmico é incluído no final dos convites de reunião, juntamente com os números de telefone que podem ser discados para que os chamadores participem de uma reunião. Quando o usuário discar para o número de telefone, um atendedor automático da reunião solicitará que ele insira esse ID de conferência para que possam participar da reunião.
  
> [!NOTE]
> Se o seu provedor de conferência for da Microsoft, os IDs de conferência dos usuários serão definidos como Somente dinâmicos por padrão. Infelizmente, não é possível alterá-lo para que se torne estático, pois isso não tem mais suporte. Os IDs de conferência são definidos automaticamente somente para usuários do Microsoft Teams habilitados para a audioconferência. 


## <a name="resetting-the-conference-id-for-a-user"></a>Redefinir o ID de conferência de um usuário

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Clique em **Editar**.

3. Em **Conferência de áudio** , clique em **Redefinir ID de conferência**.

2. Na janela **Redefinir ID de conferência** , clique em **Redefinir**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Por padrão, os emails são enviados aos usuários, mas isso pode ser desativado.   

    
> [!NOTE]
> Após você redefinir o ID de conferência, um email com a nova ID de conferência será enviado ao usuário. Este email será enviado para o endereço de email primário, em muitos casos, suas caixas de correio do Office 365. O email contém a nova ID de conferência, números de telefone de discagem padrão e instruções para atualizar as reuniões existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de discagem ao clicar em **Enviar informações de conferência no email** para o usuário na seção de **Conferência de áudio** . Isso não envia o PIN.
    
- Uma ID de conferência conterá 7 dígitos, e não é possível alterar seu comprimento.
    
- Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.
    
- [!IMPORTANTE]  Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites. 

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir o PIN de conferência de áudio](reset-the-audio-conferencing-pin-in-teams.md)
