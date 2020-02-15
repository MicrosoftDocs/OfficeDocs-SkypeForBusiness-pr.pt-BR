---
title: 'Lync Server 2013: novos recursos de virtualização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New virtualization features
ms:assetid: edeb2c41-765e-47b8-8a2b-7a7ce09de2ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721926(v=OCS.15)
ms:contentKeyID: 49733861
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d5c60926db1238c586c2c516302649c5c44cd8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="eb29b-102">Novos recursos de virtualização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb29b-102">New virtualization features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb29b-103">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="eb29b-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="eb29b-104">O Lync Server 2013 oferece suporte à virtualização no Windows Server 2012, no Windows Server 2012 R2 e no Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="eb29b-104">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="eb29b-105">O suporte no Windows Server 2012 e no Windows Server 2012 R2 inclui suporte para os recursos de virtualização de e/s de raiz única (SR-IOV).</span><span class="sxs-lookup"><span data-stu-id="eb29b-105">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="eb29b-106">Com a SR-IOV, a função virtual de um adaptador de rede físico é atribuída diretamente a uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="eb29b-106">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="eb29b-107">Isso aumenta a transmissão e reduz a latência da rede, ao mesmo tempo que reduz a utilização da CPU host necessária para processar o tráfego de rede.</span><span class="sxs-lookup"><span data-stu-id="eb29b-107">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="eb29b-108">Para tirar proveito da SR-IOV, você deve usar um servidor de host com BIOS que ofereça suporte à SR-IOV, além de adaptadores de rede que também ofereçam suporte à SR-IOV.</span><span class="sxs-lookup"><span data-stu-id="eb29b-108">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

