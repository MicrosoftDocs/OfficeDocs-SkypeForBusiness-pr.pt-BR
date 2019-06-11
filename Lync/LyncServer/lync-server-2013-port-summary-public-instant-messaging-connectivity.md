---
title: 'Lync Server 2013: Resumo de porta-conectividade de mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bb6b8d0d9277b7d77440519596da76585b9d91b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="005da-102">Resumo de portabilidade-conectividade de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="005da-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="005da-103">_**Tópico da última modificação:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="005da-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="005da-104">Para configurar o firewall para portas e protocolos necessários para dar suporte à conectividade de mensagens instantâneas públicas, primeiro Observe que o SIP/MTLS/TCP 5061 é bidirecional para a conta da capacidade dos contatos no provedor de IM públicos entrarem em contato com os clientes do Lync ou do Lync para entre em contato com contatos públicos de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="005da-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="005da-105">O Windows Live Messenger pode participar de comunicações de áudio/vídeo com clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="005da-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="005da-106">Isso conta com uma configuração de protocolo e porta de firewall muito parecidas que você normalmente teria no firewall para dar suporte a clientes Lync como usuários externos.</span><span class="sxs-lookup"><span data-stu-id="005da-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="005da-107">Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo.</span><span class="sxs-lookup"><span data-stu-id="005da-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="005da-108">A Federação com o Windows Live Messenger não requer mais licenças de usuário/dispositivo além da licença de acesso de cliente padrão do Lync (CAL).</span><span class="sxs-lookup"><span data-stu-id="005da-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="005da-109">A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</span><span class="sxs-lookup"><span data-stu-id="005da-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="005da-110">A Federação com contatos de cliente do Messenger será encerrada oficialmente em 15 de março de 2013, exceto para a China continental.</span><span class="sxs-lookup"><span data-stu-id="005da-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="005da-111">O Skype se tornará o cliente de Federação para usuários federados que usaram anteriormente o Messenger.</span><span class="sxs-lookup"><span data-stu-id="005da-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="005da-112">Resumo do Firewall – Conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="005da-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="005da-113">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="005da-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="005da-114">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="005da-114">Source IP address</span></span></th>
<th><span data-ttu-id="005da-115">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="005da-115">Destination IP address</span></span></th>
<th><span data-ttu-id="005da-116">Notas</span><span class="sxs-lookup"><span data-stu-id="005da-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="005da-117">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="005da-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="005da-118">Parceiros de conectividade de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="005da-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="005da-119">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="005da-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="005da-120">Para conectividade de mensagem de chat pública e federada que usa SIP.</span><span class="sxs-lookup"><span data-stu-id="005da-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="005da-121">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="005da-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="005da-122">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="005da-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="005da-123">Parceiros de conectividade de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="005da-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="005da-124">Para conectividade de mensagem de chat pública e federada que usa SIP.</span><span class="sxs-lookup"><span data-stu-id="005da-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="005da-125">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="005da-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="005da-126">Clientes</span><span class="sxs-lookup"><span data-stu-id="005da-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="005da-127">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="005da-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="005da-128">Tráfego SIP do cliente ao servidor para o acesso do usuário externo.</span><span class="sxs-lookup"><span data-stu-id="005da-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="005da-129">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="005da-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="005da-130">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="005da-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="005da-131">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="005da-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="005da-132">Usado para sessões de A/V com o Windows Live Messenger se a conectividade de mensagem de chat pública estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="005da-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="005da-133">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="005da-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="005da-134">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="005da-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="005da-135">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="005da-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="005da-136">Necessário para conectividade de IM pública com o Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="005da-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="005da-137">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="005da-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="005da-138">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="005da-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="005da-139">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="005da-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="005da-140">Necessário para conectividade de IM pública com o Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="005da-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="005da-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="005da-141">See Also</span></span>


[<span data-ttu-id="005da-142">Cenários de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="005da-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="005da-143">Determinar firewall A/V externo e requisitos de porta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="005da-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

