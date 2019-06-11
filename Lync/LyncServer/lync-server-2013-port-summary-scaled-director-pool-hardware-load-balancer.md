---
title: 'Lync Server 2013: Resumo de porta - Pool de Diretor em escala, balanceador de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9a78225f7cf523d5f120f291498007fcdfa0cd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="e7a67-102">Resumo de porta - Pool de Diretor em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7a67-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7a67-103">_**Tópico da última modificação:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="e7a67-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="e7a67-104">Os requisitos de porta do firewall para um pool de directors consistem nas portas usadas para estabelecer comunicação com o diretor da interface interna do servidor de borda ou da interface interna do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="e7a67-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="e7a67-105">O Microsoft Lync Server 2013 por padrão espera que as portas HTTP/TCP 8080 e HTTPS/TCP 4443 sejam abertas do proxy reverso para o diretor, bem como do pool de front-end e do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e7a67-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="e7a67-106">Além disso, deve haver comunicação SIP (Session Initiation Protocol) da interface interna do servidor de borda para o diretor e para o pool de front-end e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e7a67-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="e7a67-107">O protocolo SIP usa SIP/MTLS/TCP 5061 do servidor de borda para o pool de front-ends e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e7a67-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="e7a67-108">Uma regra que permita a comunicação SIP/MTLS/TCP 5061 do diretor, do pool de front-ends e do servidor front-end para a interface interna do servidor de borda também deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="e7a67-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="e7a67-109">Portas e protocolos do diretor para definições de firewall</span><span class="sxs-lookup"><span data-stu-id="e7a67-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7a67-110">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="e7a67-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e7a67-111">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="e7a67-111">Source IP address</span></span></th>
<th><span data-ttu-id="e7a67-112">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="e7a67-112">Destination IP address</span></span></th>
<th><span data-ttu-id="e7a67-113">Notas</span><span class="sxs-lookup"><span data-stu-id="e7a67-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7a67-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="e7a67-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="e7a67-115">Interface interna de proxy inversa</span><span class="sxs-lookup"><span data-stu-id="e7a67-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="e7a67-116">VIP do balanceador de carga de hardware do diretor</span><span class="sxs-lookup"><span data-stu-id="e7a67-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e7a67-117">Inicialmente recebido pelo lado externo do proxy reverso, a comunicação é enviada para o diretor HLB VIP e serviços Web de servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e7a67-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7a67-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="e7a67-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="e7a67-119">Interface interna de proxy inversa</span><span class="sxs-lookup"><span data-stu-id="e7a67-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="e7a67-120">VIP do balanceador de carga de hardware do diretor</span><span class="sxs-lookup"><span data-stu-id="e7a67-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e7a67-121">Inicialmente recebido pelo lado externo do proxy reverso, a comunicação é enviada para o diretor HLB VIP e serviços Web de servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e7a67-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7a67-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="e7a67-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="e7a67-123">Diretor</span><span class="sxs-lookup"><span data-stu-id="e7a67-123">Director</span></span></p></td>
<td><p><span data-ttu-id="e7a67-124">Servidor front-end ou pool de front-end</span><span class="sxs-lookup"><span data-stu-id="e7a67-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="e7a67-125">Comunicação entre servidores entre o diretor HLB VIP e os servidores front-end</span><span class="sxs-lookup"><span data-stu-id="e7a67-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7a67-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="e7a67-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="e7a67-127">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="e7a67-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="e7a67-128">VIP do balanceador de carga de hardware do diretor</span><span class="sxs-lookup"><span data-stu-id="e7a67-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e7a67-129">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="e7a67-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7a67-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="e7a67-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="e7a67-131">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="e7a67-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="e7a67-132">VIP do balanceador de carga de hardware do diretor</span><span class="sxs-lookup"><span data-stu-id="e7a67-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e7a67-133">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="e7a67-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7a67-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="e7a67-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="e7a67-135">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e7a67-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e7a67-136">VIP do balanceador de carga de hardware do diretor</span><span class="sxs-lookup"><span data-stu-id="e7a67-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="e7a67-137">Comunicação SIP do servidor de borda para o diretor e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="e7a67-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7a67-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e7a67-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e7a67-139">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="e7a67-139">Any</span></span></p></td>
<td><p><span data-ttu-id="e7a67-140">Diretor</span><span class="sxs-lookup"><span data-stu-id="e7a67-140">Director</span></span></p></td>
<td><p><span data-ttu-id="e7a67-141">Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClsAgent. exe) e o conjunto de logs</span><span class="sxs-lookup"><span data-stu-id="e7a67-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7a67-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e7a67-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e7a67-143">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="e7a67-143">Any</span></span></p></td>
<td><p><span data-ttu-id="e7a67-144">Diretor</span><span class="sxs-lookup"><span data-stu-id="e7a67-144">Director</span></span></p></td>
<td><p><span data-ttu-id="e7a67-145">Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClsAgent. exe) e o conjunto de logs</span><span class="sxs-lookup"><span data-stu-id="e7a67-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7a67-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e7a67-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e7a67-147">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="e7a67-147">Any</span></span></p></td>
<td><p><span data-ttu-id="e7a67-148">Diretor</span><span class="sxs-lookup"><span data-stu-id="e7a67-148">Director</span></span></p></td>
<td><p><span data-ttu-id="e7a67-149">Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClsAgent. exe) e o conjunto de logs</span><span class="sxs-lookup"><span data-stu-id="e7a67-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

