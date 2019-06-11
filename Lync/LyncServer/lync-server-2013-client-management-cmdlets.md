---
title: 'Lync Server 2013: cmdlets de gerenciamento de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client management cmdlets
ms:assetid: 0384f8ab-453d-49d6-aaa7-52439e27b7e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398087(v=OCS.15)
ms:contentKeyID: 48183261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c40ad68a228f06c1275460a38aa1f6fbfff53f5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="85ebd-102">Cmdlets de gerenciamento de cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ebd-102">Client management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85ebd-103">_**Tópico da última modificação:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="85ebd-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="85ebd-104">O gerenciamento de clientes consiste principalmente em determinar quais aplicativos cliente (como o Microsoft Lync 2013) terão permissão para fazer logon no Lync Server 2013 e determinar as funcionalidades disponíveis para esses aplicativos cliente depois de terem feito logon.</span><span class="sxs-lookup"><span data-stu-id="85ebd-104">Client management consists primarily of determining which client applications (such as Microsoft Lync 2013) will be allowed to log on to Lync Server 2013 and determining the capabilities available to those client applications after they have logged on.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="85ebd-105">Para obter informações adicionais sobre cmdlets, consulte o blog&nbsp;do Lync Server do <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>Windows PowerShell em.</span><span class="sxs-lookup"><span data-stu-id="85ebd-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="85ebd-106">O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="85ebd-106">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="client-management-cmdlets"></a><span data-ttu-id="85ebd-107">Cmdlets de gerenciamento de cliente</span><span class="sxs-lookup"><span data-stu-id="85ebd-107">Client Management Cmdlets</span></span>

<span data-ttu-id="85ebd-108">A maioria das tarefas de gerenciamento que se aplicam ao gerenciamento de cliente pode ser executada no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85ebd-108">Most management tasks that apply to client management can be performed from the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="85ebd-109">Essas mesmas tarefas podem ser executadas usando cmdlets do Shell de gerenciamento do Lync Server ou de dentro de um script.</span><span class="sxs-lookup"><span data-stu-id="85ebd-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="85ebd-110">Usando um script, você pode automatizar determinadas tarefas.</span><span class="sxs-lookup"><span data-stu-id="85ebd-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="85ebd-111">Veja a seguir uma lista de cmdlets relacionados diretamente ao gerenciamento de cliente:</span><span class="sxs-lookup"><span data-stu-id="85ebd-111">The following is a list of cmdlets that relate directly to client management:</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-112">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-112">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-113">[Grant CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-113">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-114">[New-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-114">[New-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-115">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-115">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-116">[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-116">[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="85ebd-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="85ebd-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="85ebd-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-123">[Grant CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="85ebd-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="85ebd-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="85ebd-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

