---
title: 'Lync Server 2013: portas e protocolos para servidores internos'
description: 'Lync Server 2013: portas e protocolos para servidores internos.'
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
ms.openlocfilehash: d7d8f12c78c5dec5caacaeb1156f4d228b7cd591
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566348"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="29c06-103">Portas e protocolos para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c06-103">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29c06-104">_**Última modificação do tópico:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="29c06-104">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="29c06-105">Esta seção resume as portas e os protocolos usados por servidores, balanceadores de carga e clientes em uma implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29c06-105">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="29c06-106">Os clientes do Lync e do Communicator, quando envolvidos em uma comunicação de um para um, costumam ser chamados de ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="29c06-106">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="29c06-107">Tecnicamente, os dois clientes estão se comunicando em uma única conversa, com a unidade de controle multiponto (IMMCU) do sistema de mensagens instantâneas no meio.</span><span class="sxs-lookup"><span data-stu-id="29c06-107">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="29c06-108">O IMMCU é um componente do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="29c06-108">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="29c06-109">Colocar o IMMCU no fluxo de trabalho de comunicação necessário permite a gravação de detalhes da chamada e outros recursos que o servidor front-end habilita.</span><span class="sxs-lookup"><span data-stu-id="29c06-109">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="29c06-110">A comunicação é de uma porta de origem dinâmica no cliente para a porta de servidor front-end TLS/TCP/5061 (supondo que o uso da segurança da camada de transporte recomendada).</span><span class="sxs-lookup"><span data-stu-id="29c06-110">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="29c06-111">Por design, a comunicação ponto a ponto (bem como mensagens instantâneas de vários participantes) só é possível quando o Lync Server e o IMMCU estão ativos e disponíveis.</span><span class="sxs-lookup"><span data-stu-id="29c06-111">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="29c06-112">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="29c06-112">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29c06-113">O Firewall do Windows deve estar em execução antes de iniciar os serviços do Lync Server em um servidor, pois isso ocorre quando o Lync Server abre as portas necessárias no firewall.</span><span class="sxs-lookup"><span data-stu-id="29c06-113">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="29c06-114">Para obter detalhes sobre a configuração de firewall para componentes de borda, consulte [determinar firewall de A/V externo e requisitos de porta para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c06-114">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="29c06-115">A tabela a seguir lista as portas que precisam ser abertas em cada função de servidor interno.</span><span class="sxs-lookup"><span data-stu-id="29c06-115">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="29c06-116">Portas do servidor necessárias (por Função de servidor)</span><span class="sxs-lookup"><span data-stu-id="29c06-116">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="29c06-117">Função de servidor</span><span class="sxs-lookup"><span data-stu-id="29c06-117">Server role</span></span></th>
<th><span data-ttu-id="29c06-118">Nome do serviço</span><span class="sxs-lookup"><span data-stu-id="29c06-118">Service name</span></span></th>
<th><span data-ttu-id="29c06-119">Porta</span><span class="sxs-lookup"><span data-stu-id="29c06-119">Port</span></span></th>
<th><span data-ttu-id="29c06-120">Protocolo</span><span class="sxs-lookup"><span data-stu-id="29c06-120">Protocol</span></span></th>
<th><span data-ttu-id="29c06-121">Observações</span><span class="sxs-lookup"><span data-stu-id="29c06-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29c06-122">Todos os servidores</span><span class="sxs-lookup"><span data-stu-id="29c06-122">All Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-123">Navegador do SQL</span><span class="sxs-lookup"><span data-stu-id="29c06-123">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="29c06-124">1434</span><span class="sxs-lookup"><span data-stu-id="29c06-124">1434</span></span></p></td>
<td><p><span data-ttu-id="29c06-125">VIA</span><span class="sxs-lookup"><span data-stu-id="29c06-125">UDP</span></span></p></td>
<td><p><span data-ttu-id="29c06-126">SQL browser para a cópia replicada local do banco de dados do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="29c06-126">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-127">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-127">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-128">Serviço de Front-End do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-128">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="29c06-129">5060</span><span class="sxs-lookup"><span data-stu-id="29c06-129">5060</span></span></p></td>
<td><p><span data-ttu-id="29c06-130">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-130">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-131">Usada como opção pelos servidores Standard Edition e Servidores Front-End para rotas estáticas para serviços confiáveis, como servidores de controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="29c06-131">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-132">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-132">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-133">Serviço de Front-End do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-133">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="29c06-134">5061</span><span class="sxs-lookup"><span data-stu-id="29c06-134">5061</span></span></p></td>
<td><p><span data-ttu-id="29c06-135">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-135">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-p102">Usada pelos servidores Standard Edition e pools Front-End para todas as comunicações SIP internas entre servidores (MTLS), para comunicações SIP entre o Servidor e o Cliente (TLS) e para comunicações SIP entre os Servidores Front-End e os Servidores de Mediação (MTLS). Também é usada para comunicações com o Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="29c06-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-138">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-138">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-139">Serviço de Front-End do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-139">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="29c06-140">444</span><span class="sxs-lookup"><span data-stu-id="29c06-140">444</span></span></p></td>
<td><p><span data-ttu-id="29c06-141">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-141">HTTPS</span></span></p>
<p><span data-ttu-id="29c06-142">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-142">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-143">Usada para comunicação HTTPS entre o foco (o componente do Lync Server que gerencia o estado da conferência) e os servidores individuais.</span><span class="sxs-lookup"><span data-stu-id="29c06-143">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="29c06-144">Essa porta também é usada para comunicação TCP entre aparelhos de filial persistente e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="29c06-144">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-145">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-145">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-146">Serviço de Front-End do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-146">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="29c06-147">135</span><span class="sxs-lookup"><span data-stu-id="29c06-147">135</span></span></p></td>
<td><p><span data-ttu-id="29c06-148">DCOM e RPC (controle de procedimento remoto)</span><span class="sxs-lookup"><span data-stu-id="29c06-148">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="29c06-149">Usada para operações com base em DCOM, como Movendo Usuários, Sincronização do Replicador do Usuário e Sincronização do Catálogo de Endereços.</span><span class="sxs-lookup"><span data-stu-id="29c06-149">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-150">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-150">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-151">Serviço de conferência de mensagens instantâneas do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-151">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="29c06-152">5062</span><span class="sxs-lookup"><span data-stu-id="29c06-152">5062</span></span></p></td>
<td><p><span data-ttu-id="29c06-153">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-153">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-154">Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).</span><span class="sxs-lookup"><span data-stu-id="29c06-154">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-155">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-155">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-156">Serviço de conferência da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-156">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="29c06-157">8057</span><span class="sxs-lookup"><span data-stu-id="29c06-157">8057</span></span></p></td>
<td><p><span data-ttu-id="29c06-158">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-158">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-159">Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.</span><span class="sxs-lookup"><span data-stu-id="29c06-159">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-160">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-160">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-161">Serviço de compatibilidade de conferência da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-161">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="29c06-162">8058</span><span class="sxs-lookup"><span data-stu-id="29c06-162">8058</span></span></p></td>
<td><p><span data-ttu-id="29c06-163">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-163">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-164">Usado para escutar conexões do modelo de objeto compartilhado persistente (PSOM) do cliente do Live Meeting e versões anteriores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29c06-164">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-165">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-165">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-166">Serviço de conferência de áudio/vídeo do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-166">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="29c06-167">5063</span><span class="sxs-lookup"><span data-stu-id="29c06-167">5063</span></span></p></td>
<td><p><span data-ttu-id="29c06-168">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-168">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-169">Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="29c06-169">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-170">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-170">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-171">Serviço de conferência de áudio/vídeo do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-171">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="29c06-172">57501-65535</span><span class="sxs-lookup"><span data-stu-id="29c06-172">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="29c06-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="29c06-173">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="29c06-174">Intervalo de porta de mídia usado para videoconferência.</span><span class="sxs-lookup"><span data-stu-id="29c06-174">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-175">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-176">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-176">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="29c06-177">80</span><span class="sxs-lookup"><span data-stu-id="29c06-177">80</span></span></p></td>
<td><p><span data-ttu-id="29c06-178">HTTP</span><span class="sxs-lookup"><span data-stu-id="29c06-178">HTTP</span></span></p></td>
<td><p><span data-ttu-id="29c06-179">Usada para comunicação dos Servidores Front-End com os FQDNs do farm da web (as URLs usadas pelos componentes da web IIS) quando HTTPS não é usado.</span><span class="sxs-lookup"><span data-stu-id="29c06-179">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-180">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-180">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-181">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-181">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="29c06-182">443</span><span class="sxs-lookup"><span data-stu-id="29c06-182">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-183">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-183">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="29c06-184">Usado para comunicação dos servidores front-End no farm da web FQDNs (as URLs usadas pelos componentes da web do IIS).</span><span class="sxs-lookup"><span data-stu-id="29c06-184">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-185">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-185">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-186">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-186">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="29c06-187">8080</span><span class="sxs-lookup"><span data-stu-id="29c06-187">8080</span></span></p></td>
<td><p><span data-ttu-id="29c06-188">TCP e HTTP</span><span class="sxs-lookup"><span data-stu-id="29c06-188">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="29c06-189">Usado por componentes da Web para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="29c06-189">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-190">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-190">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-191">Componente do servidor Web</span><span class="sxs-lookup"><span data-stu-id="29c06-191">Web server component</span></span></p></td>
<td><p><span data-ttu-id="29c06-192">4443</span><span class="sxs-lookup"><span data-stu-id="29c06-192">4443</span></span></p></td>
<td><p><span data-ttu-id="29c06-193">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-193">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="29c06-194">HTTPS (de proxy reverso) e comunicação de front-ends entre pools de HTTPS para entrada de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="29c06-194">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-195">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-195">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-196">Componente do servidor Web</span><span class="sxs-lookup"><span data-stu-id="29c06-196">Web server component</span></span></p></td>
<td><p><span data-ttu-id="29c06-197">8060</span><span class="sxs-lookup"><span data-stu-id="29c06-197">8060</span></span></p></td>
<td><p><span data-ttu-id="29c06-198">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-198">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-199">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-199">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-200">Componente do servidor Web</span><span class="sxs-lookup"><span data-stu-id="29c06-200">Web server component</span></span></p></td>
<td><p><span data-ttu-id="29c06-201">8061</span><span class="sxs-lookup"><span data-stu-id="29c06-201">8061</span></span></p></td>
<td><p><span data-ttu-id="29c06-202">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-202">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-203">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-203">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-204">Componente de serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="29c06-204">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="29c06-205">5086</span><span class="sxs-lookup"><span data-stu-id="29c06-205">5086</span></span></p></td>
<td><p><span data-ttu-id="29c06-206">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-206">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-207">Porta SIP usada pelos processos internos de serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="29c06-207">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-208">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-208">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-209">Componente de serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="29c06-209">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="29c06-210">5087</span><span class="sxs-lookup"><span data-stu-id="29c06-210">5087</span></span></p></td>
<td><p><span data-ttu-id="29c06-211">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-211">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-212">Porta SIP usada pelos processos internos de serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="29c06-212">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-213">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-213">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-214">Componente de serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="29c06-214">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="29c06-215">443</span><span class="sxs-lookup"><span data-stu-id="29c06-215">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-216">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-216">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-217">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-217">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-218">Serviço de atendedor de conferência do Lync Server (conferência discada)</span><span class="sxs-lookup"><span data-stu-id="29c06-218">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="29c06-219">5064</span><span class="sxs-lookup"><span data-stu-id="29c06-219">5064</span></span></p></td>
<td><p><span data-ttu-id="29c06-220">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-220">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-221">Usada para solicitações SIP de entrada para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="29c06-221">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-222">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-222">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-223">Serviço de atendedor de conferência do Lync Server (conferência discada)</span><span class="sxs-lookup"><span data-stu-id="29c06-223">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="29c06-224">5072</span><span class="sxs-lookup"><span data-stu-id="29c06-224">5072</span></span></p></td>
<td><p><span data-ttu-id="29c06-225">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-225">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-226">Usado para solicitações SIP de entrada para o atendedor (conferência discada).</span><span class="sxs-lookup"><span data-stu-id="29c06-226">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-227">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="29c06-227">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="29c06-228">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-228">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="29c06-229">5070</span><span class="sxs-lookup"><span data-stu-id="29c06-229">5070</span></span></p></td>
<td><p><span data-ttu-id="29c06-230">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-230">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-231">Usada pelo Servidor de Mediação para solicitações de entrada do Servidor Front-End para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="29c06-231">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-232">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="29c06-232">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="29c06-233">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-233">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="29c06-234">5067</span><span class="sxs-lookup"><span data-stu-id="29c06-234">5067</span></span></p></td>
<td><p><span data-ttu-id="29c06-235">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-235">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-236">Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="29c06-236">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-237">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="29c06-237">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="29c06-238">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-238">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="29c06-239">5068</span><span class="sxs-lookup"><span data-stu-id="29c06-239">5068</span></span></p></td>
<td><p><span data-ttu-id="29c06-240">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-240">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-241">Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="29c06-241">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-242">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="29c06-242">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="29c06-243">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-243">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="29c06-244">5081</span><span class="sxs-lookup"><span data-stu-id="29c06-244">5081</span></span></p></td>
<td><p><span data-ttu-id="29c06-245">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-245">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-246">Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="29c06-246">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-247">Servidores Front-End que também executam um Servidor de Mediação Colocado</span><span class="sxs-lookup"><span data-stu-id="29c06-247">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="29c06-248">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-248">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="29c06-249">5082</span><span class="sxs-lookup"><span data-stu-id="29c06-249">5082</span></span></p></td>
<td><p><span data-ttu-id="29c06-250">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-250">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-251">Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="29c06-251">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-252">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-252">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-253">Serviço de compartilhamento de aplicativos do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-253">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="29c06-254">5065</span><span class="sxs-lookup"><span data-stu-id="29c06-254">5065</span></span></p></td>
<td><p><span data-ttu-id="29c06-255">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-255">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-256">Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="29c06-256">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-257">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-257">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-258">Serviço de compartilhamento de aplicativos do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-258">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="29c06-259">49152-65535</span><span class="sxs-lookup"><span data-stu-id="29c06-259">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="29c06-260">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-260">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-261">Intervalo de porta de mídia usado para compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="29c06-261">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-262">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-262">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-263">Serviço de anúncio de conferência do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-263">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="29c06-264">5073</span><span class="sxs-lookup"><span data-stu-id="29c06-264">5073</span></span></p></td>
<td><p><span data-ttu-id="29c06-265">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-265">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-266">Usado para solicitações SIP de entrada para o serviço de anúncio de conferência do Lync Server (ou seja, para conferência discada).</span><span class="sxs-lookup"><span data-stu-id="29c06-266">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-267">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-267">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-268">Serviço de estacionamento de chamada do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-268">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="29c06-269">5075</span><span class="sxs-lookup"><span data-stu-id="29c06-269">5075</span></span></p></td>
<td><p><span data-ttu-id="29c06-270">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-270">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-271">Usada para solicitações SIP de entrada para o aplicativo Estacionamento de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="29c06-271">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-272">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-272">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-273">Serviço de teste de áudio do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-273">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="29c06-274">5076</span><span class="sxs-lookup"><span data-stu-id="29c06-274">5076</span></span></p></td>
<td><p><span data-ttu-id="29c06-275">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-275">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-276">Usada para solicitações SIP de entrada para o serviço Teste de Áudio.</span><span class="sxs-lookup"><span data-stu-id="29c06-276">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-277">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-277">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-278">NA (Not applicable)</span><span class="sxs-lookup"><span data-stu-id="29c06-278">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="29c06-279">5066</span><span class="sxs-lookup"><span data-stu-id="29c06-279">5066</span></span></p></td>
<td><p><span data-ttu-id="29c06-280">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-280">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-281">Usada para o gateway de E9-1-1 (9-1-1 Avançado) de saída.</span><span class="sxs-lookup"><span data-stu-id="29c06-281">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-282">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-282">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-283">Serviço do grupo de resposta do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-283">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="29c06-284">5071</span><span class="sxs-lookup"><span data-stu-id="29c06-284">5071</span></span></p></td>
<td><p><span data-ttu-id="29c06-285">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-285">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-286">Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.</span><span class="sxs-lookup"><span data-stu-id="29c06-286">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-287">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-287">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-288">Serviço do grupo de resposta do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-288">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="29c06-289">8404</span><span class="sxs-lookup"><span data-stu-id="29c06-289">8404</span></span></p></td>
<td><p><span data-ttu-id="29c06-290">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-290">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-291">Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.</span><span class="sxs-lookup"><span data-stu-id="29c06-291">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-292">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-292">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-293">Serviço de política de largura de banda do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-293">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="29c06-294">5080</span><span class="sxs-lookup"><span data-stu-id="29c06-294">5080</span></span></p></td>
<td><p><span data-ttu-id="29c06-295">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-295">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-296">Usada para controle de admissão de chamada pelo serviço Política de Largura de banda para tráfego TURN de Borda A/V.</span><span class="sxs-lookup"><span data-stu-id="29c06-296">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-297">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-297">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-298">Serviço de política de largura de banda do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-298">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="29c06-299">448</span><span class="sxs-lookup"><span data-stu-id="29c06-299">448</span></span></p></td>
<td><p><span data-ttu-id="29c06-300">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-300">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-301">Usada para controle de admissão de chamadas pelo serviço de política de largura de banda do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29c06-301">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-302">Servidores front-end onde reside o repositório de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="29c06-302">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="29c06-303">Serviço Agente Replicador Mestre do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-303">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="29c06-304">445</span><span class="sxs-lookup"><span data-stu-id="29c06-304">445</span></span></p></td>
<td><p><span data-ttu-id="29c06-305">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-305">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-306">Usado para enviar dados de configuração do repositório de gerenciamento central para servidores que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29c06-306">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-307">Todos os servidores</span><span class="sxs-lookup"><span data-stu-id="29c06-307">All Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-308">Navegador do SQL</span><span class="sxs-lookup"><span data-stu-id="29c06-308">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="29c06-309">1434</span><span class="sxs-lookup"><span data-stu-id="29c06-309">1434</span></span></p></td>
<td><p><span data-ttu-id="29c06-310">VIA</span><span class="sxs-lookup"><span data-stu-id="29c06-310">UDP</span></span></p></td>
<td><p><span data-ttu-id="29c06-311">Navegador do SQL para cópia replicada local de dados do repositório de gerenciamento central na instância local do SQL Server</span><span class="sxs-lookup"><span data-stu-id="29c06-311">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-312">Todos os servidores internos</span><span class="sxs-lookup"><span data-stu-id="29c06-312">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-313">Vários</span><span class="sxs-lookup"><span data-stu-id="29c06-313">Various</span></span></p></td>
<td><p><span data-ttu-id="29c06-314">49152-57500</span><span class="sxs-lookup"><span data-stu-id="29c06-314">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="29c06-315">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="29c06-315">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="29c06-316">Intervalo de porta de mídia usado para audioconferência em todos os servidores internos.</span><span class="sxs-lookup"><span data-stu-id="29c06-316">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="29c06-317">Usado por todos os servidores que encerram áudio: servidores front-end (para o serviço de atendedor de conferência do Lync Server, serviço de anúncio de conferência do Lync Server e serviço de conferência de áudio/vídeo do Lync Server) e servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="29c06-317">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-318">Servidores do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="29c06-318">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="29c06-319">443</span><span class="sxs-lookup"><span data-stu-id="29c06-319">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="29c06-320">Usado pelo Lync Server 2013 para se conectar ao servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="29c06-320">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-321">Director</span><span class="sxs-lookup"><span data-stu-id="29c06-321">Directors</span></span></p></td>
<td><p><span data-ttu-id="29c06-322">Serviço de Front-End do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-322">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="29c06-323">5060</span><span class="sxs-lookup"><span data-stu-id="29c06-323">5060</span></span></p></td>
<td><p><span data-ttu-id="29c06-324">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-324">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-325">Usada como opção para rotas estáticas até os serviços confiáveis, como servidores de controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="29c06-325">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-326">Director</span><span class="sxs-lookup"><span data-stu-id="29c06-326">Directors</span></span></p></td>
<td><p><span data-ttu-id="29c06-327">Serviço de Front-End do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-327">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="29c06-328">444</span><span class="sxs-lookup"><span data-stu-id="29c06-328">444</span></span></p></td>
<td><p><span data-ttu-id="29c06-329">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-329">HTTPS</span></span></p>
<p><span data-ttu-id="29c06-330">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-330">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-331">A comunicação entre servidores Front-End e Diretor.</span><span class="sxs-lookup"><span data-stu-id="29c06-331">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="29c06-332">Além disso, a publicação de certificado de cliente (para servidores front-end) ou a validação se o certificado de cliente já tiver sido publicado.</span><span class="sxs-lookup"><span data-stu-id="29c06-332">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-333">Director</span><span class="sxs-lookup"><span data-stu-id="29c06-333">Directors</span></span></p></td>
<td><p><span data-ttu-id="29c06-334">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-334">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="29c06-335">80</span><span class="sxs-lookup"><span data-stu-id="29c06-335">80</span></span></p></td>
<td><p><span data-ttu-id="29c06-336">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-336">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-p105">Usada para comunicação inicial dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS). Em uma operação normal, trocará para tráfego HTTPS, usando a porta 443 e o tipo de protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="29c06-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-339">Director</span><span class="sxs-lookup"><span data-stu-id="29c06-339">Directors</span></span></p></td>
<td><p><span data-ttu-id="29c06-340">Serviço de compatibilidade da Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-340">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="29c06-341">443</span><span class="sxs-lookup"><span data-stu-id="29c06-341">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-342">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-342">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="29c06-343">Usada para comunicação dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS).</span><span class="sxs-lookup"><span data-stu-id="29c06-343">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-344">Director</span><span class="sxs-lookup"><span data-stu-id="29c06-344">Directors</span></span></p></td>
<td><p><span data-ttu-id="29c06-345">Serviço de Front-End do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-345">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="29c06-346">5061</span><span class="sxs-lookup"><span data-stu-id="29c06-346">5061</span></span></p></td>
<td><p><span data-ttu-id="29c06-347">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-347">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-348">Usada para comunicações internas entre os servidores e para conexões do cliente.</span><span class="sxs-lookup"><span data-stu-id="29c06-348">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-349">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="29c06-349">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-350">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-350">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="29c06-351">5070</span><span class="sxs-lookup"><span data-stu-id="29c06-351">5070</span></span></p></td>
<td><p><span data-ttu-id="29c06-352">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-352">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-353">Usada pelo Servidor de mediação para solicitações de entrada do Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="29c06-353">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-354">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="29c06-354">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-355">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-355">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="29c06-356">5067</span><span class="sxs-lookup"><span data-stu-id="29c06-356">5067</span></span></p></td>
<td><p><span data-ttu-id="29c06-357">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-357">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-358">Usada para solicitações SIP de entrada do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="29c06-358">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-359">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="29c06-359">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-360">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-360">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="29c06-361">5068</span><span class="sxs-lookup"><span data-stu-id="29c06-361">5068</span></span></p></td>
<td><p><span data-ttu-id="29c06-362">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-362">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-363">Usada para solicitações SIP de entrada do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="29c06-363">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-364">Servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="29c06-364">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="29c06-365">Serviço de mediação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="29c06-365">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="29c06-366">5070</span><span class="sxs-lookup"><span data-stu-id="29c06-366">5070</span></span></p></td>
<td><p><span data-ttu-id="29c06-367">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-367">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-368">Usada para solicitações SIP dos Servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="29c06-368">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-369">Servidor front-end de chats persistentes</span><span class="sxs-lookup"><span data-stu-id="29c06-369">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="29c06-370">SIP de chat persistente</span><span class="sxs-lookup"><span data-stu-id="29c06-370">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="29c06-371">5041</span><span class="sxs-lookup"><span data-stu-id="29c06-371">5041</span></span></p></td>
<td><p><span data-ttu-id="29c06-372">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-372">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-373">Servidor front-end de chats persistentes</span><span class="sxs-lookup"><span data-stu-id="29c06-373">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="29c06-374">Chat persistente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="29c06-374">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="29c06-375">881</span><span class="sxs-lookup"><span data-stu-id="29c06-375">881</span></span></p></td>
<td><p><span data-ttu-id="29c06-376">TCP (TLS) e TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-376">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-377">Servidor front-end de chats persistentes</span><span class="sxs-lookup"><span data-stu-id="29c06-377">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="29c06-378">Serviço de transferência de arquivos de chat persistente</span><span class="sxs-lookup"><span data-stu-id="29c06-378">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="29c06-379">443</span><span class="sxs-lookup"><span data-stu-id="29c06-379">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-380">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-380">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="29c06-381">Alguns cenários de controle de chamada remota exigem uma conexão TCP entre o Servidor Front-End ou o Diretor e o PBX.</span><span class="sxs-lookup"><span data-stu-id="29c06-381">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="29c06-382">Embora o Lync Server não use mais a porta TCP 5060, durante a implantação de controle de chamada remota, você cria uma configuração de servidor confiável, que associa o FQDN do servidor de linha RCC à porta TCP que o servidor front-end ou diretor usará para se conectar ao sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="29c06-382">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="29c06-383">Para obter detalhes, consulte o cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29c06-383">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="29c06-384">Para os seus pools que usam somente o balanceamento de carga de hardware (não o balanceamento de carga DNS), a tabela a seguir mostra as portas que precisam abrir os balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="29c06-384">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="29c06-385">Portas do balanceador de carga de hardware se estiver usando somente o balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="29c06-385">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29c06-386">Balanceador de carga</span><span class="sxs-lookup"><span data-stu-id="29c06-386">Load Balancer</span></span></th>
<th><span data-ttu-id="29c06-387">Porta</span><span class="sxs-lookup"><span data-stu-id="29c06-387">Port</span></span></th>
<th><span data-ttu-id="29c06-388">Protocolo</span><span class="sxs-lookup"><span data-stu-id="29c06-388">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29c06-389">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-389">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-390">5061</span><span class="sxs-lookup"><span data-stu-id="29c06-390">5061</span></span></p></td>
<td><p><span data-ttu-id="29c06-391">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-391">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-392">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-392">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-393">444</span><span class="sxs-lookup"><span data-stu-id="29c06-393">444</span></span></p></td>
<td><p><span data-ttu-id="29c06-394">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-394">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-395">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-395">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-396">135</span><span class="sxs-lookup"><span data-stu-id="29c06-396">135</span></span></p></td>
<td><p><span data-ttu-id="29c06-397">DCOM e RPC (controle de procedimento remoto)</span><span class="sxs-lookup"><span data-stu-id="29c06-397">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-398">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-398">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-399">80</span><span class="sxs-lookup"><span data-stu-id="29c06-399">80</span></span></p></td>
<td><p><span data-ttu-id="29c06-400">HTTP</span><span class="sxs-lookup"><span data-stu-id="29c06-400">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-401">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-401">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-402">8080</span><span class="sxs-lookup"><span data-stu-id="29c06-402">8080</span></span></p></td>
<td><p><span data-ttu-id="29c06-403">TCP - Recuperação por parte do cliente e do dispositivo do certificado raiz do Servidor Front-End – clientes e dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="29c06-403">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-404">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-404">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-405">443</span><span class="sxs-lookup"><span data-stu-id="29c06-405">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-406">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-406">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-407">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-407">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-408">4443</span><span class="sxs-lookup"><span data-stu-id="29c06-408">4443</span></span></p></td>
<td><p><span data-ttu-id="29c06-409">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="29c06-409">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-410">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-410">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-411">5072</span><span class="sxs-lookup"><span data-stu-id="29c06-411">5072</span></span></p></td>
<td><p><span data-ttu-id="29c06-412">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-412">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-413">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-413">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-414">5073</span><span class="sxs-lookup"><span data-stu-id="29c06-414">5073</span></span></p></td>
<td><p><span data-ttu-id="29c06-415">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-415">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-416">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-416">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-417">5075</span><span class="sxs-lookup"><span data-stu-id="29c06-417">5075</span></span></p></td>
<td><p><span data-ttu-id="29c06-418">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-418">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-419">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-419">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-420">5076</span><span class="sxs-lookup"><span data-stu-id="29c06-420">5076</span></span></p></td>
<td><p><span data-ttu-id="29c06-421">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-421">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-422">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-422">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-423">5071</span><span class="sxs-lookup"><span data-stu-id="29c06-423">5071</span></span></p></td>
<td><p><span data-ttu-id="29c06-424">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-424">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-425">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-425">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-426">5080</span><span class="sxs-lookup"><span data-stu-id="29c06-426">5080</span></span></p></td>
<td><p><span data-ttu-id="29c06-427">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-427">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-428">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-428">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-429">448</span><span class="sxs-lookup"><span data-stu-id="29c06-429">448</span></span></p></td>
<td><p><span data-ttu-id="29c06-430">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-430">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-431">Balanceador de carga do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="29c06-431">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-432">5070</span><span class="sxs-lookup"><span data-stu-id="29c06-432">5070</span></span></p></td>
<td><p><span data-ttu-id="29c06-433">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-433">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-434">Balanceador de carga do servidor front-end (se o pool também executar o servidor de mediação)</span><span class="sxs-lookup"><span data-stu-id="29c06-434">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="29c06-435">5070</span><span class="sxs-lookup"><span data-stu-id="29c06-435">5070</span></span></p></td>
<td><p><span data-ttu-id="29c06-436">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-436">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-437">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="29c06-437">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-438">443</span><span class="sxs-lookup"><span data-stu-id="29c06-438">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-439">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-439">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-440">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="29c06-440">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-441">444</span><span class="sxs-lookup"><span data-stu-id="29c06-441">444</span></span></p></td>
<td><p><span data-ttu-id="29c06-442">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-442">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-443">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="29c06-443">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-444">5061</span><span class="sxs-lookup"><span data-stu-id="29c06-444">5061</span></span></p></td>
<td><p><span data-ttu-id="29c06-445">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-445">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-446">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="29c06-446">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-447">4443</span><span class="sxs-lookup"><span data-stu-id="29c06-447">4443</span></span></p></td>
<td><p><span data-ttu-id="29c06-448">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="29c06-448">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="29c06-p107">Seus pools do Front-End e do Diretor que usam o balanceamento de carga DNS também precisam ter um balanceador de carga de hardware implantado. A tabela a seguir mostra as portas que precisam ser abertas nesses balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="29c06-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="29c06-451">Portas do balanceador de carga de hardware se estiver usando o balanceamento de carga DNS</span><span class="sxs-lookup"><span data-stu-id="29c06-451">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29c06-452">Balanceador de carga</span><span class="sxs-lookup"><span data-stu-id="29c06-452">Load Balancer</span></span></th>
<th><span data-ttu-id="29c06-453">Porta</span><span class="sxs-lookup"><span data-stu-id="29c06-453">Port</span></span></th>
<th><span data-ttu-id="29c06-454">Protocolo</span><span class="sxs-lookup"><span data-stu-id="29c06-454">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29c06-455">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-455">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-456">80</span><span class="sxs-lookup"><span data-stu-id="29c06-456">80</span></span></p></td>
<td><p><span data-ttu-id="29c06-457">HTTP</span><span class="sxs-lookup"><span data-stu-id="29c06-457">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-458">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-458">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-459">443</span><span class="sxs-lookup"><span data-stu-id="29c06-459">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-460">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-460">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-461">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-461">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-462">8080</span><span class="sxs-lookup"><span data-stu-id="29c06-462">8080</span></span></p></td>
<td><p><span data-ttu-id="29c06-463">TCP - Recuperação por parte do cliente e do dispositivo do certificado raiz do Servidor Front-End – clientes e dispositivos autenticados por NTLM</span><span class="sxs-lookup"><span data-stu-id="29c06-463">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-464">Balanceador de carga do Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="29c06-464">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-465">4443</span><span class="sxs-lookup"><span data-stu-id="29c06-465">4443</span></span></p></td>
<td><p><span data-ttu-id="29c06-466">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="29c06-466">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-467">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="29c06-467">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-468">443</span><span class="sxs-lookup"><span data-stu-id="29c06-468">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-469">HTTPS</span><span class="sxs-lookup"><span data-stu-id="29c06-469">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-470">Balanceador de carga do Diretor</span><span class="sxs-lookup"><span data-stu-id="29c06-470">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="29c06-471">4443</span><span class="sxs-lookup"><span data-stu-id="29c06-471">4443</span></span></p></td>
<td><p><span data-ttu-id="29c06-472">HTTPS (do proxy reverso)</span><span class="sxs-lookup"><span data-stu-id="29c06-472">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="29c06-473">Portas do cliente necessárias</span><span class="sxs-lookup"><span data-stu-id="29c06-473">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29c06-474">Componente</span><span class="sxs-lookup"><span data-stu-id="29c06-474">Component</span></span></th>
<th><span data-ttu-id="29c06-475">Porta</span><span class="sxs-lookup"><span data-stu-id="29c06-475">Port</span></span></th>
<th><span data-ttu-id="29c06-476">Protocolo</span><span class="sxs-lookup"><span data-stu-id="29c06-476">Protocol</span></span></th>
<th><span data-ttu-id="29c06-477">Observações</span><span class="sxs-lookup"><span data-stu-id="29c06-477">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29c06-478">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-478">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-479">67/68</span><span class="sxs-lookup"><span data-stu-id="29c06-479">67/68</span></span></p></td>
<td><p><span data-ttu-id="29c06-480">ESCOPO</span><span class="sxs-lookup"><span data-stu-id="29c06-480">DHCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-481">Usado pelo Lync Server para encontrar o FQDN do registrador (ou seja, se o DNS SRV falhar e as configurações manuais não forem definidas).</span><span class="sxs-lookup"><span data-stu-id="29c06-481">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-482">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-482">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-483">443</span><span class="sxs-lookup"><span data-stu-id="29c06-483">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-484">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-484">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-485">Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="29c06-485">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-486">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-486">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-487">443</span><span class="sxs-lookup"><span data-stu-id="29c06-487">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-488">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-488">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-489">Usada para acesso de usuário externo às sessões de webconferência.</span><span class="sxs-lookup"><span data-stu-id="29c06-489">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-490">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-490">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-491">443</span><span class="sxs-lookup"><span data-stu-id="29c06-491">443</span></span></p></td>
<td><p><span data-ttu-id="29c06-492">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="29c06-492">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="29c06-493">Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)</span><span class="sxs-lookup"><span data-stu-id="29c06-493">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-494">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-494">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-495">3478</span><span class="sxs-lookup"><span data-stu-id="29c06-495">3478</span></span></p></td>
<td><p><span data-ttu-id="29c06-496">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="29c06-496">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="29c06-497">Usado para acesso de usuário externo a sessões de A/V e mídia (UDP)</span><span class="sxs-lookup"><span data-stu-id="29c06-497">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-498">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-498">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-499">5061</span><span class="sxs-lookup"><span data-stu-id="29c06-499">5061</span></span></p></td>
<td><p><span data-ttu-id="29c06-500">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="29c06-500">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="29c06-501">Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="29c06-501">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-502">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-502">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-503">6891-6901</span><span class="sxs-lookup"><span data-stu-id="29c06-503">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="29c06-504">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-504">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-505">Usado para transferência de arquivos entre clientes do Lync e clientes anteriores (clientes do Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 e Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="29c06-505">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-506">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-506">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-507">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="29c06-507">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="29c06-508">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="29c06-508">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="29c06-509">Intervalo de porta de áudio (mínimo de 20 portas necessárias)</span><span class="sxs-lookup"><span data-stu-id="29c06-509">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-510">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-510">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-511">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="29c06-511">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="29c06-512">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="29c06-512">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="29c06-513">Intervalo de porta de vídeo (mínimo de 20 portas necessárias)</span><span class="sxs-lookup"><span data-stu-id="29c06-513">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-514">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-514">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-515">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="29c06-515">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="29c06-516">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-516">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-517">Transferência de arquivos ponto a ponto (para transferência de arquivo de conferência, clientes que usam PSOM).</span><span class="sxs-lookup"><span data-stu-id="29c06-517">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c06-518">Clientes</span><span class="sxs-lookup"><span data-stu-id="29c06-518">Clients</span></span></p></td>
<td><p><span data-ttu-id="29c06-519">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="29c06-519">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="29c06-520">TCP</span><span class="sxs-lookup"><span data-stu-id="29c06-520">TCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-521">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="29c06-521">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c06-522">Telefone de área comum Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="29c06-522">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="29c06-523">Telefone de mesa Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="29c06-523">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="29c06-524">Telefone IP HP 4110 (telefone de área comum)</span><span class="sxs-lookup"><span data-stu-id="29c06-524">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="29c06-525">Telefone IP HP 4120 (telefone de mesa)</span><span class="sxs-lookup"><span data-stu-id="29c06-525">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="29c06-526">Telefone de área comum IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="29c06-526">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="29c06-527">Telefone de mesa IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="29c06-527">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="29c06-528">Telefone de mesa IP Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="29c06-528">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="29c06-529">Telefone de conferência IP Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="29c06-529">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="29c06-530">67/68</span><span class="sxs-lookup"><span data-stu-id="29c06-530">67/68</span></span></p></td>
<td><p><span data-ttu-id="29c06-531">ESCOPO</span><span class="sxs-lookup"><span data-stu-id="29c06-531">DHCP</span></span></p></td>
<td><p><span data-ttu-id="29c06-532">Usada pelos dispositivos listados para encontrar o certificado do Lync Server, o FQDN do provisionamento e o FQDN do registrador.</span><span class="sxs-lookup"><span data-stu-id="29c06-532">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="29c06-533">**\*** Para configurar portas específicas para esses tipos de mídia, use o cmdlet CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange parâmetros).</span><span class="sxs-lookup"><span data-stu-id="29c06-533">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29c06-534">Os programas definidos para clientes Lync criam automaticamente as exceções de firewall necessárias do sistema operacional no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="29c06-534">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="29c06-535">As portas usadas para acesso de usuário externo são necessárias para qualquer cenário no qual o cliente precisa atravessar o firewall da organização (por exemplo, quaisquer comunicações externas ou reuniões hospedadas por outras organizações).</span><span class="sxs-lookup"><span data-stu-id="29c06-535">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

