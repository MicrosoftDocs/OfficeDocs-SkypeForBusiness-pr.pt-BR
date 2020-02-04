---
title: 'Lync Server 2013: Resumo de porta - Diretor único'
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
ms.openlocfilehash: 0179d6fd27207d28caa10ffa01bea155f9b00c03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="32f1e-102">Resumo de porta - Diretor único no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32f1e-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32f1e-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="32f1e-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="32f1e-104">Os requisitos de porta do firewall para um único diretor consistem em portas que são usadas para estabelecer comunicação com o diretor da interface interna ou da rede de face interna do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="32f1e-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="32f1e-105">O Microsoft Lync Server 2013 por padrão espera que as portas HTTP/TCP 8080 e HTTPS/TCP 4443 sejam abertas do proxy reverso para o diretor, bem como do pool de front-end e do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="32f1e-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="32f1e-106">Além disso, deve haver comunicação SIP (Session Initiation Protocol) da interface interna do servidor de borda para o diretor e para o pool de front-end e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="32f1e-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="32f1e-107">O protocolo SIP usa SIP/MTLS/TCP 5061 do servidor de borda para o pool de front-ends e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="32f1e-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="32f1e-108">Uma regra que permita a comunicação SIP/MTLS/TCP 5061 do diretor, do pool de front-ends e do servidor front-end para a interface interna do servidor de borda também deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="32f1e-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="32f1e-109">Portas e protocolos de director único para definições de firewall</span><span class="sxs-lookup"><span data-stu-id="32f1e-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32f1e-110">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="32f1e-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="32f1e-111">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="32f1e-111">Source IP address</span></span></th>
<th><span data-ttu-id="32f1e-112">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="32f1e-112">Destination IP address</span></span></th>
<th><span data-ttu-id="32f1e-113">Notas</span><span class="sxs-lookup"><span data-stu-id="32f1e-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32f1e-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="32f1e-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="32f1e-115">Interface interna de proxy inversa</span><span class="sxs-lookup"><span data-stu-id="32f1e-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="32f1e-116">Diretor</span><span class="sxs-lookup"><span data-stu-id="32f1e-116">Director</span></span></p></td>
<td><p><span data-ttu-id="32f1e-117">Inicialmente recebido pelo lado externo do proxy reverso, a comunicação é enviada para o diretor e serviços Web do servidor front-end</span><span class="sxs-lookup"><span data-stu-id="32f1e-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32f1e-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="32f1e-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="32f1e-119">Interface interna de proxy inversa</span><span class="sxs-lookup"><span data-stu-id="32f1e-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="32f1e-120">Diretor</span><span class="sxs-lookup"><span data-stu-id="32f1e-120">Director</span></span></p></td>
<td><p><span data-ttu-id="32f1e-121">Inicialmente recebido pelo lado externo do proxy reverso, a comunicação é enviada para o diretor e serviços Web do servidor front-end</span><span class="sxs-lookup"><span data-stu-id="32f1e-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32f1e-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="32f1e-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="32f1e-123">Diretor</span><span class="sxs-lookup"><span data-stu-id="32f1e-123">Director</span></span></p></td>
<td><p><span data-ttu-id="32f1e-124">Servidor front-end ou pool de front-end</span><span class="sxs-lookup"><span data-stu-id="32f1e-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="32f1e-125">Comunicação entre servidores entre o diretor e o servidor front-end</span><span class="sxs-lookup"><span data-stu-id="32f1e-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32f1e-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="32f1e-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="32f1e-127">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="32f1e-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="32f1e-128">Serviços Web de diretor</span><span class="sxs-lookup"><span data-stu-id="32f1e-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="32f1e-129">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="32f1e-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32f1e-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="32f1e-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="32f1e-131">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="32f1e-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="32f1e-132">Serviços Web de diretor</span><span class="sxs-lookup"><span data-stu-id="32f1e-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="32f1e-133">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="32f1e-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32f1e-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="32f1e-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="32f1e-135">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="32f1e-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="32f1e-136">Diretor</span><span class="sxs-lookup"><span data-stu-id="32f1e-136">Director</span></span></p></td>
<td><p><span data-ttu-id="32f1e-137">Comunicação SIP do servidor de borda para o diretor e do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="32f1e-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32f1e-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="32f1e-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="32f1e-139">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="32f1e-139">Any</span></span></p></td>
<td><p><span data-ttu-id="32f1e-140">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="32f1e-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="32f1e-141">Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClasAgent. exe) e o conjunto de logs</span><span class="sxs-lookup"><span data-stu-id="32f1e-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32f1e-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="32f1e-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="32f1e-143">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="32f1e-143">Any</span></span></p></td>
<td><p><span data-ttu-id="32f1e-144">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="32f1e-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="32f1e-145">Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClasAgent. exe) e o conjunto de logs</span><span class="sxs-lookup"><span data-stu-id="32f1e-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32f1e-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="32f1e-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="32f1e-147">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="32f1e-147">Any</span></span></p></td>
<td><p><span data-ttu-id="32f1e-148">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="32f1e-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="32f1e-149">Comandos do agente centralizado do serviço de log (ClsController. exe) ou agente (ClasAgent. exe) e o conjunto de logs</span><span class="sxs-lookup"><span data-stu-id="32f1e-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

