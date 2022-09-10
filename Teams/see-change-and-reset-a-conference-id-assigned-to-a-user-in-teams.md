---
title: Ver, alterar e redefinir a ID de conferência de um usuário
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Saiba como atribuir uma ID de conferência a um usuário no Microsoft Teams e quais devem ser os parâmetros de IDs de conferência.
ms.openlocfilehash: 9ff068a8485f77531ba034ebeaab3e27e1ed42ef
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642112"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Exibir e redefinir uma ID de conferência atribuída a um usuário no Microsoft Teams

Uma ID de conferência é atribuída automaticamente a um usuário do Microsoft Teams quando ele está configurado para Audioconferência no Microsoft 365 ou Office 365 e usa a Microsoft como provedor de audioconferência. A ID de conferência atribuída é enviada no convite da reunião quando a reunião é agendada. Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva.
  
Embora uma ID de conferência seja criada automaticamente e atribuída a um usuário, pode haver ocasiões em que um usuário não deseja usar essa ID e você deseja defini-la como um determinado número, ou quando os usuários não se lembram ou perderam sua ID de conferência. Você pode usar o Centro de administração do Microsoft Teams ou Windows PowerShell para exibir, alterar e redefinir sua ID de conferência.
  
Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN. Consulte [Redefinir uma ID de conferência para um usuário no Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) para obter mais informações sobre como redefinir o PIN de um organizador de conferência.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Visualizar e redefinir as IDs de conferências

### <a name="to-view-the-conference-id"></a>Para exibir a ID da conferência

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>Exibir a ID de conferência usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, clique **em Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Audioconferência**, examine a **ID da Conferência**.

    > [!TIP]
    > Você pode enviar todas as informações de conferência para o usuário em um email que inclui a ID de conferência e os números de telefone de áudio clicando nas informações enviar conferência no link **de email** .
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>Exibir a ID de conferência usando Windows PowerShell

Consulte a [referência do PowerShell do Microsoft Teams](/powershell/module/teams/?view=teams-ps) para obter mais informações.

### <a name="to-reset-the-conference-id"></a>Para redefinir a ID de conferência

É possível redefinir uma ID de conferência para um usuário se, por exemplo, ele a esquecer.
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>Redefinir a ID de conferência usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, clique **em Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Audioconferência**, clique em **Redefinir ID de conferência**.

4. Na janela **Redefinir ID de conferência** , clique em **Redefinir**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>Redefinir a ID de conferência usando Windows PowerShell

Consulte a [referência do PowerShell do Microsoft Teams](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

> [!IMPORTANT]
> Depois que uma nova ID de conferência é criada ou uma é redefinida, a ID de conferência antiga não pode ser usada por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites.

- A ID de conferência deve atender ao comprimento em dígitos definidos na ponte de audioconferência. Você não pode usar caracteres alfabéticos ou especiais em IDs de conferência; somente números podem ser usados.

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a serem executadas. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Melhores maneiras de gerenciar o Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar Audioconferência no Microsoft 365 para Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
