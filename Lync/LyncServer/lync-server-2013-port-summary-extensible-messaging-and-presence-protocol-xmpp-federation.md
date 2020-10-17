---
title: Resumo de porta-Federação de XMPP (Extensible Messaging and Presence Protocol)
description: Resumo de porta-Federação de XMPP (Extensible Messaging and Presence Protocol).
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9508bc8b9fbcca6fb6a37478def258a9fa52c373
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543087"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="a6bc6-103">Resumo de porta-Federação XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6bc6-103">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6bc6-104">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a6bc6-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a6bc6-105">As portas e os protocolos definidos para o proxy XMPP (Extensible Messaging and Presence Protocol) implantado no servidor de borda permitem que as comunicações do parceiro federado do XMPP ao servidor de borda, além de permitir a comunicação do servidor de borda com o parceiro federado do XMPP.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-105">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="a6bc6-106">Uma regra também é definida no firewall de face interna do servidor front-end ou do pool de front-ends para o servidor de borda ou o pool de borda.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-106">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="a6bc6-107">Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="a6bc6-107">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6bc6-108">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="a6bc6-108">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a6bc6-109">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="a6bc6-109">Source (IP address)</span></span></th>
<th><span data-ttu-id="a6bc6-110">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="a6bc6-110">Destination (IP address)</span></span></th>
<th><span data-ttu-id="a6bc6-111">Comments</span><span class="sxs-lookup"><span data-stu-id="a6bc6-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6bc6-112">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a6bc6-112">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a6bc6-113">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a6bc6-113">Any</span></span></p></td>
<td><p><span data-ttu-id="a6bc6-114">Endereço IP da interface de serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="a6bc6-114">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a6bc6-115">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-115">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a6bc6-116">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="a6bc6-116">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6bc6-117">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a6bc6-117">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a6bc6-118">Endereço IP da interface de serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="a6bc6-118">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a6bc6-119">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a6bc6-119">Any</span></span></p></td>
<td><p><span data-ttu-id="a6bc6-120">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="a6bc6-120">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a6bc6-121">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="a6bc6-121">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6bc6-122">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="a6bc6-122">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="a6bc6-123">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a6bc6-123">Any</span></span></p></td>
<td><p><span data-ttu-id="a6bc6-124">IP da interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="a6bc6-124">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="a6bc6-125">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou no pool de front-ends para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a6bc6-125">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6bc6-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="a6bc6-126">See Also</span></span>


[<span data-ttu-id="a6bc6-127">Exemplo de configuração de XMPP no Lync Server 2013 – Federação do XMPP com Google Talk</span><span class="sxs-lookup"><span data-stu-id="a6bc6-127">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="a6bc6-128">Gerenciar parceiros federados do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6bc6-128">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

