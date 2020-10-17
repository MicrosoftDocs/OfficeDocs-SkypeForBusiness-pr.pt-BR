---
title: 'Lync Server 2013: Resumo de porta-proxy reverso'
description: 'Lync Server 2013: Resumo de porta-proxy reverso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf07800c91f5a28165eb05e14e2d775758460f50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555247"
---
# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="6ea5e-103">Resumo de porta-proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ea5e-103">Port summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ea5e-104">_**Última modificação do tópico:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="6ea5e-104">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="6ea5e-105">O proxy reverso tem requisitos mínimos de firewall e porta/protocolo.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-105">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="6ea5e-106">Os requisitos de firewall externos são o HTTPS/TCP/443 e o HTTP/TCP/80 opcional.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-106">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="6ea5e-107">O HTTPS é usado para comunicações seguras SSL e TLS por meio do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-107">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="6ea5e-108">HTTP é usado se você optar por permitir o acesso ao serviço de descoberta automática ao modificar certificados pode ser muito difícil ou não ser justificado.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-108">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="6ea5e-109">Os clientes esperam entrar em contato com o servidor do Office Web Apps no HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-109">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="6ea5e-110">O servidor do Office Web Apps espera a comunicação de clientes internos em HTTPS/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-110">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="6ea5e-111">A configuração recomendada é permitir HTTPS/TCP/443 do proxy reverso para o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-111">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="6ea5e-112">A porta 8080 é usada para rotear o tráfego da interface interna do proxy reverso para o servidor front-end, VIP (IP virtual) do pool de front-end ou o diretor opcional ou VIP do pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-112">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="6ea5e-113">A porta TCP 8080 é necessária para dispositivos móveis que executam o Lync para localizar o serviço de descoberta automática em situações em que a modificação do certificado de regra de publicação do serviço Web externo é indesejável (por exemplo, se você tiver um grande número de domínios SIP).</span><span class="sxs-lookup"><span data-stu-id="6ea5e-113">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="6ea5e-114">Se você optar por adquirir novos certificados com as entradas de SAN necessárias, a porta TCP 8080 não será necessária e será opcional.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-114">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="6ea5e-115">A porta 4443 é usada para o tráfego da interface interna do proxy reverso para o servidor front-end, IP virtual do pool de front-end (VIP) ou o diretor opcional ou VIP do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="6ea5e-115">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="6ea5e-116">![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="6ea5e-116">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="6ea5e-117">Não confunda o 4443 sobre TCP do proxy reverso para a implantação interna da porta 4443 sobre o tráfego TCP do servidor Standard Edition ou do pool de front-ends que gerencia a função de repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-117">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="6ea5e-118">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="6ea5e-118">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="6ea5e-119">Detalhes de firewall do servidor proxy reverso: interface externa</span><span class="sxs-lookup"><span data-stu-id="6ea5e-119">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ea5e-120">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="6ea5e-120">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6ea5e-121">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="6ea5e-121">Source IP Address</span></span></th>
<th><span data-ttu-id="6ea5e-122">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="6ea5e-122">Destination IP Address</span></span></th>
<th><span data-ttu-id="6ea5e-123">Observações</span><span class="sxs-lookup"><span data-stu-id="6ea5e-123">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ea5e-124">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="6ea5e-124">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-125">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6ea5e-125">Any</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-126">Ouvinte de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="6ea5e-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-127">Opcion Redirecionamento para HTTPS se o usuário inserir http:// &lt; publishedSiteFQDN &gt; .</span><span class="sxs-lookup"><span data-stu-id="6ea5e-127">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="6ea5e-128">Também necessário se estiver usando o Office Web Apps para conferência e o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação do serviço Web externo.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-128">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ea5e-129">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6ea5e-129">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-130">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6ea5e-130">Any</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-131">Ouvinte de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="6ea5e-131">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-132">Downloads do catálogo de endereços, serviço de consulta à Web do catálogo de endereços, descoberta automática, atualizações do cliente, conteúdo da reunião, atualizações de dispositivo, expansão de grupo, Office Web Apps para conferência, conferência discada e reuniões.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-132">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="6ea5e-133">Detalhes de firewall do servidor proxy reverso: interface interna</span><span class="sxs-lookup"><span data-stu-id="6ea5e-133">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ea5e-134">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="6ea5e-134">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6ea5e-135">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="6ea5e-135">Source IP Address</span></span></th>
<th><span data-ttu-id="6ea5e-136">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="6ea5e-136">Destination IP Address</span></span></th>
<th><span data-ttu-id="6ea5e-137">Observações</span><span class="sxs-lookup"><span data-stu-id="6ea5e-137">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ea5e-138">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="6ea5e-138">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-139">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="6ea5e-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-140">Servidor front-end, pool de front-ends, diretor, pool de diretores</span><span class="sxs-lookup"><span data-stu-id="6ea5e-140">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-141">Necessário se estiver usando o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação do serviço Web externo.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-141">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="6ea5e-142">O tráfego enviado para a porta 80 na interface externa do proxy reverso é redirecionado para um pool na porta 8080 a partir da interface interna do proxy reverso, para que os serviços Web do pool possam distingui-lo do tráfego Web interno.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-142">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ea5e-143">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="6ea5e-143">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-144">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="6ea5e-144">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-145">Servidor front-end, pool de front-ends, diretor, pool de diretores</span><span class="sxs-lookup"><span data-stu-id="6ea5e-145">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-146">O tráfego enviado para a porta 443 na interface externa do proxy reverso é redirecionado para um pool na porta 4443 a partir da interface interna do proxy reverso, para que os serviços Web do pool possam distingui-lo do tráfego Web interno.</span><span class="sxs-lookup"><span data-stu-id="6ea5e-146">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ea5e-147">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6ea5e-147">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-148">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="6ea5e-148">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="6ea5e-149">Office Web Apps para conferência</span><span class="sxs-lookup"><span data-stu-id="6ea5e-149">Office Web Apps for conferencing</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

