---
title: Usar o PowerShell para controlar o acesso de convidados a uma equipe
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
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
ms.openlocfilehash: 0b429d4e2411e697c4e3357ebd7b5fc66ab27376
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2019
ms.locfileid: "35220882"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="0afa1-103">Usar o PowerShell para controlar o acesso de convidados a uma equipe</span><span class="sxs-lookup"><span data-stu-id="0afa1-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="0afa1-104">Além de usar o centro de administração do Microsoft 365 e o portal do Azure Active Directory (Azure AD), você pode usar o Windows PowerShell para controlar o acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="0afa1-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="0afa1-105">Com o PowerShell, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0afa1-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="0afa1-106">Permitir ou bloquear o acesso de convidados a todas as equipes e grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="0afa1-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="0afa1-107">Permitir que os convidados sejam adicionados a todas as equipes e grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="0afa1-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="0afa1-108">Permitir ou bloquear usuários convidados de uma equipe ou grupo do Office 365 específico</span><span class="sxs-lookup"><span data-stu-id="0afa1-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="0afa1-109">Para obter detalhes, consulte "usar o PowerShell para controlar o acesso de convidado" em [gerenciar o acesso de convidados nos grupos do Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span><span class="sxs-lookup"><span data-stu-id="0afa1-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>
  
<span data-ttu-id="0afa1-110">Você também pode usar o PowerShell para permitir ou bloquear um usuário convidado com base no seu domínio.</span><span class="sxs-lookup"><span data-stu-id="0afa1-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="0afa1-111">Por exemplo, digamos que a sua empresa (Contoso) tem uma parceria com outra empresa (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="0afa1-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="0afa1-112">Você pode adicionar a Fabrikam na sua lista de permissões para que seus usuários possam adicionar esses convidados aos seus grupos.</span><span class="sxs-lookup"><span data-stu-id="0afa1-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="0afa1-113">Para obter mais informações, consulte [permitir/bloquear o acesso de convidados a grupos do Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="0afa1-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="0afa1-114">Se quiser bloquear convidados no Microsoft Teams e ainda quiser permitir que eles acessem sites do SharePoint, você pode usar cmdlets do PowerShell do Azure AD para desabilitar o parâmetro AllowGuestsToAccessGroups no objeto Company, pressupondo que o compartilhamento externo esteja ativado para sites do SharePoint .</span><span class="sxs-lookup"><span data-stu-id="0afa1-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="0afa1-115">Acesso de convidado versus acesso externo</span><span class="sxs-lookup"><span data-stu-id="0afa1-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
