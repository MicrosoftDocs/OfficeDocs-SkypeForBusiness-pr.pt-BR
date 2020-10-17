---
title: 'Lync Server 2013: Get-CsWebServiceConfiguration para gerenciamento de catálogo de endereços'
description: 'Lync Server 2013: Get-CsWebServiceConfiguration para gerenciamento de catálogo de endereços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb22d7607f9ac18cda9c8653374ae86839b033e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554637"
---
# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="93a59-103">Get-CsWebServiceConfiguration para gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93a59-103">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93a59-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="93a59-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="93a59-p101">Quem pode executar este cmdlet: por padrão, os membros dos seguintes grupos estão autorizados a executar o cmdlet Get-CsWebServiceConfiguration localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) que receberam a atribuição desse cmdlet (incluindo qualquer função RBAC personalizada criada por você), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="93a59-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsWebServiceConfiguration cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

<span data-ttu-id="93a59-p102">O Get-CsWebServiceConfiguration retorna as informações das configurações dos Serviços da Web sendo usadas em sua organização. De interesse do Serviço de Catálogo de Endereços está o status da função de Expansão da Lista de Distribuição. Se o atributo do EnableGroupExpansion for Verdadeiro, sua organização atualmente permite a expansão de grupo.</span><span class="sxs-lookup"><span data-stu-id="93a59-p102">Get-CsWebServiceConfiguration returns information of the Web Services configuration currently in use in your organization. Of interest to the Address Book Services is the status of Distribution List Expansion function. If the attribute EnableGroupExpansion is True, your organization currently allows group expansion.</span></span>

<span data-ttu-id="93a59-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="93a59-110">For example:</span></span>

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="93a59-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="93a59-111">See Also</span></span>


[<span data-ttu-id="93a59-112">Get-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="93a59-112">Get-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

