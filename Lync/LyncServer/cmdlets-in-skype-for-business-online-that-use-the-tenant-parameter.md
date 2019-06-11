---
title: Cmdlets no Skype for Business online que usam o parâmetro locatário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa3b09e6f419c7425332427ccf4a4ff664b9e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836089"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="ed2b0-102">Cmdlets no Skype for Business online que usam o parâmetro locatário</span><span class="sxs-lookup"><span data-stu-id="ed2b0-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="ed2b0-103">Ao modificar suas configurações de provedor público, você sempre precisa fornecer uma identidade de locatário; Isso é verdadeiro mesmo se você tiver apenas um único locatário.</span><span class="sxs-lookup"><span data-stu-id="ed2b0-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="ed2b0-104">Por exemplo, este comando define o Windows Live como o único provedor público com o qual os usuários podem se comunicar:</span><span class="sxs-lookup"><span data-stu-id="ed2b0-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="ed2b0-105">Felizmente, você não precisa digitar a ID do locatário (por exemplo, bf19b7db-6960-41e5-a139-2aa373474354) toda vez que executar um destes cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ed2b0-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="ed2b0-106">Em vez disso, você pode recuperar a ID do locatário executando o cmdlet [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) , armazenando a ID do locatário em uma variável e, em seguida, usando essa variável quando você chama um dos outros cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ed2b0-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="ed2b0-107">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ed2b0-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="ed2b0-108">Você também pode fazer isso em um único comando ao recuperar a ID do locatário e, em seguida, canalizar esse valor para o cmdlet Set-CsTenantPublicProvider:</span><span class="sxs-lookup"><span data-stu-id="ed2b0-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="ed2b0-109">Você não precisa especificar a ID do locatário ao chamar o cmdlet **Get-CsTenant** .</span><span class="sxs-lookup"><span data-stu-id="ed2b0-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="ed2b0-110">Esse comando retorna informações sobre o seu locatário:</span><span class="sxs-lookup"><span data-stu-id="ed2b0-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="ed2b0-111">Os cmdlets a seguir aceitam uma identidade de locatário.</span><span class="sxs-lookup"><span data-stu-id="ed2b0-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="ed2b0-112">No entanto, nesses casos, o parâmetro é opcional e não precisa ser inserido ao chamar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ed2b0-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="ed2b0-113">Em vez disso, o Windows PowerShell inserirá efetivamente a identidade do locatário para você com base no locatário do Skype for Business online ao qual você está conectado:</span><span class="sxs-lookup"><span data-stu-id="ed2b0-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="ed2b0-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ed2b0-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ed2b0-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ed2b0-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ed2b0-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ed2b0-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ed2b0-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ed2b0-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ed2b0-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ed2b0-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ed2b0-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ed2b0-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="ed2b0-120">Por exemplo, o cmdlet **Get-CsTenantFederationConfiguration** pode ser chamado usando este comando:</span><span class="sxs-lookup"><span data-stu-id="ed2b0-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="ed2b0-121">Embora não seja necessário, você pode incluir o parâmetro locatário ao chamar Get-CsTenantFederationConfiguration:</span><span class="sxs-lookup"><span data-stu-id="ed2b0-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="ed2b0-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="ed2b0-122">See Also</span></span>


[<span data-ttu-id="ed2b0-123">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ed2b0-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="ed2b0-124">[Os cmdlets do Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ed2b0-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

