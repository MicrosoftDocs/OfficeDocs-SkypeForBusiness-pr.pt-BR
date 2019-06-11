---
title: 'Lync Server 2013: Requisitos de hardware e de software para o Diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="1d33c-102">Requisitos de hardware e de software para o Diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d33c-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d33c-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1d33c-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1d33c-104">Esta seção detalha os requisitos de hardware e software para o diretor e os cenários de localização compatíveis para o diretor.</span><span class="sxs-lookup"><span data-stu-id="1d33c-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="1d33c-105">Requisitos de hardware para o diretor</span><span class="sxs-lookup"><span data-stu-id="1d33c-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="1d33c-106">A tabela a seguir lista os requisitos de hardware para o diretor:</span><span class="sxs-lookup"><span data-stu-id="1d33c-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="1d33c-107">Requisitos de hardware para o diretor</span><span class="sxs-lookup"><span data-stu-id="1d33c-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d33c-108">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="1d33c-108">Hardware component</span></span></th>
<th><span data-ttu-id="1d33c-109">Requisitos mínimos</span><span class="sxs-lookup"><span data-stu-id="1d33c-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d33c-110">CPU</span><span class="sxs-lookup"><span data-stu-id="1d33c-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1d33c-111">processador de 64 bits, Quad-Core, 2,0 GHz ou mais</span><span class="sxs-lookup"><span data-stu-id="1d33c-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="1d33c-112">processador dual de 64 bits, Dual-Core, 2,0 GHz ou superior</span><span class="sxs-lookup"><span data-stu-id="1d33c-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d33c-113">Memória</span><span class="sxs-lookup"><span data-stu-id="1d33c-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="1d33c-114">4 gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="1d33c-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d33c-115">Disco</span><span class="sxs-lookup"><span data-stu-id="1d33c-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1d33c-116">unidade de disco rígido de 10K RPM (HDD)</span><span class="sxs-lookup"><span data-stu-id="1d33c-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="1d33c-117">Unidade de estado sólido (SSD) de alto desempenho com desempenho igual ou melhor do que o HDD de 10K RPM</span><span class="sxs-lookup"><span data-stu-id="1d33c-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="1d33c-118">RAID 10 (distribuído e espelhado) 2 mil discos de 15.000 RPM para arquivos de dados de banco de dados</span><span class="sxs-lookup"><span data-stu-id="1d33c-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d33c-119">Rede</span><span class="sxs-lookup"><span data-stu-id="1d33c-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1d33c-120">Adaptadores de rede duplos de 1 gigabit por segundo (Gbps) (recomendado)</span><span class="sxs-lookup"><span data-stu-id="1d33c-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="1d33c-121">Um único adaptador de rede de 1 Gbps (aceito)</span><span class="sxs-lookup"><span data-stu-id="1d33c-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="1d33c-122">Requisitos de software para o diretor</span><span class="sxs-lookup"><span data-stu-id="1d33c-122">Software Requirements for the Director</span></span>

<span data-ttu-id="1d33c-123">A função de diretor pode ser implantada somente em servidores que executam o Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1d33c-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="1d33c-124">Um dos seguintes sistemas operacionais de 64 bits é necessário para os directors:</span><span class="sxs-lookup"><span data-stu-id="1d33c-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="1d33c-125">O sistema operacional padrão do Windows Server 2008 R2 com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1d33c-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="1d33c-126">O sistema operacional Windows Server 2008 R2 Enterprise com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1d33c-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="1d33c-127">O sistema operacional Windows Server 2008 R2 Datacenter com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1d33c-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="1d33c-128">O sistema operacional padrão do Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1d33c-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="1d33c-129">O sistema operacional Windows Server 2012 datacenter</span><span class="sxs-lookup"><span data-stu-id="1d33c-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="1d33c-130">O Lync Server 2013 também exige a instalação dos seguintes programas e atualizações detalhados no tópico [suporte adicional do servidor e requisitos no Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d33c-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="1d33c-131">Colocação compatível</span><span class="sxs-lookup"><span data-stu-id="1d33c-131">Supported Collocation</span></span>

<span data-ttu-id="1d33c-132">A função de servidor diretor não pode ser posicionada com qualquer função de servidor no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d33c-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="1d33c-133">No entanto, se você não implantar um director, os servidores front-end assumirão a função.</span><span class="sxs-lookup"><span data-stu-id="1d33c-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

