---
title: 'Lync Server 2013: Resumo de porta-conectividade de mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87a51e2030c17e7ed228a75b474b168a74924cb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="480e0-102">Resumo de porta-conectividade de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="480e0-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="480e0-103">_**Última modificação do tópico:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="480e0-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="480e0-104">Para configurar seu firewall para portas e protocolos necessários para dar suporte à conectividade de mensagens instantâneas públicas, primeiro Observe que SIP/MTLS/TCP 5061 é bidirecional para considerar a capacidade de os contatos no provedor de IM público entrarem em contato com os clientes do Lync ou para o Lync entrarem em contato com contatos públicos de IM.</span><span class="sxs-lookup"><span data-stu-id="480e0-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="480e0-105">O Windows Live Messenger pode participar de comunicações de áudio/vídeo com clientes Lync.</span><span class="sxs-lookup"><span data-stu-id="480e0-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="480e0-106">Isso conta para a porta de firewall muito parecida e a configuração de protocolo que você normalmente teria no firewall para dar suporte aos clientes do Lync como usuários externos.</span><span class="sxs-lookup"><span data-stu-id="480e0-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="480e0-107">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="480e0-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="480e0-108">A Federação com o Windows Live Messenger não requer nenhuma licença adicional de usuário/dispositivo além da licença de acesso para cliente (CAL) do Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="480e0-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="480e0-109">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="480e0-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="480e0-110">A Federação com contatos do cliente do Messenger será oficialmente termina em 15 de março de 2013, exceto para a China continental.</span><span class="sxs-lookup"><span data-stu-id="480e0-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="480e0-111">O Skype se tornará o cliente de Federação para usuários federados que usavam o Messenger anteriormente.</span><span class="sxs-lookup"><span data-stu-id="480e0-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="480e0-112">Resumo do firewall – Conectividade pública de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="480e0-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="480e0-113">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="480e0-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="480e0-114">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="480e0-114">Source IP address</span></span></th>
<th><span data-ttu-id="480e0-115">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="480e0-115">Destination IP address</span></span></th>
<th><span data-ttu-id="480e0-116">Observações</span><span class="sxs-lookup"><span data-stu-id="480e0-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="480e0-117">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="480e0-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="480e0-118">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="480e0-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="480e0-119">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="480e0-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="480e0-120">Para conectividade federada e pública de IM que usam SIP.</span><span class="sxs-lookup"><span data-stu-id="480e0-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480e0-121">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="480e0-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="480e0-122">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="480e0-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="480e0-123">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="480e0-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="480e0-124">Para conectividade federada e pública de IM que usam SIP.</span><span class="sxs-lookup"><span data-stu-id="480e0-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="480e0-125">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="480e0-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="480e0-126">Clientes</span><span class="sxs-lookup"><span data-stu-id="480e0-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="480e0-127">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="480e0-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="480e0-128">Tráfego SIP de cliente para servidor para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="480e0-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480e0-129">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="480e0-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="480e0-130">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="480e0-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="480e0-131">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="480e0-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="480e0-132">Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="480e0-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="480e0-133">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="480e0-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="480e0-134">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="480e0-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="480e0-135">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="480e0-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="480e0-136">Necessário para conectividade pública de IM com o Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="480e0-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="480e0-137">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="480e0-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="480e0-138">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="480e0-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="480e0-139">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="480e0-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="480e0-140">Necessário para conectividade pública de IM com o Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="480e0-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="480e0-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="480e0-141">See Also</span></span>


[<span data-ttu-id="480e0-142">Cenários para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="480e0-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="480e0-143">Determinar firewall A/V externo e requisitos de porta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="480e0-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

