---
title: 'Lync Server 2013: New-CsWebServiceConfiguration para gerenciamento de catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 434c9a7c4ded9516cd930bbaa9bba72873b15a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="11aa0-102">New-CsWebServiceConfiguration para o gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11aa0-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11aa0-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="11aa0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="11aa0-104">Quem pode executar este cmdlet: por padrão, os membros dos grupos a seguir estão autorizados a executar o cmdlet New-CsWebServiceConfiguration localmente: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="11aa0-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="11aa0-105">Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="11aa0-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="11aa0-106">O cmdlet New-CsWebServiceConfiguration define uma nova configuração para serviços Web em sua organização.</span><span class="sxs-lookup"><span data-stu-id="11aa0-106">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization.</span></span> <span data-ttu-id="11aa0-107">O escopo para a configuração de serviços Web só pode estar no nível do site ou do serviço.</span><span class="sxs-lookup"><span data-stu-id="11aa0-107">The scope for the Web Services configuration can only be at the site or service level.</span></span> <span data-ttu-id="11aa0-108">Não é possível criar uma nova configuração de serviços Web no nível global.</span><span class="sxs-lookup"><span data-stu-id="11aa0-108">It cannot create a new Web Services configuration at the global level.</span></span> <span data-ttu-id="11aa0-109">Especificamente o interesse do catálogo de endereços é o atributo EnableGroupExansion.</span><span class="sxs-lookup"><span data-stu-id="11aa0-109">Specifically of interest to the Address Book is the EnableGroupExansion attribute.</span></span> <span data-ttu-id="11aa0-110">Se definido como true, os serviços Web podem responder às solicitações de expansão de grupo.</span><span class="sxs-lookup"><span data-stu-id="11aa0-110">If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="11aa0-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="11aa0-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="11aa0-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="11aa0-112">See Also</span></span>


[<span data-ttu-id="11aa0-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="11aa0-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

