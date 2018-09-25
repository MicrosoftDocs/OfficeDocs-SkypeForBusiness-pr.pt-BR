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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como atribuir um ID de conferência a um usuário no Microsoft Teams e quais devem ser os parâmetros do ID de conferência. '
ms.openlocfilehash: 317216f84044eb404541a98d24c69b2f7fb61bc4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017081"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Visualizar e redefinir um ID de conferência atribuído a um usuário no Microsoft Teams

Uma ID de conferência é automaticamente atribuída a um usuário do Microsoft Teams quando eles estiverem configurados para conferência de áudio no Office 365 e usarem o Microsoft como um provedor de serviços de audioconferência. A ID de conferência atribuída é enviada no convite da reunião, quando a reunião foi agendada. Cada reunião que um usuário agenda será obtido atribuída uma ID de conferência exclusivas. 
  
Embora uma ID de conferência será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número, ou quando os usuários não conseguir se lembrar ou tem perdido sua ID de conferência. Você pode usar o Centro de administração do Microsoft Teams ou o Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.
  
Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN. Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user-in-teams.md). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Visualizar e redefinir as IDs de conferências

### <a name="to-view-the-conference-id"></a>Para visualizar o ID de conferência

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Em **Audioconferência**, veja **ID de conferência**.

    > [!TIP]
    > É possível enviar todas as informações da conferência para o usuário em um e-mail que contém o ID de conferência e os números de telefone de áudio, clicando em **Enviar informações da conferência por e-mail**.
  
**Usar o Windows PowerShell**

Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
  
### <a name="to-reset-the-conference-id"></a>Para redefinir o ID de conferência

É possível redefinir o ID de conferência para um usuário se ele esquecer o ID, por exemplo.
  
![teams-logo-30x30.png](media/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Em **Audio conferência**, clique em **Redefinir ID de conferência**.

4. Na janela **Redefinir ID de conferência** , clique em **Redefinir**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**Usar o Windows PowerShell**

Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.


## <a name="what-else-should-you-know"></a>O que mais você precisa saber?

   > [!IMPORTANT]
   >  Depois que uma nova ID de conferência é criada ou um é redefinido, o ID de conferência antigos não pode ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites. 
  
    
- A ID de conferência deve atender a duração em dígitos, defina a ponte de conferência de áudio. Você não pode usar caracteres alfabéticos ou especiais de conferência IDs; somente números podem ser usados.
    
- O ID de conferência de todos os seus usuários de audioconferência deve ter sete dígitos por padrão; o número de dígitos não pode ser alterado.
    
    
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

