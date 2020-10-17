---
title: 'Lync Server 2013: Resumo de porta-descoberta automática'
description: 'Lync Server 2013: Resumo de porta-descoberta automática.'
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
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543137"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="b1a4e-103">Resumo de porta-descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1a4e-103">Port summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1a4e-104">_**Última modificação do tópico:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="b1a4e-104">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="b1a4e-105">O serviço de descoberta automática do Lync Server 2013 é executado nos servidores do diretor e do pool de front-ends, e quando publicado no DNS usando os `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` registros de host, pode ser usado por clientes para localizar recursos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="b1a4e-106">Para que os dispositivos móveis que executam o Lync Mobile usem a descoberta automática, você precisará primeiro modificar listas de nomes alternativos de entidades de certificado em qualquer diretor e servidor front-end executando o serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-106">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="b1a4e-107">Além disso, pode ser necessário modificar as listas de nomes alternativos de entidade nos certificados usados pelas regras de publicação de serviços de Web externa em proxies reversos.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="b1a4e-108">A decisão sobre a utilização de listas de nomes alternativos de entidades em proxies reversos baseia-se no fato de você publicar o serviço de descoberta automática na porta 80 ou na porta 443:</span><span class="sxs-lookup"><span data-stu-id="b1a4e-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="b1a4e-109">**Publicado na porta 80**     Para dispositivos móveis, nenhuma alteração de certificado será necessária se a consulta inicial para o serviço de descoberta automática ocorrer pela porta 80.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-109">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="b1a4e-110">Isso ocorre porque os dispositivos móveis que executam o Lync acessarão o proxy reverso na porta 80 externamente e, em seguida, serão redirecionados para um diretor ou servidor front-end na porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="b1a4e-111">**Publicado na porta 443**     A lista de nomes alternativos da entidade em certificados usados pela regra de publicação dos serviços Web externos deve conter uma `lyncdiscover.<sipdomain>` entrada para cada domínio SIP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b1a4e-112">Para novas instalações ou atualizações do Lync Server 2010 onde você implantou a mobilidade, você usou a porta 80 para descoberta automática do serviço de mobilidade ou emitiu novamente os certificados com o nome da entidade e os nomes alternativos da entidade apropriados.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-112">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="b1a4e-113">Revise os certificados no diretor e servidor front-end para confirmar qual caminho você escolheu.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-113">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="b1a4e-114">Detalhes de firewall do servidor proxy reverso: interface externa</span><span class="sxs-lookup"><span data-stu-id="b1a4e-114">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1a4e-115">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="b1a4e-115">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b1a4e-116">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="b1a4e-116">Source IP Address</span></span></th>
<th><span data-ttu-id="b1a4e-117">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="b1a4e-117">Destination IP Address</span></span></th>
<th><span data-ttu-id="b1a4e-118">Observações</span><span class="sxs-lookup"><span data-stu-id="b1a4e-118">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1a4e-119">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b1a4e-119">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-120">Qualquer</span><span class="sxs-lookup"><span data-stu-id="b1a4e-120">Any</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-121">Ouvinte de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="b1a4e-121">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-122">Opcion Redirecionamento para HTTPS se o usuário inserir http:// &lt; publishedSiteFQDN &gt; .</span><span class="sxs-lookup"><span data-stu-id="b1a4e-122">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="b1a4e-123">Também necessário se estiver usando o Office Web Apps para conferência e o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação do serviço Web externo.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-123">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1a4e-124">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b1a4e-124">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-125">Qualquer</span><span class="sxs-lookup"><span data-stu-id="b1a4e-125">Any</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-126">Ouvinte de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="b1a4e-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-127">Downloads do catálogo de endereços, serviço de consulta à Web do catálogo de endereços, descoberta automática, atualizações do cliente, conteúdo da reunião, atualizações de dispositivo, expansão de grupo, Office Web Apps para conferência, conferência discada e reuniões.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-127">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="b1a4e-128">Detalhes de firewall do servidor proxy reverso: interface interna</span><span class="sxs-lookup"><span data-stu-id="b1a4e-128">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1a4e-129">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="b1a4e-129">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b1a4e-130">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="b1a4e-130">Source IP Address</span></span></th>
<th><span data-ttu-id="b1a4e-131">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="b1a4e-131">Destination IP Address</span></span></th>
<th><span data-ttu-id="b1a4e-132">Observações</span><span class="sxs-lookup"><span data-stu-id="b1a4e-132">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1a4e-133">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="b1a4e-133">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-134">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="b1a4e-134">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-135">Servidor front-end, pool de front-ends, diretor, pool de diretores, Office Web Apps para conferência</span><span class="sxs-lookup"><span data-stu-id="b1a4e-135">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-136">Necessário se estiver usando o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação do serviço Web externo.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-136">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="b1a4e-137">O tráfego enviado para a porta 80 na interface externa do proxy reverso é redirecionado para um pool na porta 8080 a partir da interface interna do proxy reverso, para que os serviços Web do pool possam distingui-lo do tráfego Web interno.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-137">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1a4e-138">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b1a4e-138">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-139">Interface interna do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="b1a4e-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-140">Servidor front-end, pool de front-ends, diretor, pool de diretores, Office Web Apps para conferência</span><span class="sxs-lookup"><span data-stu-id="b1a4e-140">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="b1a4e-141">O tráfego enviado para a porta 443 na interface externa do proxy reverso é redirecionado para um pool na porta 4443 a partir da interface interna do proxy reverso, para que os serviços Web do pool possam distingui-lo do tráfego Web interno.</span><span class="sxs-lookup"><span data-stu-id="b1a4e-141">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

