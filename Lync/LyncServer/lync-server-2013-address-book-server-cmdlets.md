---
title: 'Lync Server 2013: cmdlets do servidor do catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91a4953edf97d45cb29038ed8803917fe62a076c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521178"
---
# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="bffd4-102">Cmdlets do servidor de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bffd4-102">Address Book Server cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bffd4-103">_**Última modificação do tópico:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="bffd4-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="bffd4-104">Os servidores de catálogo de endereços são intermediários entre os serviços de domínio do Active Directory e o Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bffd4-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="bffd4-105">O servidor de catálogo de endereços garante que as informações do usuário armazenadas no Lync Server 2013 estão sincronizadas com as informações do usuário armazenadas no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bffd4-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="bffd4-106">Isso é feito pela sincronização periódica dos arquivos do Catálogo de Endereços com as informações armazenadas no banco de dados do Usuário.</span><span class="sxs-lookup"><span data-stu-id="bffd4-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="bffd4-107">Por sua vez, o Lync Server inclui vários cmdlets para gerenciar servidores de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="bffd4-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="bffd4-108">Address Book Server Cmdlets</span><span class="sxs-lookup"><span data-stu-id="bffd4-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="bffd4-109">Não é possível definir as configurações do servidor do catálogo de endereços no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bffd4-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="bffd4-110">O Windows PowerShell é a principal ferramenta para gerenciar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="bffd4-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="bffd4-111">Veja a seguir uma lista de cmdlets que se relacionam diretamente com o gerenciamento do Servidor de Catálogo de Endereços:</span><span class="sxs-lookup"><span data-stu-id="bffd4-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="bffd4-112">**Servidor do Catálogo de Endereços**</span><span class="sxs-lookup"><span data-stu-id="bffd4-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="bffd4-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bffd4-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bffd4-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bffd4-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bffd4-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bffd4-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bffd4-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bffd4-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="bffd4-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bffd4-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="bffd4-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bffd4-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="bffd4-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bffd4-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="bffd4-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bffd4-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bffd4-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="bffd4-121">See Also</span></span>


[<span data-ttu-id="bffd4-122">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="bffd4-122">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

