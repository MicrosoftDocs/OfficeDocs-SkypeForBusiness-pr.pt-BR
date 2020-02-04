---
title: 'Lync Server 2013: Configuração de federação do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7df0dd85bac0aa3053fb6a3496d6a13fa1f4a85e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="5f292-102">Configuração de federação do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f292-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f292-103">_**Tópico da última modificação:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="5f292-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="5f292-104">Se você já tiver implantado o servidor de borda ou servidores de borda, adicionar os recursos de cenários agrupados será encaminhado diretamente.</span><span class="sxs-lookup"><span data-stu-id="5f292-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="5f292-105">Se você não configurou os servidores de borda, deve primeiro fazer isso.</span><span class="sxs-lookup"><span data-stu-id="5f292-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="5f292-106">Para obter detalhes, consulte: [planejando o acesso de usuários externos no Lync server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento e [implantando o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="5f292-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f292-107">Se você pretende configurar qualquer combinação de agrupamento XMPP, Federação do Lync ou conectividade de mensagens instantâneas públicas, poderá implantá-los simultaneamente ou um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="5f292-107">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time.</span></span> <span data-ttu-id="5f292-108">Se você configurar as opções por meio do construtor de topologias e do Shell de gerenciamento do Lync Server, execute o assistente de implantação no servidor de borda após configurar as opções para um, dois ou todos os três tipos de Federação, você pode reduzir o número de etapas necessárias.</span><span class="sxs-lookup"><span data-stu-id="5f292-108">If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="5f292-109">Configurar a Federação do Lync no construtor de topologias e no assistente de implantação</span><span class="sxs-lookup"><span data-stu-id="5f292-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="5f292-110">Em um servidor front-end, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="5f292-110">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="5f292-111">Expanda Pools de bordas e clique com o botão direito do mouse no seu servidor de borda ou no pool do servidor</span><span class="sxs-lookup"><span data-stu-id="5f292-111">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="5f292-112">Selecione Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="5f292-112">Select Edit properties.</span></span>

2.  <span data-ttu-id="5f292-113">Em Editar propriedades em geral, selecione Habilitar Federação para este pool de bordas (porta 5061).</span><span class="sxs-lookup"><span data-stu-id="5f292-113">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="5f292-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5f292-114">Click OK.</span></span>

3.  <span data-ttu-id="5f292-115">Clique em ação, selecione topologia, selecione publicar.</span><span class="sxs-lookup"><span data-stu-id="5f292-115">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="5f292-116">Quando solicitado em publicar a topologia, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="5f292-116">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="5f292-117">Quando a publicação estiver concluída, clique em concluir.</span><span class="sxs-lookup"><span data-stu-id="5f292-117">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="5f292-118">No servidor de borda, abra o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f292-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="5f292-119">Clique em instalar ou atualizar o Lync Server System e, em seguida, clique em configurar ou remover componentes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f292-119">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="5f292-120">Clique em executar novamente.</span><span class="sxs-lookup"><span data-stu-id="5f292-120">Click Run Again.</span></span>

5.  <span data-ttu-id="5f292-121">Em configurar componentes do Lync Server, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="5f292-121">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="5f292-122">A tela Resumo mostrará as ações conforme elas são executadas.</span><span class="sxs-lookup"><span data-stu-id="5f292-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="5f292-123">Depois que a implantação for concluída, clique em Exibir log para exibir os arquivos de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5f292-123">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="5f292-124">Clique em concluir para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="5f292-124">Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5f292-125">Você pode selecionar essa opção, mas somente um pool de bordas ou um servidor de borda em sua organização pode ser publicado externamente para Federação.</span><span class="sxs-lookup"><span data-stu-id="5f292-125">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="5f292-126">Todo o acesso de usuários federados, incluindo usuários públicos de mensagens instantâneas (IM), passam pelo mesmo pool de bordas ou servidor de borda única.</span><span class="sxs-lookup"><span data-stu-id="5f292-126">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="5f292-127">Por exemplo, se sua implantação inclui um pool de bordas ou um servidor de borda única implantado em Nova York e um implantado em Londres e você habilitar o suporte de Federação no pool de bordas de Nova York ou no servidor de borda único, o tráfego de sinal para usuários federados passará pela Nova York Pool de bordas ou servidor de borda único.</span><span class="sxs-lookup"><span data-stu-id="5f292-127">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="5f292-128">Isso se aplica inclusive para comunicações com usuários de Londres, embora um usuário interno de Londres chamando um usuário federado de Londres use o pool de Londres ou Servidor de Borda para tráfego de A/V.</span><span class="sxs-lookup"><span data-stu-id="5f292-128">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="5f292-129">Configurando a Federação com parceiros</span><span class="sxs-lookup"><span data-stu-id="5f292-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="5f292-130">Para configurar uma reunião bem-sucedida com outro Microsoft Lync Server 2013, o Lync Server 2010, o Office Communications Server 2007 R2 ou o Office Communicator 2007, selecione o tipo de Federação na tabela a seguir e defina Registros SRV DNS, host DNS (A ou AAAA para IPv6) e configurar políticas aplicáveis ao tipo de Federação:</span><span class="sxs-lookup"><span data-stu-id="5f292-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5f292-131">Tipo de Federação</span><span class="sxs-lookup"><span data-stu-id="5f292-131">Federation type</span></span></th>
    <th><span data-ttu-id="5f292-132">Registros de DNS</span><span class="sxs-lookup"><span data-stu-id="5f292-132">DNS Records</span></span></th>
    <th><span data-ttu-id="5f292-133">Definição da política</span><span class="sxs-lookup"><span data-stu-id="5f292-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="5f292-134">Observações</span><span class="sxs-lookup"><span data-stu-id="5f292-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5f292-135">Domínio de parceiro descoberto</span><span class="sxs-lookup"><span data-stu-id="5f292-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="5f292-136">Configure o registro SRV do formato _sipfederationtls. _tcp. &lt;nome&gt;de domínio externo em que o valor de porta do registro SRV é TCP 5061 e o <strong>host que oferece esse serviço</strong> é definido como SIP.</span><span class="sxs-lookup"><span data-stu-id="5f292-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="5f292-137">&lt;nome&gt; do domínio externo – o FQDN do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="5f292-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="5f292-138">Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</a> para obter detalhes sobre como criar o registro SRV</span><span class="sxs-lookup"><span data-stu-id="5f292-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="5f292-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f292-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="5f292-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar ou desabilitar descoberta de parceiros de federação no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f292-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="5f292-141">Versões anteriores referenciadas a esse tipo de Federação como <strong>Federação aprimorada aberta</strong>.</span><span class="sxs-lookup"><span data-stu-id="5f292-141">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>.</span></span> <span data-ttu-id="5f292-142">A criação do registro SRV é necessária para esse tipo de Federação e é permitir que outros parceiros descubram sua Federação.</span><span class="sxs-lookup"><span data-stu-id="5f292-142">The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5f292-143">Domínio de parceiro permitido</span><span class="sxs-lookup"><span data-stu-id="5f292-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="5f292-144">Configure o registro SRV do formato _sipfederationtls. _tcp. &lt;nome&gt;de domínio externo em que o valor de porta do registro SRV é TCP 5061 e o <strong>host que oferece esse serviço</strong> é definido como SIP.</span><span class="sxs-lookup"><span data-stu-id="5f292-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="5f292-145">&lt;nome&gt; do domínio externo – o FQDN do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="5f292-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="5f292-146">Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</a> para obter detalhes sobre como criar o registro SRV</span><span class="sxs-lookup"><span data-stu-id="5f292-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="5f292-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f292-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="5f292-148">Versões anteriores referenciadas a esse tipo de Federação como <strong>Federação aprimorada</strong>.</span><span class="sxs-lookup"><span data-stu-id="5f292-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="5f292-149">A criação do registro SRV é opcional para esse tipo de Federação e é permitir que outros parceiros descubram sua Federação.</span><span class="sxs-lookup"><span data-stu-id="5f292-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="5f292-150">É claro que, em seguida, é uma <strong>Federação aprimorada aberta</strong>ou um <strong>domínio de parceiro descoberto</strong></span><span class="sxs-lookup"><span data-stu-id="5f292-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5f292-151">Servidor parceiro permitido</span><span class="sxs-lookup"><span data-stu-id="5f292-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="5f292-152">Configurar o nome de domínio SIP e o FQDN do servidor de borda de parceiro como um parceiro de Federação em políticas</span><span class="sxs-lookup"><span data-stu-id="5f292-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="5f292-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f292-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="5f292-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurar suprote para domínios externos permitidos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f292-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="5f292-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurar suporte para domínios externos bloqueados no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f292-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="5f292-156">Esse tipo de Federação é a definição de uma relação de um para um e não permite a descoberta de outros parceiros de Federação.</span><span class="sxs-lookup"><span data-stu-id="5f292-156">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners.</span></span> <span data-ttu-id="5f292-157">Cada parceiro de Federação é configurado explicitamente.</span><span class="sxs-lookup"><span data-stu-id="5f292-157">Each federation partner is configured explicitly.</span></span> <span data-ttu-id="5f292-158">Em versões anteriores, isso era conhecido como <strong>Federação direta</strong></span><span class="sxs-lookup"><span data-stu-id="5f292-158">In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5f292-159">Provedor de hospedagem e provedor de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="5f292-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="5f292-160">Nenhum requisito de DNS específico é definido para esse tipo de Federação</span><span class="sxs-lookup"><span data-stu-id="5f292-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="5f292-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f292-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="5f292-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Criar ou editar fornecedores SIP públicos federados no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f292-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="5f292-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Criar ou editar provedores hospedados federados SIP no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f292-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="5f292-164">Esse tipo de Federação define serviços e provedores de hospedagem que você deseja configurar para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="5f292-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="5f292-165">Os usos típicos incluem a configuração de provedores de IM públicos, como o Windows Live Messenger, o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5f292-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="5f292-166">e AOL, bem como provedores de hospedagem como o Lync Online e o Office 365</span><span class="sxs-lookup"><span data-stu-id="5f292-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="5f292-167">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="5f292-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="5f292-168">Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5f292-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="5f292-169">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="5f292-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="5f292-170">Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5f292-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="5f292-171">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="5f292-171">has been announced.</span></span> <span data-ttu-id="5f292-172">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5f292-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="5f292-173">O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5f292-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="5f292-174">Spam.</span><span class="sxs-lookup"><span data-stu-id="5f292-174">Messenger.</span></span> <span data-ttu-id="5f292-175">A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</span><span class="sxs-lookup"><span data-stu-id="5f292-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="5f292-176">Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo.</span><span class="sxs-lookup"><span data-stu-id="5f292-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5f292-177">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="5f292-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="5f292-178">A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</span><span class="sxs-lookup"><span data-stu-id="5f292-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="5f292-179">Definir e configurar qualquer host DNS obrigatório (A ou AAAA para IPv6) e Registros SRV DNS</span><span class="sxs-lookup"><span data-stu-id="5f292-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="5f292-180">Defina e configure qualquer política usando o painel de controle do Lync Server ou usando o Shell de gerenciamento do Lync Server e os cmdlets apropriados.</span><span class="sxs-lookup"><span data-stu-id="5f292-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="5f292-181">Para obter detalhes sobre os cmdlets do Shell de gerenciamento do Lync Server, consulte [cmdlets de acesso externo e Federação no Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="5f292-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5f292-182">O LRS (Lync Room System) não mostra o botão ingressar para reuniões enviadas por organizadores em parceiros federados do Lync.</span><span class="sxs-lookup"><span data-stu-id="5f292-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="5f292-183">Para que um link de ingresso na reunião apareça no LRS, a organização de envio deve habilitar o TNEF usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5f292-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="5f292-184">Observe que isso não é LRS específico.</span><span class="sxs-lookup"><span data-stu-id="5f292-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="5f292-185">O Outlook e o Lync também não mostraram links de junção nesse caso, pois as propriedades MAPI não são transportadas, mas na caixa do Outlook, o usuário pode abrir o convite da reunião e clicar na URL da reunião.</span><span class="sxs-lookup"><span data-stu-id="5f292-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="5f292-186">Quando TNEFEnabled está definido como true, o Exchange 2013 não distribui propriedades MAPI, incluindo OnlineMeetingExternalLink, e o botão de junção é mostrado no lembrete.</span><span class="sxs-lookup"><span data-stu-id="5f292-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f292-187">Confira também</span><span class="sxs-lookup"><span data-stu-id="5f292-187">See Also</span></span>


[<span data-ttu-id="5f292-188">Planejando o SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f292-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="5f292-189">Gerenciamento de Federação e acesso externo ao Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f292-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

