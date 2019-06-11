---
title: Resumo da porta-SIP, Federação do XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2edcad9806c5e6c8714f3face301211633a53fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="38ea2-102">Resumo da porta-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38ea2-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38ea2-103">_**Tópico da última modificação:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="38ea2-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="38ea2-104">Os requisitos de portabilidade, protocolo e firewall para federação com o Microsoft Lync Server 2013, o Lync Server 2010 e o Office Communications Server são semelhantes aos do servidor de borda implantado.</span><span class="sxs-lookup"><span data-stu-id="38ea2-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="38ea2-105">Os clientes iniciam a comunicação com o serviço de borda de acesso por TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="38ea2-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="38ea2-106">No entanto, os parceiros federados iniciarão as comunicações com o serviço de borda de acesso sobre MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="38ea2-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="38ea2-107">Para configurar o firewall para portas e protocolos necessários para dar suporte à conectividade de mensagens instantâneas públicas, primeiro Observe que o SIP/MTLS/TCP 5061 é bidirecional para a conta da capacidade dos contatos no provedor de IM públicos entrarem em contato com os clientes do Lync ou do Lync para entre em contato com contatos públicos de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="38ea2-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="38ea2-108">O Windows Live Messenger pode participar de comunicações de áudio/vídeo com clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="38ea2-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="38ea2-109">Isso conta com uma configuração de protocolo e porta de firewall muito parecidas que você normalmente teria no firewall para dar suporte a clientes Lync como usuários externos.</span><span class="sxs-lookup"><span data-stu-id="38ea2-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="38ea2-110">Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo.</span><span class="sxs-lookup"><span data-stu-id="38ea2-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="38ea2-111">A Federação com o Windows Live Messenger não requer mais licenças de usuário/dispositivo além da licença de acesso de cliente padrão do Lync (CAL).</span><span class="sxs-lookup"><span data-stu-id="38ea2-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="38ea2-112">A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</span><span class="sxs-lookup"><span data-stu-id="38ea2-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="38ea2-113">A Federação com contatos de cliente do Messenger será encerrada oficialmente em 15 de março de 2013, exceto para a China continental.</span><span class="sxs-lookup"><span data-stu-id="38ea2-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="38ea2-114">O Skype se tornará o cliente de Federação para usuários federados que usaram anteriormente o Messenger.</span><span class="sxs-lookup"><span data-stu-id="38ea2-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="38ea2-115">As portas e protocolos definidos para o proxy de protocolo de presença e mensagens extensível (XMPP) implantadas no servidor de borda permitem comunicações do parceiro federado do XMPP com o servidor de borda e também permite a comunicação do servidor de borda com o XMPP parceiro federado.</span><span class="sxs-lookup"><span data-stu-id="38ea2-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="38ea2-116">Uma regra também é definida no firewall de face interna do servidor front-end ou do pool de front-ends para o servidor de borda ou o pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="38ea2-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="38ea2-117">Resumo do firewall-Federação SIP</span><span class="sxs-lookup"><span data-stu-id="38ea2-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38ea2-118">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="38ea2-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="38ea2-119">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="38ea2-119">Source IP address</span></span></th>
<th><span data-ttu-id="38ea2-120">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="38ea2-120">Destination IP address</span></span></th>
<th><span data-ttu-id="38ea2-121">Notas</span><span class="sxs-lookup"><span data-stu-id="38ea2-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38ea2-122">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38ea2-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="38ea2-123">Endereço IP público do serviço de borda do Access</span><span class="sxs-lookup"><span data-stu-id="38ea2-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="38ea2-124">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="38ea2-124">Any</span></span></p></td>
<td><p><span data-ttu-id="38ea2-125">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="38ea2-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="38ea2-126">Resumo do Firewall – Conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="38ea2-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38ea2-127">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="38ea2-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="38ea2-128">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="38ea2-128">Source IP address</span></span></th>
<th><span data-ttu-id="38ea2-129">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="38ea2-129">Destination IP address</span></span></th>
<th><span data-ttu-id="38ea2-130">Notas</span><span class="sxs-lookup"><span data-stu-id="38ea2-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38ea2-131">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38ea2-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="38ea2-132">Parceiros de conectividade de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="38ea2-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="38ea2-133">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="38ea2-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="38ea2-134">Para conectividade de mensagem de chat pública e federada que usa SIP.</span><span class="sxs-lookup"><span data-stu-id="38ea2-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ea2-135">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="38ea2-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="38ea2-136">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="38ea2-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="38ea2-137">Parceiros de conectividade de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="38ea2-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="38ea2-138">Para conectividade de mensagem de chat pública e federada que usa SIP.</span><span class="sxs-lookup"><span data-stu-id="38ea2-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ea2-139">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="38ea2-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="38ea2-140">Clientes</span><span class="sxs-lookup"><span data-stu-id="38ea2-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="38ea2-141">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="38ea2-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="38ea2-142">Tráfego SIP do cliente ao servidor para o acesso do usuário externo.</span><span class="sxs-lookup"><span data-stu-id="38ea2-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ea2-143">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="38ea2-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="38ea2-144">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="38ea2-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="38ea2-145">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="38ea2-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="38ea2-146">Usado para sessões de A/V com o Windows Live Messenger se a conectividade de mensagem de chat pública estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="38ea2-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ea2-147">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="38ea2-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="38ea2-148">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="38ea2-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="38ea2-149">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="38ea2-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="38ea2-150">Necessário para conectividade de IM pública com o Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="38ea2-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ea2-151">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="38ea2-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="38ea2-152">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="38ea2-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="38ea2-153">Interface de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="38ea2-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="38ea2-154">Necessário para conectividade de IM pública com o Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="38ea2-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="38ea2-155">Resumo de firewall-mensagens extensíveis e protocolo de presença (XMPP)</span><span class="sxs-lookup"><span data-stu-id="38ea2-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38ea2-156">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="38ea2-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="38ea2-157">Fonte (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="38ea2-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="38ea2-158">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="38ea2-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="38ea2-159">Comentários</span><span class="sxs-lookup"><span data-stu-id="38ea2-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38ea2-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="38ea2-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="38ea2-161">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="38ea2-161">Any</span></span></p></td>
<td><p><span data-ttu-id="38ea2-162">Endereço IP da interface do serviço de borda do Access</span><span class="sxs-lookup"><span data-stu-id="38ea2-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="38ea2-163">Porta de comunicação de servidor para servidor padrão para XMPP.</span><span class="sxs-lookup"><span data-stu-id="38ea2-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="38ea2-164">Permite a comunicação com o servidor de borda XMPP o proxy de parceiros de XMPP federado</span><span class="sxs-lookup"><span data-stu-id="38ea2-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ea2-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="38ea2-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="38ea2-166">Endereço IP da interface do serviço de borda do Access</span><span class="sxs-lookup"><span data-stu-id="38ea2-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="38ea2-167">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="38ea2-167">Any</span></span></p></td>
<td><p><span data-ttu-id="38ea2-168">Porta de comunicação de servidor para servidor padrão para XMPP.</span><span class="sxs-lookup"><span data-stu-id="38ea2-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="38ea2-169">Permite a comunicação do proxy do servidor de borda XMPP com parceiros do XMPP federado</span><span class="sxs-lookup"><span data-stu-id="38ea2-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ea2-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="38ea2-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="38ea2-171">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="38ea2-171">Any</span></span></p></td>
<td><p><span data-ttu-id="38ea2-172">IP de interface do servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="38ea2-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="38ea2-173">Tráfego de XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-end para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="38ea2-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38ea2-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="38ea2-174">See Also</span></span>


[<span data-ttu-id="38ea2-175">Cenários de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38ea2-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="38ea2-176">Determinar firewall A/V externo e requisitos de porta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38ea2-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="38ea2-177">Gerenciar parceiros XMPP federados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38ea2-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

