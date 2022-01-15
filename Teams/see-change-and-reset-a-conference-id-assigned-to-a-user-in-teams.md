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
description: Saiba como atribuir uma ID de conferência a um usuário no Microsoft Teams e quais os parâmetros de IDs de conferência devem ser.
ms.openlocfilehash: 89b74dc97206f064cd88c30e69ed4b3752c19e08
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055122"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Exibir e redefinir uma ID de conferência atribuída a um usuário em Microsoft Teams

Uma ID de conferência é atribuída automaticamente a um usuário Microsoft Teams quando está configurada para Audioconferência no Microsoft 365 ou Office 365 e usa a Microsoft como provedor de audioconferência. A ID da conferência atribuída é enviada no convite da reunião quando a reunião é agendada. Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva.
  
Embora uma ID de conferência seja criada e atribuída automaticamente a um usuário, pode haver momentos em que um usuário não deseja usá-la e você deseja defini-la como um determinado número, ou quando seus usuários não puderem se lembrar ou perderem a ID da conferência. Você pode usar o Microsoft Teams de administração ou Windows PowerShell para exibir, alterar e redefinir a ID da conferência.
  
Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN. Consulte [Redefinir uma ID](reset-a-conference-id-for-a-user-in-teams.md) de conferência para um usuário no Microsoft Teams para obter mais informações sobre como redefinir o PIN de um organizador de conferência.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Visualizar e redefinir as IDs de conferências

### <a name="to-view-the-conference-id"></a>Para exibir a ID da conferência

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>Exibir a ID da conferência usando o Microsoft Teams de administração

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Audioconferência,** procure em **ID da Conferência.**

    > [!TIP]
    > Você pode enviar todas as informações de conferência para o usuário em um email que inclui a ID da conferência e números de telefone de áudio clicando no **link** Enviar informações de conferência no email.
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>Exibir a ID da conferência usando Windows PowerShell

Consulte a [Microsoft Teams referência do PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.

### <a name="to-reset-the-conference-id"></a>Para redefinir a ID da conferência

É possível redefinir uma ID de conferência para um usuário se, por exemplo, ele a esquecer.
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>Redefinir a ID da conferência usando o Microsoft Teams de administração

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Audioconferência,** clique **em Redefinir a ID da conferência.**

4. Na janela **Redefinir a ID da** conferência, clique em **Redefinir**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>Redefinir a ID da conferência usando Windows PowerShell

Consulte a [Microsoft Teams referência do PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

> [!IMPORTANT]
> Depois que uma nova ID de conferência é criada ou uma é redefinida, a ID de conferência antiga não pode ser usada pelos chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites.

- A ID da conferência deve atender ao comprimento em dígitos definidos na ponte de audioconferência. Não é possível usar caracteres alfabéticos ou especiais em IDs de conferência; somente números podem ser usados.

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
