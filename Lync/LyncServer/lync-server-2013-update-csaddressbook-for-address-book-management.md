---
title: 'Lync Server 2013: Update-CsAddressBook para gerenciamento de catálogo de endereços'
description: 'Lync Server 2013: Update-CsAddressBook para gerenciamento de catálogo de endereços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4adc7f94e2f31f64f6517b8cdf9bbcb0649f6c8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546237"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="a2802-103">Update-CsAddressBook para gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2802-103">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2802-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a2802-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a2802-105">Quem pode executar esse cmdlet: Por padrão, membros dos seguintes grupos estão autorizados a executar o cmdlet Update-CsAddressBook localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a2802-105">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="a2802-106">Para retornar uma lista de todas as funções RBAC que este cmdlet foi atribuído (incluindo qualquer função RBAC que você criou sozinho), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a2802-106">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="a2802-107">O cmdlet Update-CsAddressBook substitui o comando **abserver.exe – syncNow** do Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="a2802-107">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="a2802-108">O objetivo do cmdlet é iniciar uma sincronização imediatamente em vez de aguardar o horário agendado.</span><span class="sxs-lookup"><span data-stu-id="a2802-108">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="a2802-109">O primeiro comando de exemplo atualiza todos os catálogos de endereços na organização.</span><span class="sxs-lookup"><span data-stu-id="a2802-109">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="a2802-110">A segunda atualiza apenas o catálogo de endereços associado ao servidor definido.</span><span class="sxs-lookup"><span data-stu-id="a2802-110">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a2802-111">No Lync Server 2013, o replicador de usuários do Lync Server selecionará as alterações do Active Directory e atualizará o banco de dados de usuário do Lync Server com base em um intervalo configurado.</span><span class="sxs-lookup"><span data-stu-id="a2802-111">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="a2802-112">O replicador de usuários do Lync Server também propagará as alterações para o banco de dados do RTCab rapidamente, sem que o administrador tenha que executar Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="a2802-112">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="a2802-113">Os administradores precisarão executar o Atualizar -CSAddressBook somente se o download de arquivo do Catálogo de Endereços estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="a2802-113">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="a2802-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a2802-114">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="a2802-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a2802-115">See Also</span></span>


[<span data-ttu-id="a2802-116">Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="a2802-116">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

