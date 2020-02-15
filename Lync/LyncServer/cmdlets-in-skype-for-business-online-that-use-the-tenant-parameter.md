---
title: Cmdlets no Skype for Business online que usam o parâmetro locatário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 121133ce163b73bd0ddf49faa1db03ae352056d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42000926"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="af42f-102">Cmdlets no Skype for Business online que usam o parâmetro locatário</span><span class="sxs-lookup"><span data-stu-id="af42f-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="af42f-103">Ao modificar suas configurações de provedor público, você sempre precisa fornecer uma identidade de locatário; Isso é verdadeiro mesmo que você tenha apenas um único locatário.</span><span class="sxs-lookup"><span data-stu-id="af42f-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="af42f-104">Por exemplo, este comando define o Windows Live como o único provedor público com o qual os usuários têm permissão para se comunicar:</span><span class="sxs-lookup"><span data-stu-id="af42f-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="af42f-105">Felizmente, não é necessário digitar a ID do locatário (por exemplo, bf19b7db-6960-41e5-a139-2aa373474354) sempre que você executar um desses cmdlets.</span><span class="sxs-lookup"><span data-stu-id="af42f-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="af42f-106">Em vez disso, você pode recuperar a ID do locatário executando o cmdlet [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) , armazenando a ID do locatário em uma variável e usando essa variável ao chamar um dos outros cmdlets.</span><span class="sxs-lookup"><span data-stu-id="af42f-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="af42f-107">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="af42f-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="af42f-108">Como alternativa, você pode fazer isso em um único comando, recuperando a ID do locatário e canalizando esse valor para o cmdlet Set-CsTenantPublicProvider:</span><span class="sxs-lookup"><span data-stu-id="af42f-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="af42f-109">Você não precisa especificar a ID do locatário ao chamar o cmdlet **Get-CsTenant** .</span><span class="sxs-lookup"><span data-stu-id="af42f-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="af42f-110">Este comando retorna informações sobre o locatário:</span><span class="sxs-lookup"><span data-stu-id="af42f-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="af42f-111">Os cmdlets a seguir aceitam uma identidade de locatário.</span><span class="sxs-lookup"><span data-stu-id="af42f-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="af42f-112">No entanto, nesses casos, o parâmetro é opcional e não precisa ser inserido ao chamar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="af42f-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="af42f-113">Em vez disso, o Windows PowerShell inserirá efetivamente a identidade do locatário com base no locatário do Skype for Business online ao qual você está atualmente conectado:</span><span class="sxs-lookup"><span data-stu-id="af42f-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="af42f-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="af42f-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="af42f-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="af42f-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="af42f-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="af42f-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="af42f-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="af42f-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="af42f-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="af42f-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="af42f-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="af42f-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="af42f-120">Por exemplo, o cmdlet **Get-CsTenantFederationConfiguration** pode ser chamado usando este comando:</span><span class="sxs-lookup"><span data-stu-id="af42f-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="af42f-121">Embora não seja necessário, você pode incluir o parâmetro locatário ao chamar Get-CsTenantFederationConfiguration:</span><span class="sxs-lookup"><span data-stu-id="af42f-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="af42f-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="af42f-122">See Also</span></span>


[<span data-ttu-id="af42f-123">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="af42f-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="af42f-124">[Cmdlets do Skype for Business Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="af42f-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

