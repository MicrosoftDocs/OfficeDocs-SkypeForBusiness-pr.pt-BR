---
title: Plataformas de hardware de servidor do Lync Server 2013
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
ms.openlocfilehash: cb5c5cbe1ef98a4028f8b05d96e4acc90cae7963
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510268"
---
# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="f4c5a-102">Plataformas de hardware de servidor para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4c5a-102">Server hardware platforms for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4c5a-103">_**Última modificação do tópico:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="f4c5a-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="f4c5a-104">As funções de servidor do Lync Server 2013 e os computadores que executam as ferramentas administrativas do Lync Server exigem hardware de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="f4c5a-105">O hardware específico usado para a implantação do Lync Server 2013 pode variar, dependendo dos requisitos de tamanho e uso.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="f4c5a-106">Esta seção descreve o hardware recomendado.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="f4c5a-107">Embora estas sejam recomendações, não obrigações, usar o hardware não atende estas recomendações pode resultar em problemas significativos de desempenho e outros problemas.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="f4c5a-108">Plataforma de Hardware Recomendada</span><span class="sxs-lookup"><span data-stu-id="f4c5a-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="f4c5a-109">Para obter um melhor desempenho, recomendamos que você execute o Lync Server em servidores com hardware que atenda aos requisitos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="f4c5a-110">Se você usar hardware menos poderoso, você pode enfrentar problemas de funcionalidade ou mau desempenho.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="f4c5a-111">Observe que esses requisitos de hardware são maiores do que os das versões anteriores do Lync Server, principalmente por causa do Lync Server 2013, todos os servidores front-end executam o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4c5a-112">A equipe de NIC é suportada e deve ser transparente para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="f4c5a-113">Para obter detalhes, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and Network Adapter teaming</A>.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-113">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="f4c5a-114">Hardware recomendado para servidores front-end, servidores back-end, servidores Standard Edition, servidores de chat persistente e repositório de chat persistente e repositório de conformidade de chat persistente (funções de servidor back-end para servidor de chat persistente)</span><span class="sxs-lookup"><span data-stu-id="f4c5a-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4c5a-115">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="f4c5a-115">Hardware component</span></span></th>
<th><span data-ttu-id="f4c5a-116">Recomendado</span><span class="sxs-lookup"><span data-stu-id="f4c5a-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4c5a-117">CPU</span><span class="sxs-lookup"><span data-stu-id="f4c5a-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="f4c5a-118">processador dual de 64 bits, Hex-Core, 2,26 gigahertz (GHz) ou superior.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="f4c5a-119">Processadores Intel Itanium não são suportados para funções de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c5a-120">Memória</span><span class="sxs-lookup"><span data-stu-id="f4c5a-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="f4c5a-121">32 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="f4c5a-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c5a-122">Disco</span><span class="sxs-lookup"><span data-stu-id="f4c5a-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f4c5a-123">8 ou mais drives de disco rígido de 10.000 RPM com pelo menos 72 GB espaço de disco livre.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="f4c5a-124">Dois dos discos devem usar RAID 1 e seis devem usar RAID 10.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="f4c5a-125">- Ou</span><span class="sxs-lookup"><span data-stu-id="f4c5a-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="f4c5a-126">Drivers de estado sólido (SSDs) que oferecem desempenho semelhante à 8 drivers de disco mecânico de 10.000-RPM.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c5a-127">Rede</span><span class="sxs-lookup"><span data-stu-id="f4c5a-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f4c5a-128">1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendado, que requer o agrupamento com um único endereço MAC e um único endereço IP).</span><span class="sxs-lookup"><span data-stu-id="f4c5a-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f4c5a-129">As configurações de duas ou várias bases não têm suporte para servidores front-end, servidores de back-end, servidores Standard Edition e servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="f4c5a-130">ILO/DRAC/etc. as conexões não expostas ao sistema operacional e usadas para monitorar e gerenciar o hardware do servidor não constituem um servidor de hospedagem múltipla e, portanto, são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="f4c5a-131">Hardware recomendado para Servidores de Borda, Servidores de Mediação Autônomo e Diretores</span><span class="sxs-lookup"><span data-stu-id="f4c5a-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4c5a-132">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="f4c5a-132">Hardware component</span></span></th>
<th><span data-ttu-id="f4c5a-133">Recomendado</span><span class="sxs-lookup"><span data-stu-id="f4c5a-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4c5a-134">CPU</span><span class="sxs-lookup"><span data-stu-id="f4c5a-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f4c5a-135">processador dual de 64 bits, Quad-Core, 2,0 gigahertz (GHz) ou superior.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="f4c5a-136">- Ou</span><span class="sxs-lookup"><span data-stu-id="f4c5a-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="f4c5a-137">processador de 4 vias com 64 bits, Dual-Core, 2,0 GHz ou superior.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="f4c5a-138">Processadores Intel Itanium não são suportados para funções de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c5a-139">Memória</span><span class="sxs-lookup"><span data-stu-id="f4c5a-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="f4c5a-140">16 gigabytes (GB).</span><span class="sxs-lookup"><span data-stu-id="f4c5a-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c5a-141">Disco</span><span class="sxs-lookup"><span data-stu-id="f4c5a-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f4c5a-142">4 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="f4c5a-143">Os discos devem estar em uma configuração RAID 1 2x.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="f4c5a-144">- Ou</span><span class="sxs-lookup"><span data-stu-id="f4c5a-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="f4c5a-145">Drivers de estado sólido (SSDs) que oferecem desempenho semelhante a 4 drivers de disco mecânico de 10.000-RPM.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c5a-146">Rede</span><span class="sxs-lookup"><span data-stu-id="f4c5a-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f4c5a-147">1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendado, que requer o agrupamento com um único endereço MAC e um único endereço IP).</span><span class="sxs-lookup"><span data-stu-id="f4c5a-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="f4c5a-148">2 as interfaces de rede são necessárias em servidores de borda e são compatíveis com servidores de mediação autônomos.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="f4c5a-149">As configurações de duas ou várias bases não têm suporte para diretores.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="f4c5a-150">ILO/DRAC/etc. as conexões não expostas ao sistema operacional e usadas para monitorar e gerenciar o hardware do servidor não constituem um servidor de hospedagem múltipla e, portanto, são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="f4c5a-151">Os servidores de borda exigirão duas interfaces de rede que sejam adaptadores de rede de duas portas, 1 Gbps ou superior (ou dois adaptadores de rede emparelhados, para um total de quatro, cada par que está sendo agrupado com um único endereço MAC e um único endereço IP, para um total de dois pares).</span><span class="sxs-lookup"><span data-stu-id="f4c5a-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="f4c5a-152">A instalação de NICs (placas de interface de rede) adicionais para permitir a configuração de um endereço IP PSTN específico é suportada em servidores de mediação autônomos.</span><span class="sxs-lookup"><span data-stu-id="f4c5a-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

