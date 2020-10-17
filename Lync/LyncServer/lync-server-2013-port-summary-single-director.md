---
title: 'Lync Server 2013: Resumo de porta-diretor único'
description: 'Lync Server 2013: Resumo de porta-diretor único.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566367"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="e10af-103">Resumo de porta-diretor único no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e10af-103">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e10af-104">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e10af-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e10af-105">Os requisitos de porta de firewall para um único diretor consistem nas portas usadas para estabelecer comunicação com o diretor da interface interna ou da rede de face interna do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="e10af-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="e10af-106">O Microsoft Lync Server 2013, por padrão, espera que as portas HTTP/TCP 8080 e HTTPS/TCP 4443 sejam abertas do proxy reverso para o diretor, bem como o pool de front-ends e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e10af-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="e10af-107">Além disso, deve haver comunicação SIP (Session Initiation Protocol) da interface interna do servidor de borda para o diretor e para o pool de front-ends e servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="e10af-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="e10af-108">O protocolo SIP usa SIP/MTLS/TCP 5061 do servidor de borda para o pool de front-ends e servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e10af-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="e10af-109">Uma regra que permite a comunicação SIP/MTLS/TCP 5061 do diretor, do pool de front-ends e do servidor front-end para a interface interna do servidor de borda também deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="e10af-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="e10af-110">Portas e protocolos de diretor único para definições de firewall</span><span class="sxs-lookup"><span data-stu-id="e10af-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e10af-111">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="e10af-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e10af-112">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="e10af-112">Source IP address</span></span></th>
<th><span data-ttu-id="e10af-113">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="e10af-113">Destination IP address</span></span></th>
<th><span data-ttu-id="e10af-114">Observações</span><span class="sxs-lookup"><span data-stu-id="e10af-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e10af-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="e10af-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="e10af-116">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="e10af-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="e10af-117">Diretor</span><span class="sxs-lookup"><span data-stu-id="e10af-117">Director</span></span></p></td>
<td><p><span data-ttu-id="e10af-118">Recebido inicialmente pelo lado externo do proxy reverso, a comunicação é enviada para os serviços Web diretor e servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e10af-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10af-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="e10af-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="e10af-120">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="e10af-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="e10af-121">Diretor</span><span class="sxs-lookup"><span data-stu-id="e10af-121">Director</span></span></p></td>
<td><p><span data-ttu-id="e10af-122">Recebido inicialmente pelo lado externo do proxy reverso, a comunicação é enviada para os serviços Web diretor e servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e10af-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10af-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="e10af-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="e10af-124">Diretor</span><span class="sxs-lookup"><span data-stu-id="e10af-124">Director</span></span></p></td>
<td><p><span data-ttu-id="e10af-125">Servidor Front-End ou pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="e10af-125">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="e10af-126">Comunicação entre servidores entre o diretor e o servidor front-end</span><span class="sxs-lookup"><span data-stu-id="e10af-126">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10af-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="e10af-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="e10af-128">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="e10af-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="e10af-129">Serviços Web diretor</span><span class="sxs-lookup"><span data-stu-id="e10af-129">Director web services</span></span></p></td>
<td><p><span data-ttu-id="e10af-130">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="e10af-130">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10af-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="e10af-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="e10af-132">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="e10af-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="e10af-133">Serviços Web diretor</span><span class="sxs-lookup"><span data-stu-id="e10af-133">Director web services</span></span></p></td>
<td><p><span data-ttu-id="e10af-134">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="e10af-134">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10af-135">SIP/MTLS/5061</span><span class="sxs-lookup"><span data-stu-id="e10af-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="e10af-136">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e10af-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e10af-137">Diretor</span><span class="sxs-lookup"><span data-stu-id="e10af-137">Director</span></span></p></td>
<td><p><span data-ttu-id="e10af-138">Comunicação SIP do servidor de borda para o diretor e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="e10af-138">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10af-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e10af-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e10af-140">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e10af-140">Any</span></span></p></td>
<td><p><span data-ttu-id="e10af-141">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e10af-141">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e10af-142">Comandos e coleção de registros do controlador (ClsController.exe) ou agente (ClasAgent.exe) de serviços centralizados de registro</span><span class="sxs-lookup"><span data-stu-id="e10af-142">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e10af-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e10af-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e10af-144">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e10af-144">Any</span></span></p></td>
<td><p><span data-ttu-id="e10af-145">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e10af-145">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e10af-146">Comandos e coleção de registros do controlador (ClsController.exe) ou agente (ClasAgent.exe) de serviços centralizados de registro</span><span class="sxs-lookup"><span data-stu-id="e10af-146">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e10af-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e10af-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e10af-148">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e10af-148">Any</span></span></p></td>
<td><p><span data-ttu-id="e10af-149">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e10af-149">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e10af-150">Comandos e coleção de registros do controlador (ClsController.exe) ou agente (ClasAgent.exe) de serviços centralizados de registro</span><span class="sxs-lookup"><span data-stu-id="e10af-150">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

