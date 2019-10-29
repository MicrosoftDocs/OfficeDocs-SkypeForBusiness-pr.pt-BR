---
title: Usar o PowerShell para controlar o acesso de convidados a uma equipe
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Use o PowerShell para permitir ou bloquear o acesso de convidados às equipes do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90ca96b6a28b1a94c375af0b4b4166da5bbee9e9
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753326"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="0c80c-103">Usar o PowerShell para controlar o acesso de convidados a uma equipe</span><span class="sxs-lookup"><span data-stu-id="0c80c-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="0c80c-104">Além de usar o centro de administração do Microsoft 365 e o portal do Azure Active Directory (Azure AD), você pode usar o Windows PowerShell para controlar o acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="0c80c-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="0c80c-105">Com o PowerShell, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0c80c-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="0c80c-106">Permitir ou bloquear o acesso de convidados a todas as equipes e grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="0c80c-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="0c80c-107">Permitir que os convidados sejam adicionados a todas as equipes e grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="0c80c-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="0c80c-108">Permitir ou bloquear usuários convidados de uma equipe ou grupo do Office 365 específico</span><span class="sxs-lookup"><span data-stu-id="0c80c-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="0c80c-109">Para obter detalhes, consulte "usar o PowerShell para controlar o acesso de convidado" em [gerenciar o acesso de convidados nos grupos do Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span><span class="sxs-lookup"><span data-stu-id="0c80c-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>

  
<span data-ttu-id="0c80c-110">Você também pode usar o PowerShell para permitir ou bloquear um usuário convidado com base no seu domínio.</span><span class="sxs-lookup"><span data-stu-id="0c80c-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="0c80c-111">Por exemplo, digamos que a sua empresa (Contoso) tem uma parceria com outra empresa (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="0c80c-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="0c80c-112">Você pode adicionar a Fabrikam na sua lista de permissões para que seus usuários possam adicionar esses convidados aos seus grupos.</span><span class="sxs-lookup"><span data-stu-id="0c80c-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="0c80c-113">Para obter mais informações, consulte [permitir/bloquear o acesso de convidados a grupos do Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="0c80c-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="0c80c-114">Se quiser bloquear convidados no Microsoft Teams e ainda quiser permitir que eles acessem sites do SharePoint, você pode usar cmdlets do PowerShell do Azure AD para desabilitar o parâmetro AllowGuestsToAccessGroups no objeto Company, pressupondo que o compartilhamento externo esteja ativado para sites do SharePoint .</span><span class="sxs-lookup"><span data-stu-id="0c80c-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="0c80c-115">Use o PowerShell para ativar ou desativar o acesso de convidados</span><span class="sxs-lookup"><span data-stu-id="0c80c-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="0c80c-116">Baixe o módulo PowerShell do Skype for Business Online em https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="0c80c-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="0c80c-117">Conecte uma sessão do PowerShell ao ponto de extremidade do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="0c80c-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="0c80c-118">Verifique sua configuração e se `AllowGuestUser` for `$False`, use o cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para defini-lo como `$True`.</span><span class="sxs-lookup"><span data-stu-id="0c80c-118">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
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
<span data-ttu-id="0c80c-119">Agora você pode ter usuários convidados no Teams da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0c80c-119">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="0c80c-120">Acesso de convidado versus acesso externo</span><span class="sxs-lookup"><span data-stu-id="0c80c-120">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
