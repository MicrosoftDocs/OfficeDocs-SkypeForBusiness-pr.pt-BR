---
title: 'Lync Server 2013: New-CsAddressBookConfiguration para gerenciamento de catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69c1ea9c68dfacb68ada70d4f7643b2777f062f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="74fa6-102">New-CsAddressBookConfiguration para o gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74fa6-102">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74fa6-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="74fa6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="74fa6-104">Quem pode executar este cmdlet: por padrão, os membros dos grupos a seguir estão autorizados a executar o cmdlet New-CsAddressBookConfiguration localmente: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="74fa6-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="74fa6-105">Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="74fa6-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

<span data-ttu-id="74fa6-106">O cmdlet New-CsAddressBookConfiguration cria uma nova configuração para gerenciar o comportamento do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="74fa6-106">The New-CsAddressBookConfiguration cmdlet creates a new configuration to manage the behavior of the Address book.</span></span> <span data-ttu-id="74fa6-107">Específico para esse cmdlet é a capacidade de definir se o serviço de catálogo de endereços cria os arquivos de download do cliente, como e se as regras de normalização forem usadas, por quanto tempo manter os arquivos Delta e Delta, o tamanho do arquivo Delta antes de incorporar uma nova criação completa de arquivo, o que hora do dia em que o catálogo completo de endereços foi criado e o que o interno deve ter para a sincronização das informações no banco de dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="74fa6-107">Specific to this cmdlet is the ability to define if the Address Book Service creates the client download files, how and if normalization rules are used, how long to retain delta and compact delta files, delta file size before incorporating a new full file creation, what time of day the full file Address Book is created, and what the internal should be for synchronization of information in the User database.</span></span>

<span data-ttu-id="74fa6-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="74fa6-108">For example:</span></span>

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a><span data-ttu-id="74fa6-109">Confira também</span><span class="sxs-lookup"><span data-stu-id="74fa6-109">See Also</span></span>


[<span data-ttu-id="74fa6-110">New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="74fa6-110">New-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

