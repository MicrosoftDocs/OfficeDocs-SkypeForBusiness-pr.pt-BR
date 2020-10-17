---
title: 'Lync Server 2013: Test-CsAddressBookWebQuery para gerenciamento de catálogo de endereços'
description: 'Lync Server 2013: Test-CsAddressBookWebQuery para gerenciamento de catálogo de endereços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7448733ed1477d36b887648154d66c96f9e6d0b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547437"
---
# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="e681f-103">Test-CsAddressBookWebQuery para gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e681f-103">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e681f-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e681f-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e681f-105">Quem pode executar este cmdlet: por padrão, os membros dos seguintes grupos são autorizados a executar o cmdlet Test-CsAddressBookWebQuery: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e681f-105">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="e681f-106">Para retornar uma lista de todas as funções RBAC que este cmdlet foi atribuído (incluindo qualquer função RBAC que você criou sozinho), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e681f-106">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="e681f-107">Semelhante à transação sintética de Test-CsAddressBookService, Test-CsAddressBookWebQuery executa uma consulta em relação à consulta à Web do catálogo de endereços para garantir que ela esteja funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="e681f-107">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="e681f-108">O cmdlet será conectado à autenticação de tíquete da Web e apresentará as credenciais especificadas em – usercredential.</span><span class="sxs-lookup"><span data-stu-id="e681f-108">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="e681f-109">Se for autenticado, o cmdlet apresentará as informações – TargetSipAddress.</span><span class="sxs-lookup"><span data-stu-id="e681f-109">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="e681f-110">O cmdlet deve relatar êxito se tiver conseguido recuperar as informações sobre o contato.</span><span class="sxs-lookup"><span data-stu-id="e681f-110">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="e681f-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e681f-111">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="e681f-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e681f-112">See Also</span></span>


[<span data-ttu-id="e681f-113">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="e681f-113">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

