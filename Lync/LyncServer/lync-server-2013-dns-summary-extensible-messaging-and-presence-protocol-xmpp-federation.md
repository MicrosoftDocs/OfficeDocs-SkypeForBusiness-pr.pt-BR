---
title: Resumo de DNS-Federação de protocolo de presença e mensagens extensíveis (XMPP)
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
ms.openlocfilehash: 941996ea1167cf9baeee05567a00c71ea5ed4baa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="d6576-102">Resumo de DNS-Federação de protocolo de presença e mensagens extensíveis (XMPP) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6576-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6576-103">_**Tópico da última modificação:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="d6576-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="d6576-104">Para configurar o protocolo de presença e mensagens extensíveis (XMPP) para a sua implantação, crie dois registros DNS (sistema de nomes de domínio) em um servidor DNS externo que resolverá os registros para o serviço de borda de acesso do servidor de borda ou do pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="d6576-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="d6576-105">Resumo de DNS para o protocolo de mensagens extensíveis e de presença</span><span class="sxs-lookup"><span data-stu-id="d6576-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6576-106">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="d6576-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="d6576-107">FQDN</span><span class="sxs-lookup"><span data-stu-id="d6576-107">FQDN</span></span></th>
<th><span data-ttu-id="d6576-108">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="d6576-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="d6576-109">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="d6576-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6576-110">DNS/SRV/5269 externo</span><span class="sxs-lookup"><span data-stu-id="d6576-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="d6576-111">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d6576-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d6576-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d6576-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d6576-113">Interface externa de proxy XMPP no serviço de borda do Access ou no pool de bordas. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync nos quais o contato com contatos do XMPP é permitido pela configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao Usuário compatível com o Lync.</span><span class="sxs-lookup"><span data-stu-id="d6576-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="d6576-114">Um domínio XMPP permitido também deve ser configurado na política de parceiros federados do XMPP.</span><span class="sxs-lookup"><span data-stu-id="d6576-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="d6576-115">Consulte os tópicos em <strong>Consulte também</strong> para obter detalhes adicionais</span><span class="sxs-lookup"><span data-stu-id="d6576-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6576-116">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="d6576-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d6576-117">xmpp.contoso.com (por exemplo)</span><span class="sxs-lookup"><span data-stu-id="d6576-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="d6576-118">Endereço IP do serviço de borda de acesso em seu servidor de borda ou em um pool de bordas que hospeda o proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="d6576-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="d6576-119">Aponta para o serviço de borda de acesso ou o pool de bordas que hospeda o serviço de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="d6576-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="d6576-120">Geralmente, o registro SRV que você cria aponta para esse registro de host (A ou AAAA)</span><span class="sxs-lookup"><span data-stu-id="d6576-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6576-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="d6576-121">See Also</span></span>


[<span data-ttu-id="d6576-122">Configurando federação de XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6576-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="d6576-123">Determinar requisitios de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6576-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

