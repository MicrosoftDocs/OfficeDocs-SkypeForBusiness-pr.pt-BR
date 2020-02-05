---
title: 'Lync Server 2013: Plataformas de hardware de servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95c8b0e9b1e13d845672cff07d30b7f2ac1a5b22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="e3395-102">Plataformas de hardware de servidor para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3395-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3395-103">_**Tópico da última modificação:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="e3395-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="e3395-104">As funções de servidor do Lync Server 2013 e os computadores executando as ferramentas administrativas do Lync Server exigem hardware de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e3395-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="e3395-105">O hardware específico usado para a implantação do Lync Server 2013 pode variar, dependendo dos requisitos de tamanho e uso.</span><span class="sxs-lookup"><span data-stu-id="e3395-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="e3395-106">Esta seção descreve o hardware recomendado.</span><span class="sxs-lookup"><span data-stu-id="e3395-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="e3395-107">Embora estas sejam recomendações, não obrigações, o uso de hardware que não atende a estas recomendações pode resultar em problemas significativos de desempenho e outros problemas.</span><span class="sxs-lookup"><span data-stu-id="e3395-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="e3395-108">Plataforma de Hardware Recomendada</span><span class="sxs-lookup"><span data-stu-id="e3395-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="e3395-109">Para obter o melhor desempenho, recomendamos que você execute o Lync Server em servidores com hardware que atenda aos requisitos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e3395-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="e3395-110">Se usar um hardware menos poderoso, você poderá enfrentar problemas de funcionalidade ou mau desempenho.</span><span class="sxs-lookup"><span data-stu-id="e3395-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="e3395-111">Observe que esses requisitos de hardware são maiores do que os das versões anteriores do Lync Server, principalmente porque no Lync Server 2013, todos os servidores de front-end executam o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e3395-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3395-112">O agrupamento da NIC tem suporte e deve ser transparente para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3395-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="e3395-113">Para obter detalhes, consulte <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">servidor de comunicações ou Lync Server e agrupamento de adaptadores de rede</A>.</span><span class="sxs-lookup"><span data-stu-id="e3395-113">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="e3395-114">Hardware recomendado para Servidores de Front-End, Servidores de Back-End, Servidores de Edição Padrão, Servidores de Chat Persistente e Armazenamento de Chat Persistente e Armazenamento de Conformidade de Chat Persistente (Funções de Servidores de Back-End para Servidores de Chat Persistente)</span><span class="sxs-lookup"><span data-stu-id="e3395-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3395-115">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="e3395-115">Hardware component</span></span></th>
<th><span data-ttu-id="e3395-116">Recomendado</span><span class="sxs-lookup"><span data-stu-id="e3395-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3395-117">CPU</span><span class="sxs-lookup"><span data-stu-id="e3395-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="e3395-118">Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior.</span><span class="sxs-lookup"><span data-stu-id="e3395-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="e3395-119">Não há suporte para processadores Intel Itanium para funções de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3395-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3395-120">Memória</span><span class="sxs-lookup"><span data-stu-id="e3395-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="e3395-121">32 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="e3395-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3395-122">Disco</span><span class="sxs-lookup"><span data-stu-id="e3395-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3395-123">Oito ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço em disco livre.</span><span class="sxs-lookup"><span data-stu-id="e3395-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="e3395-124">Dois dos discos devem usar RAID 1 e seis devem usar RAID 10.</span><span class="sxs-lookup"><span data-stu-id="e3395-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="e3395-125">-OR</span><span class="sxs-lookup"><span data-stu-id="e3395-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="e3395-126">Drivers de estado sólido (SSDs) que oferecem desempenho semelhante a 8 drivers de disco mecânico de 10.000-RPM.</span><span class="sxs-lookup"><span data-stu-id="e3395-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3395-127">Rede</span><span class="sxs-lookup"><span data-stu-id="e3395-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3395-128">1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, que exige agrupamento com um único endereço MAC e um único endereço IP).</span><span class="sxs-lookup"><span data-stu-id="e3395-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e3395-129">Não há suporte para configurações de duas ou várias bases para servidores front-end, servidores back-end, servidores de edição padrão e servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e3395-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="e3395-130">ILO/DRAC/etc. as conexões não expostas ao sistema operacional e usadas para monitorar e gerenciar o hardware do servidor não constituem um servidor de hospedagem múltipla e, assim, é compatível.</span><span class="sxs-lookup"><span data-stu-id="e3395-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="e3395-131">Hardware recomendado para Servidores de Borda, Servidores de Mediação Autônomo e Diretores</span><span class="sxs-lookup"><span data-stu-id="e3395-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3395-132">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="e3395-132">Hardware component</span></span></th>
<th><span data-ttu-id="e3395-133">Recomendado</span><span class="sxs-lookup"><span data-stu-id="e3395-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3395-134">CPU</span><span class="sxs-lookup"><span data-stu-id="e3395-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3395-135">processador dual de 64 bits, Quad-Core, 2,0 gigahertz (GHz) ou superior.</span><span class="sxs-lookup"><span data-stu-id="e3395-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="e3395-136">-OR</span><span class="sxs-lookup"><span data-stu-id="e3395-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="e3395-137">processador de 4 vias de 64 bits, Dual-Core, 2,0 GHz ou superior.</span><span class="sxs-lookup"><span data-stu-id="e3395-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="e3395-138">Não há suporte para processadores Intel Itanium para funções de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3395-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3395-139">Memória</span><span class="sxs-lookup"><span data-stu-id="e3395-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="e3395-140">16 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="e3395-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3395-141">Disco</span><span class="sxs-lookup"><span data-stu-id="e3395-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3395-142">4 ou mais 10.000 unidades de disco rígido RPM com pelo menos 72 GB de espaço livre em disco.</span><span class="sxs-lookup"><span data-stu-id="e3395-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="e3395-143">Os discos devem estar em uma configuração 2x RAID 1.</span><span class="sxs-lookup"><span data-stu-id="e3395-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="e3395-144">-OR</span><span class="sxs-lookup"><span data-stu-id="e3395-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="e3395-145">Unidades de estado sólido (SSDs) que ofereçam desempenho semelhante a quatro unidades de disco mecânico de 10.000 RPM.</span><span class="sxs-lookup"><span data-stu-id="e3395-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3395-146">Rede</span><span class="sxs-lookup"><span data-stu-id="e3395-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3395-147">1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, que exige agrupamento com um único endereço MAC e um único endereço IP).</span><span class="sxs-lookup"><span data-stu-id="e3395-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="e3395-148">duas interfaces de rede são necessárias em servidores de borda e têm suporte em servidores de mediação autônomos.</span><span class="sxs-lookup"><span data-stu-id="e3395-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="e3395-149">Não há suporte para configurações de duas ou várias bases para os directors.</span><span class="sxs-lookup"><span data-stu-id="e3395-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="e3395-150">ILO/DRAC/etc. as conexões não expostas ao sistema operacional e usadas para monitorar e gerenciar o hardware do servidor não constituem um servidor de hospedagem múltipla e, assim, é compatível.</span><span class="sxs-lookup"><span data-stu-id="e3395-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="e3395-151">Os servidores de borda exigem duas interfaces de rede que sejam adaptadores de rede de duas portas, 1 Gbps ou superior (ou dois adaptadores de rede emparelhados, para um total de quatro, cada par sendo agrupado com um único endereço MAC e um único endereço IP, para um total de dois pares).</span><span class="sxs-lookup"><span data-stu-id="e3395-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="e3395-152">A instalação de placas de interface de rede adicionais (NICs) para permitir a configuração de um endereço IP PSTN específico tem suporte em servidores de mediação autônomos.</span><span class="sxs-lookup"><span data-stu-id="e3395-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

