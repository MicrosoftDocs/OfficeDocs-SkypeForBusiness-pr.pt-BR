---
title: 'Lync Server 2013: Resumo de porta-balanceamento de carga DNS e HLB'
description: 'Lync Server 2013: Resumo de porta-balanceamento de carga DNS e HLB.'
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
ms.openlocfilehash: be2e8204e792fd9c4718cb9171e90784af2d0104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543127"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="dc450-103">Resumo de porta-carga de DNS e HLB balanceada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc450-103">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc450-104">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="dc450-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="dc450-105">Os requisitos de porta de firewall para um único diretor consistem nas portas usadas para estabelecer comunicação com o diretor da interface interna ou da rede de face interna do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="dc450-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="dc450-106">O Microsoft Lync Server 2013, por padrão, espera que as portas HTTP/TCP 8080 e HTTPS/TCP 4443 sejam abertas do proxy reverso para o diretor, bem como o pool de front-ends e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="dc450-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="dc450-107">Além disso, deve haver comunicação SIP (Session Initiation Protocol) da interface interna do servidor de borda para o diretor e para o pool de front-ends e servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="dc450-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="dc450-108">O protocolo SIP usa SIP/MTLS/TCP 5061 do servidor de borda para o pool de front-ends e servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="dc450-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="dc450-109">Uma regra que permite a comunicação SIP/MTLS/TCP 5061 do diretor, do pool de front-ends e do servidor front-end para a interface interna do servidor de borda também deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="dc450-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="dc450-110">Portas e protocolos de diretor único para definições de firewall</span><span class="sxs-lookup"><span data-stu-id="dc450-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc450-111">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="dc450-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dc450-112">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="dc450-112">Source IP address</span></span></th>
<th><span data-ttu-id="dc450-113">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="dc450-113">Destination IP address</span></span></th>
<th><span data-ttu-id="dc450-114">Observações</span><span class="sxs-lookup"><span data-stu-id="dc450-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc450-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="dc450-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="dc450-116">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="dc450-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="dc450-117">VIP do balanceador de carga de hardware diretor</span><span class="sxs-lookup"><span data-stu-id="dc450-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="dc450-118">Recebido inicialmente pelo lado externo do proxy reverso, a comunicação é enviada para os serviços Web do diretor de HLB VIP e servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="dc450-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc450-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="dc450-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="dc450-120">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="dc450-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="dc450-121">VIP do balanceador de carga de hardware diretor</span><span class="sxs-lookup"><span data-stu-id="dc450-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="dc450-122">Recebido inicialmente pelo lado externo do proxy reverso, a comunicação é enviada para os serviços Web do diretor de HLB VIP e servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="dc450-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc450-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="dc450-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="dc450-124">Diretor</span><span class="sxs-lookup"><span data-stu-id="dc450-124">Director</span></span></p></td>
<td><p><span data-ttu-id="dc450-125">Pool de front-ends ou servidor front-end</span><span class="sxs-lookup"><span data-stu-id="dc450-125">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="dc450-126">Comunicação entre servidores entre o VIP HLB do diretor e o servidor front-end ou servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dc450-126">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc450-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="dc450-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="dc450-128">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="dc450-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="dc450-129">VIP do balanceador de carga de hardware diretor</span><span class="sxs-lookup"><span data-stu-id="dc450-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="dc450-130">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="dc450-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc450-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="dc450-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="dc450-132">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="dc450-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="dc450-133">VIP do balanceador de carga de hardware diretor</span><span class="sxs-lookup"><span data-stu-id="dc450-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="dc450-134">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="dc450-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc450-135">SIP/MTLS/5061</span><span class="sxs-lookup"><span data-stu-id="dc450-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="dc450-136">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="dc450-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dc450-137">Diretor</span><span class="sxs-lookup"><span data-stu-id="dc450-137">Director</span></span></p></td>
<td><p><span data-ttu-id="dc450-138">Comunicação SIP do servidor de borda ao diretor, bem como dos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dc450-138">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc450-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="dc450-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="dc450-140">Qualquer</span><span class="sxs-lookup"><span data-stu-id="dc450-140">Any</span></span></p></td>
<td><p><span data-ttu-id="dc450-141">Diretor</span><span class="sxs-lookup"><span data-stu-id="dc450-141">Director</span></span></p></td>
<td><p><span data-ttu-id="dc450-142">Comandos de controlador de serviço de registro centralizado (ClsController.exe) ou agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="dc450-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc450-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="dc450-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="dc450-144">Qualquer</span><span class="sxs-lookup"><span data-stu-id="dc450-144">Any</span></span></p></td>
<td><p><span data-ttu-id="dc450-145">Diretor</span><span class="sxs-lookup"><span data-stu-id="dc450-145">Director</span></span></p></td>
<td><p><span data-ttu-id="dc450-146">Comandos de controlador de serviço de registro centralizado (ClsController.exe) ou agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="dc450-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc450-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="dc450-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="dc450-148">Qualquer</span><span class="sxs-lookup"><span data-stu-id="dc450-148">Any</span></span></p></td>
<td><p><span data-ttu-id="dc450-149">Diretor</span><span class="sxs-lookup"><span data-stu-id="dc450-149">Director</span></span></p></td>
<td><p><span data-ttu-id="dc450-150">Comandos de controlador de serviço de registro centralizado (ClsController.exe) ou agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="dc450-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

