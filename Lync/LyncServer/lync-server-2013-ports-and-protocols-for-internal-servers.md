---
title: 'Lync Server 2013: portas e protocolos para servidores internos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="ff930-102">Portas e protocolos para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff930-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff930-103">_**Tópico da última modificação:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="ff930-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="ff930-104">Esta seção resume as portas e os protocolos usados por servidores, balanceadores de carga e clientes em uma implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff930-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ff930-105">Os clientes do Lync e do Communicator, quando envolvidos em uma comunicação de um para um, geralmente são chamados de ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="ff930-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="ff930-106">Tecnicamente, os dois clientes estão se comunicando em uma conversa de uma ou uma, com a IMMCU (unidade de controle Multipoint) do chat no meio.</span><span class="sxs-lookup"><span data-stu-id="ff930-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="ff930-107">O IMMCU é um componente do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="ff930-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="ff930-108">Colocar o IMMCU no fluxo de trabalho de comunicação necessário permite a gravação de detalhes da chamada e outros recursos que o servidor de front-end permite.</span><span class="sxs-lookup"><span data-stu-id="ff930-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="ff930-109">A comunicação é de uma porta de origem dinâmica no cliente para a porta de servidor front-end TLS/TCP/5061 (pressupondo o uso da segurança da camada de transporte recomendada).</span><span class="sxs-lookup"><span data-stu-id="ff930-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="ff930-110">Por design, a comunicação ponto a ponto (bem como mensagens instantâneas de vários participantes) só é possível quando o Lync Server e o IMMCU estão ativos e disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ff930-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ff930-111">Detalhes de protocolo e porta</span><span class="sxs-lookup"><span data-stu-id="ff930-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff930-112">O Firewall do Windows deve estar em execução antes de iniciar os serviços do Lync Server em um servidor, pois isso ocorre quando o Lync Server abre as portas obrigatórias no firewall.</span><span class="sxs-lookup"><span data-stu-id="ff930-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="ff930-113">Para obter detalhes sobre a configuração de firewall para componentes de borda, consulte [determinar requisitos de firewall e porta externo A/V para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff930-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="ff930-114">A tabela a seguir lista as portas que precisam ser abertas em cada função de servidor interno.</span><span class="sxs-lookup"><span data-stu-id="ff930-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="ff930-115">Portas do servidor necessárias (por Função de servidor)</span><span class="sxs-lookup"><span data-stu-id="ff930-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="ff930-116">Função de servidor</span><span class="sxs-lookup"><span data-stu-id="ff930-116">Server role</span></span></th>
<th><span data-ttu-id="ff930-117">Nome do serviço</span><span class="sxs-lookup"><span data-stu-id="ff930-117">Service name</span></span></th>
<th><span data-ttu-id="ff930-118">Porta</span><span class="sxs-lookup"><span data-stu-id="ff930-118">Port</span></span></th>
<th><span data-ttu-id="ff930-119">Protocolo</span><span class="sxs-lookup"><span data-stu-id="ff930-119">Protocol</span></span></th>
<th><span data-ttu-id="ff930-120">Notas</span><span class="sxs-lookup"><span data-stu-id="ff930-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff930-121">Todos os servidores</span><span class="sxs-lookup"><span data-stu-id="ff930-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-122">Navegador do SQL</span><span class="sxs-lookup"><span data-stu-id="ff930-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="ff930-123">1434</span><span class="sxs-lookup"><span data-stu-id="ff930-123">1434</span></span></p></td>
<td><p><span data-ttu-id="ff930-124">UDP</span><span class="sxs-lookup"><span data-stu-id="ff930-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="ff930-125">Navegador do SQL para a cópia replicada local do banco de dados do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="ff930-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-126">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-127">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ff930-128">5060</span><span class="sxs-lookup"><span data-stu-id="ff930-128">5060</span></span></p></td>
<td><p><span data-ttu-id="ff930-129">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-130">Usada como opção pelos servidores Standard Edition e Servidores Front-End para rotas estáticas para serviços confiáveis, como servidores de controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="ff930-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-131">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-132">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ff930-133">5061</span><span class="sxs-lookup"><span data-stu-id="ff930-133">5061</span></span></p></td>
<td><p><span data-ttu-id="ff930-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-135">Usada pelos servidores Standard Edition e pools de front-ends em todas as comunicações SIP internas entre servidores (MTLS), em comunicações SIP entre o servidor e o cliente (TLS) e em comunicações SIP entre os servidores front-end e os servidores de mediação (MTLS).</span><span class="sxs-lookup"><span data-stu-id="ff930-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="ff930-136">Também usado para comunicações com o Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="ff930-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-137">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-138">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ff930-139">444</span><span class="sxs-lookup"><span data-stu-id="ff930-139">444</span></span></p></td>
<td><p><span data-ttu-id="ff930-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-140">HTTPS</span></span></p>
<p><span data-ttu-id="ff930-141">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-142">Usado para comunicação HTTPS entre o foco (o componente do Lync Server que gerencia o estado da conferência) e os servidores individuais.</span><span class="sxs-lookup"><span data-stu-id="ff930-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="ff930-143">Essa porta também é usada para comunicação TCP entre aparelhos de ramificação sobreviventes e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ff930-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-144">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-145">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ff930-146">135</span><span class="sxs-lookup"><span data-stu-id="ff930-146">135</span></span></p></td>
<td><p><span data-ttu-id="ff930-147">DCOM e RPC (controle de procedimento remoto)</span><span class="sxs-lookup"><span data-stu-id="ff930-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="ff930-148">Usada para operações com base em DCOM, como Movendo Usuários, Sincronização do Replicador do Usuário e Sincronização do Catálogo de Endereços.</span><span class="sxs-lookup"><span data-stu-id="ff930-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-149">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-150">Serviço de conferência IM do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ff930-151">5062</span><span class="sxs-lookup"><span data-stu-id="ff930-151">5062</span></span></p></td>
<td><p><span data-ttu-id="ff930-152">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-153">Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).</span><span class="sxs-lookup"><span data-stu-id="ff930-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-154">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-155">Serviço de conferência Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ff930-156">8057</span><span class="sxs-lookup"><span data-stu-id="ff930-156">8057</span></span></p></td>
<td><p><span data-ttu-id="ff930-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-158">Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.</span><span class="sxs-lookup"><span data-stu-id="ff930-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-159">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-160">Serviço de compatibilidade do Lync Server Web referencing</span><span class="sxs-lookup"><span data-stu-id="ff930-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ff930-161">8058</span><span class="sxs-lookup"><span data-stu-id="ff930-161">8058</span></span></p></td>
<td><p><span data-ttu-id="ff930-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-163">Usado para escutar conexões do modelo de objeto compartilhado persistente (PSOM) do cliente de reunião ao vivo e versões anteriores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff930-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-164">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-165">Serviço de conferência de áudio/vídeo do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ff930-166">5063</span><span class="sxs-lookup"><span data-stu-id="ff930-166">5063</span></span></p></td>
<td><p><span data-ttu-id="ff930-167">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-168">Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="ff930-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-169">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-170">Serviço de conferência de áudio/vídeo do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="ff930-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="ff930-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="ff930-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ff930-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ff930-173">Intervalo de porta de mídia usado para videoconferência.</span><span class="sxs-lookup"><span data-stu-id="ff930-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-174">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-175">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ff930-176">80</span><span class="sxs-lookup"><span data-stu-id="ff930-176">80</span></span></p></td>
<td><p><span data-ttu-id="ff930-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="ff930-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="ff930-178">Usada para comunicação dos Servidores Front-End com os FQDNs do farm da web (as URLs usadas pelos componentes da web IIS) quando HTTPS não é usado.</span><span class="sxs-lookup"><span data-stu-id="ff930-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-179">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-180">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ff930-181">443</span><span class="sxs-lookup"><span data-stu-id="ff930-181">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ff930-183">Usado para comunicação dos servidores front-End no farm da web FQDNs (as URLs usadas pelos componentes da web do IIS).</span><span class="sxs-lookup"><span data-stu-id="ff930-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-184">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-185">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ff930-186">8080</span><span class="sxs-lookup"><span data-stu-id="ff930-186">8080</span></span></p></td>
<td><p><span data-ttu-id="ff930-187">TCP e HTTP</span><span class="sxs-lookup"><span data-stu-id="ff930-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="ff930-188">Usado pelos componentes da Web para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="ff930-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-189">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-190">Servidor de componentes da Web</span><span class="sxs-lookup"><span data-stu-id="ff930-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ff930-191">4443</span><span class="sxs-lookup"><span data-stu-id="ff930-191">4443</span></span></p></td>
<td><p><span data-ttu-id="ff930-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ff930-193">Comunicações entre pools de front-end HTTPS (de Proxy Reverso) e HTTPS para conexão de Descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="ff930-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-194">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-195">Servidor de componentes da Web</span><span class="sxs-lookup"><span data-stu-id="ff930-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ff930-196">8060</span><span class="sxs-lookup"><span data-stu-id="ff930-196">8060</span></span></p></td>
<td><p><span data-ttu-id="ff930-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-198">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-199">Servidor de componentes da Web</span><span class="sxs-lookup"><span data-stu-id="ff930-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="ff930-200">8061</span><span class="sxs-lookup"><span data-stu-id="ff930-200">8061</span></span></p></td>
<td><p><span data-ttu-id="ff930-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-202">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-203">Componente dos serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="ff930-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ff930-204">5086</span><span class="sxs-lookup"><span data-stu-id="ff930-204">5086</span></span></p></td>
<td><p><span data-ttu-id="ff930-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-206">Porta SIP usada pelos processos internos dos Serviços de Mobilidade</span><span class="sxs-lookup"><span data-stu-id="ff930-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-207">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-208">Componente dos serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="ff930-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ff930-209">5087</span><span class="sxs-lookup"><span data-stu-id="ff930-209">5087</span></span></p></td>
<td><p><span data-ttu-id="ff930-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-211">Porta SIP usada pelos processos internos dos Serviços de Mobilidade</span><span class="sxs-lookup"><span data-stu-id="ff930-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-212">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-213">Componente dos serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="ff930-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="ff930-214">443</span><span class="sxs-lookup"><span data-stu-id="ff930-214">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-216">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-217">Serviço de atendedor do Lync Server Conferencing (conferência discada)</span><span class="sxs-lookup"><span data-stu-id="ff930-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="ff930-218">5064</span><span class="sxs-lookup"><span data-stu-id="ff930-218">5064</span></span></p></td>
<td><p><span data-ttu-id="ff930-219">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-220">Usada para solicitações SIP de entrada para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="ff930-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-221">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-222">Serviço de atendedor do Lync Server Conferencing (conferência discada)</span><span class="sxs-lookup"><span data-stu-id="ff930-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="ff930-223">5072</span><span class="sxs-lookup"><span data-stu-id="ff930-223">5072</span></span></p></td>
<td><p><span data-ttu-id="ff930-224">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-225">Usado para solicitações SIP de entrada do atendente (discagem por conferência).</span><span class="sxs-lookup"><span data-stu-id="ff930-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-226">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="ff930-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ff930-227">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ff930-228">5070</span><span class="sxs-lookup"><span data-stu-id="ff930-228">5070</span></span></p></td>
<td><p><span data-ttu-id="ff930-229">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-230">Usada pelo Servidor de Mediação para solicitações de entrada do Servidor Front-End para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="ff930-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-231">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="ff930-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ff930-232">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ff930-233">5067</span><span class="sxs-lookup"><span data-stu-id="ff930-233">5067</span></span></p></td>
<td><p><span data-ttu-id="ff930-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-235">Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="ff930-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-236">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="ff930-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ff930-237">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ff930-238">5068</span><span class="sxs-lookup"><span data-stu-id="ff930-238">5068</span></span></p></td>
<td><p><span data-ttu-id="ff930-239">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-240">Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="ff930-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-241">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="ff930-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ff930-242">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ff930-243">5081</span><span class="sxs-lookup"><span data-stu-id="ff930-243">5081</span></span></p></td>
<td><p><span data-ttu-id="ff930-244">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-245">Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ff930-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-246">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="ff930-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="ff930-247">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ff930-248">5082</span><span class="sxs-lookup"><span data-stu-id="ff930-248">5082</span></span></p></td>
<td><p><span data-ttu-id="ff930-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-250">Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ff930-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-251">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-252">Serviço de compartilhamento de aplicativos do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="ff930-253">5065</span><span class="sxs-lookup"><span data-stu-id="ff930-253">5065</span></span></p></td>
<td><p><span data-ttu-id="ff930-254">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-255">Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ff930-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-256">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-257">Serviço de compartilhamento de aplicativos do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="ff930-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="ff930-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="ff930-259">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-260">Intervalo de porta de mídia usado para compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ff930-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-261">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-262">Serviço de anúncio de conferência do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="ff930-263">5073</span><span class="sxs-lookup"><span data-stu-id="ff930-263">5073</span></span></p></td>
<td><p><span data-ttu-id="ff930-264">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-265">Usado para solicitações SIP recebidas para o serviço de anúncio de conferência do Lync Server (ou seja, para conferência discada).</span><span class="sxs-lookup"><span data-stu-id="ff930-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-266">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-267">Serviço de Estacionamento de Chamada do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="ff930-268">5075</span><span class="sxs-lookup"><span data-stu-id="ff930-268">5075</span></span></p></td>
<td><p><span data-ttu-id="ff930-269">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-270">Usada para solicitações SIP de entrada para o aplicativo Estacionamento de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="ff930-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-271">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-272">Serviço de teste de áudio do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="ff930-273">5076</span><span class="sxs-lookup"><span data-stu-id="ff930-273">5076</span></span></p></td>
<td><p><span data-ttu-id="ff930-274">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-275">Usada para solicitações SIP de entrada para o serviço Teste de Áudio.</span><span class="sxs-lookup"><span data-stu-id="ff930-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-276">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-277">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="ff930-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="ff930-278">5066</span><span class="sxs-lookup"><span data-stu-id="ff930-278">5066</span></span></p></td>
<td><p><span data-ttu-id="ff930-279">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-280">Usada para o gateway de E9-1-1 (9-1-1 Avançado) de saída.</span><span class="sxs-lookup"><span data-stu-id="ff930-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-281">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-282">Serviço Grupo de Resposta do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="ff930-283">5071</span><span class="sxs-lookup"><span data-stu-id="ff930-283">5071</span></span></p></td>
<td><p><span data-ttu-id="ff930-284">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-285">Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.</span><span class="sxs-lookup"><span data-stu-id="ff930-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-286">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-287">Serviço Grupo de Resposta do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="ff930-288">8404</span><span class="sxs-lookup"><span data-stu-id="ff930-288">8404</span></span></p></td>
<td><p><span data-ttu-id="ff930-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-290">Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.</span><span class="sxs-lookup"><span data-stu-id="ff930-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-291">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-292">Serviço de política de largura de banda do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="ff930-293">5080</span><span class="sxs-lookup"><span data-stu-id="ff930-293">5080</span></span></p></td>
<td><p><span data-ttu-id="ff930-294">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-295">Usada para controle de admissão de chamada pelo serviço Política de Largura de banda para tráfego TURN de Borda A/V.</span><span class="sxs-lookup"><span data-stu-id="ff930-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-296">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-297">Serviço de política de largura de banda do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="ff930-298">448</span><span class="sxs-lookup"><span data-stu-id="ff930-298">448</span></span></p></td>
<td><p><span data-ttu-id="ff930-299">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-300">Usado para controle de admissão de chamadas pelo serviço de política de largura de banda do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff930-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-301">Servidores front-end nos quais o repositório de gerenciamento central reside</span><span class="sxs-lookup"><span data-stu-id="ff930-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="ff930-302">Serviço de agente do Lync Server Master Replicator</span><span class="sxs-lookup"><span data-stu-id="ff930-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="ff930-303">445</span><span class="sxs-lookup"><span data-stu-id="ff930-303">445</span></span></p></td>
<td><p><span data-ttu-id="ff930-304">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-305">Usado para enviar por push dados de configuração do repositório de gerenciamento central para servidores que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff930-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-306">Todos os servidores</span><span class="sxs-lookup"><span data-stu-id="ff930-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-307">Navegador do SQL</span><span class="sxs-lookup"><span data-stu-id="ff930-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="ff930-308">1434</span><span class="sxs-lookup"><span data-stu-id="ff930-308">1434</span></span></p></td>
<td><p><span data-ttu-id="ff930-309">UDP</span><span class="sxs-lookup"><span data-stu-id="ff930-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="ff930-310">Navegador do SQL para cópia replicada local de dados do repositório de gerenciamento central na instância do SQL Server local</span><span class="sxs-lookup"><span data-stu-id="ff930-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-311">Todos os servidores internos</span><span class="sxs-lookup"><span data-stu-id="ff930-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-312">Vários</span><span class="sxs-lookup"><span data-stu-id="ff930-312">Various</span></span></p></td>
<td><p><span data-ttu-id="ff930-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="ff930-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="ff930-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ff930-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ff930-315">Intervalo de porta de mídia usada para audioconferência em todos os servidores internos.</span><span class="sxs-lookup"><span data-stu-id="ff930-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="ff930-316">Usado por todos os servidores que encerram áudio: servidores front-end (para o serviço de atendedor do Lync Server Conferencing, serviço de anúncio de conferência do Lync Server e serviço de videoconferência/vídeo do Lync Server) e servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="ff930-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-317">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="ff930-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff930-318">443</span><span class="sxs-lookup"><span data-stu-id="ff930-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff930-319">Usado pelo Lync Server 2013 para se conectar ao servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="ff930-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-320">Diretores</span><span class="sxs-lookup"><span data-stu-id="ff930-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="ff930-321">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ff930-322">5060</span><span class="sxs-lookup"><span data-stu-id="ff930-322">5060</span></span></p></td>
<td><p><span data-ttu-id="ff930-323">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-324">Usada como opção para rotas estáticas até os serviços confiáveis, como servidores de controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="ff930-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-325">Diretores</span><span class="sxs-lookup"><span data-stu-id="ff930-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="ff930-326">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ff930-327">444</span><span class="sxs-lookup"><span data-stu-id="ff930-327">444</span></span></p></td>
<td><p><span data-ttu-id="ff930-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-328">HTTPS</span></span></p>
<p><span data-ttu-id="ff930-329">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-330">Comunicação entre servidores entre Front-End e Diretor.</span><span class="sxs-lookup"><span data-stu-id="ff930-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="ff930-331">Além disso, a publicação de certificado do cliente (para servidores front-end) ou a validar se o certificado do cliente já foi publicado.</span><span class="sxs-lookup"><span data-stu-id="ff930-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-332">Diretores</span><span class="sxs-lookup"><span data-stu-id="ff930-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="ff930-333">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ff930-334">80</span><span class="sxs-lookup"><span data-stu-id="ff930-334">80</span></span></p></td>
<td><p><span data-ttu-id="ff930-335">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-p105">Usada para comunicação inicial dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS). Em uma operação normal, trocará para tráfego HTTPS, usando a porta 443 e o tipo de protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="ff930-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-338">Diretores</span><span class="sxs-lookup"><span data-stu-id="ff930-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="ff930-339">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="ff930-340">443</span><span class="sxs-lookup"><span data-stu-id="ff930-340">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="ff930-342">Usada para comunicação dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS).</span><span class="sxs-lookup"><span data-stu-id="ff930-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-343">Diretores</span><span class="sxs-lookup"><span data-stu-id="ff930-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="ff930-344">Serviço de front-end do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="ff930-345">5061</span><span class="sxs-lookup"><span data-stu-id="ff930-345">5061</span></span></p></td>
<td><p><span data-ttu-id="ff930-346">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-347">Usada para comunicações internas entre os servidores e para conexões do cliente.</span><span class="sxs-lookup"><span data-stu-id="ff930-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-348">Servidores de Mediação</span><span class="sxs-lookup"><span data-stu-id="ff930-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-349">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ff930-350">5070</span><span class="sxs-lookup"><span data-stu-id="ff930-350">5070</span></span></p></td>
<td><p><span data-ttu-id="ff930-351">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-352">Usada pelo Servidor de mediação para solicitações de entrada do Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="ff930-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-353">Servidores de Mediação</span><span class="sxs-lookup"><span data-stu-id="ff930-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-354">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ff930-355">5067</span><span class="sxs-lookup"><span data-stu-id="ff930-355">5067</span></span></p></td>
<td><p><span data-ttu-id="ff930-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-357">Usada para solicitações SIP de entrada do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ff930-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-358">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="ff930-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-359">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ff930-360">5068</span><span class="sxs-lookup"><span data-stu-id="ff930-360">5068</span></span></p></td>
<td><p><span data-ttu-id="ff930-361">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-362">Usada para solicitações SIP de entrada do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ff930-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-363">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="ff930-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="ff930-364">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ff930-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="ff930-365">5070</span><span class="sxs-lookup"><span data-stu-id="ff930-365">5070</span></span></p></td>
<td><p><span data-ttu-id="ff930-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-367">Usada para solicitações SIP dos Servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="ff930-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-368">Servidor de front-end de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="ff930-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ff930-369">SIP de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="ff930-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="ff930-370">5041</span><span class="sxs-lookup"><span data-stu-id="ff930-370">5041</span></span></p></td>
<td><p><span data-ttu-id="ff930-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-372">Servidor de front-end de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="ff930-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ff930-373">Bate-papo persistente do Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="ff930-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="ff930-374">881</span><span class="sxs-lookup"><span data-stu-id="ff930-374">881</span></span></p></td>
<td><p><span data-ttu-id="ff930-375">TCP (TLS) e TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-376">Servidor de front-end de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="ff930-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ff930-377">Serviço de transferência de arquivos de bate-papo persistente</span><span class="sxs-lookup"><span data-stu-id="ff930-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="ff930-378">443</span><span class="sxs-lookup"><span data-stu-id="ff930-378">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ff930-380">Alguns cenários de controle de chamada remota exigem uma conexão TCP entre o Servidor Front-End ou o Diretor e o PBX.</span><span class="sxs-lookup"><span data-stu-id="ff930-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="ff930-381">Embora o Lync Server não use mais a porta TCP 5060, durante a implantação do controle de chamada remota, você cria uma configuração de servidor confiável, que associa o FQDN do servidor de linha de RCC à porta TCP que o servidor front-end ou o diretor usará para se conectar ao sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="ff930-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="ff930-382">Para obter detalhes, consulte o cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff930-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="ff930-383">Para os seus pools que usam somente o balanceamento de carga de hardware (não o balanceamento de carga DNS), a tabela a seguir mostra as portas que precisam abrir os balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="ff930-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="ff930-384">Portas do balanceador de carga de hardware se estiver usando somente o balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="ff930-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff930-385">Balanceador de carga</span><span class="sxs-lookup"><span data-stu-id="ff930-385">Load Balancer</span></span></th>
<th><span data-ttu-id="ff930-386">Porta</span><span class="sxs-lookup"><span data-stu-id="ff930-386">Port</span></span></th>
<th><span data-ttu-id="ff930-387">Protocolo</span><span class="sxs-lookup"><span data-stu-id="ff930-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff930-388">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-389">5061</span><span class="sxs-lookup"><span data-stu-id="ff930-389">5061</span></span></p></td>
<td><p><span data-ttu-id="ff930-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-391">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-392">444</span><span class="sxs-lookup"><span data-stu-id="ff930-392">444</span></span></p></td>
<td><p><span data-ttu-id="ff930-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-394">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-395">135</span><span class="sxs-lookup"><span data-stu-id="ff930-395">135</span></span></p></td>
<td><p><span data-ttu-id="ff930-396">DCOM e RPC (controle de procedimento remoto)</span><span class="sxs-lookup"><span data-stu-id="ff930-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-397">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-398">80</span><span class="sxs-lookup"><span data-stu-id="ff930-398">80</span></span></p></td>
<td><p><span data-ttu-id="ff930-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="ff930-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-400">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-401">8080</span><span class="sxs-lookup"><span data-stu-id="ff930-401">8080</span></span></p></td>
<td><p><span data-ttu-id="ff930-402">TCP - Recuperação por parte do cliente e do dispositivo do certificado raiz do Servidor Front-End – clientes e dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="ff930-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-403">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-404">443</span><span class="sxs-lookup"><span data-stu-id="ff930-404">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-406">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-407">4443</span><span class="sxs-lookup"><span data-stu-id="ff930-407">4443</span></span></p></td>
<td><p><span data-ttu-id="ff930-408">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="ff930-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-409">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-410">5072</span><span class="sxs-lookup"><span data-stu-id="ff930-410">5072</span></span></p></td>
<td><p><span data-ttu-id="ff930-411">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-412">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-413">5073</span><span class="sxs-lookup"><span data-stu-id="ff930-413">5073</span></span></p></td>
<td><p><span data-ttu-id="ff930-414">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-415">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-416">5075</span><span class="sxs-lookup"><span data-stu-id="ff930-416">5075</span></span></p></td>
<td><p><span data-ttu-id="ff930-417">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-418">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-419">5076</span><span class="sxs-lookup"><span data-stu-id="ff930-419">5076</span></span></p></td>
<td><p><span data-ttu-id="ff930-420">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-421">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-422">5071</span><span class="sxs-lookup"><span data-stu-id="ff930-422">5071</span></span></p></td>
<td><p><span data-ttu-id="ff930-423">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-424">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-425">5080</span><span class="sxs-lookup"><span data-stu-id="ff930-425">5080</span></span></p></td>
<td><p><span data-ttu-id="ff930-426">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-427">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-428">448</span><span class="sxs-lookup"><span data-stu-id="ff930-428">448</span></span></p></td>
<td><p><span data-ttu-id="ff930-429">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-430">Balanceador de carga do Servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="ff930-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-431">5070</span><span class="sxs-lookup"><span data-stu-id="ff930-431">5070</span></span></p></td>
<td><p><span data-ttu-id="ff930-432">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-433">Balanceador de carga do Servidor Front-End (se o pool também executa o Servidor de mediação)</span><span class="sxs-lookup"><span data-stu-id="ff930-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="ff930-434">5070</span><span class="sxs-lookup"><span data-stu-id="ff930-434">5070</span></span></p></td>
<td><p><span data-ttu-id="ff930-435">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-436">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="ff930-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-437">443</span><span class="sxs-lookup"><span data-stu-id="ff930-437">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-439">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="ff930-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-440">444</span><span class="sxs-lookup"><span data-stu-id="ff930-440">444</span></span></p></td>
<td><p><span data-ttu-id="ff930-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-442">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="ff930-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-443">5061</span><span class="sxs-lookup"><span data-stu-id="ff930-443">5061</span></span></p></td>
<td><p><span data-ttu-id="ff930-444">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-445">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="ff930-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-446">4443</span><span class="sxs-lookup"><span data-stu-id="ff930-446">4443</span></span></p></td>
<td><p><span data-ttu-id="ff930-447">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="ff930-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ff930-p107">Seus pools do Front-End e do Diretor que usam o balanceamento de carga DNS também precisam ter um balanceador de carga de hardware implantado. A tabela a seguir mostra as portas que precisam ser abertas nesses balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="ff930-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="ff930-450">Portas do balanceador de carga de hardware se estiver usando o balanceamento de carga DNS</span><span class="sxs-lookup"><span data-stu-id="ff930-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff930-451">Balanceador de carga</span><span class="sxs-lookup"><span data-stu-id="ff930-451">Load Balancer</span></span></th>
<th><span data-ttu-id="ff930-452">Porta</span><span class="sxs-lookup"><span data-stu-id="ff930-452">Port</span></span></th>
<th><span data-ttu-id="ff930-453">Protocolo</span><span class="sxs-lookup"><span data-stu-id="ff930-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff930-454">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-455">80</span><span class="sxs-lookup"><span data-stu-id="ff930-455">80</span></span></p></td>
<td><p><span data-ttu-id="ff930-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="ff930-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-457">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-458">443</span><span class="sxs-lookup"><span data-stu-id="ff930-458">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-460">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-461">8080</span><span class="sxs-lookup"><span data-stu-id="ff930-461">8080</span></span></p></td>
<td><p><span data-ttu-id="ff930-462">TCP - Recuperação por parte do cliente e do dispositivo do certificado raiz do Servidor Front-End – clientes e dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="ff930-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-463">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ff930-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-464">4443</span><span class="sxs-lookup"><span data-stu-id="ff930-464">4443</span></span></p></td>
<td><p><span data-ttu-id="ff930-465">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="ff930-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-466">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="ff930-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-467">443</span><span class="sxs-lookup"><span data-stu-id="ff930-467">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ff930-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-469">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="ff930-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="ff930-470">4443</span><span class="sxs-lookup"><span data-stu-id="ff930-470">4443</span></span></p></td>
<td><p><span data-ttu-id="ff930-471">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="ff930-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="ff930-472">Portas do cliente necessárias</span><span class="sxs-lookup"><span data-stu-id="ff930-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff930-473">Componente</span><span class="sxs-lookup"><span data-stu-id="ff930-473">Component</span></span></th>
<th><span data-ttu-id="ff930-474">Porta</span><span class="sxs-lookup"><span data-stu-id="ff930-474">Port</span></span></th>
<th><span data-ttu-id="ff930-475">Protocolo</span><span class="sxs-lookup"><span data-stu-id="ff930-475">Protocol</span></span></th>
<th><span data-ttu-id="ff930-476">Notas</span><span class="sxs-lookup"><span data-stu-id="ff930-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff930-477">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-478">67/68</span><span class="sxs-lookup"><span data-stu-id="ff930-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="ff930-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="ff930-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-480">Usado pelo Lync Server para localizar o FQDN do registrador (isto é, se as configurações de SRV DNS falharem e as configurações manuais não estiverem definidas).</span><span class="sxs-lookup"><span data-stu-id="ff930-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-481">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-482">443</span><span class="sxs-lookup"><span data-stu-id="ff930-482">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-484">Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="ff930-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-485">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-486">443</span><span class="sxs-lookup"><span data-stu-id="ff930-486">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-488">Usada para acesso de usuário externo às sessões de webconferência.</span><span class="sxs-lookup"><span data-stu-id="ff930-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-489">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-490">443</span><span class="sxs-lookup"><span data-stu-id="ff930-490">443</span></span></p></td>
<td><p><span data-ttu-id="ff930-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="ff930-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="ff930-492">Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)</span><span class="sxs-lookup"><span data-stu-id="ff930-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-493">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-494">3478</span><span class="sxs-lookup"><span data-stu-id="ff930-494">3478</span></span></p></td>
<td><p><span data-ttu-id="ff930-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="ff930-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="ff930-496">Usada para acesso de usuário externo às sessões de A/V e mídia (UDP)</span><span class="sxs-lookup"><span data-stu-id="ff930-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-497">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-498">5061</span><span class="sxs-lookup"><span data-stu-id="ff930-498">5061</span></span></p></td>
<td><p><span data-ttu-id="ff930-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ff930-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="ff930-500">Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="ff930-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-501">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="ff930-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="ff930-503">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-504">Usado para transferência de arquivos entre clientes do Lync e clientes anteriores (clientes do Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 e Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="ff930-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-505">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ff930-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ff930-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ff930-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ff930-508">Intervalo de porta de áudio (mínimo de 20 portas necessárias)</span><span class="sxs-lookup"><span data-stu-id="ff930-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-509">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ff930-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ff930-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ff930-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="ff930-512">Intervalo de porta de vídeo (mínimo de 20 portas necessárias).</span><span class="sxs-lookup"><span data-stu-id="ff930-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-513">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ff930-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ff930-515">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-516">Transferência de arquivos ponto a ponto (para transferência de arquivo de conferência, clientes que usam PSOM).</span><span class="sxs-lookup"><span data-stu-id="ff930-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff930-517">Clientes</span><span class="sxs-lookup"><span data-stu-id="ff930-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="ff930-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="ff930-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="ff930-519">TCP</span><span class="sxs-lookup"><span data-stu-id="ff930-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-520">Compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ff930-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff930-521">Telefone de área comum Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="ff930-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="ff930-522">Telefone de mesa Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="ff930-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="ff930-523">Telefone IP HP 4110 (telefone de área comum)</span><span class="sxs-lookup"><span data-stu-id="ff930-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="ff930-524">Telefone IP HP 4120 (telefone de mesa)</span><span class="sxs-lookup"><span data-stu-id="ff930-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="ff930-525">Telefone de área comum IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="ff930-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="ff930-526">Telefone de mesa IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="ff930-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="ff930-527">Telefone de mesa IP Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="ff930-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="ff930-528">Telefone de conferência IP Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="ff930-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="ff930-529">67/68</span><span class="sxs-lookup"><span data-stu-id="ff930-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="ff930-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="ff930-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="ff930-531">Usado pelos dispositivos listados para localizar o certificado do Lync Server, o provisionamento e o FQDN do registrador.</span><span class="sxs-lookup"><span data-stu-id="ff930-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ff930-532">**\*** Para configurar portas específicas para esses tipos de mídia, use o cmdlet CsConferencingConfiguration (parâmetros ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="ff930-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff930-533">Os programas definidos para clientes do Lync criam automaticamente as exceções necessárias de firewall do sistema operacional no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="ff930-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ff930-534">As portas usadas para acesso de usuário externo são necessárias para qualquer cenário no qual o cliente precisa atravessar o firewall da organização (por exemplo, quaisquer comunicações externas ou reuniões hospedadas por outras organizações).</span><span class="sxs-lookup"><span data-stu-id="ff930-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

