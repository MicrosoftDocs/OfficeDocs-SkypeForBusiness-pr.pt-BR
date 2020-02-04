---
title: 'Lync Server 2013: Resumo de porta - cargas de DNS e de HLB balanceadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb594057977fbe39f6be6a9a9c678806d7e2d8dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="6140d-102">Resumo de porta - cargas de DNS e de HLB balanceadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6140d-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6140d-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6140d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6140d-104">Os requisitos de porta do firewall para um único diretor consistem em portas que são usadas para estabelecer comunicação com o diretor da interface interna ou da rede de face interna do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="6140d-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="6140d-105">O Microsoft Lync Server 2013 por padrão espera que as portas HTTP/TCP 8080 e HTTPS/TCP 4443 sejam abertas do proxy reverso para o diretor, bem como do pool de front-end e do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6140d-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="6140d-106">Além disso, deve haver comunicação SIP (Session Initiation Protocol) da interface interna do servidor de borda para o diretor e para o pool de front-end e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6140d-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="6140d-107">O protocolo SIP usa SIP/MTLS/TCP 5061 do servidor de borda para o pool de front-ends e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6140d-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="6140d-108">Uma regra que permita a comunicação SIP/MTLS/TCP 5061 do diretor, do pool de front-ends e do servidor front-end para a interface interna do servidor de borda também deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="6140d-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="6140d-109">Portas e protocolos de director único para definições de firewall</span><span class="sxs-lookup"><span data-stu-id="6140d-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6140d-110">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="6140d-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6140d-111">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="6140d-111">Source IP address</span></span></th>
<th><span data-ttu-id="6140d-112">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="6140d-112">Destination IP address</span></span></th>
<th><span data-ttu-id="6140d-113">Notas</span><span class="sxs-lookup"><span data-stu-id="6140d-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6140d-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="6140d-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="6140d-115">Interface interna de proxy inversa</span><span class="sxs-lookup"><span data-stu-id="6140d-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="6140d-116">VIP do balanceador de carga de hardware do diretor</span><span class="sxs-lookup"><span data-stu-id="6140d-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="6140d-117">Inicialmente recebido pelo lado externo do proxy reverso, a comunicação é enviada para o diretor de serviços Web do diretor HLB VIP e servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6140d-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6140d-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="6140d-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="6140d-119">Interface interna de proxy inversa</span><span class="sxs-lookup"><span data-stu-id="6140d-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="6140d-120">VIP do balanceador de carga de hardware do diretor</span><span class="sxs-lookup"><span data-stu-id="6140d-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="6140d-121">Inicialmente recebido pelo lado externo do proxy reverso, a comunicação é enviada para o diretor de serviços Web do diretor HLB VIP e servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6140d-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6140d-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="6140d-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="6140d-123">Diretor</span><span class="sxs-lookup"><span data-stu-id="6140d-123">Director</span></span></p></td>
<td><p><span data-ttu-id="6140d-124">Pool de front-end ou servidor front-end</span><span class="sxs-lookup"><span data-stu-id="6140d-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="6140d-125">Comunicação entre servidores entre o VIP do diretor HLB e o servidor front-end ou servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6140d-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6140d-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="6140d-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="6140d-127">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="6140d-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="6140d-128">VIP do balanceador de carga de hardware do diretor</span><span class="sxs-lookup"><span data-stu-id="6140d-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="6140d-129">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="6140d-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6140d-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="6140d-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="6140d-131">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="6140d-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="6140d-132">VIP do balanceador de carga de hardware do diretor</span><span class="sxs-lookup"><span data-stu-id="6140d-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="6140d-133">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="6140d-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6140d-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="6140d-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="6140d-135">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6140d-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6140d-136">Diretor</span><span class="sxs-lookup"><span data-stu-id="6140d-136">Director</span></span></p></td>
<td><p><span data-ttu-id="6140d-137">Comunicação SIP do servidor de borda para o diretor, bem como os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6140d-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6140d-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="6140d-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="6140d-139">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6140d-139">Any</span></span></p></td>
<td><p><span data-ttu-id="6140d-140">Diretor</span><span class="sxs-lookup"><span data-stu-id="6140d-140">Director</span></span></p></td>
<td><p><span data-ttu-id="6140d-141">Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClsAgent. exe) e o conjunto de logs</span><span class="sxs-lookup"><span data-stu-id="6140d-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6140d-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="6140d-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="6140d-143">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6140d-143">Any</span></span></p></td>
<td><p><span data-ttu-id="6140d-144">Diretor</span><span class="sxs-lookup"><span data-stu-id="6140d-144">Director</span></span></p></td>
<td><p><span data-ttu-id="6140d-145">Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClsAgent. exe) e o conjunto de logs</span><span class="sxs-lookup"><span data-stu-id="6140d-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6140d-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="6140d-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="6140d-147">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6140d-147">Any</span></span></p></td>
<td><p><span data-ttu-id="6140d-148">Diretor</span><span class="sxs-lookup"><span data-stu-id="6140d-148">Director</span></span></p></td>
<td><p><span data-ttu-id="6140d-149">Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClsAgent. exe) e o conjunto de logs</span><span class="sxs-lookup"><span data-stu-id="6140d-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

