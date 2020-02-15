---
title: 'Lync Server 2013: Get-CsAddressBookConfiguration para gerenciamento de catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d0129f32081b28e3baf11df2d5521778f5841e1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="01c6a-102">Get-CsAddressBookConfiguration para gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01c6a-102">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01c6a-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="01c6a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="01c6a-p101">Quem pode executar este cmdlet: por padrão, os membros do grupo a seguir estão autorizados a executar o cmdlet Get-CsAddressBookConfiguration localmente: RTCUniversalServerAdmins. Para retornar uma lista de todas as funções RBAC (controle de acesso baseado em função) que receberam a atribuição desse cmdlet (incluindo qualquer função RBAC personalizada criada por você), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="01c6a-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

<span data-ttu-id="01c6a-106">O cmdlet Get-CsAddressBookConfiguration retorna informações sobre uma configuração que já existe.</span><span class="sxs-lookup"><span data-stu-id="01c6a-106">The cmdlet Get-CsAddressBookConfiguration returns information about a configuration that already exists.</span></span>

<span data-ttu-id="01c6a-107">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="01c6a-107">For example:</span></span>

    Get-CsAddressBookConfiguration -Identity site:Redmond

<span data-ttu-id="01c6a-p102">Combinando a funcionalidade do CsAddressBookConfiguration Get e do Set CsAddressBookConfiguration, permite ao administrador definir quais configurações serão modificadas e aplicar as modificações. Por exemplo, isto combinado:</span><span class="sxs-lookup"><span data-stu-id="01c6a-p102">Combining the functionality of Get-CsAddressBookConfiguration and Set-CsAddressBookConfiguration allows the administrator to define which configurations to modify and then apply the modifications. For example, this combined:</span></span>

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

<span data-ttu-id="01c6a-110">Retorna todas as configurações em todos os sites e aplica RunTimeOfDay de 23h às configurações.</span><span class="sxs-lookup"><span data-stu-id="01c6a-110">Returns all configurations in all sites and applies the RunTimeOfDay of 23:00 hours to the configurations.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="01c6a-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="01c6a-111">See Also</span></span>


[<span data-ttu-id="01c6a-112">Get-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="01c6a-112">Get-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

