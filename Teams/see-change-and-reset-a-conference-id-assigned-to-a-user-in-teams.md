---
title: Consultar, alterar e redefinir um ID de conferência atribuído a um usuário no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba como atribuir um ID de conferência a um usuário no Microsoft Teams e quais devem ser os parâmetros do ID de conferência. '
ms.openlocfilehash: fe166dc7b70c30e995bbbd6412a6baa6769c1bb6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41694116"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Visualizar e redefinir um ID de conferência atribuído a um usuário no Microsoft Teams

Um ID de conferência é atribuído automaticamente a um usuário do Microsoft Teams quando ele está configurado para audioconferência no Office 365 e usa a Microsoft como o provedor de audioconferência. O ID de conferência atribuído é enviado no convite da reunião quando ela é agendada. Cada reunião agendada por um usuário terá um ID de conferência exclusivo atribuído. 
  
Ainda que um ID de conferência seja automaticamente criado e atribuído ao usuário, poderá haver momentos em que o usuário não desejará usá-lo ou você desejará defini-lo como um número específico, ou quando os usuários se esquecem ou pedem o ID de conferência. É possível usar o centro de administração do Microsoft Teams ou o Windows PowerShell para visualizar, alterar e redefinir o ID de conferência.
  
Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN. Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user-in-teams.md). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Visualizar e redefinir as IDs de conferências

### <a name="to-view-the-conference-id"></a>Para visualizar o ID de conferência

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Em **Audioconferência**, veja **ID de conferência**.

    > [!TIP]
    > É possível enviar todas as informações da conferência para o usuário em um e-mail que contém o ID de conferência e os números de telefone de áudio, clicando em **Enviar informações da conferência por e-mail**.
  
**Usar o Windows PowerShell**

Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
  
### <a name="to-reset-the-conference-id"></a>Para redefinir o ID de conferência

É possível redefinir o ID de conferência para um usuário se ele esquecer o ID, por exemplo.
  
![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Em **Audio conferência**, clique em **Redefinir ID de conferência**.

4. Na janela **Redefinir ID de conferência**, clique em **Redefinir**. Um ID de conferência será criado automaticamente e um e-mail será enviado ao usuário com o novo ID de conferência.
  
**Usar o Windows PowerShell**

Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.


## <a name="what-else-should-you-know"></a>O que mais você precisa saber?

   > [!IMPORTANT]
   >  Depois que o ID de conferência é redefinido ou um novo é criado, o ID antigo não pode ser usado pelos chamadores. Você deve notificar os usuários para que reagendem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites. 
  
    
- O ID de conferência deve seguir o comprimento em dígitos definido na ponte de audioconferência. Não é possível usar letras e caracteres especiais nos IDs de conferência, somente números.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

