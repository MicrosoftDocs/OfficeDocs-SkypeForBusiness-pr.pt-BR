---
title: Resumo de porta-Federação de XMPP (Extensible Messaging and Presence Protocol)
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
ms.openlocfilehash: b72ab2f2912a78ee30e9c032592a704eccbab8bf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="3414b-102">Resumo de porta-Federação XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3414b-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3414b-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="3414b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="3414b-104">As portas e os protocolos definidos para o proxy XMPP (Extensible Messaging and Presence Protocol) implantado no servidor de borda permitem que as comunicações do parceiro federado do XMPP ao servidor de borda, além de permitir a comunicação do servidor de borda com o XMPP parceiro federado.</span><span class="sxs-lookup"><span data-stu-id="3414b-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="3414b-105">Uma regra também é definida no firewall de face interna do servidor front-end ou do pool de front-ends para o servidor de borda ou o pool de borda.</span><span class="sxs-lookup"><span data-stu-id="3414b-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="3414b-106">Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="3414b-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3414b-107">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="3414b-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3414b-108">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="3414b-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="3414b-109">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="3414b-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="3414b-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="3414b-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3414b-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3414b-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3414b-112">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3414b-112">Any</span></span></p></td>
<td><p><span data-ttu-id="3414b-113">Endereço IP da interface de serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="3414b-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3414b-114">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="3414b-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3414b-115">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="3414b-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3414b-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3414b-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3414b-117">Endereço IP da interface de serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="3414b-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3414b-118">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3414b-118">Any</span></span></p></td>
<td><p><span data-ttu-id="3414b-119">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="3414b-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3414b-120">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="3414b-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3414b-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="3414b-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="3414b-122">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3414b-122">Any</span></span></p></td>
<td><p><span data-ttu-id="3414b-123">IP da interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="3414b-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="3414b-124">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou no pool de front-ends para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3414b-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3414b-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="3414b-125">See Also</span></span>


[<span data-ttu-id="3414b-126">Exemplo de configuração de XMPP no Lync Server 2013 – Federação do XMPP com Google Talk</span><span class="sxs-lookup"><span data-stu-id="3414b-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="3414b-127">Gerenciar parceiros federados do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3414b-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

