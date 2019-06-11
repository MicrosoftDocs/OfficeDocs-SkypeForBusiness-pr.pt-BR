---
title: 'Lync Server 2013: portas e protocolos para servidores internos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="80dd1-102">Portas e protocolos para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80dd1-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80dd1-103">_**Tópico da última modificação:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="80dd1-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="80dd1-104">Esta seção resume as portas e os protocolos usados por servidores, balanceadores de carga e clientes em uma implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80dd1-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="80dd1-105">Os clientes do Lync e do Communicator, quando envolvidos em uma comunicação de um para um, geralmente são chamados de ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="80dd1-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="80dd1-106">Tecnicamente, os dois clientes estão se comunicando em uma conversa de uma ou uma, com a IMMCU (unidade de controle Multipoint) do chat no meio.</span><span class="sxs-lookup"><span data-stu-id="80dd1-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="80dd1-107">O IMMCU é um componente do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="80dd1-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="80dd1-108">Colocar o IMMCU no fluxo de trabalho de comunicação necessário permite a gravação de detalhes da chamada e outros recursos que o servidor de front-end permite.</span><span class="sxs-lookup"><span data-stu-id="80dd1-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="80dd1-109">A comunicação é de uma porta de origem dinâmica no cliente para a porta de servidor front-end TLS/TCP/5061 (pressupondo o uso da segurança da camada de transporte recomendada).</span><span class="sxs-lookup"><span data-stu-id="80dd1-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="80dd1-110">Por design, a comunicação ponto a ponto (bem como mensagens instantâneas de vários participantes) só é possível quando o Lync Server e o IMMCU estão ativos e disponíveis.</span><span class="sxs-lookup"><span data-stu-id="80dd1-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="80dd1-111">Detalhes de protocolo e porta</span><span class="sxs-lookup"><span data-stu-id="80dd1-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80dd1-112">O Firewall do Windows deve estar em execução antes de iniciar os serviços do Lync Server em um servidor, pois isso ocorre quando o Lync Server abre as portas obrigatórias no firewall.</span><span class="sxs-lookup"><span data-stu-id="80dd1-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="80dd1-113">Para obter detalhes sobre a configuração de firewall para componentes de borda, consulte [determinar requisitos de firewall e porta externo A/V para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80dd1-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="80dd1-114">A tabela a seguir lista as portas que precisam ser abertas em cada função de servidor interno.</span><span class="sxs-lookup"><span data-stu-id="80dd1-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="80dd1-115">Portas do servidor necessárias (por Função de servidor)</span><span class="sxs-lookup"><span data-stu-id="80dd1-115">Required Server Ports (by Server Role)</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80dd1-116">Função de servidor</span><span class="sxs-lookup"><span data-stu-id="80dd1-116">Server role</span></span></th>
<th><span data-ttu-id="80dd1-117">Nome do serviço</span><span class="sxs-lookup"><span data-stu-id="80dd1-117">Service name</span></span></th>
<th><span data-ttu-id="80dd1-118">Porta</span><span class="sxs-lookup"><span data-stu-id="80dd1-118">Port</span></span></th>
<th><span data-ttu-id="80dd1-119">Protocolo</span><span class="sxs-lookup"><span data-stu-id="80dd1-119">Protocol</span></span></th>
<th><span data-ttu-id="80dd1-120">Notas</span><span class="sxs-lookup"><span data-stu-id="80dd1-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-121">Todos os servidores</span><span class="sxs-lookup"><span data-stu-id="80dd1-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-122">Navegador do SQL</span><span class="sxs-lookup"><span data-stu-id="80dd1-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="80dd1-123">1434</span><span class="sxs-lookup"><span data-stu-id="80dd1-123">1434</span></span></p></td>
<td><p><span data-ttu-id="80dd1-124">UDP</span><span class="sxs-lookup"><span data-stu-id="80dd1-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-125">Navegador do SQL para a cópia replicada local do banco de dados do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="80dd1-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-126">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-127">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-128">5060</span><span class="sxs-lookup"><span data-stu-id="80dd1-128">5060</span></span></p></td>
<td><p><span data-ttu-id="80dd1-129">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-130">Usada como opção pelos servidores Standard Edition e Servidores Front-End para rotas estáticas para serviços confiáveis, como servidores de controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="80dd1-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-131">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-132">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-133">5061</span><span class="sxs-lookup"><span data-stu-id="80dd1-133">5061</span></span></p></td>
<td><p><span data-ttu-id="80dd1-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-135">Usada pelos servidores Standard Edition e pools de front-ends em todas as comunicações SIP internas entre servidores (MTLS), em comunicações SIP entre o servidor e o cliente (TLS) e em comunicações SIP entre os servidores front-end e os servidores de mediação (MTLS).</span><span class="sxs-lookup"><span data-stu-id="80dd1-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="80dd1-136">Também usado para comunicações com o Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="80dd1-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-137">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-138">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-139">444</span><span class="sxs-lookup"><span data-stu-id="80dd1-139">444</span></span></p></td>
<td><p><span data-ttu-id="80dd1-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-140">HTTPS</span></span></p>
<p><span data-ttu-id="80dd1-141">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-142">Usado para comunicação HTTPS entre o foco (o componente do Lync Server que gerencia o estado da conferência) e os servidores individuais.</span><span class="sxs-lookup"><span data-stu-id="80dd1-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="80dd1-143">Essa porta também é usada para comunicação TCP entre aparelhos de ramificação sobreviventes e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="80dd1-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-144">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-145">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-146">135</span><span class="sxs-lookup"><span data-stu-id="80dd1-146">135</span></span></p></td>
<td><p><span data-ttu-id="80dd1-147">DCOM e RPC (controle de procedimento remoto)</span><span class="sxs-lookup"><span data-stu-id="80dd1-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-148">Usada para operações com base em DCOM, como Movendo Usuários, Sincronização do Replicador do Usuário e Sincronização do Catálogo de Endereços.</span><span class="sxs-lookup"><span data-stu-id="80dd1-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-149">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-150">Serviço de conferência IM do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-151">5062</span><span class="sxs-lookup"><span data-stu-id="80dd1-151">5062</span></span></p></td>
<td><p><span data-ttu-id="80dd1-152">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-153">Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).</span><span class="sxs-lookup"><span data-stu-id="80dd1-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-154">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-155">Serviço de conferência Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-156">8057</span><span class="sxs-lookup"><span data-stu-id="80dd1-156">8057</span></span></p></td>
<td><p><span data-ttu-id="80dd1-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-158">Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.</span><span class="sxs-lookup"><span data-stu-id="80dd1-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-159">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-160">Serviço de compatibilidade do Lync Server Web referencing</span><span class="sxs-lookup"><span data-stu-id="80dd1-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-161">8058</span><span class="sxs-lookup"><span data-stu-id="80dd1-161">8058</span></span></p></td>
<td><p><span data-ttu-id="80dd1-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-163">Usado para escutar conexões do modelo de objeto compartilhado persistente (PSOM) do cliente de reunião ao vivo e versões anteriores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80dd1-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-164">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-165">Serviço de conferência de áudio/vídeo do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-166">5063</span><span class="sxs-lookup"><span data-stu-id="80dd1-166">5063</span></span></p></td>
<td><p><span data-ttu-id="80dd1-167">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-168">Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="80dd1-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-169">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-170">Serviço de conferência de áudio/vídeo do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="80dd1-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="80dd1-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="80dd1-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-173">Intervalo de porta de mídia usado para videoconferência.</span><span class="sxs-lookup"><span data-stu-id="80dd1-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-174">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-175">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-176">80</span><span class="sxs-lookup"><span data-stu-id="80dd1-176">80</span></span></p></td>
<td><p><span data-ttu-id="80dd1-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="80dd1-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-178">Usada para comunicação dos Servidores Front-End com os FQDNs do farm da web (as URLs usadas pelos componentes da web IIS) quando HTTPS não é usado.</span><span class="sxs-lookup"><span data-stu-id="80dd1-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-179">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-180">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-181">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-181">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="80dd1-183">Usado para comunicação dos servidores front-End no farm da web FQDNs (as URLs usadas pelos componentes da web do IIS).</span><span class="sxs-lookup"><span data-stu-id="80dd1-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-184">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-185">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-186">8080</span><span class="sxs-lookup"><span data-stu-id="80dd1-186">8080</span></span></p></td>
<td><p><span data-ttu-id="80dd1-187">TCP e HTTP</span><span class="sxs-lookup"><span data-stu-id="80dd1-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-188">Usado pelos componentes da Web para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="80dd1-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-189">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-190">Servidor de componentes da Web</span><span class="sxs-lookup"><span data-stu-id="80dd1-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="80dd1-191">4443</span><span class="sxs-lookup"><span data-stu-id="80dd1-191">4443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="80dd1-193">Comunicações entre pools de front-end HTTPS (de Proxy Reverso) e HTTPS para conexão de Descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="80dd1-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-194">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-195">Servidor de componentes da Web</span><span class="sxs-lookup"><span data-stu-id="80dd1-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="80dd1-196">8060</span><span class="sxs-lookup"><span data-stu-id="80dd1-196">8060</span></span></p></td>
<td><p><span data-ttu-id="80dd1-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-198">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-199">Servidor de componentes da Web</span><span class="sxs-lookup"><span data-stu-id="80dd1-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="80dd1-200">8061</span><span class="sxs-lookup"><span data-stu-id="80dd1-200">8061</span></span></p></td>
<td><p><span data-ttu-id="80dd1-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-202">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-203">Componente dos serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="80dd1-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="80dd1-204">5086</span><span class="sxs-lookup"><span data-stu-id="80dd1-204">5086</span></span></p></td>
<td><p><span data-ttu-id="80dd1-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-206">Porta SIP usada pelos processos internos dos Serviços de Mobilidade</span><span class="sxs-lookup"><span data-stu-id="80dd1-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-207">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-208">Componente dos serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="80dd1-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="80dd1-209">5087</span><span class="sxs-lookup"><span data-stu-id="80dd1-209">5087</span></span></p></td>
<td><p><span data-ttu-id="80dd1-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-211">Porta SIP usada pelos processos internos dos Serviços de Mobilidade</span><span class="sxs-lookup"><span data-stu-id="80dd1-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-212">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-213">Componente dos serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="80dd1-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="80dd1-214">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-214">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-216">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-217">Serviço de atendedor do Lync Server Conferencing (conferência discada)</span><span class="sxs-lookup"><span data-stu-id="80dd1-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-218">5064</span><span class="sxs-lookup"><span data-stu-id="80dd1-218">5064</span></span></p></td>
<td><p><span data-ttu-id="80dd1-219">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-220">Usada para solicitações SIP de entrada para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="80dd1-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-221">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-222">Serviço de atendedor do Lync Server Conferencing (conferência discada)</span><span class="sxs-lookup"><span data-stu-id="80dd1-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-223">5072</span><span class="sxs-lookup"><span data-stu-id="80dd1-223">5072</span></span></p></td>
<td><p><span data-ttu-id="80dd1-224">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-225">Usado para solicitações SIP de entrada do atendente (discagem por conferência).</span><span class="sxs-lookup"><span data-stu-id="80dd1-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-226">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="80dd1-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="80dd1-227">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-228">5070</span><span class="sxs-lookup"><span data-stu-id="80dd1-228">5070</span></span></p></td>
<td><p><span data-ttu-id="80dd1-229">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-230">Usada pelo Servidor de Mediação para solicitações de entrada do Servidor Front-End para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="80dd1-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-231">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="80dd1-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="80dd1-232">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-233">5067</span><span class="sxs-lookup"><span data-stu-id="80dd1-233">5067</span></span></p></td>
<td><p><span data-ttu-id="80dd1-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-235">Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="80dd1-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-236">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="80dd1-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="80dd1-237">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-238">5068</span><span class="sxs-lookup"><span data-stu-id="80dd1-238">5068</span></span></p></td>
<td><p><span data-ttu-id="80dd1-239">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-240">Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="80dd1-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-241">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="80dd1-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="80dd1-242">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-243">5081</span><span class="sxs-lookup"><span data-stu-id="80dd1-243">5081</span></span></p></td>
<td><p><span data-ttu-id="80dd1-244">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-245">Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="80dd1-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-246">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="80dd1-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="80dd1-247">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-248">5082</span><span class="sxs-lookup"><span data-stu-id="80dd1-248">5082</span></span></p></td>
<td><p><span data-ttu-id="80dd1-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-250">Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="80dd1-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-251">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-252">Serviço de compartilhamento de aplicativos do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-253">5065</span><span class="sxs-lookup"><span data-stu-id="80dd1-253">5065</span></span></p></td>
<td><p><span data-ttu-id="80dd1-254">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-255">Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="80dd1-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-256">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-257">Serviço de compartilhamento de aplicativos do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="80dd1-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="80dd1-259">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-260">Intervalo de porta de mídia usado para compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="80dd1-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-261">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-262">Serviço de anúncio de conferência do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-263">5073</span><span class="sxs-lookup"><span data-stu-id="80dd1-263">5073</span></span></p></td>
<td><p><span data-ttu-id="80dd1-264">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-265">Usado para solicitações SIP recebidas para o serviço de anúncio de conferência do Lync Server (ou seja, para conferência discada).</span><span class="sxs-lookup"><span data-stu-id="80dd1-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-266">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-267">Serviço de Estacionamento de Chamada do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-268">5075</span><span class="sxs-lookup"><span data-stu-id="80dd1-268">5075</span></span></p></td>
<td><p><span data-ttu-id="80dd1-269">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-270">Usada para solicitações SIP de entrada para o aplicativo Estacionamento de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="80dd1-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-271">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-272">Serviço de teste de áudio do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-273">5076</span><span class="sxs-lookup"><span data-stu-id="80dd1-273">5076</span></span></p></td>
<td><p><span data-ttu-id="80dd1-274">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-275">Usada para solicitações SIP de entrada para o serviço Teste de Áudio.</span><span class="sxs-lookup"><span data-stu-id="80dd1-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-276">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-277">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="80dd1-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="80dd1-278">5066</span><span class="sxs-lookup"><span data-stu-id="80dd1-278">5066</span></span></p></td>
<td><p><span data-ttu-id="80dd1-279">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-280">Usada para o gateway de E9-1-1 (9-1-1 Avançado) de saída.</span><span class="sxs-lookup"><span data-stu-id="80dd1-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-281">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-282">Serviço Grupo de Resposta do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-283">5071</span><span class="sxs-lookup"><span data-stu-id="80dd1-283">5071</span></span></p></td>
<td><p><span data-ttu-id="80dd1-284">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-285">Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.</span><span class="sxs-lookup"><span data-stu-id="80dd1-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-286">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-287">Serviço Grupo de Resposta do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-288">8404</span><span class="sxs-lookup"><span data-stu-id="80dd1-288">8404</span></span></p></td>
<td><p><span data-ttu-id="80dd1-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-290">Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.</span><span class="sxs-lookup"><span data-stu-id="80dd1-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-291">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-292">Serviço de política de largura de banda do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-293">5080</span><span class="sxs-lookup"><span data-stu-id="80dd1-293">5080</span></span></p></td>
<td><p><span data-ttu-id="80dd1-294">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-295">Usada para controle de admissão de chamada pelo serviço Política de Largura de banda para tráfego TURN de Borda A/V.</span><span class="sxs-lookup"><span data-stu-id="80dd1-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-296">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-297">Serviço de política de largura de banda do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-298">448</span><span class="sxs-lookup"><span data-stu-id="80dd1-298">448</span></span></p></td>
<td><p><span data-ttu-id="80dd1-299">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-300">Usado para controle de admissão de chamadas pelo serviço de política de largura de banda do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80dd1-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-301">Servidores front-end nos quais o repositório de gerenciamento central reside</span><span class="sxs-lookup"><span data-stu-id="80dd1-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="80dd1-302">Serviço de agente do Lync Server Master Replicator</span><span class="sxs-lookup"><span data-stu-id="80dd1-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-303">445</span><span class="sxs-lookup"><span data-stu-id="80dd1-303">445</span></span></p></td>
<td><p><span data-ttu-id="80dd1-304">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-305">Usado para enviar por push dados de configuração do repositório de gerenciamento central para servidores que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80dd1-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-306">Todos os servidores</span><span class="sxs-lookup"><span data-stu-id="80dd1-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-307">Navegador do SQL</span><span class="sxs-lookup"><span data-stu-id="80dd1-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="80dd1-308">1434</span><span class="sxs-lookup"><span data-stu-id="80dd1-308">1434</span></span></p></td>
<td><p><span data-ttu-id="80dd1-309">UDP</span><span class="sxs-lookup"><span data-stu-id="80dd1-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-310">Navegador do SQL para cópia replicada local de dados do repositório de gerenciamento central na instância do SQL Server local</span><span class="sxs-lookup"><span data-stu-id="80dd1-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-311">Todos os servidores internos</span><span class="sxs-lookup"><span data-stu-id="80dd1-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-312">Vários</span><span class="sxs-lookup"><span data-stu-id="80dd1-312">Various</span></span></p></td>
<td><p><span data-ttu-id="80dd1-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="80dd1-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="80dd1-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="80dd1-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-315">Intervalo de porta de mídia usada para audioconferência em todos os servidores internos.</span><span class="sxs-lookup"><span data-stu-id="80dd1-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="80dd1-316">Usado por todos os servidores que encerram áudio: servidores front-end (para o serviço de atendedor do Lync Server Conferencing, serviço de anúncio de conferência do Lync Server e serviço de videoconferência/vídeo do Lync Server) e servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="80dd1-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-317">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="80dd1-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80dd1-318">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80dd1-319">Usado pelo Lync Server 2013 para se conectar ao servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="80dd1-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-320">Diretores</span><span class="sxs-lookup"><span data-stu-id="80dd1-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="80dd1-321">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-322">5060</span><span class="sxs-lookup"><span data-stu-id="80dd1-322">5060</span></span></p></td>
<td><p><span data-ttu-id="80dd1-323">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-324">Usada como opção para rotas estáticas até os serviços confiáveis, como servidores de controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="80dd1-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-325">Diretores</span><span class="sxs-lookup"><span data-stu-id="80dd1-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="80dd1-326">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-327">444</span><span class="sxs-lookup"><span data-stu-id="80dd1-327">444</span></span></p></td>
<td><p><span data-ttu-id="80dd1-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-328">HTTPS</span></span></p>
<p><span data-ttu-id="80dd1-329">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-330">Comunicação entre servidores entre Front-End e Diretor.</span><span class="sxs-lookup"><span data-stu-id="80dd1-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="80dd1-331">Além disso, a publicação de certificado do cliente (para servidores front-end) ou a validar se o certificado do cliente já foi publicado.</span><span class="sxs-lookup"><span data-stu-id="80dd1-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-332">Diretores</span><span class="sxs-lookup"><span data-stu-id="80dd1-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="80dd1-333">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-334">80</span><span class="sxs-lookup"><span data-stu-id="80dd1-334">80</span></span></p></td>
<td><p><span data-ttu-id="80dd1-335">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-p105">Usada para comunicação inicial dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS). Em uma operação normal, trocará para tráfego HTTPS, usando a porta 443 e o tipo de protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="80dd1-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-338">Diretores</span><span class="sxs-lookup"><span data-stu-id="80dd1-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="80dd1-339">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-340">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-340">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="80dd1-342">Usada para comunicação dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS).</span><span class="sxs-lookup"><span data-stu-id="80dd1-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-343">Diretores</span><span class="sxs-lookup"><span data-stu-id="80dd1-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="80dd1-344">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-345">5061</span><span class="sxs-lookup"><span data-stu-id="80dd1-345">5061</span></span></p></td>
<td><p><span data-ttu-id="80dd1-346">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-347">Usada para comunicações internas entre os servidores e para conexões do cliente.</span><span class="sxs-lookup"><span data-stu-id="80dd1-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-348">Servidores de Mediação</span><span class="sxs-lookup"><span data-stu-id="80dd1-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-349">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-350">5070</span><span class="sxs-lookup"><span data-stu-id="80dd1-350">5070</span></span></p></td>
<td><p><span data-ttu-id="80dd1-351">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-352">Usada pelo Servidor de mediação para solicitações de entrada do Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="80dd1-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-353">Servidores de Mediação</span><span class="sxs-lookup"><span data-stu-id="80dd1-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-354">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-355">5067</span><span class="sxs-lookup"><span data-stu-id="80dd1-355">5067</span></span></p></td>
<td><p><span data-ttu-id="80dd1-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-357">Usada para solicitações SIP de entrada do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="80dd1-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-358">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="80dd1-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-359">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-360">5068</span><span class="sxs-lookup"><span data-stu-id="80dd1-360">5068</span></span></p></td>
<td><p><span data-ttu-id="80dd1-361">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-362">Usada para solicitações SIP de entrada do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="80dd1-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-363">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="80dd1-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="80dd1-364">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="80dd1-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-365">5070</span><span class="sxs-lookup"><span data-stu-id="80dd1-365">5070</span></span></p></td>
<td><p><span data-ttu-id="80dd1-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-367">Usada para solicitações SIP dos Servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="80dd1-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-368">Servidor de front-end de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="80dd1-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="80dd1-369">SIP de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="80dd1-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-370">5041</span><span class="sxs-lookup"><span data-stu-id="80dd1-370">5041</span></span></p></td>
<td><p><span data-ttu-id="80dd1-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-372">Servidor de front-end de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="80dd1-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="80dd1-373">Bate-papo persistente do Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="80dd1-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-374">881</span><span class="sxs-lookup"><span data-stu-id="80dd1-374">881</span></span></p></td>
<td><p><span data-ttu-id="80dd1-375">TCP (TLS) e TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-376">Servidor de front-end de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="80dd1-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="80dd1-377">Serviço de transferência de arquivos de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="80dd1-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="80dd1-378">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-378">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="80dd1-380">Alguns cenários de controle de chamada remota exigem uma conexão TCP entre o Servidor Front-End ou o Diretor e o PBX.</span><span class="sxs-lookup"><span data-stu-id="80dd1-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="80dd1-381">Embora o Lync Server não use mais a porta TCP 5060, durante a implantação do controle de chamada remota, você cria uma configuração de servidor confiável, que associa o FQDN do servidor de linha de RCC à porta TCP que o servidor front-end ou o diretor usará para se conectar ao sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="80dd1-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="80dd1-382">Para obter detalhes, consulte o cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80dd1-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="80dd1-383">Para os seus pools que usam somente o balanceamento de carga de hardware (não o balanceamento de carga DNS), a tabela a seguir mostra as portas que precisam abrir os balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="80dd1-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="80dd1-384">Portas do balanceador de carga de hardware se estiver usando somente o balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="80dd1-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80dd1-385">Balanceador de carga</span><span class="sxs-lookup"><span data-stu-id="80dd1-385">Load Balancer</span></span></th>
<th><span data-ttu-id="80dd1-386">Porta</span><span class="sxs-lookup"><span data-stu-id="80dd1-386">Port</span></span></th>
<th><span data-ttu-id="80dd1-387">Protocolo</span><span class="sxs-lookup"><span data-stu-id="80dd1-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-388">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-389">5061</span><span class="sxs-lookup"><span data-stu-id="80dd1-389">5061</span></span></p></td>
<td><p><span data-ttu-id="80dd1-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-391">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-392">444</span><span class="sxs-lookup"><span data-stu-id="80dd1-392">444</span></span></p></td>
<td><p><span data-ttu-id="80dd1-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-394">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-395">135</span><span class="sxs-lookup"><span data-stu-id="80dd1-395">135</span></span></p></td>
<td><p><span data-ttu-id="80dd1-396">DCOM e RPC (controle de procedimento remoto)</span><span class="sxs-lookup"><span data-stu-id="80dd1-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-397">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-398">80</span><span class="sxs-lookup"><span data-stu-id="80dd1-398">80</span></span></p></td>
<td><p><span data-ttu-id="80dd1-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="80dd1-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-400">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-401">8080</span><span class="sxs-lookup"><span data-stu-id="80dd1-401">8080</span></span></p></td>
<td><p><span data-ttu-id="80dd1-402">TCP - Recuperação por parte do cliente e do dispositivo do certificado raiz do Servidor Front-End – clientes e dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="80dd1-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-403">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-404">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-404">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-406">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-407">4443</span><span class="sxs-lookup"><span data-stu-id="80dd1-407">4443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-408">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="80dd1-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-409">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-410">5072</span><span class="sxs-lookup"><span data-stu-id="80dd1-410">5072</span></span></p></td>
<td><p><span data-ttu-id="80dd1-411">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-412">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-413">5073</span><span class="sxs-lookup"><span data-stu-id="80dd1-413">5073</span></span></p></td>
<td><p><span data-ttu-id="80dd1-414">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-415">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-416">5075</span><span class="sxs-lookup"><span data-stu-id="80dd1-416">5075</span></span></p></td>
<td><p><span data-ttu-id="80dd1-417">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-418">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-419">5076</span><span class="sxs-lookup"><span data-stu-id="80dd1-419">5076</span></span></p></td>
<td><p><span data-ttu-id="80dd1-420">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-421">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-422">5071</span><span class="sxs-lookup"><span data-stu-id="80dd1-422">5071</span></span></p></td>
<td><p><span data-ttu-id="80dd1-423">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-424">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-425">5080</span><span class="sxs-lookup"><span data-stu-id="80dd1-425">5080</span></span></p></td>
<td><p><span data-ttu-id="80dd1-426">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-427">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-428">448</span><span class="sxs-lookup"><span data-stu-id="80dd1-428">448</span></span></p></td>
<td><p><span data-ttu-id="80dd1-429">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-430">Balanceador de carga do Servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="80dd1-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-431">5070</span><span class="sxs-lookup"><span data-stu-id="80dd1-431">5070</span></span></p></td>
<td><p><span data-ttu-id="80dd1-432">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-433">Balanceador de carga do Servidor Front-End (se o pool também executa o Servidor de mediação)</span><span class="sxs-lookup"><span data-stu-id="80dd1-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-434">5070</span><span class="sxs-lookup"><span data-stu-id="80dd1-434">5070</span></span></p></td>
<td><p><span data-ttu-id="80dd1-435">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-436">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="80dd1-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-437">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-437">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-439">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="80dd1-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-440">444</span><span class="sxs-lookup"><span data-stu-id="80dd1-440">444</span></span></p></td>
<td><p><span data-ttu-id="80dd1-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-442">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="80dd1-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-443">5061</span><span class="sxs-lookup"><span data-stu-id="80dd1-443">5061</span></span></p></td>
<td><p><span data-ttu-id="80dd1-444">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-445">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="80dd1-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-446">4443</span><span class="sxs-lookup"><span data-stu-id="80dd1-446">4443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-447">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="80dd1-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="80dd1-p107">Seus pools do Front-End e do Diretor que usam o balanceamento de carga DNS também precisam ter um balanceador de carga de hardware implantado. A tabela a seguir mostra as portas que precisam ser abertas nesses balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="80dd1-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="80dd1-450">Portas do balanceador de carga de hardware se estiver usando o balanceamento de carga DNS</span><span class="sxs-lookup"><span data-stu-id="80dd1-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80dd1-451">Balanceador de carga</span><span class="sxs-lookup"><span data-stu-id="80dd1-451">Load Balancer</span></span></th>
<th><span data-ttu-id="80dd1-452">Porta</span><span class="sxs-lookup"><span data-stu-id="80dd1-452">Port</span></span></th>
<th><span data-ttu-id="80dd1-453">Protocolo</span><span class="sxs-lookup"><span data-stu-id="80dd1-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-454">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-455">80</span><span class="sxs-lookup"><span data-stu-id="80dd1-455">80</span></span></p></td>
<td><p><span data-ttu-id="80dd1-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="80dd1-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-457">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-458">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-458">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-460">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-461">8080</span><span class="sxs-lookup"><span data-stu-id="80dd1-461">8080</span></span></p></td>
<td><p><span data-ttu-id="80dd1-462">TCP - Recuperação por parte do cliente e do dispositivo do certificado raiz do Servidor Front-End – clientes e dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="80dd1-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-463">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="80dd1-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-464">4443</span><span class="sxs-lookup"><span data-stu-id="80dd1-464">4443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-465">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="80dd1-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-466">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="80dd1-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-467">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-467">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="80dd1-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-469">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="80dd1-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="80dd1-470">4443</span><span class="sxs-lookup"><span data-stu-id="80dd1-470">4443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-471">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="80dd1-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="80dd1-472">Portas do cliente necessárias</span><span class="sxs-lookup"><span data-stu-id="80dd1-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80dd1-473">Componente</span><span class="sxs-lookup"><span data-stu-id="80dd1-473">Component</span></span></th>
<th><span data-ttu-id="80dd1-474">Porta</span><span class="sxs-lookup"><span data-stu-id="80dd1-474">Port</span></span></th>
<th><span data-ttu-id="80dd1-475">Protocolo</span><span class="sxs-lookup"><span data-stu-id="80dd1-475">Protocol</span></span></th>
<th><span data-ttu-id="80dd1-476">Notas</span><span class="sxs-lookup"><span data-stu-id="80dd1-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-477">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-478">67/68</span><span class="sxs-lookup"><span data-stu-id="80dd1-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="80dd1-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-480">Usado pelo Lync Server para localizar o FQDN do registrador (isto é, se as configurações de SRV DNS falharem e as configurações manuais não estiverem definidas).</span><span class="sxs-lookup"><span data-stu-id="80dd1-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-481">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-482">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-482">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-484">Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="80dd1-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-485">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-486">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-486">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-488">Usada para acesso de usuário externo às sessões de webconferência.</span><span class="sxs-lookup"><span data-stu-id="80dd1-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-489">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-490">443</span><span class="sxs-lookup"><span data-stu-id="80dd1-490">443</span></span></p></td>
<td><p><span data-ttu-id="80dd1-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="80dd1-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-492">Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)</span><span class="sxs-lookup"><span data-stu-id="80dd1-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-493">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-494">3478</span><span class="sxs-lookup"><span data-stu-id="80dd1-494">3478</span></span></p></td>
<td><p><span data-ttu-id="80dd1-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="80dd1-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-496">Usada para acesso de usuário externo às sessões de A/V e mídia (UDP)</span><span class="sxs-lookup"><span data-stu-id="80dd1-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-497">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-498">5061</span><span class="sxs-lookup"><span data-stu-id="80dd1-498">5061</span></span></p></td>
<td><p><span data-ttu-id="80dd1-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="80dd1-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="80dd1-500">Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="80dd1-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-501">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="80dd1-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="80dd1-503">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-504">Usado para transferência de arquivos entre clientes do Lync e clientes anteriores (clientes do Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 e Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="80dd1-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-505">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="80dd1-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="80dd1-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="80dd1-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-508">Intervalo de porta de áudio (mínimo de 20 portas necessárias)</span><span class="sxs-lookup"><span data-stu-id="80dd1-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-509">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="80dd1-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="80dd1-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="80dd1-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-512">Intervalo de porta de vídeo (mínimo de 20 portas necessárias).</span><span class="sxs-lookup"><span data-stu-id="80dd1-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-513">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="80dd1-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="80dd1-515">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-516">Transferência de arquivos ponto a ponto (para transferência de arquivo de conferência, clientes que usam PSOM).</span><span class="sxs-lookup"><span data-stu-id="80dd1-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80dd1-517">Clientes</span><span class="sxs-lookup"><span data-stu-id="80dd1-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="80dd1-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="80dd1-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="80dd1-519">TCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-520">Compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="80dd1-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80dd1-521">Telefone de área comum Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="80dd1-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="80dd1-522">Telefone de mesa Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="80dd1-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="80dd1-523">Telefone IP HP 4110 (telefone de área comum)</span><span class="sxs-lookup"><span data-stu-id="80dd1-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="80dd1-524">Telefone IP HP 4120 (telefone de mesa)</span><span class="sxs-lookup"><span data-stu-id="80dd1-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="80dd1-525">Telefone de área comum IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="80dd1-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="80dd1-526">Telefone de mesa IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="80dd1-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="80dd1-527">Telefone de mesa IP Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="80dd1-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="80dd1-528">Telefone de conferência IP Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="80dd1-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="80dd1-529">67/68</span><span class="sxs-lookup"><span data-stu-id="80dd1-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="80dd1-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="80dd1-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="80dd1-531">Usado pelos dispositivos listados para localizar o certificado do Lync Server, o provisionamento e o FQDN do registrador.</span><span class="sxs-lookup"><span data-stu-id="80dd1-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="80dd1-532">**\*** Para configurar portas específicas para esses tipos de mídia, use o cmdlet CsConferencingConfiguration (parâmetros ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="80dd1-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80dd1-533">Os programas definidos para clientes do Lync criam automaticamente as exceções necessárias de firewall do sistema operacional no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="80dd1-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="80dd1-534">As portas usadas para acesso de usuário externo são necessárias para qualquer cenário no qual o cliente precisa atravessar o firewall da organização (por exemplo, quaisquer comunicações externas ou reuniões hospedadas por outras organizações).</span><span class="sxs-lookup"><span data-stu-id="80dd1-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

