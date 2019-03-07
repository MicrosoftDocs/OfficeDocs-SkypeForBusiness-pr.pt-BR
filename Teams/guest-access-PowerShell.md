---
title: Usar o PowerShell para controlar o acesso de convidados a uma equipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Use o PowerShell para permitir ou bloquear o acesso de convidados às equipes do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9215cdbc360f1bda1d9d0ea75c1a9fe6ab0f458
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464584"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="f777c-103">Usar o PowerShell para controlar o acesso de convidados a uma equipe</span><span class="sxs-lookup"><span data-stu-id="f777c-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="f777c-104">Além de usar o centro de administração do Office 365 e o portal do Azure Active Directory, você pode usar o Windows PowerShell para controlar o acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="f777c-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="f777c-105">Com o PowerShell, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f777c-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="f777c-106">Permitir ou bloquear o acesso de convidados a todas as equipes e grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="f777c-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="f777c-107">Permitir que convidados sejam adicionados em todas as equipes e grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="f777c-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="f777c-108">Permitir ou bloquear usuários convidados de uma equipe ou grupo do Office 365 específico</span><span class="sxs-lookup"><span data-stu-id="f777c-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="f777c-109">Para obter detalhes, consulte a seção "Usar o PowerShell para controlar o acesso de convidado" na guia gerenciar de [acesso de convidado em grupos do Office 365](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="f777c-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="f777c-110">Você também pode usar o PowerShell para permitir ou bloquear um usuário convidado com base no seu domínio.</span><span class="sxs-lookup"><span data-stu-id="f777c-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="f777c-111">Por exemplo, digamos que a sua empresa (Contoso) tem uma parceria com outra empresa (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="f777c-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="f777c-112">Você pode adicionar a Fabrikam na sua lista de permissões para que seus usuários possam adicionar esses convidados aos seus grupos.</span><span class="sxs-lookup"><span data-stu-id="f777c-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="f777c-113">Para obter mais informações, consulte [Permitir/bloquear o acesso de convidados nos grupos do Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="f777c-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="f777c-114">Se desejar bloquear convidados nas equipes mas ainda permitir que os convidados acessem os sites do SharePoint, você pode usar os cmdlets Powershell do Azure Active Directory para desabilitar o parâmetro AllowGuestAccessToGroups no objeto da Empresa, presumindo que o compartilhamento externo esteja ativado para os sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f777c-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="f777c-115">Acesso de convidado versus acesso externo</span><span class="sxs-lookup"><span data-stu-id="f777c-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]