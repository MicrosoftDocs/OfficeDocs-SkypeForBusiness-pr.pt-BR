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
ms.openlocfilehash: 8cc418b050b254930a74db8b0894dc14ccc090e5
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014127"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Redefinir o ID de conferência de um usuário no Microsoft Teams

Uma ID de conferência dinâmico é incluída na parte inferior da reunião convites, juntamente com os números de telefone de discagem que podem ser usados por chamadores para efetuar uma chamada para uma reunião. Quando o usuário disca o número de telefone, o atendedor automático para a reunião pedirá que o chamador para inserir esta ID de conferência, de forma que eles podem participar da reunião.
  
> [!NOTE]
> Se seu provedor de conferência for Microsoft, IDs de conferência dos usuários são definidos para somente dinâmico por padrão. Infelizmente, não há nenhuma capacidade para alterá-lo a se tornar estáticas, como agora está sem suporte. IDs de conferência são definidas automaticamente apenas para usuários de Microsoft Teams habilitados para conferência de áudio. 


## <a name="resetting-the-conference-id-for-a-user"></a>Redefinir o ID de conferência de um usuário

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Em **Audioconferência** clique em **Redefinir ID de conferência**.

2. Na janela **Redefinir ID de conferência** , clique em **Redefinir**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Por padrão, os emails são enviados aos usuários, mas isso pode ser desativado.   

    
> [!NOTE]
> Após você redefinir o ID de conferência, um email com a nova ID de conferência será enviado ao usuário. Este email será enviado para o endereço de email primário, em muitos casos, suas caixas de correio do Office 365. O email contém a nova ID de conferência, números de telefone de discagem padrão e instruções para atualizar as reuniões existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>O que mais preciso saber?

- Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de discagem ao clicar em **Enviar informações de conferência no email** para o usuário na seção de **Conferência de áudio** . Isso não envia o PIN.
    
- Um ID de conferência contém sete dígitos e o tamanho não pode ser alterado.
    
- Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.
    
- [!IMPORTANTE] Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites. 

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md)
