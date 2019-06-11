---
title: 'Lync Server 2013: Interoperabilidade do Cliente no Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ccc6239ffa0216e36839a7e58b510d8c8c3240
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="46866-102">Interoperabilidade do Cliente no Lync 2013</span><span class="sxs-lookup"><span data-stu-id="46866-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46866-103">_**Tópico da última modificação:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="46866-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="46866-104">Este tópico discute a capacidade dos clientes do Microsoft Lync Server 2013 de coexistência e interação com clientes de versões anteriores do Lync Server e do Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="46866-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="46866-105">Compatibilidade do servidor e do cliente</span><span class="sxs-lookup"><span data-stu-id="46866-105">Server and Client Compatibility</span></span>

<span data-ttu-id="46866-106">A tabela a seguir mostra as combinações de versões de servidor e versões de cliente com suporte.</span><span class="sxs-lookup"><span data-stu-id="46866-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="46866-107">Esta tabela indica se há suporte para entrada quando o cliente tenta se conectar ao servidor indicado.</span><span class="sxs-lookup"><span data-stu-id="46866-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="46866-108">O Lync Server 2013 dá suporte à versão anterior do cliente.</span><span class="sxs-lookup"><span data-stu-id="46866-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="46866-109">Além disso, ao contrário das versões anteriores, o Lync Server 2010 oferece suporte aos novos clientes do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="46866-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="46866-110">Isso permite que as organizações que estão fazendo a atualização do Lync Server 2010 para distribuir novos clientes independentemente das atualizações do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46866-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46866-111">Cliente</span><span class="sxs-lookup"><span data-stu-id="46866-111">Client</span></span></th>
<th><span data-ttu-id="46866-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46866-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="46866-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="46866-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="46866-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="46866-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46866-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="46866-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="46866-116">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="46866-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="46866-118">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="46866-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="46866-120">Compatível </span><span class="sxs-lookup"><span data-stu-id="46866-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-121">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-122">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="46866-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="46866-124">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-125">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-126">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="46866-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="46866-128">Compatível </span><span class="sxs-lookup"><span data-stu-id="46866-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-129">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-130">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="46866-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="46866-132">Compatível </span><span class="sxs-lookup"><span data-stu-id="46866-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-133">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-134">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-135">Chat de Grupo do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="46866-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="46866-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="46866-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="46866-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="46866-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="46866-138">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="46866-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="46866-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="46866-140">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-141">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-142">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="46866-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="46866-144">Não Supported3</span><span class="sxs-lookup"><span data-stu-id="46866-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="46866-145">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-146">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="46866-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="46866-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="46866-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="46866-149">Compatível </span><span class="sxs-lookup"><span data-stu-id="46866-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-150">Compatível</span><span class="sxs-lookup"><span data-stu-id="46866-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-151">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="46866-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="46866-152">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-153">Compatível </span><span class="sxs-lookup"><span data-stu-id="46866-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-154">Compatível</span><span class="sxs-lookup"><span data-stu-id="46866-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="46866-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="46866-156">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-157">Compatível </span><span class="sxs-lookup"><span data-stu-id="46866-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-158">Compatível</span><span class="sxs-lookup"><span data-stu-id="46866-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="46866-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="46866-160">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-161">Compatível </span><span class="sxs-lookup"><span data-stu-id="46866-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-162">Compatível</span><span class="sxs-lookup"><span data-stu-id="46866-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-163">Aplicativo Lync Windows Store</span><span class="sxs-lookup"><span data-stu-id="46866-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="46866-164">Compatível </span><span class="sxs-lookup"><span data-stu-id="46866-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-165">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-166">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46866-167">1Para obter detalhes, confira [migrar do Lync Server 2010, chat em grupo ou Office Communications Server 2007 R2 Grupo chat para o Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="46866-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="46866-168">2In Microsoft Lync Server 2010, a funcionalidade do chat em grupo estava disponível com o servidor de chat em grupo, um aplicativo confiável de terceiros para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="46866-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="46866-169">Os clientes do Lync 2013 não são compatíveis com o Lync Server 2010, o chat em grupo.</span><span class="sxs-lookup"><span data-stu-id="46866-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="46866-170">o 3Lync Web App 2013 agora oferece uma experiência completa na reunião, incluindo áudio e vídeo do computador, e é considerado como substituto para o participante do Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="46866-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="46866-171">O Lync 2010 se conectará ao Lync Server 2013 somente quando você estiver usando um navegador sem suporte (Internet Explorer 6 ou Internet Explorer 7) e Windows XP.</span><span class="sxs-lookup"><span data-stu-id="46866-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="46866-172">os recursos de presença e de mensagem instantânea do 4The no Office Communicator 2007 R2 são compatíveis com o Lync Server 2013, mas os recursos de conferência não são.</span><span class="sxs-lookup"><span data-stu-id="46866-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="46866-173">Durante a migração do Office Communications Server 2007 R2, o Office Communicator 2007 R2 é adequado para presença e interoperabilidade de mensagens instantâneas, mas os usuários devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46866-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="46866-174">5 para obter limitações, consulte "recurso de conferência de suporte para clientes do Lync 2013 no Lync Server 2010 reuniões" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="46866-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="46866-175">Interoperabilidade entre clientes</span><span class="sxs-lookup"><span data-stu-id="46866-175">Interoperability among Clients</span></span>

<span data-ttu-id="46866-176">Com o lançamento do Lync Server 2013, várias versões de cliente podem interagir perfeitamente em cenários ponto a ponto e conferência.</span><span class="sxs-lookup"><span data-stu-id="46866-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="46866-177">Esta seção discute a disponibilidade de recursos quando os usuários interagem com outros usuários que usam versões diferentes de clientes e servidores.</span><span class="sxs-lookup"><span data-stu-id="46866-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="46866-178">Suporte a recursos ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="46866-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="46866-179">Os recursos ponto a ponto são suportados para os usuários que são hospedados em diferentes versões do servidor e quem está usando versões diferentes do cliente.</span><span class="sxs-lookup"><span data-stu-id="46866-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="46866-180">A experiência do usuário final e os recursos disponíveis são consistentes com os recursos do cliente do usuário e a versão do servidor ao qual o usuário está conectado.</span><span class="sxs-lookup"><span data-stu-id="46866-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="46866-181">Em outras palavras:</span><span class="sxs-lookup"><span data-stu-id="46866-181">In other words:</span></span>

  - <span data-ttu-id="46866-182">Se um usuário estiver conectado ao Lync Server 2013 com um cliente mais antigo, o usuário terá a mesma experiência para a qual ele é usado.</span><span class="sxs-lookup"><span data-stu-id="46866-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="46866-183">Nenhum dos novos recursos introduzidos no Lync Server 2013 estará disponível até que o cliente do usuário seja atualizado.</span><span class="sxs-lookup"><span data-stu-id="46866-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="46866-184">Exemplos incluem modo de exibição de galeria de vídeos, vídeo em HD, compartilhamento do PowerPoint atualizado e a opção de ativar o áudio e o vídeo dos participantes após a entrada da reunião.</span><span class="sxs-lookup"><span data-stu-id="46866-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="46866-185">Os novos recursos estão descritos nos [novos recursos de conferência do Lync server 2013](lync-server-2013-new-conferencing-features.md) e novidades [para clientes do Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="46866-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="46866-186">Se um usuário estiver conectado ao Lync Server 2010 com um cliente do Lync 2013, todos os novos recursos não suportados pelo Lync Server 2010 ficarão indisponíveis até que o usuário seja movido para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46866-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="46866-187">A tabela a seguir compara a disponibilidade de recursos em sessões ponto a ponto nas quais o cliente está conectado ao Lync Server 2013 ou ao Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="46866-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46866-188">O Lync Web App e o Lync 2010 participantes são somente clientes de reunião e não estão incluídos nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="46866-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46866-189">Cliente</span><span class="sxs-lookup"><span data-stu-id="46866-189">Client</span></span></th>
<th><span data-ttu-id="46866-190">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="46866-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="46866-191">Presença</span><span class="sxs-lookup"><span data-stu-id="46866-191">Presence</span></span></th>
<th><span data-ttu-id="46866-192">Voz</span><span class="sxs-lookup"><span data-stu-id="46866-192">Voice</span></span></th>
<th><span data-ttu-id="46866-193">Vídeo</span><span class="sxs-lookup"><span data-stu-id="46866-193">Video</span></span></th>
<th><span data-ttu-id="46866-194">Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="46866-194">Application Sharing</span></span></th>
<th><span data-ttu-id="46866-195">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="46866-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46866-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="46866-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="46866-197">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-198">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-199">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-200">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-201">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-202">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="46866-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="46866-204">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-205">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-206">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-207">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-208">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-209">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="46866-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="46866-211">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-212">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-213">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-214">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-215">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-216">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="46866-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="46866-218">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-219">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-220">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="46866-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="46866-222">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-223">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="46866-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="46866-225">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-226">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-227">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="46866-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="46866-229">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-230">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-231">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-232">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-233">Yes1</span><span class="sxs-lookup"><span data-stu-id="46866-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="46866-234">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-235">MENSAGEM de chat pública (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="46866-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="46866-236">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-237">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-238">MENSAGEM de chat pública (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="46866-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="46866-239">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-240">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-241">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-242">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="46866-243">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="46866-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="46866-244">Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="46866-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="46866-245">Messenger até a data de desligamento do serviço.</span><span class="sxs-lookup"><span data-stu-id="46866-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="46866-246">Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="46866-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="46866-247">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="46866-247">has been announced.</span></span> <span data-ttu-id="46866-248">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="46866-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="46866-249">O PIC USL é uma licença de assinatura por usuário e por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="46866-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="46866-250">Spam.</span><span class="sxs-lookup"><span data-stu-id="46866-250">Messenger.</span></span> <span data-ttu-id="46866-251">O recurso da Microsoft para fornecer esse serviço tem o apoio acordado do Yahoo!, o contrato subjacente para o qual não será renovado.</span><span class="sxs-lookup"><span data-stu-id="46866-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="46866-252">Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo.</span><span class="sxs-lookup"><span data-stu-id="46866-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="46866-253">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="46866-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="46866-254">A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de mensagens instantâneas e de voz.</span><span class="sxs-lookup"><span data-stu-id="46866-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="46866-255">1 no Office Communicator 2007 R2, somente o compartilhamento de área de trabalho (e não o compartilhamento de programas) está disponível.</span><span class="sxs-lookup"><span data-stu-id="46866-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46866-256">O compartilhamento de área de trabalho entre o Office Communicator 2007 R2 e o Skype for Business 2015 não pode ser iniciado a partir do cliente mais recente quando a interface do usuário do cliente do Skype for Business 2015 é imposta.</span><span class="sxs-lookup"><span data-stu-id="46866-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="46866-257">Suporte do recurso de conferência para clientes do Lync 2013 no Lync Server 2010 reuniões</span><span class="sxs-lookup"><span data-stu-id="46866-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="46866-258">Quando os usuários ingressam em reuniões do Lync Server 2010 com um cliente Lync 2013, eles têm acesso aos recursos do cliente Lync 2013 com as seguintes exceções:</span><span class="sxs-lookup"><span data-stu-id="46866-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="46866-259">Nas opções de gerenciamento de **participantes** , que podem ser acessadas apontando para o ícone pessoas na janela da reunião, a opção **nenhuma mensagem instantânea de reunião** não funciona.</span><span class="sxs-lookup"><span data-stu-id="46866-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="46866-260">O modo de exibição de galeria não funciona em videoconferências.</span><span class="sxs-lookup"><span data-stu-id="46866-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="46866-261">O usuário vê apenas o alto-falante ativo em vez de todos os alto-falantes.</span><span class="sxs-lookup"><span data-stu-id="46866-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="46866-262">Na lista de opções **escolher um layout** , o **modo de exibição Galeria** não está disponível</span><span class="sxs-lookup"><span data-stu-id="46866-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="46866-263">A lista de participantes é exibida por padrão em videoconferências.</span><span class="sxs-lookup"><span data-stu-id="46866-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="46866-264">Ao clicar com o botão direito do mouse em um usuário na lista de participantes, o botão **bloquear as opções de gerenciamento de participantes do vídeo** e **fixar em Galeria** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="46866-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="46866-265">Suporte do recurso de conferência nas reuniões do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46866-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="46866-266">O Lync Server 2013 oferece novos recursos de conferência que se tornam disponíveis para os usuários após suas contas serem movidos para o Lync Server 2013 e que entram com o cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="46866-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="46866-267">Os exemplos incluem modo de exibição de galeria de vídeo, vídeo em alta definição, compartilhamento de PowerPoint e opção para desativar o áudio e o vídeo dos participantes após a entrada da reunião.</span><span class="sxs-lookup"><span data-stu-id="46866-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="46866-268">Os novos recursos estão descritos nos [novos recursos de conferência do Lync server 2013](lync-server-2013-new-conferencing-features.md) e novidades [para clientes do Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="46866-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="46866-269">Em reuniões do Lync Server 2013, determinados recursos de conferência têm suporte para os usuários que são hospedados em diferentes versões do servidor e quem usa diferentes clientes e versões do cliente.</span><span class="sxs-lookup"><span data-stu-id="46866-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="46866-270">Quando os clientes ingressam em uma reunião do Lync Server 2013, os usuários têm acesso aos recursos e funcionalidades mostrados nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="46866-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46866-271">Cliente</span><span class="sxs-lookup"><span data-stu-id="46866-271">Client</span></span></th>
<th><span data-ttu-id="46866-272">Mensagem instantânea ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="46866-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="46866-273">Voz</span><span class="sxs-lookup"><span data-stu-id="46866-273">Voice</span></span></th>
<th><span data-ttu-id="46866-274">Vídeo</span><span class="sxs-lookup"><span data-stu-id="46866-274">Video</span></span></th>
<th><span data-ttu-id="46866-275">Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="46866-275">Application Sharing</span></span></th>
<th><span data-ttu-id="46866-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="46866-276">PowerPoint</span></span></th>
<th><span data-ttu-id="46866-277">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="46866-277">File Transfer</span></span></th>
<th><span data-ttu-id="46866-278">Quadro de comunicações</span><span class="sxs-lookup"><span data-stu-id="46866-278">Whiteboard</span></span></th>
<th><span data-ttu-id="46866-279">Poll</span><span class="sxs-lookup"><span data-stu-id="46866-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46866-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="46866-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="46866-281">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-282">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-283">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-284">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-285">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-286">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-287">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-288">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="46866-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="46866-290">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-291">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-292">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-293">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-294">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-295">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-296">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-297">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="46866-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="46866-299">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-300">Sim </span><span class="sxs-lookup"><span data-stu-id="46866-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-301">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-302">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-303">Yes2</span><span class="sxs-lookup"><span data-stu-id="46866-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="46866-304">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-305">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-306">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="46866-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="46866-308">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-309">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-310">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-311">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-312">Yes3</span><span class="sxs-lookup"><span data-stu-id="46866-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="46866-313">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-314">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="46866-315">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="46866-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="46866-317">Sim</span><span class="sxs-lookup"><span data-stu-id="46866-317">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46866-318">1 no Office Communicator 2007 R2, somente o compartilhamento de área de trabalho (e não o compartilhamento de programas) está disponível.</span><span class="sxs-lookup"><span data-stu-id="46866-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="46866-319">2 o Lync Server 2013 usa um mecanismo atualizado para carregar arquivos do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="46866-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="46866-320">Os usuários do Lync Web App que ingressarem em uma reunião originalmente agendada no Lync Server 2010 podem exibir e navegar em apresentações do PowerPoint, mas não podem carregar arquivos do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="46866-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="46866-321">3 se a reunião tiver sido agendada nos slides do Lync Server 2013 e do PowerPoint foram carregadas por um cliente do Lync 2013, os usuários do Lync 2010 terão acesso somente para exibição aos slides.</span><span class="sxs-lookup"><span data-stu-id="46866-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="46866-322">Por outro lado, se os slides do PowerPoint foram carregados por um usuário do Lync 2010, os usuários do Lync Server 2013 poderão exibir e os slides e, se o Office Web Apps estiver configurado, acessar novos recursos, como exibição de resolução mais alta, animações, transições de slides e vídeo inserido.</span><span class="sxs-lookup"><span data-stu-id="46866-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="46866-323">Para obter mais informações, consulte Configurando [a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="46866-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="46866-324">os recursos de presença e de mensagem instantânea do 4The no Office Communicator 2007 R2 são compatíveis com o Lync Server 2013, mas os recursos de conferência não são.</span><span class="sxs-lookup"><span data-stu-id="46866-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="46866-325">Durante a migração do Office Communications Server 2007 R2, o Office Communicator 2007 R2 é adequado para presença e interoperabilidade de mensagens instantâneas, mas os usuários devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46866-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="46866-326">Agendando o suporte ao suplemento</span><span class="sxs-lookup"><span data-stu-id="46866-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="46866-327">O suporte do servidor para os vários suplementos de agendamento é consistente com a compatibilidade de versão do servidor e do cliente.</span><span class="sxs-lookup"><span data-stu-id="46866-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="46866-328">Em geral, os seguintes suplementos de agendamento são suportados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46866-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="46866-329">No entanto, as versões anteriores dos suplementos não fornecem novos recursos de suplemento do Lync 2013, como a opção de ativar o áudio e o vídeo dos participantes após a entrada da reunião.</span><span class="sxs-lookup"><span data-stu-id="46866-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="46866-330">**O suplemento de reunião online para o Lync 2013**   oferece os mesmos recursos que o suplemento de reunião online do Lync 2010, com a adição de controles de desativação de participantes, que permitem que os organizadores da reunião agendem conferências com áudio e vídeo de participantes com mudo ativado assume.</span><span class="sxs-lookup"><span data-stu-id="46866-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="46866-331">Os administradores também podem personalizar os convites para reunião da organização adicionando um logotipo personalizado, uma URL de suporte, uma URL de isenção de responsabilidade legal ou texto de rodapé personalizado.</span><span class="sxs-lookup"><span data-stu-id="46866-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="46866-332">**O suplemento de reunião online para o Lync 2010**   fornece agendamento para reuniões do Lync e remove a funcionalidade de agendar conferências do Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="46866-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="46866-333">**O suplemento de conferência do Office Communicator 2007 R2**   fornece agendamento para conferências do Office Live Meeting e do Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="46866-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="46866-334">Não é possível agendar conferências do Live Meeting no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="46866-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46866-335">Cliente de agendamento</span><span class="sxs-lookup"><span data-stu-id="46866-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="46866-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46866-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="46866-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="46866-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="46866-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="46866-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46866-339">Suplemento de reunião online do Lync 2013 (pode ser usado com o Office 2013, o Outlook 2010 e o Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="46866-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="46866-340">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-341">Com suporte (novos recursos de suplemento não disponíveis)</span><span class="sxs-lookup"><span data-stu-id="46866-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="46866-342">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-343">Agendador da Web do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="46866-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="46866-344">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-345">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-346">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46866-347">Suplemento de Reunião Online para Lync 2010</span><span class="sxs-lookup"><span data-stu-id="46866-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="46866-348">Compatível </span><span class="sxs-lookup"><span data-stu-id="46866-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-349">Com suporte</span><span class="sxs-lookup"><span data-stu-id="46866-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-350">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46866-351">Suplemento de conferência do Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="46866-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="46866-352">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="46866-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-353">Compatível </span><span class="sxs-lookup"><span data-stu-id="46866-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="46866-354">Compatível</span><span class="sxs-lookup"><span data-stu-id="46866-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="46866-355">Suporte para ingressar em reuniões</span><span class="sxs-lookup"><span data-stu-id="46866-355">Support for Joining Meetings</span></span>

<span data-ttu-id="46866-356">Todos os clientes aos quais o Lync Server 2013 dá suporte têm permissão para ingressar em reuniões do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="46866-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="46866-357">Como o Lync Web App é um componente da Web do servidor, em casos em que o Lync Web App é usado para ingressar em uma reunião do Lync Server 2013, a versão mais recente do Lync Web App é sempre usada.</span><span class="sxs-lookup"><span data-stu-id="46866-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="46866-358">Os clientes do Lync 2013 podem ingressar em reuniões hospedadas no Lync 2010 e no Office Communications Server 2007 R2 com funcionalidade reduzida.</span><span class="sxs-lookup"><span data-stu-id="46866-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="46866-359">Os recursos na reunião são limitados pela versão do servidor na qual a reunião está hospedada.</span><span class="sxs-lookup"><span data-stu-id="46866-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46866-360">Confira também</span><span class="sxs-lookup"><span data-stu-id="46866-360">See Also</span></span>


[<span data-ttu-id="46866-361">Requisitos do aplicativo Lync da Windows Store para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46866-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="46866-362">Novos recursos de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46866-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="46866-363">Novidades para clientes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46866-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

