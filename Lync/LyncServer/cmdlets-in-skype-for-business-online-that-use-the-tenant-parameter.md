---
title: Cmdlets no Skype for Business online que usam o parâmetro locatário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd58e375bcacfcb18cbc21e6ac352b8d98b56661
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233089"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="71950-102">Cmdlets no Skype for Business online que usam o parâmetro locatário</span><span class="sxs-lookup"><span data-stu-id="71950-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="71950-103">Ao modificar suas configurações de provedor público, você sempre precisa fornecer uma identidade de locatário; Isso é verdadeiro mesmo se você tiver apenas um único locatário.</span><span class="sxs-lookup"><span data-stu-id="71950-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="71950-104">Por exemplo, este comando define o Windows Live como o único provedor público com o qual os usuários podem se comunicar:</span><span class="sxs-lookup"><span data-stu-id="71950-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="71950-105">Felizmente, você não precisa digitar a ID do locatário (por exemplo, bf19b7db-6960-41e5-a139-2aa373474354) toda vez que executar um destes cmdlets.</span><span class="sxs-lookup"><span data-stu-id="71950-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="71950-106">Em vez disso, você pode recuperar a ID do locatário executando o cmdlet [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) , armazenando a ID do locatário em uma variável e, em seguida, usando essa variável quando você chama um dos outros cmdlets.</span><span class="sxs-lookup"><span data-stu-id="71950-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="71950-107">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="71950-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="71950-108">Você também pode fazer isso em um único comando ao recuperar a ID do locatário e, em seguida, canalizar esse valor para o cmdlet Set-CsTenantPublicProvider:</span><span class="sxs-lookup"><span data-stu-id="71950-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="71950-109">Você não precisa especificar a ID do locatário ao chamar o cmdlet **Get-CsTenant** .</span><span class="sxs-lookup"><span data-stu-id="71950-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="71950-110">Esse comando retorna informações sobre o seu locatário:</span><span class="sxs-lookup"><span data-stu-id="71950-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="71950-111">Os cmdlets a seguir aceitam uma identidade de locatário.</span><span class="sxs-lookup"><span data-stu-id="71950-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="71950-112">No entanto, nesses casos, o parâmetro é opcional e não precisa ser inserido ao chamar o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="71950-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="71950-113">Em vez disso, o Windows PowerShell inserirá efetivamente a identidade do locatário para você com base no locatário do Skype for Business online ao qual você está conectado:</span><span class="sxs-lookup"><span data-stu-id="71950-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="71950-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="71950-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="71950-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="71950-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="71950-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="71950-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="71950-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="71950-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="71950-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="71950-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="71950-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="71950-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="71950-120">Por exemplo, o cmdlet **Get-CsTenantFederationConfiguration** pode ser chamado usando este comando:</span><span class="sxs-lookup"><span data-stu-id="71950-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="71950-121">Embora não seja necessário, você pode incluir o parâmetro locatário ao chamar Get-CsTenantFederationConfiguration:</span><span class="sxs-lookup"><span data-stu-id="71950-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="71950-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="71950-122">See Also</span></span>


[<span data-ttu-id="71950-123">Identidades, escopos e locatários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="71950-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="71950-124">[Os cmdlets do Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="71950-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

