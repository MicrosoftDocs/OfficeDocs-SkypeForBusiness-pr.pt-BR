---
title: 'Lync Server 2013: Instalando e configurando nós do Inspetor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89465227e351da3c69116201efe5ee4eab89eca4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="3fc29-102">Instalar e configurar nós do Inspetor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fc29-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fc29-103">_**Tópico da última modificação:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="3fc29-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="3fc29-104">*Nós de Inspetor* são computadores que executam periodicamente transações sintéticas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3fc29-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="3fc29-105">*As transações sintéticas* são cmdlets do Windows PowerShell que verificam se os principais cenários do usuário final, como a capacidade de entrar no sistema, ou a capacidade de trocar mensagens de chat, estão funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="3fc29-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="3fc29-106">Para o Lync Server 2013, o System Center Operations Manager pode executar as transações sintéticas mostradas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="3fc29-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="3fc29-107">Há três tipos diferentes de transações sintéticas mostradas na tabela:</span><span class="sxs-lookup"><span data-stu-id="3fc29-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="3fc29-108">**Padrão**.</span><span class="sxs-lookup"><span data-stu-id="3fc29-108">**Default**.</span></span> <span data-ttu-id="3fc29-109">Estas são as transações sintéticas que um nó de Inspetor será executado por padrão.</span><span class="sxs-lookup"><span data-stu-id="3fc29-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="3fc29-110">Ao criar um novo nó Inspetor, você tem a opção de especificar quais transações sintéticas esse nó executará.</span><span class="sxs-lookup"><span data-stu-id="3fc29-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="3fc29-111">(Essa é a finalidade do parâmetro testes usado pelo cmdlet **New-CsWatcherNodeConfiguration** .) Se você não usar o parâmetro tests quando o nó do Inspetor for criado, ele executará automaticamente todas as transações sintéticas padrão e não executará qualquer uma das transações sintéticas não padrão.</span><span class="sxs-lookup"><span data-stu-id="3fc29-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="3fc29-112">Isso significa, por exemplo, que o nó do Inspetor será configurado para executar o teste Test-CsAddressBookService, mas não será configurado para executar o teste Test-CsExumConnectivity.</span><span class="sxs-lookup"><span data-stu-id="3fc29-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="3fc29-113">**Não padrão**.</span><span class="sxs-lookup"><span data-stu-id="3fc29-113">**Non-default**.</span></span> <span data-ttu-id="3fc29-114">Como o nome indica, as transações sintéticas não padrão são testes que os nós do inspetor não são executados por padrão.</span><span class="sxs-lookup"><span data-stu-id="3fc29-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="3fc29-115">No entanto, o nó do Inspetor pode ser habilitado para executar qualquer uma das transações sintéticas não padrão.</span><span class="sxs-lookup"><span data-stu-id="3fc29-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="3fc29-116">Você pode fazer isso quando cria o nó do Inspetor (usando o cmdlet **New-CsWatcherNodeConfiguration** ) ou a qualquer momento após isso.</span><span class="sxs-lookup"><span data-stu-id="3fc29-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="3fc29-117">Muitas das transações sintéticas não padrão exigem etapas adicionais de configuração.</span><span class="sxs-lookup"><span data-stu-id="3fc29-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="3fc29-118">Para obter detalhes, consulte [instruções de configuração especial para transações sintéticas no Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="3fc29-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="3fc29-119">**Estendido**.</span><span class="sxs-lookup"><span data-stu-id="3fc29-119">**Extended**.</span></span> <span data-ttu-id="3fc29-120">Os testes estendidos são um tipo especial de transação sintética não padrão.</span><span class="sxs-lookup"><span data-stu-id="3fc29-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="3fc29-121">Diferentemente das outras transações sintéticas, os testes estendidos podem ser executados várias vezes durante cada fase.</span><span class="sxs-lookup"><span data-stu-id="3fc29-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="3fc29-122">Isso pode ser útil ao verificar o comportamento, como várias rotas de voz PSTN (rede telefônica pública comutada) para um pool.</span><span class="sxs-lookup"><span data-stu-id="3fc29-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="3fc29-123">Isso pode ser configurado simplesmente adicionando várias instâncias de um teste estendido a um nó de Inspetor.</span><span class="sxs-lookup"><span data-stu-id="3fc29-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="3fc29-124">Para obter detalhes sobre o processo de adicionar outras transações sintéticas a um nó de Inspetor, consulte [Gerenciando nós de Inspetor no Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="3fc29-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="3fc29-125">Você pode usar o Shell de gerenciamento do Lync Server para remover transações sintéticas de um nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="3fc29-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="3fc29-126">As transações sintéticas disponíveis para os nós do inspetor incluem as seguintes:</span><span class="sxs-lookup"><span data-stu-id="3fc29-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fc29-127">Nome do cmdlet (nome do teste)</span><span class="sxs-lookup"><span data-stu-id="3fc29-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="3fc29-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="3fc29-128">Description</span></span></th>
<th><span data-ttu-id="3fc29-129">Tipo de transação sintética</span><span class="sxs-lookup"><span data-stu-id="3fc29-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-130">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="3fc29-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-131">Confirma que os usuários podem procurar usuários que não estão na lista de contatos deles.</span><span class="sxs-lookup"><span data-stu-id="3fc29-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-132">Padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fc29-133">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="3fc29-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-134">Confirma que os usuários podem procurar usuários que não estão na lista de contatos via HTTP.</span><span class="sxs-lookup"><span data-stu-id="3fc29-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-135">Padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-136">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="3fc29-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-137">Confirma se os usuários podem enviar mensagens instantâneas ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="3fc29-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-138">Padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fc29-139">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="3fc29-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-140">Confirma se os usuários podem realizar chamadas de áudio ponto a ponto (apenas sinalização).</span><span class="sxs-lookup"><span data-stu-id="3fc29-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="3fc29-141">Padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-142">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="3fc29-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-143">Confirma se os usuários podem exibir a presença de outros usuários.</span><span class="sxs-lookup"><span data-stu-id="3fc29-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-144">Padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fc29-145">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="3fc29-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-146">Confirma se os usuários podem entrar no Lync.</span><span class="sxs-lookup"><span data-stu-id="3fc29-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-147">Padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-148">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="3fc29-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-149">Não usado com a versão local do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fc29-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="3fc29-150">Estendidas</span><span class="sxs-lookup"><span data-stu-id="3fc29-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fc29-151">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="3fc29-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-152">Confirma se os usuários podem realizar e receber chamadas de pessoas de fora da organização (números PSTN).</span><span class="sxs-lookup"><span data-stu-id="3fc29-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="3fc29-153">Não padrão, estendido</span><span class="sxs-lookup"><span data-stu-id="3fc29-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-154">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="3fc29-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-155">Confirma se os usuários podem criar e participar de uma conferência de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="3fc29-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-156">Padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fc29-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="3fc29-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-158">Confirma que os servidores de borda A/V podem aceitar conexões para chamadas ponto a ponto e chamadas em conferência.</span><span class="sxs-lookup"><span data-stu-id="3fc29-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-159">Não padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-160">Test-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="3fc29-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-161">Confirma que os usuários podem participar de uma conferência de colaboração de dados, uma reunião online que inclui atividades como quadros de comunicações e sondagens.</span><span class="sxs-lookup"><span data-stu-id="3fc29-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-162">Não padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fc29-163">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="3fc29-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-164">Confirma se um usuário pode se conectar à uma mensagem unificada do Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="3fc29-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="3fc29-165">Não padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-166">Test-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="3fc29-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-167">Confirma se os usuários podem enviar mensagens instantâneas em conferências e participar de conversas de mensagem instantânea com três ou mais pessoas.</span><span class="sxs-lookup"><span data-stu-id="3fc29-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-168">Padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fc29-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="3fc29-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-170">Confirma que os usuários podem criar e ingressar em reuniões agendadas por meio de um link de endereço da Web.</span><span class="sxs-lookup"><span data-stu-id="3fc29-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-171">Não padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-172">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="3fc29-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-173">Confirma se usuários de dispositivos móveis podem registrar-se e enviar mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="3fc29-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-174">Não padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fc29-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="3fc29-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-176">Confirma se os usuários podem trocar mensagens usando o serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3fc29-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-177">Não padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="3fc29-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-179">Confirma se os contatos de um usuário podem ser acessados por meio do repositório unificado de contatos.</span><span class="sxs-lookup"><span data-stu-id="3fc29-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="3fc29-180">O repositório de contatos unificado fornece uma maneira para os usuários manterem um único conjunto de contatos que podem ser acessados usando o Lync 2013, o Outlook e/ou o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3fc29-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-181">Não padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fc29-182">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="3fc29-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="3fc29-183">Confirma que uma mensagem instantânea pode ser enviada pelo Gateway XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="3fc29-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="3fc29-184">Não padrão</span><span class="sxs-lookup"><span data-stu-id="3fc29-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3fc29-185">Você não precisa instalar nós de inspetor para usar o System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="3fc29-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="3fc29-186">Se você não instalar esses nós, ainda poderá obter alertas em tempo real dos componentes do Lync Server 2013 quando ocorrer um problema.</span><span class="sxs-lookup"><span data-stu-id="3fc29-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="3fc29-187">(O componente e o pacote de gerenciamento do usuário não usam nós do Inspetor.) No entanto, nós de Inspetor são necessários se você deseja monitorar cenários de ponta a ponta usando o pacote de gerenciamento de monitoramento ativo.</span><span class="sxs-lookup"><span data-stu-id="3fc29-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3fc29-188">Os administradores também podem executar transações sintéticas manualmente, sem precisar usar ou instalar o Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="3fc29-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="3fc29-189">Para obter detalhes sobre os vários cmdlets Test-cs, consulte o <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">índice de cmdlets do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3fc29-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="3fc29-190">Dependendo do tamanho da sua implantação, as transações sintéticas podem usar uma grande quantidade de memória do computador e tempo do processador.</span><span class="sxs-lookup"><span data-stu-id="3fc29-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="3fc29-191">Por esse motivo, recomendamos que você use um computador dedicado como nó de Inspetor.</span><span class="sxs-lookup"><span data-stu-id="3fc29-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="3fc29-192">Por exemplo, você não deve configurar um servidor front-end para atuar como um nó de Inspetor.</span><span class="sxs-lookup"><span data-stu-id="3fc29-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="3fc29-193">Os nós de Inspetor devem atender às seguintes especificações de hardware:</span><span class="sxs-lookup"><span data-stu-id="3fc29-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3fc29-194">Um nó de Inspetor do Microsoft Lync Server 2010 herdado não pode ser posicionado na mesma máquina com um nó do Inspetor do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3fc29-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="3fc29-195">Isso ocorre porque os principais arquivos de sistema do Lync Server 2010 e do Lync Server 2013 não podem ser instalados no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="3fc29-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="3fc29-196">No entanto, os nós do Inspetor do Lync Server 2013 podem monitorar simultaneamente o Lync Server 2013 e o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3fc29-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="3fc29-197">As transações sintéticas padrão são suportadas nas duas versões do produto.</span><span class="sxs-lookup"><span data-stu-id="3fc29-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="3fc29-198">Os nós do Inspetor do Lync Server 2013 podem ser implantados dentro ou fora de uma empresa para ajudar a verificar:</span><span class="sxs-lookup"><span data-stu-id="3fc29-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="3fc29-199">A conectividade com pools para usuários internos da empresa.</span><span class="sxs-lookup"><span data-stu-id="3fc29-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="3fc29-200">Conectividade por meio de redes de perímetro para usuários remotos que trabalham fora da empresa.</span><span class="sxs-lookup"><span data-stu-id="3fc29-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="3fc29-201">A conectividade com dispositivos de filiais.</span><span class="sxs-lookup"><span data-stu-id="3fc29-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="3fc29-202">Conectividade com o Lync Server 2010 dentro da empresa e através de redes de perímetro.</span><span class="sxs-lookup"><span data-stu-id="3fc29-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="3fc29-203">Opções de autenticação diferentes estão disponíveis para dentro e para fora da empresa para ajudar a simplificar a administração.</span><span class="sxs-lookup"><span data-stu-id="3fc29-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="3fc29-204">Para obter detalhes, consulte [Configurando um nó de inspetor para executar transações sintéticas no Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="3fc29-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="3fc29-205">Para configurar um computador para atuar como um nó de Inspetor, você deve concluir as seguintes etapas após ter instalado o System Center Operations Manager e importado os pacotes de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3fc29-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="3fc29-206">Antes de instalar os arquivos do Lync Server 2013 Core e os arquivos do agente do System Center, você também deve verificar se o computador do nó do Inspetor atende a todos os pré-requisitos para instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3fc29-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="3fc29-207">Além disso, o computador do nó do Inspetor também deve ter os seguintes itens instalados:</span><span class="sxs-lookup"><span data-stu-id="3fc29-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fc29-208">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="3fc29-208">Hardware component</span></span></th>
<th><span data-ttu-id="3fc29-209">Requisitos mínimos</span><span class="sxs-lookup"><span data-stu-id="3fc29-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-210">CPU</span><span class="sxs-lookup"><span data-stu-id="3fc29-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="3fc29-211">Um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="3fc29-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3fc29-212">Processador de 64 bits, quad-core, 2.33 GHz ou superior</span><span class="sxs-lookup"><span data-stu-id="3fc29-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="3fc29-213">Processador de 2 vias e 64 bits, dual-core, 2.33 GHz ou superior</span><span class="sxs-lookup"><span data-stu-id="3fc29-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fc29-214">Memória</span><span class="sxs-lookup"><span data-stu-id="3fc29-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="3fc29-215">8 GB</span><span class="sxs-lookup"><span data-stu-id="3fc29-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fc29-216">Sistema operacional de rede</span><span class="sxs-lookup"><span data-stu-id="3fc29-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3fc29-217">1 adaptador de rede 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="3fc29-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="3fc29-218">Windows Server 2008 R2, Windows Server 2012 ou</span><span class="sxs-lookup"><span data-stu-id="3fc29-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="3fc29-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3fc29-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="3fc29-220">A versão completa do .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="3fc29-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="3fc29-221">Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="3fc29-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="3fc29-222">Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="3fc29-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="3fc29-223">Assim que todos esses pré-requisitos forem atendidos, você poderá configurar o nó do Inspetor por:</span><span class="sxs-lookup"><span data-stu-id="3fc29-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="3fc29-224">Instalar os arquivos do Lync Server 2013 Core no computador do nó inspetor.</span><span class="sxs-lookup"><span data-stu-id="3fc29-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="3fc29-225">Instalando o agente do System Center Operations Manager no computador do nó inspetor.</span><span class="sxs-lookup"><span data-stu-id="3fc29-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="3fc29-226">Executar o arquivo executável Watchernode. msi.</span><span class="sxs-lookup"><span data-stu-id="3fc29-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="3fc29-227">Usar os cmdlets **CsWatcherNodeConfiguration** para configurar os usuários de teste para serem empregados pelo nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="3fc29-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

