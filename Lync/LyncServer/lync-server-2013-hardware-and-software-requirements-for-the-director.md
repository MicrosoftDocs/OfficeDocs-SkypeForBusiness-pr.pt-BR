---
title: 'Lync Server 2013: requisitos de hardware e software para o diretor'
description: 'Lync Server 2013: requisitos de hardware e software para o diretor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dd868a3a566f1d89b4ada5a16695f8eb02b3b21
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552927"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="5fa2f-103">Requisitos de hardware e software para o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fa2f-103">Hardware and software requirements for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fa2f-104">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="5fa2f-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="5fa2f-105">Esta seção detalha os requisitos de hardware e software para o diretor e os cenários de colocação com suporte para o diretor.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-105">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="5fa2f-106">Requisitos de hardware por Diretor</span><span class="sxs-lookup"><span data-stu-id="5fa2f-106">Hardware Requirements for the Director</span></span>

<span data-ttu-id="5fa2f-107">A tabela a seguir lista os requisitos de hardware para o diretor:</span><span class="sxs-lookup"><span data-stu-id="5fa2f-107">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="5fa2f-108">Requisitos de hardware por Diretor</span><span class="sxs-lookup"><span data-stu-id="5fa2f-108">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fa2f-109">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="5fa2f-109">Hardware component</span></span></th>
<th><span data-ttu-id="5fa2f-110">Requisitos mínimos</span><span class="sxs-lookup"><span data-stu-id="5fa2f-110">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fa2f-111">CPU</span><span class="sxs-lookup"><span data-stu-id="5fa2f-111">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5fa2f-112">Processador de 64 bits, quad-core, 2.0 GHz ou superior</span><span class="sxs-lookup"><span data-stu-id="5fa2f-112">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="5fa2f-113">Processador 64 bits dual, dual-core, 2.0 GHz ou superior</span><span class="sxs-lookup"><span data-stu-id="5fa2f-113">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fa2f-114">Memória</span><span class="sxs-lookup"><span data-stu-id="5fa2f-114">Memory</span></span></p></td>
<td><p><span data-ttu-id="5fa2f-115">4 GB</span><span class="sxs-lookup"><span data-stu-id="5fa2f-115">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fa2f-116">Disco</span><span class="sxs-lookup"><span data-stu-id="5fa2f-116">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5fa2f-117">Disco rígido (HDD) de10K de RPM</span><span class="sxs-lookup"><span data-stu-id="5fa2f-117">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="5fa2f-118">Drive de estado sólido (SSD) de alto desempenho com desempenho igual ou superior a 10K RPM HDD</span><span class="sxs-lookup"><span data-stu-id="5fa2f-118">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="5fa2f-119">Discos para arquivos de dados do banco de dados de 2 x RAID 10 (distribuídos e espelhados), 15.000 de RPM</span><span class="sxs-lookup"><span data-stu-id="5fa2f-119">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fa2f-120">Rede</span><span class="sxs-lookup"><span data-stu-id="5fa2f-120">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5fa2f-121">Adaptadores de rede Dual 1 Gbps (recomendado)</span><span class="sxs-lookup"><span data-stu-id="5fa2f-121">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="5fa2f-122">Adaptador de rede de 1 Gbps único (suportado)</span><span class="sxs-lookup"><span data-stu-id="5fa2f-122">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="5fa2f-123">Requisitos de software para o diretor</span><span class="sxs-lookup"><span data-stu-id="5fa2f-123">Software Requirements for the Director</span></span>

<span data-ttu-id="5fa2f-124">A função diretor pode ser implantada somente em servidores que executam o Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-124">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="5fa2f-125">Um dos seguintes sistemas operacionais de 64 bits é necessário para os diretores:</span><span class="sxs-lookup"><span data-stu-id="5fa2f-125">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="5fa2f-126">O sistema operacional Windows Server 2008 R2 Standard com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="5fa2f-126">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="5fa2f-127">O sistema operacional Windows Server 2008 R2 Enterprise com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="5fa2f-127">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="5fa2f-128">O sistema operacional Windows Server 2008 R2 Datacenter com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="5fa2f-128">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="5fa2f-129">O sistema operacional Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="5fa2f-129">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="5fa2f-130">O sistema operacional Windows Server 2012 datacenter</span><span class="sxs-lookup"><span data-stu-id="5fa2f-130">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="5fa2f-131">O Lync Server 2013 também exige a instalação dos seguintes programas e atualizações detalhados no tópico [suporte adicional de servidor e requisitos no Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fa2f-131">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="5fa2f-132">Colocação suportada</span><span class="sxs-lookup"><span data-stu-id="5fa2f-132">Supported Collocation</span></span>

<span data-ttu-id="5fa2f-133">A função de servidor diretor não pode ser posicionada com qualquer outra função de servidor no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-133">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="5fa2f-134">No entanto, se você não implantar um diretor, os servidores front-end assumirão a função.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-134">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

