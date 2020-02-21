---
title: Processo de implantação para integração de Unificação de mensagens local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f8edade1ed4f0480d776e77eb66816c033a7e3d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="6cbcd-102">Processo de implantação para integração de Unificação de mensagens local e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cbcd-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cbcd-103">_**Última modificação do tópico:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="6cbcd-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="6cbcd-104">Se você deseja integrar a UM (Unificação de mensagens) do Exchange com o Lync Server 2013, você deve executar as tarefas descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="6cbcd-105">Além disso, certifique-se de examinar as práticas recomendadas de planejamento e implantação descritas em [diretrizes para integrar a Unificação de mensagens local e o Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="6cbcd-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="6cbcd-106">Este tópico pressupõe que você implantou o Lync Server 2013 com um servidor de mediação colocado e que você habilitou usuários para o Lync Server 2013, mas não necessariamente que você tenha executado todas as etapas de implantação e configuração para habilitar o Enterprise Voice, conforme descrito em [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="6cbcd-107">Processo de integração de Unificação de mensagens</span><span class="sxs-lookup"><span data-stu-id="6cbcd-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6cbcd-108">É importante que você coordene com os administradores do Exchange da sua organização para confirmar as tarefas que cada um executará para ajudar a garantir uma integração tranqüila e bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



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
<th><span data-ttu-id="6cbcd-109">Fase</span><span class="sxs-lookup"><span data-stu-id="6cbcd-109">Phase</span></span></th>
<th><span data-ttu-id="6cbcd-110">Etapas</span><span class="sxs-lookup"><span data-stu-id="6cbcd-110">Steps</span></span></th>
<th><span data-ttu-id="6cbcd-111">Grupos e funções exigidos</span><span class="sxs-lookup"><span data-stu-id="6cbcd-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="6cbcd-112">Documentação da implantação</span><span class="sxs-lookup"><span data-stu-id="6cbcd-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cbcd-113">Implante uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6cbcd-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6cbcd-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) ou Service Pack mais recente</span><span class="sxs-lookup"><span data-stu-id="6cbcd-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-115">Microsoft Exchange Server 2010 ou Service Pack mais recente</span><span class="sxs-lookup"><span data-stu-id="6cbcd-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cbcd-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6cbcd-117">Se você estiver usando o Microsoft Exchange Server 2013, instale as seguintes funções do Exchange Server na mesma floresta ou em uma floresta diferente como o Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6cbcd-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="6cbcd-118">Acesso para Cliente</span><span class="sxs-lookup"><span data-stu-id="6cbcd-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-119">Caixa de correio</span><span class="sxs-lookup"><span data-stu-id="6cbcd-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="6cbcd-120">Se o Microsoft Exchange Server 2013 e UM (Unificação de mensagens) do Exchange estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="6cbcd-121">Se você estiver usando o Exchange 2010, instale as seguintes funções do Exchange Server na mesma floresta ou em uma floresta diferente como o Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6cbcd-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="6cbcd-122">Unificação de Mensagens</span><span class="sxs-lookup"><span data-stu-id="6cbcd-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-123">Transporte de Hub</span><span class="sxs-lookup"><span data-stu-id="6cbcd-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-124">Acesso para Cliente</span><span class="sxs-lookup"><span data-stu-id="6cbcd-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-125">Caixa de correio</span><span class="sxs-lookup"><span data-stu-id="6cbcd-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="6cbcd-126">Se o Lync Server 2013 e a Unificação de mensagens do Exchange estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-127">Administradores corporativos (se este for o primeiro servidor do Exchange na organização)</span><span class="sxs-lookup"><span data-stu-id="6cbcd-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="6cbcd-128">-OU-</span><span class="sxs-lookup"><span data-stu-id="6cbcd-128">-OR-</span></span></p>
<p><span data-ttu-id="6cbcd-129">Administrador da organização do Exchange (se este não for o primeiro servidor do Exchange na organização)</span><span class="sxs-lookup"><span data-stu-id="6cbcd-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-130">Consulte a documentação apropriada para sua versão do Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="6cbcd-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="6cbcd-131">Documentação de implantação do Exchange Server <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 em.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-131">Exchange Server 2007 deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="6cbcd-132">Documentação de implantação do Exchange Server 2010 ou Service Pack <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>mais recente em.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="6cbcd-133">Microsoft Exchange Server 2013 planejamento e implantação em <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cbcd-134">Instalar certificados.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-135">Baixe e instale certificados para cada servidor de UM do Exchange de uma autoridade de certificação raiz confiável (AC).</span><span class="sxs-lookup"><span data-stu-id="6cbcd-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="6cbcd-136">Os certificados são necessários para a MTLS (segurança de nível de transporte) mútuo entre os servidores que executam o UM do Exchange e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-137">Administradores</span><span class="sxs-lookup"><span data-stu-id="6cbcd-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurar certificados no servidor que executa a Unificação de mensagens do Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="6cbcd-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cbcd-139">Crie e configure um novo plano de discagem SIP do UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-140">No servidor UM do Exchange, crie um plano de discagem SIP com base nos requisitos de implantação específicos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-141">Administrador da organização do Exchange</span><span class="sxs-lookup"><span data-stu-id="6cbcd-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-142">Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte como criar um plano&quot; de DISCAgem de URI <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>SIP de Unificação de mensagens em.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="6cbcd-143">Para o Exchange 2010 ou Service Pack mais recente &quot;, consulte criar um plano&quot; de <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>discagem de um em.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="6cbcd-144">Para o Exchange 2013, consulte Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-144">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cbcd-145">Definir configurações de segurança para o plano de discagem SIP do UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-146">Para criptografar o tráfego de voz da empresa, defina as configurações de segurança no plano de discagem SIP do UM do Exchange como <strong>SIP protegido</strong> ou <strong>protegido</strong>.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="6cbcd-147">Esta é uma etapa especialmente importante se você implantou ou planeja implantar dispositivos do Lync Phone Edition em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="6cbcd-148">Para que dispositivos do Lync Phone Edition funcionem em um ambiente com integração com UM do Exchange, as configurações de criptografia do Lync Server devem ser alinhadas com as configurações de segurança do plano de discagem de UM do Exchange</span><span class="sxs-lookup"><span data-stu-id="6cbcd-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="6cbcd-149">Para obter detalhes, consulte a documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-150">Administrador da organização do Exchange</span><span class="sxs-lookup"><span data-stu-id="6cbcd-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cbcd-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="6cbcd-152">Para o Exchange 2007 SP1 ou Service Pack mais recente, consulte também:</span><span class="sxs-lookup"><span data-stu-id="6cbcd-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="6cbcd-153">&quot;Como configurar a segurança em um plano&quot; de discagem de <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>Unificação de mensagens em.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="6cbcd-154">Para o Exchange 2010 ou Service Pack mais recente, consulte também:</span><span class="sxs-lookup"><span data-stu-id="6cbcd-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="6cbcd-155">&quot;Configurar a segurança VoIP em um plano&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>de discagem de um.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="6cbcd-156">Para o Exchange 2013, consulte Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-156">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cbcd-157">Adicione servidores de Unificação de mensagens ao plano de discagem SIP UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-158">Para habilitar um servidor de Unificação de mensagens recém-instalado para responder e processar chamadas de entrada, você deve adicionar o servidor de Unificação de mensagens a um plano de discagem de UM.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="6cbcd-159">Nesse caso, adicione o servidor ao plano de discagem SIP UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-160">Administradores</span><span class="sxs-lookup"><span data-stu-id="6cbcd-160">Administrators</span></span></p>
<p><span data-ttu-id="6cbcd-161">Administradores do Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6cbcd-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-162">Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte Como adicionar um servidor de Unificação&quot; de <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>mensagens a um plano de discagem em.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="6cbcd-163">Para o Exchange 2010 ou Service Pack mais recente &quot;, consulte Exibir ou configurar as propriedades de um&quot; servidor <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>de um em.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="6cbcd-164">Para o Exchange 2013, consulte Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-164">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cbcd-165">Configurar caixas de correio com endereços SIP.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-166">Atribua endereços SIP às caixas de correio de usuários do Enterprise Voice que usarão os recursos de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-167">Administrador do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cbcd-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="6cbcd-168">Administrador de destinatários do Exchange</span><span class="sxs-lookup"><span data-stu-id="6cbcd-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-169">Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte Como adicionar, remover ou modificar um endereço SIP para um usuário&quot; habilitado para um em <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="6cbcd-170">Para o Exchange 2010 ou Service Pack mais recente &quot;, consulte modificar um endereço SIP para um usuário&quot; habilitado para <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>um em.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="6cbcd-171">Para o Exchange 2013, consulte Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-171">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cbcd-172">Execute o script exchucutil. ps1.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-173">No servidor que executa os serviços de UM do Exchange, abra o Shell de gerenciamento do Exchange e execute o script exchucutil. ps1, que faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6cbcd-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6cbcd-174">Concede ao Lync Server 2013 permissão para ler objetos dos serviços de domínio do Active Directory da UM do Exchange, especificamente, os planos de discagem SIP criados na tarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-175">Cria um objeto de gateway IP de Unificação de mensagens no Active Directory para cada pool do Lync Server 2013 Enterprise Edition ou servidor Standard Edition que hospeda os usuários habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-176">Cria um grupo de busca de UM do Exchange para cada gateway.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="6cbcd-177">O identificador piloto do grupo de busca será o nome do plano de discagem associado ao gateway correspondente.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="6cbcd-178">Eles precisam ser mapeados 1:1 se houver mais de um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6cbcd-179">Administrador da organização do Exchange</span><span class="sxs-lookup"><span data-stu-id="6cbcd-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="6cbcd-180">Administrador de destinatários do Exchange</span><span class="sxs-lookup"><span data-stu-id="6cbcd-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cbcd-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cbcd-182">Configure os planos de discagem do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-183">Se você estiver integrando com o Exchange 2007 SP1 ou Service Pack mais recente ou o Exchange 2010, crie um novo plano de discagem do Enterprise Voice com um nome que corresponda ao nome de domínio totalmente qualificado (FQDN) do plano de discagem do UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="6cbcd-184">Você precisará fazer isso para cada plano de discagem de UM.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="6cbcd-185">Se você estiver integrando com o Exchange 2010 SP1, certifique-se de que os planos de discagem do Enterprise Voice em nível global/local ou de pool adequados foram configurados.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="6cbcd-186">Se você estiver integrando com o Exchange 2010 SP1, o plano de discagem do Lync Server e os nomes do plano de discagem SIP da UM do Exchange não precisam corresponder.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="6cbcd-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cbcd-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-188"><a href="lync-server-2013-configuring-dial-plans.md">Configurando planos de discagem no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cbcd-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cbcd-189">Execute a ferramenta de integração do UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-190">No Lync Server 2013, execute <strong>ocsumutil. exe</strong>, que:</span><span class="sxs-lookup"><span data-stu-id="6cbcd-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="6cbcd-191">Cria objetos de contato de acesso do assinante e atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-192">Valida que há um plano de discagem do Enterprise Voice com um nome que corresponde ao FQDN do plano de discagem do UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="6cbcd-193">Se você estiver executando o Exchange 2010 SP1 ou posterior, os nomes do plano de discagem não precisarão corresponder e você poderá ignorar o aviso da ferramenta sobre isso.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="6cbcd-194">Essa ferramenta funciona examinando as configurações do Active Directory para UM do Exchange e permitindo que o administrador do Lync Server 2013 visualize, crie e edite objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-195">RTCUniversalServerAdmins <em>e</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="6cbcd-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="6cbcd-196">Para executar o ocsumutil. exe com êxito, o usuário deve pertencer a esses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="6cbcd-197">Para criar objetos de contato, o usuário que executa o ocsumutil. exe deve ter a permissão correta para a UO (unidade organizacional) do Active Directory, onde os novos objetos de contato estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="6cbcd-198">Essa permissão pode ser concedida executando-se o cmdlet <STRONG>Grant-CsOUPermission</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="6cbcd-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="6cbcd-199">Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="6cbcd-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurar o Lync Server 2013 para trabalhar com a Unificação de mensagens no Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="6cbcd-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cbcd-201">Se necessário, execute outras etapas de configuração do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-202">Se você ainda não tiver configurado as configurações do Enterprise Voice em seus servidores ou usuários, siga um ou mais destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6cbcd-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6cbcd-203">Implantar e configurar</span><span class="sxs-lookup"><span data-stu-id="6cbcd-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="6cbcd-204">Gateways PSTN (rede telefônica pública comutada) e servidores de mediação</span><span class="sxs-lookup"><span data-stu-id="6cbcd-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-205">Definir políticas de voz, registros de uso de PSTN e rotas de chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-206">Habilitar usuários para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="6cbcd-207">Opcionalmente, configure usuários específicos com planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="6cbcd-208">Outras etapas de configuração podem ser necessárias dependendo dos recursos do Enterprise Voice que você habilitar.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cbcd-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cbcd-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="6cbcd-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-211">Confira os tópicos nas seções a seguir:</span><span class="sxs-lookup"><span data-stu-id="6cbcd-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="6cbcd-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurando políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cbcd-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="6cbcd-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Implantando o Enterprise Voice no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cbcd-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cbcd-214">Habilitar usuários do Enterprise Voice para o UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-215">No servidor UM do Exchange, certifique-se de que uma política de caixa de correio de Unificação de mensagens tenha sido criada e que cada usuário tenha uma atribuição de número de ramal exclusivo e habilite o usuário para a Unificação de mensagens.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-216">Administrador de destinatários do Exchange</span><span class="sxs-lookup"><span data-stu-id="6cbcd-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="6cbcd-217">Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte Como habilitar um usuário para Unificação de mensagens&quot; em. <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a></span><span class="sxs-lookup"><span data-stu-id="6cbcd-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="6cbcd-218">Para o Exchange 2010 ou Service Pack mais recente &quot;, consulte Habilitar um usuário para&quot; Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="6cbcd-219">Para o Exchange 2013, consulte Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="6cbcd-219">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

