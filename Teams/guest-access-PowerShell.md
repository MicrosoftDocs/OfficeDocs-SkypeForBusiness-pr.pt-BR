---
title: Usar o PowerShell para controlar o acesso de convidados a uma equipe
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba mais sobre como usar o PowerShell para permitir ou bloquear o acesso de convidados a todas as equipes ou equipes específicas do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e2833d1afedb975edf2532fb69c4fdbbdb31d4
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46655902"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Usar o PowerShell para controlar o acesso de convidados a uma equipe
================================================

Além de usar o centro de administração do Microsoft 365 e o portal do Azure Active Directory (Azure AD), você pode usar o Windows PowerShell para controlar o acesso de convidados. Com o PowerShell, você pode fazer o seguinte:
  
- Permitir ou bloquear o acesso de convidados a todas as equipes e grupos do Microsoft 365

- Permitir que os convidados sejam adicionados a todas as equipes e grupos do Microsoft 365

- Permitir ou bloquear usuários convidados de uma equipe específica ou um grupo do Microsoft 365

Para obter detalhes, consulte "usar o PowerShell para controlar o acesso de convidado" em [gerenciar o acesso de convidados nos grupos do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).

  
Você também pode usar o PowerShell para permitir ou bloquear um usuário convidado com base no seu domínio. Por exemplo, digamos que a sua empresa (Contoso) tem uma parceria com outra empresa (Fabrikam). Você pode adicionar a Fabrikam na sua lista de permissões para que seus usuários possam adicionar esses convidados aos seus grupos. Para obter mais informações, consulte [permitir/bloquear o acesso de convidados a grupos do Microsoft 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Se quiser bloquear convidados no Microsoft Teams e ainda quiser permitir que eles acessem sites do SharePoint, você pode usar cmdlets do PowerShell do Azure AD para desabilitar o parâmetro AllowGuestsToAccessGroups no objeto Company, pressupondo que o compartilhamento externo esteja ativado para sites do SharePoint.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Use o PowerShell para ativar ou desativar o acesso de convidados

1.  Baixe o módulo PowerShell do Skype for Business Online em https://www.microsoft.com/download/details.aspx?id=39366
 
2.  Conecte uma sessão do PowerShell ao ponto de extremidade do Skype for Business Online.

    ```powershell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  Verifique sua configuração e se `AllowGuestUser` for `$False`, use o cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para defini-lo como `$True`.

    ```powershell
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
Agora você pode ter usuários convidados no Teams da sua organização.


## <a name="guest-access-vs-external-access"></a>Acesso de convidado versus acesso externo

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
