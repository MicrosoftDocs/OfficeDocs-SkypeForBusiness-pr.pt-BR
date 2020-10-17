---
title: Resumo de DNS-Federação do protocolo XMPP (Extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ac2e44382aa75b61ae4e2966b5ef87fd977e798
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532128"
---
# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="a9613-102">Resumo de DNS-Federação do protocolo XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9613-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9613-103">_**Última modificação do tópico:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="a9613-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="a9613-104">Para configurar o XMPP (Extensible Messaging and Presence Protocol) para sua implantação, você cria dois registros de DNS (sistema de nomes de domínio) em um servidor DNS externo que resolverá os registros para o serviço de borda de acesso do servidor de borda ou do pool de borda.</span><span class="sxs-lookup"><span data-stu-id="a9613-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="a9613-105">Resumo DNS para Mensagens Extensíveis e Protocolo de Presença</span><span class="sxs-lookup"><span data-stu-id="a9613-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9613-106">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="a9613-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="a9613-107">FQDN</span><span class="sxs-lookup"><span data-stu-id="a9613-107">FQDN</span></span></th>
<th><span data-ttu-id="a9613-108">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="a9613-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="a9613-109">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="a9613-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9613-110">DNS Externo/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="a9613-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="a9613-111">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="a9613-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a9613-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a9613-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a9613-113">XMPP interface externa do proxy no serviço de borda de acesso ou no pool de borda. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync onde contato com contatos do XMPP é permitido por meio da configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao usuário habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="a9613-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="a9613-114">Um domínio XMPP permitido também deve ser configurado na política de Parceiros Federados XMPP.</span><span class="sxs-lookup"><span data-stu-id="a9613-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="a9613-115">Veja os tópicos em <strong>Consulte também </strong> para mais detalhes</span><span class="sxs-lookup"><span data-stu-id="a9613-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9613-116">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="a9613-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a9613-117">xmpp.contoso.com (por exemplo)</span><span class="sxs-lookup"><span data-stu-id="a9613-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="a9613-118">Endereço IP do serviço de borda de acesso no servidor de borda ou no pool de borda que hospeda o proxy do XMPP</span><span class="sxs-lookup"><span data-stu-id="a9613-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="a9613-119">Aponta para o serviço de borda de acesso ou o pool de borda que hospeda o serviço de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="a9613-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="a9613-120">Tipicamente, o registro SRV que você criar apontará para este host (A ou AAAA) record</span><span class="sxs-lookup"><span data-stu-id="a9613-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9613-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="a9613-121">See Also</span></span>


[<span data-ttu-id="a9613-122">Configurando a Federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9613-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="a9613-123">Determinar requisitos de DNS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9613-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

