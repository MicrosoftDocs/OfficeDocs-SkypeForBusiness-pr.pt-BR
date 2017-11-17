---
title: Usar o PowerShell para controlar o acesso de convidados a uma equipe
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Use o PowerShell para permitir ou bloquear o acesso de convidados às equipes do Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 563a1a56449be289572020dc226df69795596d1c
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2017
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="2d22b-103">Usar o PowerShell para controlar o acesso de convidados a uma equipe</span><span class="sxs-lookup"><span data-stu-id="2d22b-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="2d22b-104">Além de usar o centro de administração do Office 365 e o portal do Azure Active Directory, você pode usar o Windows PowerShell para controlar o acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="2d22b-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="2d22b-105">Com o PowerShell, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2d22b-105">With PowerShell, you can do the following:</span></span>
  
  
   

- <span data-ttu-id="2d22b-106">Permitir ou bloquear o acesso de convidados a todas as equipes e grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="2d22b-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="2d22b-107">Permitir que convidados sejam adicionados em todas as equipes e grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="2d22b-107">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="2d22b-108">Permitir ou bloquear usuários convidados de uma equipe ou grupo do Office 365 específico</span><span class="sxs-lookup"><span data-stu-id="2d22b-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="2d22b-109">Para obter detalhes, consulte [Usar o PowerShell para controlar o acesso de convidados](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="2d22b-109">For more details, see [Use PowerShell to control guest access](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="2d22b-110">Você também pode usar o PowerShell para permitir ou bloquear um usuário convidado com base no seu domínio.</span><span class="sxs-lookup"><span data-stu-id="2d22b-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="2d22b-111">Por exemplo, digamos que a sua empresa (Contoso) tem uma parceria com outra empresa (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="2d22b-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="2d22b-112">Você pode adicionar a Fabrikam na sua lista de permissões para que seus usuários possam adicionar esses convidados aos seus grupos.</span><span class="sxs-lookup"><span data-stu-id="2d22b-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="2d22b-113">Para obter mais informações, consulte [Permitir/bloquear o acesso de convidados nos grupos do Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="2d22b-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
 
<span data-ttu-id="2d22b-114">Se desejar bloquear convidados nas equipes mas ainda permitir que os convidados acessem os sites do SharePoint, você pode usar os cmdlets Powershell do Azure Active Directory para desabilitar o parâmetro AllowGuestAccessToGroups no objeto da Empresa, presumindo que o compartilhamento externo esteja ativado para os sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2d22b-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   