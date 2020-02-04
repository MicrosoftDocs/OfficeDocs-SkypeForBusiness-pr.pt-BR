---
title: 'Lync Server 2013: Resumo de porta - Proxy reverso'
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
ms.openlocfilehash: f2944cde932413f00b5a4dcb75cd4a37bd5b3a3a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="eac9e-102">Resumo de porta - Proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eac9e-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eac9e-103">_**Tópico da última modificação:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="eac9e-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="eac9e-104">O proxy reverso tem requisitos mínimos para firewall e porta/protocolo.</span><span class="sxs-lookup"><span data-stu-id="eac9e-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="eac9e-105">Os requisitos de firewall externo são HTTPS/TCP/443 e HTTP/TCP/80 opcionais.</span><span class="sxs-lookup"><span data-stu-id="eac9e-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="eac9e-106">HTTPS é usado para comunicações seguras SSL e TLS por meio do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="eac9e-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="eac9e-107">O HTTP é usado se você optar por permitir o acesso ao serviço de descoberta automática quando a modificação de certificados pode ser muito difícil ou não ser justificada pelo custo.</span><span class="sxs-lookup"><span data-stu-id="eac9e-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="eac9e-108">Os clientes esperam entrar em contato com o servidor do Office Web Apps no HTTPS.</span><span class="sxs-lookup"><span data-stu-id="eac9e-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="eac9e-109">O servidor Office Web Apps espera a comunicação de clientes internos em HTTPS/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="eac9e-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="eac9e-110">A configuração recomendada é permitir HTTPS/TCP/443 do proxy reverso para o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="eac9e-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="eac9e-111">A porta 8080 é usada para direcionar o tráfego da interface interna de proxy inverso para o servidor front-end, o VIP (IP virtual do pool de front-end) ou o diretor opcional ou VIP do pool do diretor.</span><span class="sxs-lookup"><span data-stu-id="eac9e-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="eac9e-112">A porta TCP 8080 é necessária para dispositivos móveis que executam o Lync para localizar o serviço de descoberta automática em situações em que a modificação do certificado de regra de publicação do serviço Web externo é indesejável (por exemplo, se você tiver um grande número de domínios SIP).</span><span class="sxs-lookup"><span data-stu-id="eac9e-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="eac9e-113">Se você optar por adquirir novos certificados com as entradas de SAN necessárias, a porta TCP 8080 não será necessária e será opcional.</span><span class="sxs-lookup"><span data-stu-id="eac9e-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="eac9e-114">A porta 4443 é usada para o tráfego da interface interna de proxy reverso para o servidor front-end, o VIP (IP virtual do pool de front-end) ou o diretor opcional ou VIP do pool do diretor</span><span class="sxs-lookup"><span data-stu-id="eac9e-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="eac9e-115">![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="eac9e-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="eac9e-116">Não confunda o 4443 sobre TCP do proxy reverso para a implantação interna da porta 4443 sobre o tráfego TCP do servidor Standard Edition ou do pool de front-ends que gerencia a função de repositório central de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="eac9e-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="eac9e-117">Detalhes de protocolo e porta</span><span class="sxs-lookup"><span data-stu-id="eac9e-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="eac9e-118">Detalhes do firewall para servidor de proxy reverso: interface externa</span><span class="sxs-lookup"><span data-stu-id="eac9e-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eac9e-119">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="eac9e-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="eac9e-120">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="eac9e-120">Source IP Address</span></span></th>
<th><span data-ttu-id="eac9e-121">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="eac9e-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="eac9e-122">Observações</span><span class="sxs-lookup"><span data-stu-id="eac9e-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eac9e-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="eac9e-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="eac9e-124">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="eac9e-124">Any</span></span></p></td>
<td><p><span data-ttu-id="eac9e-125">Escuta de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="eac9e-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="eac9e-126">Adicionais Redirecionamento para HTTPS se o usuário entrar&lt;http://&gt;publishedSiteFQDN.</span><span class="sxs-lookup"><span data-stu-id="eac9e-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="eac9e-127">Também necessário se estiver usando o Office Web Apps para conferência e o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação de serviço Web externo.</span><span class="sxs-lookup"><span data-stu-id="eac9e-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eac9e-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="eac9e-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="eac9e-129">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="eac9e-129">Any</span></span></p></td>
<td><p><span data-ttu-id="eac9e-130">Escuta de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="eac9e-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="eac9e-131">Downloads do catálogo de endereços, serviço de consulta à Web do catálogo de endereços, descoberta automática, atualizações do cliente, conteúdo da reunião, atualizações de dispositivo, expansão de grupo, Office Web Apps para conferência, conferência discada e reuniões.</span><span class="sxs-lookup"><span data-stu-id="eac9e-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="eac9e-132">Detalhes do firewall para servidor proxy reverso: interface interna</span><span class="sxs-lookup"><span data-stu-id="eac9e-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eac9e-133">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="eac9e-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="eac9e-134">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="eac9e-134">Source IP Address</span></span></th>
<th><span data-ttu-id="eac9e-135">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="eac9e-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="eac9e-136">Observações</span><span class="sxs-lookup"><span data-stu-id="eac9e-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eac9e-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="eac9e-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="eac9e-138">Interface de proxy inversa interna</span><span class="sxs-lookup"><span data-stu-id="eac9e-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="eac9e-139">Servidor front-end, pool de front-end, diretor, pool de diretor</span><span class="sxs-lookup"><span data-stu-id="eac9e-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="eac9e-140">Obrigatório se estiver usando o serviço de descoberta automática para dispositivos móveis executando o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação de serviço Web externo.</span><span class="sxs-lookup"><span data-stu-id="eac9e-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="eac9e-141">O tráfego enviado para a porta 80 na interface externa de proxy reverso é redirecionado para um pool na porta 8080 da interface interna de proxy reverso para que os serviços Web de pool possam distingui-lo do tráfego interno da Web.</span><span class="sxs-lookup"><span data-stu-id="eac9e-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eac9e-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="eac9e-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="eac9e-143">Interface de proxy inversa interna</span><span class="sxs-lookup"><span data-stu-id="eac9e-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="eac9e-144">Servidor front-end, pool de front-end, diretor, pool de diretor</span><span class="sxs-lookup"><span data-stu-id="eac9e-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="eac9e-145">O tráfego enviado para a porta 443 na interface externa de proxy reverso é redirecionado para um pool na porta 4443 da interface interna de proxy reverso para que os serviços Web de pool possam distingui-lo do tráfego interno da Web.</span><span class="sxs-lookup"><span data-stu-id="eac9e-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eac9e-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="eac9e-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="eac9e-147">Interface de proxy inversa interna</span><span class="sxs-lookup"><span data-stu-id="eac9e-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="eac9e-148">Office Web Apps para conferência</span><span class="sxs-lookup"><span data-stu-id="eac9e-148">Office Web Apps for conferencing</span></span></p></td>
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

