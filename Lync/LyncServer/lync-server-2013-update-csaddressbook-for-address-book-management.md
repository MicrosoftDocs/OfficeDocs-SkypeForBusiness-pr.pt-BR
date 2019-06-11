---
title: 'Lync Server 2013: Update-CsAddressBook para gerenciamento de catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22923d0227c75ee6f2055d4a2ac350a6df6b37bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="127c1-102">Update-CsAddressBook para o gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127c1-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="127c1-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="127c1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="127c1-104">Quem pode executar este cmdlet: por padrão, os membros dos grupos a seguir estão autorizados a executar o cmdlet Update-CsAddressBook localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="127c1-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="127c1-105">Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="127c1-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="127c1-106">O cmdlet Update-CsAddressBook substitui o comando **abserver. exe – syncNow** do Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="127c1-106">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="127c1-107">A finalidade do cmdlet é iniciar uma sincronização imediatamente em vez de aguardar o horário agendado.</span><span class="sxs-lookup"><span data-stu-id="127c1-107">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="127c1-108">O primeiro exemplo de comando atualiza todos os catálogos de endereços da organização.</span><span class="sxs-lookup"><span data-stu-id="127c1-108">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="127c1-109">A segunda atualiza somente o catálogo de endereços associado ao servidor definido.</span><span class="sxs-lookup"><span data-stu-id="127c1-109">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="127c1-110">No Lync Server 2013, o duplicador de usuários do Lync Server atenderá as alterações do Active Directory e atualizará o banco de dados de usuários do Lync Server com base em um intervalo configurado.</span><span class="sxs-lookup"><span data-stu-id="127c1-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="127c1-111">O duplicador de usuários do Lync Server também propagará as alterações para o banco de dados do RTCab rapidamente, sem que o administrador tenha que executar Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="127c1-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="127c1-112">Os administradores só precisarão executar Update-CSAddressBook se o download do arquivo do catálogo de endereços estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="127c1-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="127c1-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="127c1-113">For example:</span></span>

   ```
    Update-CsAddressBook
   ```

   ```
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="127c1-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="127c1-114">See Also</span></span>


[<span data-ttu-id="127c1-115">Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="127c1-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

