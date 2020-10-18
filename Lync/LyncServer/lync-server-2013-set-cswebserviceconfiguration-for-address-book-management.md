---
title: 'Lync Server 2013: Set-CsWebServiceConfiguration para gerenciamento de catálogo de endereços'
description: 'Lync Server 2013: Set-CsWebServiceConfiguration para gerenciamento de catálogo de endereços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsWebServiceConfiguration for Address Book management
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48184572
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37dcd7676829c5a91e05667fa0ae0d74dc6f7dc1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575417"
---
# <a name="set-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="25ab1-103">Set-CsWebServiceConfiguration para gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25ab1-103">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25ab1-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="25ab1-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="25ab1-p101">Quem pode executar este cmdlet: por padrão, os membros do grupo a seguir estão autorizados a executar o cmdlet Set-CsWebServiceConfiguration localmente: RTCUniversalServerAdmins. Para retornar uma lista de todas as funções RBAC (controle de acesso baseado em função) que receberam a atribuição desse cmdlet (incluindo qualquer função RBAC personalizada criada por você), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="25ab1-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Set-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

<span data-ttu-id="25ab1-107">O cmdlet Set-CsWebServiceConfiguration permite ao administrador redefinir um atributo existente na configuração dos serviços da Web.</span><span class="sxs-lookup"><span data-stu-id="25ab1-107">The Set-CsWebServiceConfiguration cmdlet allows the administrator to redefine an existing attribute in the configuration of the Web Services.</span></span>

<span data-ttu-id="25ab1-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="25ab1-108">For example:</span></span>

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

<div>

## <a name="see-also"></a><span data-ttu-id="25ab1-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="25ab1-109">See Also</span></span>


[<span data-ttu-id="25ab1-110">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="25ab1-110">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

