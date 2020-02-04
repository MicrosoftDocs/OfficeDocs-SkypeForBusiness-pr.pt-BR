---
title: Remove-CsAddressBookConfiguration para gerenciamento de catálogo de endereços
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsAddressBookConfiguration for Address Book management
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429705(v=OCS.15)
ms:contentKeyID: 48184258
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de016366fe888a159a449f7840a0f6dca03c7075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="7b5fe-102">Remove-CsAddressBookConfiguration para gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b5fe-102">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b5fe-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7b5fe-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7b5fe-104">Quem pode executar este cmdlet: por padrão, os membros dos grupos a seguir estão autorizados a executar o cmdlet Remove-CsAddressBookConfiguration localmente: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7b5fe-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="7b5fe-105">Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7b5fe-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

<span data-ttu-id="7b5fe-106">Como o nome indica, remove-CsAddressBookConfiguration irá remover a configuração com base na identidade de site definida.</span><span class="sxs-lookup"><span data-stu-id="7b5fe-106">As the name implies, Remove-CsAddressBookConfiguration will remove the configuration based on the defined Site Identity.</span></span>

<span data-ttu-id="7b5fe-107">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7b5fe-107">For example:</span></span>

    Remove-CsAddressBookConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="7b5fe-108">Confira também</span><span class="sxs-lookup"><span data-stu-id="7b5fe-108">See Also</span></span>


<span data-ttu-id="7b5fe-109">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7b5fe-109">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

