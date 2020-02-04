---
title: 'Lync Server 2013: Resumo da porta-descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 945e3ed9d532f27676e250c29ab415646bd967ec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="4d785-102">Resumo da porta-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d785-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d785-103">_**Tópico da última modificação:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="4d785-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="4d785-104">O serviço de descoberta automática do Lync Server 2013 é executado nos servidores do diretor e do pool de front-end e, `lyncdiscover.<domain>` quando `lyncdiscoverinternal.<domain>` publicados no DNS, usando os registros de host e de host, podem ser usados por clientes para localizar os recursos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d785-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="4d785-105">Para que os dispositivos móveis que executam o Lync Mobile usem a descoberta automática, você precisa primeiro modificar listas de nomes alternativos de entidades de certificado em qualquer director e servidor front-end executando o serviço descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="4d785-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="4d785-106">Além disso, pode ser necessário modificar as listas de nomes alternativos de entidades nos certificados usados para regras de publicação de serviço Web externo em proxies reverso.</span><span class="sxs-lookup"><span data-stu-id="4d785-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="4d785-107">A decisão sobre se deve usar listas de nomes alternativos de entidades em proxies invertidos se baseia se você publica o serviço de descoberta automática na porta 80 ou na porta 443:</span><span class="sxs-lookup"><span data-stu-id="4d785-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="4d785-108">**Publicado na porta 80**   para dispositivos móveis, nenhuma alteração de certificado será necessária se a consulta inicial para o serviço descoberta automática ocorrer na porta 80.</span><span class="sxs-lookup"><span data-stu-id="4d785-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="4d785-109">Isso ocorre porque os dispositivos móveis que executam o Lync acessam o proxy reverso na porta 80 externamente e, em seguida, redirecionados para um diretor ou servidor front-end na porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="4d785-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="4d785-110">**Publicado na porta 443**   a lista de nomes alternativos de entidades nos certificados usados pela regra de publicação de serviços Web externos `lyncdiscover.<sipdomain>` deve conter uma entrada para cada domínio SIP dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="4d785-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4d785-111">Para novas instalações ou atualizações do Lync Server 2010 em que você implantou a mobilidade, você usou a porta 80 para descoberta automática do serviço de mobilidade ou emitiu novamente certificados com o nome da entidade apropriada e nomes alternativos da entidade no local.</span><span class="sxs-lookup"><span data-stu-id="4d785-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="4d785-112">Revise os certificados no seu diretor e servidor front-end para confirmar qual caminho você escolheu.</span><span class="sxs-lookup"><span data-stu-id="4d785-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="4d785-113">Detalhes do firewall para servidor de proxy reverso: interface externa</span><span class="sxs-lookup"><span data-stu-id="4d785-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d785-114">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="4d785-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4d785-115">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="4d785-115">Source IP Address</span></span></th>
<th><span data-ttu-id="4d785-116">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="4d785-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="4d785-117">Observações</span><span class="sxs-lookup"><span data-stu-id="4d785-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d785-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="4d785-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="4d785-119">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4d785-119">Any</span></span></p></td>
<td><p><span data-ttu-id="4d785-120">Escuta de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="4d785-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="4d785-121">Adicionais Redirecionamento para HTTPS se o usuário entrar&lt;http://&gt;publishedSiteFQDN.</span><span class="sxs-lookup"><span data-stu-id="4d785-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="4d785-122">Também necessário se estiver usando o Office Web Apps para conferência e o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação de serviço Web externo.</span><span class="sxs-lookup"><span data-stu-id="4d785-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d785-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4d785-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4d785-124">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4d785-124">Any</span></span></p></td>
<td><p><span data-ttu-id="4d785-125">Escuta de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="4d785-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="4d785-126">Downloads do catálogo de endereços, serviço de consulta à Web do catálogo de endereços, descoberta automática, atualizações do cliente, conteúdo da reunião, atualizações de dispositivo, expansão de grupo, Office Web Apps para conferência, conferência discada e reuniões.</span><span class="sxs-lookup"><span data-stu-id="4d785-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="4d785-127">Detalhes do firewall para servidor proxy reverso: interface interna</span><span class="sxs-lookup"><span data-stu-id="4d785-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d785-128">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="4d785-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4d785-129">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="4d785-129">Source IP Address</span></span></th>
<th><span data-ttu-id="4d785-130">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="4d785-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="4d785-131">Observações</span><span class="sxs-lookup"><span data-stu-id="4d785-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d785-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="4d785-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="4d785-133">Interface de proxy inversa interna</span><span class="sxs-lookup"><span data-stu-id="4d785-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="4d785-134">Servidor front-end, pool de front-end, diretor, pool do director, Office Web Apps para conferência</span><span class="sxs-lookup"><span data-stu-id="4d785-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="4d785-135">Obrigatório se estiver usando o serviço de descoberta automática para dispositivos móveis executando o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação de serviço Web externo.</span><span class="sxs-lookup"><span data-stu-id="4d785-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="4d785-136">O tráfego enviado para a porta 80 na interface externa de proxy reverso é redirecionado para um pool na porta 8080 da interface interna de proxy reverso para que os serviços Web de pool possam distingui-lo do tráfego interno da Web.</span><span class="sxs-lookup"><span data-stu-id="4d785-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d785-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="4d785-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="4d785-138">Interface de proxy inversa interna</span><span class="sxs-lookup"><span data-stu-id="4d785-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="4d785-139">Servidor front-end, pool de front-end, diretor, pool do director, Office Web Apps para conferência</span><span class="sxs-lookup"><span data-stu-id="4d785-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="4d785-140">O tráfego enviado para a porta 443 na interface externa de proxy reverso é redirecionado para um pool na porta 4443 da interface interna de proxy reverso para que os serviços Web de pool possam distingui-lo do tráfego interno da Web.</span><span class="sxs-lookup"><span data-stu-id="4d785-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

