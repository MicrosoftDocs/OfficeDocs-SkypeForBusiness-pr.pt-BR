---
title: 'Lync Server 2013: Resumo de porta-diretor único'
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
ms.openlocfilehash: 541cd7eb560cd9d509c5c0beec206803f2cddecc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533988"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="f59be-102">Resumo de porta-diretor único no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f59be-102">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f59be-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f59be-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f59be-104">Os requisitos de porta de firewall para um único diretor consistem nas portas usadas para estabelecer comunicação com o diretor da interface interna ou da rede de face interna do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="f59be-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="f59be-105">O Microsoft Lync Server 2013, por padrão, espera que as portas HTTP/TCP 8080 e HTTPS/TCP 4443 sejam abertas do proxy reverso para o diretor, bem como o pool de front-ends e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f59be-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="f59be-106">Além disso, deve haver comunicação SIP (Session Initiation Protocol) da interface interna do servidor de borda para o diretor e para o pool de front-ends e servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="f59be-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="f59be-107">O protocolo SIP usa SIP/MTLS/TCP 5061 do servidor de borda para o pool de front-ends e servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f59be-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="f59be-108">Uma regra que permite a comunicação SIP/MTLS/TCP 5061 do diretor, do pool de front-ends e do servidor front-end para a interface interna do servidor de borda também deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="f59be-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="f59be-109">Portas e protocolos de diretor único para definições de firewall</span><span class="sxs-lookup"><span data-stu-id="f59be-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f59be-110">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="f59be-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f59be-111">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="f59be-111">Source IP address</span></span></th>
<th><span data-ttu-id="f59be-112">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="f59be-112">Destination IP address</span></span></th>
<th><span data-ttu-id="f59be-113">Observações</span><span class="sxs-lookup"><span data-stu-id="f59be-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f59be-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="f59be-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="f59be-115">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="f59be-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="f59be-116">Diretor</span><span class="sxs-lookup"><span data-stu-id="f59be-116">Director</span></span></p></td>
<td><p><span data-ttu-id="f59be-117">Recebido inicialmente pelo lado externo do proxy reverso, a comunicação é enviada para os serviços Web diretor e servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f59be-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59be-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="f59be-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="f59be-119">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="f59be-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="f59be-120">Diretor</span><span class="sxs-lookup"><span data-stu-id="f59be-120">Director</span></span></p></td>
<td><p><span data-ttu-id="f59be-121">Recebido inicialmente pelo lado externo do proxy reverso, a comunicação é enviada para os serviços Web diretor e servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f59be-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59be-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="f59be-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="f59be-123">Diretor</span><span class="sxs-lookup"><span data-stu-id="f59be-123">Director</span></span></p></td>
<td><p><span data-ttu-id="f59be-124">Servidor Front-End ou pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="f59be-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="f59be-125">Comunicação entre servidores entre o diretor e o servidor front-end</span><span class="sxs-lookup"><span data-stu-id="f59be-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59be-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="f59be-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="f59be-127">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="f59be-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="f59be-128">Serviços Web diretor</span><span class="sxs-lookup"><span data-stu-id="f59be-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="f59be-129">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="f59be-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59be-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="f59be-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="f59be-131">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="f59be-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="f59be-132">Serviços Web diretor</span><span class="sxs-lookup"><span data-stu-id="f59be-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="f59be-133">O diretor fornece serviços Web para clientes internos e externos.</span><span class="sxs-lookup"><span data-stu-id="f59be-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59be-134">SIP/MTLS/5061</span><span class="sxs-lookup"><span data-stu-id="f59be-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="f59be-135">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="f59be-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f59be-136">Diretor</span><span class="sxs-lookup"><span data-stu-id="f59be-136">Director</span></span></p></td>
<td><p><span data-ttu-id="f59be-137">Comunicação SIP do servidor de borda para o diretor e o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f59be-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59be-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="f59be-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="f59be-139">Qualquer</span><span class="sxs-lookup"><span data-stu-id="f59be-139">Any</span></span></p></td>
<td><p><span data-ttu-id="f59be-140">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="f59be-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f59be-141">Comandos e coleção de registros do controlador (ClsController.exe) ou agente (ClasAgent.exe) de serviços centralizados de registro</span><span class="sxs-lookup"><span data-stu-id="f59be-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f59be-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="f59be-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="f59be-143">Qualquer</span><span class="sxs-lookup"><span data-stu-id="f59be-143">Any</span></span></p></td>
<td><p><span data-ttu-id="f59be-144">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="f59be-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f59be-145">Comandos e coleção de registros do controlador (ClsController.exe) ou agente (ClasAgent.exe) de serviços centralizados de registro</span><span class="sxs-lookup"><span data-stu-id="f59be-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f59be-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="f59be-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="f59be-147">Qualquer</span><span class="sxs-lookup"><span data-stu-id="f59be-147">Any</span></span></p></td>
<td><p><span data-ttu-id="f59be-148">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="f59be-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f59be-149">Comandos e coleção de registros do controlador (ClsController.exe) ou agente (ClasAgent.exe) de serviços centralizados de registro</span><span class="sxs-lookup"><span data-stu-id="f59be-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

