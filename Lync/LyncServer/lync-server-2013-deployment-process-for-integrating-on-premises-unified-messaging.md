---
title: Processo de implantação para a integração de mensagens unificadas locais
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7147a83bad1ed8b5cacc369d8d64e71fcaac32b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="0f4db-102">Processo de implantação para integração de Unificação de Mensagens local com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f4db-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f4db-103">_**Tópico da última modificação:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="0f4db-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="0f4db-104">Se você quiser integrar o Exchange Unified Messaging (UM) com o Lync Server 2013, será necessário executar as tarefas descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0f4db-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="0f4db-105">Além disso, certifique-se de rever as práticas recomendadas de planejamento e implantação descritas em [diretrizes para integrar a Unificação de mensagens e o Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="0f4db-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="0f4db-106">Este tópico pressupõe que você tenha implantado o Lync Server 2013 com um servidor de mediação posicionado e que você tenha habilitado usuários para o Lync Server 2013, mas não necessariamente que você tenha executado todas as etapas de implantação e configuração para habilitar o Enterprise Voice, como descrito em Implantando o [Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="0f4db-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="0f4db-107">Processo de integração do Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="0f4db-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0f4db-108">É importante que você coordene com os administradores do Exchange da sua organização para confirmar as tarefas que cada um executará para garantir uma integração tranquila e bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="0f4db-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



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
<th><span data-ttu-id="0f4db-109">Fase</span><span class="sxs-lookup"><span data-stu-id="0f4db-109">Phase</span></span></th>
<th><span data-ttu-id="0f4db-110">Etapas</span><span class="sxs-lookup"><span data-stu-id="0f4db-110">Steps</span></span></th>
<th><span data-ttu-id="0f4db-111">Grupos e funções necessários</span><span class="sxs-lookup"><span data-stu-id="0f4db-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="0f4db-112">Documentação de Implantação</span><span class="sxs-lookup"><span data-stu-id="0f4db-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f4db-113">Implante um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="0f4db-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f4db-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) ou Service Pack mais recente</span><span class="sxs-lookup"><span data-stu-id="0f4db-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="0f4db-115">Microsoft Exchange Server 2010 ou Service Pack mais recente</span><span class="sxs-lookup"><span data-stu-id="0f4db-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="0f4db-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f4db-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0f4db-117">Se você estiver usando o Microsoft Exchange Server 2013, instale as seguintes funções do Exchange Server na mesma floresta ou em uma floresta diferente como o Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0f4db-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f4db-118">Acesso do Cliente</span><span class="sxs-lookup"><span data-stu-id="0f4db-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="0f4db-119">Caixa de Correio</span><span class="sxs-lookup"><span data-stu-id="0f4db-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="0f4db-120">Se o Microsoft Exchange Server 2013 e a Microsoft Exchange Unified Messaging (UM) estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f4db-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="0f4db-121">Se você estiver usando o Exchange 2010, instale as seguintes funções do Exchange Server na mesma floresta ou em uma floresta diferente do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0f4db-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f4db-122">Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="0f4db-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="0f4db-123">Transporte de hub</span><span class="sxs-lookup"><span data-stu-id="0f4db-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="0f4db-124">Acesso do Cliente</span><span class="sxs-lookup"><span data-stu-id="0f4db-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="0f4db-125">Caixa de Correio</span><span class="sxs-lookup"><span data-stu-id="0f4db-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="0f4db-126">Se o Lync Server 2013 e o Exchange Unified Messaging (UM) estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f4db-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-127">Administradores de empresa (se esta for o primeiro Exchange Server na organização)</span><span class="sxs-lookup"><span data-stu-id="0f4db-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="0f4db-128">-OU-</span><span class="sxs-lookup"><span data-stu-id="0f4db-128">-OR-</span></span></p>
<p><span data-ttu-id="0f4db-129">Administrador da organização do Exchange (se este não for o primeiro Exchange Server na organização)</span><span class="sxs-lookup"><span data-stu-id="0f4db-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="0f4db-130">Consulte a documentação apropriada para sua versão do Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="0f4db-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0f4db-131">Documentação de implantação do Exchange Server <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 em.</span><span class="sxs-lookup"><span data-stu-id="0f4db-131">Exchange Server 2007 deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0f4db-132">Exchange Server 2010 ou mais recente documentação de implantação do <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>Service Pack em.</span><span class="sxs-lookup"><span data-stu-id="0f4db-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="0f4db-133">Microsoft Exchange Server 2013 planejamento e implantação em <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span><span class="sxs-lookup"><span data-stu-id="0f4db-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f4db-134">Instalar certificados.</span><span class="sxs-lookup"><span data-stu-id="0f4db-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-135">Baixar e instalar certificados para cada servidor do Exchange UM de uma CA (autoridade de certificação) raiz confiável.</span><span class="sxs-lookup"><span data-stu-id="0f4db-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="0f4db-136">Os certificados são necessários para a MTLS (Mutual Transport Level Security) entre os servidores que executam o Exchange UM e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f4db-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-137">Administradores</span><span class="sxs-lookup"><span data-stu-id="0f4db-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="0f4db-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurar certificados no servidor que executa o Microsoft Exchange Server Unified Messaging</a></span><span class="sxs-lookup"><span data-stu-id="0f4db-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f4db-139">Crie e configure um novo plano de discagem SIP do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="0f4db-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-140">No servidor Exchange UM, crie um plano de discagem SIP com base nas necessidades de implantação específicas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0f4db-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-141">Administrador da organização do Exchange</span><span class="sxs-lookup"><span data-stu-id="0f4db-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="0f4db-142">Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte como criar um plano&quot; de discagem de URI <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>SIP de Unificação de mensagens em.</span><span class="sxs-lookup"><span data-stu-id="0f4db-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="0f4db-143">Para o Exchange 2010 ou Service Pack mais recente &quot;, consulte criar um plano&quot; de <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>discagem de um em.</span><span class="sxs-lookup"><span data-stu-id="0f4db-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="0f4db-144">Para o Exchange 2013, consulte Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="0f4db-144">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f4db-145">Definir configurações de segurança para o plano de discagem do Exchange UM SIP.</span><span class="sxs-lookup"><span data-stu-id="0f4db-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-146">Para criptografar o tráfego de voz da empresa, defina as configurações de segurança no plano de discagem do Exchange UM SIP como <strong>SIP protegido</strong> ou <strong>seguro</strong>.</span><span class="sxs-lookup"><span data-stu-id="0f4db-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="0f4db-147">Essa é uma etapa especialmente importante se você tiver implantado ou planejar a implantação de dispositivos do Lync Phone Edition em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="0f4db-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="0f4db-148">Para que os dispositivos do Lync Phone Edition funcionem em um ambiente com a integração de UM do Exchange, as configurações de criptografia do Lync Server devem ser alinhadas com as configurações de segurança do plano de discagem do UM</span><span class="sxs-lookup"><span data-stu-id="0f4db-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="0f4db-149">Para obter detalhes, consulte a documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="0f4db-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-150">Administrador da organização do Exchange</span><span class="sxs-lookup"><span data-stu-id="0f4db-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="0f4db-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f4db-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0f4db-152">Para o Exchange 2007 SP1 ou Service Pack mais recente, consulte também:</span><span class="sxs-lookup"><span data-stu-id="0f4db-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="0f4db-153">&quot;Como configurar a segurança em um plano&quot; de discagem da <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>Unificação de mensagens em.</span><span class="sxs-lookup"><span data-stu-id="0f4db-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="0f4db-154">Para o Exchange 2010 ou service pack mais recente, consulte também:</span><span class="sxs-lookup"><span data-stu-id="0f4db-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="0f4db-155">&quot;Configurar a segurança de VoIP em um plano&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>de discagem de um.</span><span class="sxs-lookup"><span data-stu-id="0f4db-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="0f4db-156">Para o Exchange 2013, consulte Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="0f4db-156">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f4db-157">Adicione servidores de Unificação de mensagens ao plano de discagem SIP do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="0f4db-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-158">Para habilitar um servidor de Unificação de Mensagens recentemente instalado a responder e processar chamadas de entrada, você deve adicionar o servidor de Unificação de Mensagens a um plano de discagem de UM.</span><span class="sxs-lookup"><span data-stu-id="0f4db-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="0f4db-159">Nesse caso, adicione o servidor ao plano de discagem do Exchange UM SIP.</span><span class="sxs-lookup"><span data-stu-id="0f4db-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-160">Administradores</span><span class="sxs-lookup"><span data-stu-id="0f4db-160">Administrators</span></span></p>
<p><span data-ttu-id="0f4db-161">Administradores do Exchange Server</span><span class="sxs-lookup"><span data-stu-id="0f4db-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="0f4db-162">Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte Como adicionar um servidor de Unificação&quot; de <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>mensagens a um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="0f4db-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="0f4db-163">Para o Exchange 2010 ou Service Pack mais recente &quot;, consulte Exibir ou configurar as propriedades de um&quot; servidor <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>de um em.</span><span class="sxs-lookup"><span data-stu-id="0f4db-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="0f4db-164">Para o Exchange 2013, consulte Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="0f4db-164">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f4db-165">Configurar caixas de correio com endereços SIP.</span><span class="sxs-lookup"><span data-stu-id="0f4db-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-166">Atribua endereços SIP às caixas de correio dos usuários do Enterprise Voice que usarão os recursos do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="0f4db-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-167">Administrador do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f4db-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="0f4db-168">Administrador de destinatários do Exchange</span><span class="sxs-lookup"><span data-stu-id="0f4db-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="0f4db-169">Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte Como adicionar, remover ou modificar um endereço SIP para um usuário&quot; habilitado para um. <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a></span><span class="sxs-lookup"><span data-stu-id="0f4db-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="0f4db-170">Para o Exchange 2010 ou Service Pack mais recente &quot;, confira modificar um endereço SIP para um usuário&quot; habilitado <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>para um.</span><span class="sxs-lookup"><span data-stu-id="0f4db-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="0f4db-171">Para o Exchange 2013, consulte Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="0f4db-171">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f4db-172">Execute o script exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="0f4db-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-173">No servidor que executa os serviços do Exchange UM, abra o Shell de gerenciamento do Exchange e execute o script exchucutil. ps1, que faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f4db-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f4db-174">Concede permissão do Lync Server 2013 para ler objetos dos serviços de domínio do Active Directory de UM, especificamente, os planos de discagem SIP criados na tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="0f4db-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="0f4db-175">Cria um objeto gateway IP de Unificação de mensagens no Active Directory para cada pool do Lync Server 2013 Enterprise Edition ou um servidor Standard Edition que hospeda usuários habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0f4db-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="0f4db-176">Cria um grupo coletivo do Exchange UM para cada gateway.</span><span class="sxs-lookup"><span data-stu-id="0f4db-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="0f4db-177">O identificador piloto do grupo de busca será o nome do plano de discagem associado ao gateway correspondente.</span><span class="sxs-lookup"><span data-stu-id="0f4db-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="0f4db-178">Eles precisam ser mapeados individualmente se houver mais de um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="0f4db-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0f4db-179">Administrador da organização do Exchange</span><span class="sxs-lookup"><span data-stu-id="0f4db-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="0f4db-180">Administrador de destinatários do Exchange</span><span class="sxs-lookup"><span data-stu-id="0f4db-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="0f4db-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f4db-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f4db-182">Configurar planos de discagem do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f4db-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-183">Se você estiver integrando com o Exchange 2007 SP1 ou Service Pack mais recente ou o Exchange 2010, crie um novo plano de discagem do Enterprise Voice com um nome que corresponda ao nome de domínio totalmente qualificado (FQDN) do plano de discagem de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="0f4db-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="0f4db-184">Você precisará fazer isso para cada plano de discagem UM.</span><span class="sxs-lookup"><span data-stu-id="0f4db-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="0f4db-185">Se você estiver integrando com o Exchange 2010 SP1, certifique-se de que os planos de discagem de voz corporativos e de nível global/nível de pool adequados foram configurados.</span><span class="sxs-lookup"><span data-stu-id="0f4db-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="0f4db-186">Se você estiver integrando com o Exchange 2010 SP1, o plano de discagem do Lync Server e os nomes dos planos de discagem do Exchange UM SIP não precisam ser correspondentes.</span><span class="sxs-lookup"><span data-stu-id="0f4db-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="0f4db-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0f4db-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="0f4db-188"><a href="lync-server-2013-configuring-dial-plans.md">Configurando planos de discagem no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f4db-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f4db-189">Execute a ferramenta de integração de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="0f4db-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-190">No Lync Server 2013, execute <strong>ocsumutil. exe</strong>, que:</span><span class="sxs-lookup"><span data-stu-id="0f4db-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f4db-191">Cria objetos de contato do Acesso do Assinante e Atendedor Automático.</span><span class="sxs-lookup"><span data-stu-id="0f4db-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="0f4db-192">Valida se há um plano de discagem de voz empresarial com um nome que corresponda ao FQDN do plano de discagem do Exchange.</span><span class="sxs-lookup"><span data-stu-id="0f4db-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="0f4db-193">Se você estiver executando o Exchange 2010 SP1 ou posterior, os nomes dos planos de discagem não precisam corresponder, e você pode ignorar o aviso da ferramenta sobre isso.</span><span class="sxs-lookup"><span data-stu-id="0f4db-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="0f4db-194">Essa ferramenta funciona examinando as configurações de UM do Active Directory para UM do Exchange e permitindo que o administrador do Lync Server 2013 exiba, crie e edite objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="0f4db-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-195">RTCUniversalServerAdmins <em>e</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0f4db-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="0f4db-196">Para executar com êxito o ocsumutil.exe, o usuário deve pertencer aos dois grupos.</span><span class="sxs-lookup"><span data-stu-id="0f4db-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="0f4db-197">Para criar objetos de Contato, o usuário que executa ocsumutil.exe deve ter a permissão correta para a unidade organizacional (OU) do Active Directory onde novos objetos de contato são armazenados.</span><span class="sxs-lookup"><span data-stu-id="0f4db-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="0f4db-198">Esta permissão pode ser concedida executando-se o cmdlet <STRONG>Grant-CsOUPermission</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0f4db-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="0f4db-199">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f4db-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="0f4db-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurar o Lync Server 2013 para trabalhar com a Unificação de Mensagens no Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="0f4db-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f4db-201">Se necessário, realize outras etapas de configuração do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0f4db-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-202">Se você ainda não configurou as configurações do Enterprise Voice em seus servidores ou usuários, siga um ou mais destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="0f4db-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f4db-203">Implantar e configurar</span><span class="sxs-lookup"><span data-stu-id="0f4db-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="0f4db-204">Gateways PSTN e Servidores de Mediação</span><span class="sxs-lookup"><span data-stu-id="0f4db-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="0f4db-205">Defina as políticas de voz, os registros de uso PSTN e os roteamentos de chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="0f4db-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="0f4db-206">Habilite usuários para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0f4db-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="0f4db-207">Opcionalmente, configure usuários específicos com planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="0f4db-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="0f4db-208">Outras etapas de configuração podem ser necessárias dependendo dos recursos da Enterprise Voice que você habilitar.</span><span class="sxs-lookup"><span data-stu-id="0f4db-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0f4db-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0f4db-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0f4db-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="0f4db-211">Consulte os tópicos nas seções a seguir:</span><span class="sxs-lookup"><span data-stu-id="0f4db-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f4db-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurar políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f4db-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="0f4db-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Implantando o Enterprise Voice no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f4db-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f4db-214">Habilitar usuários do Enterprise Voice para o Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="0f4db-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-215">No servidor Exchange UM, verifique se uma política de caixa de correio de Unificação de mensagens foi criada e se cada usuário tem uma atribuição de número de ramal exclusivo e, em seguida, habilite o usuário para a Unificação de mensagens.</span><span class="sxs-lookup"><span data-stu-id="0f4db-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="0f4db-216">Administrador de destinatários do Exchange</span><span class="sxs-lookup"><span data-stu-id="0f4db-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="0f4db-217">Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte Como habilitar um usuário para a&quot; Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span><span class="sxs-lookup"><span data-stu-id="0f4db-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="0f4db-218">Para o Exchange 2010 ou Service Pack mais recente &quot;, consulte Habilitar um usuário para&quot; Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span><span class="sxs-lookup"><span data-stu-id="0f4db-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="0f4db-219">Para o Exchange 2013, consulte Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="0f4db-219">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

