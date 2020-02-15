---
title: 'Lync Server 2013: Resumo de DNS-proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fde945b4bd08020a072f36be073169454e423279
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="fa327-102">Resumo de DNS-proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa327-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa327-103">_**Última modificação do tópico:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="fa327-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="fa327-104">Você configura dois adaptadores de rede em seu proxy reverso como a seguir:</span><span class="sxs-lookup"><span data-stu-id="fa327-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="fa327-105">Requisitos do Adaptador de Rede do Proxy Reverso</span><span class="sxs-lookup"><span data-stu-id="fa327-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="fa327-106">Exemplo do **Adaptador de rede 1 (interface interna)**</span><span class="sxs-lookup"><span data-stu-id="fa327-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="fa327-107">Interface interna com 172.25.33.40 atribuído.</span><span class="sxs-lookup"><span data-stu-id="fa327-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="fa327-108">Nenhum gateway padrão é definido.</span><span class="sxs-lookup"><span data-stu-id="fa327-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="fa327-109">Verifique se há uma rota da rede que contém a interface interna do proxy reverso para qualquer rede que contenha servidores de pool Front-end do Lync Server (por exemplo, de 172.25.33.0 para 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="fa327-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="fa327-110">Exemplo do **Adaptador de rede 2 (interface externa)**</span><span class="sxs-lookup"><span data-stu-id="fa327-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="fa327-111">Um mínimo de um endereço IP público é atribuído a este adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="fa327-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="fa327-p101">O gateway é definido para o ponto do roteador ou firewall integrado em seu perímetro externo. (10.45.16.1 nos exemplos de cenário)</span><span class="sxs-lookup"><span data-stu-id="fa327-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="fa327-114">Registros DNS necessários para proxy inverso</span><span class="sxs-lookup"><span data-stu-id="fa327-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa327-115">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="fa327-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="fa327-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="fa327-116">FQDN</span></span></th>
<th><span data-ttu-id="fa327-117">Endereço IP</span><span class="sxs-lookup"><span data-stu-id="fa327-117">IP address</span></span></th>
<th><span data-ttu-id="fa327-118">Mapear para/comentários</span><span class="sxs-lookup"><span data-stu-id="fa327-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa327-119">DNS/A Externo</span><span class="sxs-lookup"><span data-stu-id="fa327-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fa327-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa327-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fa327-121">Ouvidor atribuído para recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="fa327-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="fa327-p102">Serviços da Web externos da implantação interna. Registros adicionais podem ser definidos e criados para todos os pools e servidores únicos para qualquer domínio SIP que usará este proxy reverso e tenha os serviços da Web externos definidos.</span><span class="sxs-lookup"><span data-stu-id="fa327-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa327-124">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="fa327-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fa327-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa327-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fa327-126">Ouvidor atribuído para recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="fa327-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="fa327-127">Serviços Web externos para os diretores ou pools de diretor em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="fa327-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="fa327-128">Você pode definir quantos directors forem diferentes de diretores, dos quais podem ser associados a outros domínios SIP.</span><span class="sxs-lookup"><span data-stu-id="fa327-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="fa327-129">A definição dos registros DNS para e publicação dos diretores não é um pool de front-ends ou a decisão diretor.</span><span class="sxs-lookup"><span data-stu-id="fa327-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="fa327-130">Você deve definir e publicar os serviços Web externos do diretor e do pool de front-end, se estiver usando diretores.</span><span class="sxs-lookup"><span data-stu-id="fa327-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="fa327-131">Os tipos específicos de tráfego (para autenticação e outros usos) serão enviados para o diretor primeiro, se for definido na topologia.</span><span class="sxs-lookup"><span data-stu-id="fa327-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa327-132">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="fa327-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fa327-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa327-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fa327-134">Ouvidor atribuído para recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="fa327-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="fa327-135">Conferência discada publicada externamente</span><span class="sxs-lookup"><span data-stu-id="fa327-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa327-136">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="fa327-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fa327-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa327-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fa327-138">Ouvidor atribuído para recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="fa327-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="fa327-139">Conferências publicadas externamente</span><span class="sxs-lookup"><span data-stu-id="fa327-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa327-140">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="fa327-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fa327-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa327-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fa327-142">Ouvinte atribuído para o servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="fa327-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="fa327-143">Servidor do Office Web Apps implantado internamente ou no perímetro e publicado para acesso de cliente externo</span><span class="sxs-lookup"><span data-stu-id="fa327-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa327-144">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="fa327-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fa327-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa327-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fa327-146">Ouvidor atribuído para recursos publicados externamente</span><span class="sxs-lookup"><span data-stu-id="fa327-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="fa327-147">Registro externo de descoberta do Lync para descoberta automática publicada externamente e inclui mobilidade, Microsoft Lync Web App e Agendador Web App</span><span class="sxs-lookup"><span data-stu-id="fa327-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

