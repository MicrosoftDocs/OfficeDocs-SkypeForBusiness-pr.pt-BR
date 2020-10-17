---
title: Resumo de porta-SIP, Federação XMPP e mensagens instantâneas públicas
description: Resumo de porta-SIP, Federação XMPP e mensagens instantâneas públicas.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566347"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="d5269-103">Resumo de porta-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5269-103">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5269-104">_**Última modificação do tópico:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="d5269-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="d5269-105">Requisitos de porta, protocolo e firewall para federação com o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server são semelhantes aos do servidor de borda implantado.</span><span class="sxs-lookup"><span data-stu-id="d5269-105">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="d5269-106">Os clientes iniciam a comunicação com o serviço de borda de acesso por TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="d5269-106">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="d5269-107">Parceiros federados no entanto, iniciarão comunicações com o serviço de borda de acesso sobre MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="d5269-107">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="d5269-108">Para configurar seu firewall para portas e protocolos necessários para dar suporte à conectividade de mensagens instantâneas públicas, primeiro Observe que SIP/MTLS/TCP 5061 é bidirecional para considerar a capacidade de os contatos no provedor de IM público entrarem em contato com os clientes do Lync ou para o Lync entrarem em contato com contatos públicos de IM.</span><span class="sxs-lookup"><span data-stu-id="d5269-108">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="d5269-109">O Windows Live Messenger pode participar de comunicações de áudio/vídeo com clientes Lync.</span><span class="sxs-lookup"><span data-stu-id="d5269-109">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="d5269-110">Isso conta para a porta de firewall muito parecida e a configuração de protocolo que você normalmente teria no firewall para dar suporte aos clientes do Lync como usuários externos.</span><span class="sxs-lookup"><span data-stu-id="d5269-110">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d5269-111">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="d5269-111">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d5269-112">A Federação com o Windows Live Messenger não requer nenhuma licença adicional de usuário/dispositivo além da licença de acesso para cliente (CAL) do Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="d5269-112">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="d5269-113">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="d5269-113">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="d5269-114">A Federação com contatos do cliente do Messenger será oficialmente termina em 15 de março de 2013, exceto para a China continental.</span><span class="sxs-lookup"><span data-stu-id="d5269-114">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="d5269-115">O Skype se tornará o cliente de Federação para usuários federados que usavam o Messenger anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d5269-115">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="d5269-116">As portas e os protocolos definidos para o proxy XMPP (Extensible Messaging and Presence Protocol) implantado no servidor de borda permitem que as comunicações do parceiro federado do XMPP ao servidor de borda, além de permitir a comunicação do servidor de borda com o parceiro federado do XMPP.</span><span class="sxs-lookup"><span data-stu-id="d5269-116">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="d5269-117">Uma regra também é definida no firewall de face interna do servidor front-end ou do pool de front-ends para o servidor de borda ou o pool de borda.</span><span class="sxs-lookup"><span data-stu-id="d5269-117">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="d5269-118">Resumo do firewall-Federação SIP</span><span class="sxs-lookup"><span data-stu-id="d5269-118">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5269-119">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="d5269-119">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d5269-120">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="d5269-120">Source IP address</span></span></th>
<th><span data-ttu-id="d5269-121">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="d5269-121">Destination IP address</span></span></th>
<th><span data-ttu-id="d5269-122">Observações</span><span class="sxs-lookup"><span data-stu-id="d5269-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5269-123">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d5269-123">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d5269-124">Endereço IP público do serviço da Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="d5269-124">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d5269-125">Qualquer</span><span class="sxs-lookup"><span data-stu-id="d5269-125">Any</span></span></p></td>
<td><p><span data-ttu-id="d5269-126">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="d5269-126">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="d5269-127">Resumo do firewall – Conectividade pública de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="d5269-127">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5269-128">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="d5269-128">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d5269-129">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="d5269-129">Source IP address</span></span></th>
<th><span data-ttu-id="d5269-130">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="d5269-130">Destination IP address</span></span></th>
<th><span data-ttu-id="d5269-131">Observações</span><span class="sxs-lookup"><span data-stu-id="d5269-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5269-132">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d5269-132">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d5269-133">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="d5269-133">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d5269-134">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="d5269-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="d5269-135">Para conectividade federada e pública de IM que usam SIP.</span><span class="sxs-lookup"><span data-stu-id="d5269-135">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5269-136">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d5269-136">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d5269-137">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="d5269-137">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="d5269-138">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="d5269-138">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d5269-139">Para conectividade federada e pública de IM que usam SIP.</span><span class="sxs-lookup"><span data-stu-id="d5269-139">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5269-140">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="d5269-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d5269-141">Clientes</span><span class="sxs-lookup"><span data-stu-id="d5269-141">Clients</span></span></p></td>
<td><p><span data-ttu-id="d5269-142">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="d5269-142">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="d5269-143">Tráfego SIP de cliente para servidor para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="d5269-143">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5269-144">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d5269-144">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d5269-145">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="d5269-145">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="d5269-146">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d5269-146">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d5269-147">Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="d5269-147">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5269-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d5269-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d5269-149">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="d5269-149">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="d5269-150">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d5269-150">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d5269-151">Necessário para conectividade pública de IM com o Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="d5269-151">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5269-152">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d5269-152">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d5269-153">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d5269-153">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d5269-154">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="d5269-154">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="d5269-155">Necessário para conectividade pública de IM com o Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="d5269-155">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="d5269-156">Resumo do firewall-protocolo de presença e mensagens extensíveis (XMPP)</span><span class="sxs-lookup"><span data-stu-id="d5269-156">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5269-157">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="d5269-157">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d5269-158">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="d5269-158">Source (IP address)</span></span></th>
<th><span data-ttu-id="d5269-159">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="d5269-159">Destination (IP address)</span></span></th>
<th><span data-ttu-id="d5269-160">Comments</span><span class="sxs-lookup"><span data-stu-id="d5269-160">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5269-161">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d5269-161">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d5269-162">Qualquer</span><span class="sxs-lookup"><span data-stu-id="d5269-162">Any</span></span></p></td>
<td><p><span data-ttu-id="d5269-163">Endereço IP da interface de serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="d5269-163">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d5269-164">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="d5269-164">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d5269-165">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="d5269-165">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5269-166">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d5269-166">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d5269-167">Endereço IP da interface de serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="d5269-167">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d5269-168">Qualquer</span><span class="sxs-lookup"><span data-stu-id="d5269-168">Any</span></span></p></td>
<td><p><span data-ttu-id="d5269-169">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="d5269-169">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d5269-170">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="d5269-170">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5269-171">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="d5269-171">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="d5269-172">Qualquer</span><span class="sxs-lookup"><span data-stu-id="d5269-172">Any</span></span></p></td>
<td><p><span data-ttu-id="d5269-173">IP da interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="d5269-173">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="d5269-174">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou no pool de front-ends para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="d5269-174">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5269-175">Confira também</span><span class="sxs-lookup"><span data-stu-id="d5269-175">See Also</span></span>


[<span data-ttu-id="d5269-176">Cenários para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5269-176">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="d5269-177">Determinar firewall A/V externo e requisitos de porta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5269-177">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="d5269-178">Gerenciar parceiros federados do XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5269-178">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

