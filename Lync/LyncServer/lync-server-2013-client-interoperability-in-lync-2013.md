---
title: 'Lync Server 2013: interoperabilidade do cliente no Lync 2013'
description: 'Lync Server 2013: interoperabilidade do cliente no Lync 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea6e90d9479f03dd6d946787e70a2b3cc078699
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549607"
---
# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="f0513-103">Interoperabilidade do cliente no Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-103">Client interoperability in Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0513-104">_**Última modificação do tópico:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="f0513-104">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="f0513-105">Este tópico discute a capacidade dos clientes do Microsoft Lync Server 2013 de coexistir e interagir com clientes de versões anteriores do Lync Server e Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="f0513-105">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="f0513-106">Compatibilidade de servidor e cliente</span><span class="sxs-lookup"><span data-stu-id="f0513-106">Server and Client Compatibility</span></span>

<span data-ttu-id="f0513-107">A tabela a seguir exibe as combinações com suporte de versões de cliente e de servidor.</span><span class="sxs-lookup"><span data-stu-id="f0513-107">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="f0513-108">Esta tabela indica se é permitido entrar quando o cliente tenta se conectar ao servidor indicado.</span><span class="sxs-lookup"><span data-stu-id="f0513-108">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="f0513-109">O Lync Server 2013 oferece suporte à versão anterior do cliente.</span><span class="sxs-lookup"><span data-stu-id="f0513-109">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="f0513-110">Além disso, ao contrário de versões anteriores, o Lync Server 2010 oferece suporte aos novos clientes do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f0513-110">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="f0513-111">Isso permite que as organizações que estão atualizando do Lync Server 2010 distribuem novos clientes independentemente das atualizações do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0513-111">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0513-112">Cliente</span><span class="sxs-lookup"><span data-stu-id="f0513-112">Client</span></span></th>
<th><span data-ttu-id="f0513-113">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-113">Lync Server 2013</span></span></th>
<th><span data-ttu-id="f0513-114">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f0513-114">Lync Server 2010</span></span></th>
<th><span data-ttu-id="f0513-115">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f0513-115">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0513-116">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-116">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="f0513-117">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-117">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-118">Supported5</span><span class="sxs-lookup"><span data-stu-id="f0513-118">Supported5</span></span></p></td>
<td><p><span data-ttu-id="f0513-119">Não suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-119">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-120">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="f0513-120">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="f0513-121">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-122">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-122">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-123">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-123">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-124">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-124">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="f0513-125">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-125">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-126">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-126">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-127">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-127">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-128">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f0513-128">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="f0513-129">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-130">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-130">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-131">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-131">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-132">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="f0513-132">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="f0513-133">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-134">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-134">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-135">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-135">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-136">Chat de grupo do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f0513-136">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="f0513-137">Supported1</span><span class="sxs-lookup"><span data-stu-id="f0513-137">Supported1</span></span></p></td>
<td><p><span data-ttu-id="f0513-138">Supported2</span><span class="sxs-lookup"><span data-stu-id="f0513-138">Supported2</span></span></p></td>
<td><p><span data-ttu-id="f0513-139">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="f0513-139">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-140">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="f0513-140">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="f0513-141">Não suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-141">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-142">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-142">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-143">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-143">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-144">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="f0513-144">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="f0513-145">Não Supported3</span><span class="sxs-lookup"><span data-stu-id="f0513-145">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="f0513-146">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-146">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-147">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-147">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-148">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f0513-148">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="f0513-149">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="f0513-149">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="f0513-150">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-150">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-151">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-151">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-152">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="f0513-152">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="f0513-153">Não suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-153">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-154">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-154">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-155">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-155">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-156">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="f0513-156">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="f0513-157">Não suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-157">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-158">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-158">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-159">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-159">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-160">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="f0513-160">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="f0513-161">Não suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-161">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-162">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-162">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-163">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-163">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-164">Aplicativo Lync da Windows Store</span><span class="sxs-lookup"><span data-stu-id="f0513-164">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="f0513-165">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-166">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-166">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-167">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-167">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f0513-168">1Para obter detalhes, consulte [migração do Lync Server 2010, chat de grupo ou Office Communications Server 2007 R2 Group Chat to Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0513-168">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="f0513-169">2In Microsoft Lync Server 2010, a funcionalidade de chat de grupo estava disponível com o servidor de chat de grupo, um aplicativo confiável de terceiros para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f0513-169">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="f0513-170">Os clientes do Lync 2013 não são compatíveis com o Lync Server 2010, o chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="f0513-170">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="f0513-171">o 3Lync Web App 2013 agora fornece uma experiência de reunião completa, incluindo áudio e vídeo do computador e é considerado como substituto para o participante do Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="f0513-171">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="f0513-172">Lync 2010 o participante se conectará ao Lync Server 2013 somente quando você estiver usando um navegador sem suporte (Internet Explorer 6 ou Internet Explorer 7) e Windows XP.</span><span class="sxs-lookup"><span data-stu-id="f0513-172">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="f0513-173">os recursos de presença e IM do 4The no Office Communicator 2007 R2 são compatíveis com o Lync Server 2013, mas os recursos de conferência não.</span><span class="sxs-lookup"><span data-stu-id="f0513-173">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="f0513-174">Durante a migração do Office Communications Server 2007 R2, o Office Communicator 2007 R2 é adequado para a interoperabilidade de presença e de mensagens instantâneas, mas os usuários devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0513-174">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="f0513-175">5 para obter limitações, consulte "suporte de recurso de conferência para clientes do Lync 2013 no Lync Server 2010 reuniões", mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f0513-175">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="f0513-176">Interoperabilidade entre clientes</span><span class="sxs-lookup"><span data-stu-id="f0513-176">Interoperability among Clients</span></span>

<span data-ttu-id="f0513-177">Com a versão 2013 do Lync Server, várias versões do cliente podem interagir perfeitamente nos cenários de ponto a ponto e de conferência.</span><span class="sxs-lookup"><span data-stu-id="f0513-177">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="f0513-178">Esta seção discute a disponibilidade de recursos quando os usuários interagem com outros usuários, que estejam usando versões diferentes de clientes e servidores.</span><span class="sxs-lookup"><span data-stu-id="f0513-178">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="f0513-179">Suporte ao recurso ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="f0513-179">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="f0513-p106">Recursos ponto a ponto são suportados para usuários que estão hospedados em versões diferentes do servidor e que estejam usando versões de cliente diferentes. A experiência do usuário final e os recursos disponíveis são consistentes com os recursos do cliente do usuário e a versão do servidor em que o usuário entrou. Em outras palavras:</span><span class="sxs-lookup"><span data-stu-id="f0513-p106">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions. The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to. In other words:</span></span>

  - <span data-ttu-id="f0513-183">Se um usuário estiver conectado ao Lync Server 2013 com um cliente mais antigo, o usuário terá a mesma experiência para a qual ele é usado.</span><span class="sxs-lookup"><span data-stu-id="f0513-183">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="f0513-184">Nenhum dos novos recursos introduzidos no Lync Server 2013 estará disponível até que o cliente do usuário seja atualizado.</span><span class="sxs-lookup"><span data-stu-id="f0513-184">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="f0513-185">Os exemplos incluem visualização de galeria de vídeo, vídeo HD, compartilhamento do PowerPoint atualizado e a opção de ativar o áudio e vídeo de todos os participantes na entrada da reunião.</span><span class="sxs-lookup"><span data-stu-id="f0513-185">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="f0513-186">Os novos recursos são descritos em [novos recursos de conferência no Lync Server 2013](lync-server-2013-new-conferencing-features.md) e [o que há de novo para clientes no Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f0513-186">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="f0513-187">Se um usuário estiver conectado ao Lync Server 2010 com um cliente do Lync 2013, todos os novos recursos não suportados pelo Lync Server 2010 não estarão disponíveis até que o usuário seja movido para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0513-187">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="f0513-188">A tabela a seguir compara a disponibilidade de recursos em sessões ponto a ponto nas quais o cliente está conectado ao Lync Server 2013 ou ao Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f0513-188">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0513-189">Lync Web App e Lync 2010 o participante são clientes somente da reunião e não estão incluídos nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="f0513-189">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="f0513-190">Cliente</span><span class="sxs-lookup"><span data-stu-id="f0513-190">Client</span></span></th>
<th><span data-ttu-id="f0513-191">Sistema de Mensagens Instantâneas</span><span class="sxs-lookup"><span data-stu-id="f0513-191">Instant Messaging</span></span></th>
<th><span data-ttu-id="f0513-192">Presença</span><span class="sxs-lookup"><span data-stu-id="f0513-192">Presence</span></span></th>
<th><span data-ttu-id="f0513-193">Voz</span><span class="sxs-lookup"><span data-stu-id="f0513-193">Voice</span></span></th>
<th><span data-ttu-id="f0513-194">Vídeo</span><span class="sxs-lookup"><span data-stu-id="f0513-194">Video</span></span></th>
<th><span data-ttu-id="f0513-195">Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="f0513-195">Application Sharing</span></span></th>
<th><span data-ttu-id="f0513-196">Transferência de Arquivos</span><span class="sxs-lookup"><span data-stu-id="f0513-196">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0513-197">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-197">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="f0513-198">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-199">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-200">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-201">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-202">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-203">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-203">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-204">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="f0513-204">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="f0513-205">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-206">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-207">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-208">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-209">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-210">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-211">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f0513-211">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="f0513-212">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-213">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-214">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-215">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-216">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-217">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-217">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-218">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="f0513-218">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="f0513-219">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-220">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-221">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-221">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-222">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="f0513-222">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="f0513-223">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-224">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-224">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-225">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="f0513-225">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="f0513-226">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-227">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-228">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-228">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-229">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f0513-229">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="f0513-230">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-231">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-232">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-233">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-234">Yes1</span><span class="sxs-lookup"><span data-stu-id="f0513-234">Yes1</span></span></p></td>
<td><p><span data-ttu-id="f0513-235">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-235">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-236">Rede pública de IM (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="f0513-236">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="f0513-237">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-238">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-238">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-239">Mensagens instantâneas públicas (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="f0513-239">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="f0513-240">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-241">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-242">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-243">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-243">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="f0513-244">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="f0513-244">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="f0513-245">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f0513-245">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f0513-246">Messenger até a data de desligamento do serviço.</span><span class="sxs-lookup"><span data-stu-id="f0513-246">Messenger until the service shutdown date.</span></span> <span data-ttu-id="f0513-247">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f0513-247">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f0513-248">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="f0513-248">has been announced.</span></span> <span data-ttu-id="f0513-249">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="f0513-249">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="f0513-250">O PIC USL é uma licença de assinatura por usuário, por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f0513-250">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f0513-251">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="f0513-251">Messenger.</span></span> <span data-ttu-id="f0513-252">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual não será renovado.</span><span class="sxs-lookup"><span data-stu-id="f0513-252">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="f0513-253">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="f0513-253">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f0513-254">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="f0513-254">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f0513-255">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de IM e voz.</span><span class="sxs-lookup"><span data-stu-id="f0513-255">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="f0513-256">1 no Office Communicator 2007 R2, somente o compartilhamento de área de trabalho (e não o compartilhamento de programas) está disponível.</span><span class="sxs-lookup"><span data-stu-id="f0513-256">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0513-257">O compartilhamento de área de trabalho entre o Office Communicator 2007 R2 e o Skype for Business 2015 não pode ser iniciado a partir do cliente mais recente quando a interface de usuário do cliente do Skype for Business 2015 é imposta.</span><span class="sxs-lookup"><span data-stu-id="f0513-257">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="f0513-258">Suporte de recurso de conferência para clientes do Lync 2013 nas reuniões do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f0513-258">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="f0513-259">Quando os usuários ingressam em reuniões do Lync Server 2010 com um cliente do Lync 2013, eles têm acesso aos recursos do cliente do Lync 2013 com as seguintes exceções:</span><span class="sxs-lookup"><span data-stu-id="f0513-259">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="f0513-260">Nas opções de gerenciamento de **participantes** , que podem ser acessadas apontando para o ícone pessoas na janela da reunião, a opção **sem im de reunião** não funciona.</span><span class="sxs-lookup"><span data-stu-id="f0513-260">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="f0513-261">O modo de exibição de galeria não funciona em videoconferências.</span><span class="sxs-lookup"><span data-stu-id="f0513-261">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="f0513-262">O usuário vê apenas o alto-falante ativo em vez de todos os alto-falantes.</span><span class="sxs-lookup"><span data-stu-id="f0513-262">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="f0513-263">Na lista de opções de **escolha um layout, o modo de** exibição de **Galeria** não está disponível</span><span class="sxs-lookup"><span data-stu-id="f0513-263">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="f0513-264">A lista de participantes é exibida por padrão em videoconferências.</span><span class="sxs-lookup"><span data-stu-id="f0513-264">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="f0513-265">Ao clicar com o botão direito do mouse em um usuário na lista de participantes, as opções **bloquear o gerenciamento do participante de vídeo** e **fixar na Galeria** não estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f0513-265">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="f0513-266">Suporte de recurso de conferência nas reuniões do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-266">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="f0513-267">O Lync Server 2013 fornece novos recursos de conferência que ficam disponíveis para os usuários depois que suas contas são movidas para o Lync Server 2013 e entram no cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f0513-267">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="f0513-268">Os exemplos incluem visualização de galeria de vídeo, vídeo HD, compartilhamento do PowerPoint e a opção para desativar o áudio e vídeo de todos os participantes na entrada da reunião.</span><span class="sxs-lookup"><span data-stu-id="f0513-268">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="f0513-269">Os novos recursos são descritos em [novos recursos de conferência no Lync Server 2013](lync-server-2013-new-conferencing-features.md) e [o que há de novo para clientes no Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f0513-269">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="f0513-270">Nas reuniões do Lync Server 2013, determinados recursos de conferência têm suporte para usuários hospedados em diferentes versões do servidor e que usam diferentes clientes e versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="f0513-270">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="f0513-271">Quando os clientes ingressam em uma reunião do Lync Server 2013, os usuários têm acesso aos recursos e funcionalidades mostrados nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="f0513-271">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="f0513-272">Cliente</span><span class="sxs-lookup"><span data-stu-id="f0513-272">Client</span></span></th>
<th><span data-ttu-id="f0513-273">Mensagens instantâneas ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="f0513-273">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="f0513-274">Voz</span><span class="sxs-lookup"><span data-stu-id="f0513-274">Voice</span></span></th>
<th><span data-ttu-id="f0513-275">Vídeo</span><span class="sxs-lookup"><span data-stu-id="f0513-275">Video</span></span></th>
<th><span data-ttu-id="f0513-276">Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="f0513-276">Application Sharing</span></span></th>
<th><span data-ttu-id="f0513-277">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f0513-277">PowerPoint</span></span></th>
<th><span data-ttu-id="f0513-278">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="f0513-278">File Transfer</span></span></th>
<th><span data-ttu-id="f0513-279">Quadro de comunicações</span><span class="sxs-lookup"><span data-stu-id="f0513-279">Whiteboard</span></span></th>
<th><span data-ttu-id="f0513-280">Sondagem</span><span class="sxs-lookup"><span data-stu-id="f0513-280">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0513-281">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-281">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="f0513-282">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-283">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-284">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-285">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-286">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-287">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-288">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-288">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-289">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-289">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-290">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="f0513-290">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="f0513-291">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-292">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-293">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-294">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-295">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-296">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-297">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-297">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-298">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-298">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-299">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="f0513-299">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="f0513-300">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-301">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-302">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-303">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-304">Sim2</span><span class="sxs-lookup"><span data-stu-id="f0513-304">Yes2</span></span></p></td>
<td><p><span data-ttu-id="f0513-305">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-306">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-306">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-307">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-307">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-308">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f0513-308">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="f0513-309">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-310">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-311">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-312">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-313">Yes3</span><span class="sxs-lookup"><span data-stu-id="f0513-313">Yes3</span></span></p></td>
<td><p><span data-ttu-id="f0513-314">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-315">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-315">Yes</span></span></p></td>
<td><p><span data-ttu-id="f0513-316">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-316">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-317">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="f0513-317">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="f0513-318">Sim</span><span class="sxs-lookup"><span data-stu-id="f0513-318">Yes</span></span></p></td>
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


<span data-ttu-id="f0513-319">1 no Office Communicator 2007 R2, somente o compartilhamento de área de trabalho (e não o compartilhamento de programas) está disponível.</span><span class="sxs-lookup"><span data-stu-id="f0513-319">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="f0513-320">2 o Lync Server 2013 usa um mecanismo atualizado para carregar arquivos do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f0513-320">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="f0513-321">Os usuários do Lync Web App que ingressarem em uma reunião originalmente agendada no Lync Server 2010 podem exibir e navegar em apresentações do PowerPoint, mas não podem carregar arquivos do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f0513-321">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="f0513-322">3 se a reunião foi agendada no Lync Server 2013 e slides do PowerPoint foram carregados por um cliente do Lync 2013, os usuários do Lync 2010 têm acesso somente para exibição aos slides.</span><span class="sxs-lookup"><span data-stu-id="f0513-322">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="f0513-323">Por outro lado, se os slides do PowerPoint foram carregados por um usuário do Lync 2010, os usuários do Lync Server 2013 poderão exibir e slides e, se o servidor do Office Web Apps estiver configurado, acessar novos recursos, como exibição de alta resolução, animações, transições de slides e vídeo incorporado.</span><span class="sxs-lookup"><span data-stu-id="f0513-323">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="f0513-324">Para obter mais informações, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="f0513-324">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="f0513-325">os recursos de presença e IM do 4The no Office Communicator 2007 R2 são compatíveis com o Lync Server 2013, mas os recursos de conferência não.</span><span class="sxs-lookup"><span data-stu-id="f0513-325">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="f0513-326">Durante a migração do Office Communications Server 2007 R2, o Office Communicator 2007 R2 é adequado para a interoperabilidade de presença e de mensagens instantâneas, mas os usuários devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0513-326">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="f0513-327">Suporte a suplemento de agendamento</span><span class="sxs-lookup"><span data-stu-id="f0513-327">Scheduling Add-in Support</span></span>

<span data-ttu-id="f0513-328">O suporte do servidor a vários suplementos de agendamento é consistente com a compatibilidade de versão do servidor e cliente.</span><span class="sxs-lookup"><span data-stu-id="f0513-328">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="f0513-329">Em geral, os seguintes suplementos de agendamento têm suporte no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0513-329">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="f0513-330">No entanto, versões anteriores de suplementos não fornecem novos recursos de suplemento do Lync 2013, como a opção para desativar o áudio e o vídeo de todos os participantes na entrada da reunião.</span><span class="sxs-lookup"><span data-stu-id="f0513-330">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="f0513-331">**Suplemento de reunião online para Lync 2013**     Oferece os mesmos recursos que o suplemento de reunião online para o Lync 2010, com a adição de controles sem som de participantes, que permitem que os organizadores de reunião agendem conferências com áudio e vídeo de participante sem som por padrão.</span><span class="sxs-lookup"><span data-stu-id="f0513-331">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="f0513-332">Administradores também podem personalizar convites de reunião da organização incluindo um logotipo personalizado, uma URL da equipe de suporte, uma URL de aviso de isenção legal ou um texto de rodapé personalizado.</span><span class="sxs-lookup"><span data-stu-id="f0513-332">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="f0513-333">**Suplemento de reunião online para Lync 2010**     Fornece agendamento para reuniões do Lync e remove a capacidade de agendar conferências do Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="f0513-333">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="f0513-334">Suplemento de conferência **do Office Communicator 2007 R2**     Fornece agendamento para conferências do Office Live Meeting e conferências do Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f0513-334">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="f0513-335">As conferências do Live Meeting não podem ser agendadas no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0513-335">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="f0513-336">Cliente de agendamento</span><span class="sxs-lookup"><span data-stu-id="f0513-336">Scheduling Client</span></span></th>
<th><span data-ttu-id="f0513-337">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-337">Lync Server 2013</span></span></th>
<th><span data-ttu-id="f0513-338">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f0513-338">Lync Server 2010</span></span></th>
<th><span data-ttu-id="f0513-339">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f0513-339">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0513-340">Suplemento de reunião online para Lync 2013 (pode ser usado com o Office 2013, Outlook 2010 e Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="f0513-340">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="f0513-341">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-341">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-342">Suportado (novos recursos de suplemento não disponíveis)</span><span class="sxs-lookup"><span data-stu-id="f0513-342">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="f0513-343">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-343">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-344">Agendador da Web do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-344">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="f0513-345">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-345">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-346">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-346">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-347">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-347">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0513-348">Suplemento de Reunião Online para Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f0513-348">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="f0513-349">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-350">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-350">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-351">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-351">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0513-352">Suplemento de Conferência do Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f0513-352">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="f0513-353">Não suportado</span><span class="sxs-lookup"><span data-stu-id="f0513-353">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-354">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-354">Supported</span></span></p></td>
<td><p><span data-ttu-id="f0513-355">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f0513-355">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="f0513-356">Suporte para entrar em reuniões</span><span class="sxs-lookup"><span data-stu-id="f0513-356">Support for Joining Meetings</span></span>

<span data-ttu-id="f0513-357">Todos os clientes com suporte do Lync Server 2013 têm permissão para ingressar em reuniões do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f0513-357">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="f0513-358">Como o Lync Web App é um componente da Web do servidor, em casos em que o Lync Web App é usado para ingressar em uma reunião do Lync Server 2013, a versão mais recente do Lync Web App é sempre usada.</span><span class="sxs-lookup"><span data-stu-id="f0513-358">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="f0513-359">Os clientes do Lync 2013 podem ingressar em reuniões hospedadas no Lync 2010 e no Office Communications Server 2007 R2 com funcionalidade escalada.</span><span class="sxs-lookup"><span data-stu-id="f0513-359">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="f0513-360">Recursos em reuniões são limitados pela versão do servidor em que a reunião está hospedada.</span><span class="sxs-lookup"><span data-stu-id="f0513-360">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0513-361">Confira também</span><span class="sxs-lookup"><span data-stu-id="f0513-361">See Also</span></span>


[<span data-ttu-id="f0513-362">Requisitos de aplicativo do Lync Windows Store para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-362">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="f0513-363">Novos recursos de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-363">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="f0513-364">O que há de novo para clientes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0513-364">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

