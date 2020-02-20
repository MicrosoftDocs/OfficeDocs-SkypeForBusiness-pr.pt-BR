---
title: 'Lync Server 2013: configuração de Federação do Lync'
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
ms.openlocfilehash: ce06c67e3c7e90f8e1170edb82e515f66be7a2ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="7ca03-102">Configurando a Federação do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ca03-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ca03-103">_**Última modificação do tópico:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="7ca03-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="7ca03-104">Se o servidor de borda já foi implantado nos servidores, a adição dos recursos de cenários federados é o próximo passo.</span><span class="sxs-lookup"><span data-stu-id="7ca03-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="7ca03-105">Se os servidores de borda ainda não foram definidos, faça isso primeiro.</span><span class="sxs-lookup"><span data-stu-id="7ca03-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="7ca03-106">Para obter detalhes, consulte: [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento e [implantação de acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="7ca03-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ca03-p102">Se você pretende instalar uma combinação de federação XMPP, federação do Lync ou uma conectividade pública de mensagens instantâneas, é possível implantá-las simultaneamente ou uma de cada vez. Se configurar as opções com o Construtor de Topologias e o shell de gerenciamento do Lync Server e executar o Assistente de implantação no servidor de borda depois de configurar as opções para um, dois ou todos os três tipos de federação, será possível reduzir o número de etapas necessárias.</span><span class="sxs-lookup"><span data-stu-id="7ca03-p102">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time. If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="7ca03-109">Instalando a federação do Lync no Construtor de Topologias e o Assistente de implantação</span><span class="sxs-lookup"><span data-stu-id="7ca03-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="7ca03-p103">Em um servidor front-end, abra o Construtor de Topologias. Expanda os pools de borda e clique com o botão direito do mouse no servidor de borda ou pool de servidores de borda. Selecione Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="7ca03-p103">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="7ca03-p104">Em Editar Propriedades, sob Geral, selecione Habilitar Federação para este pool de borda (Porta 5061). Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7ca03-p104">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="7ca03-p105">Clique em Ação, selecione Topologia, selecione Publicar. Quando a mensagem sobre Publicar a topologia surgir, clique em Próxima. Quando Publicar for concluído, clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="7ca03-p105">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="7ca03-p106">No servidor de borda, abra o Assistente de Implantação do Lync Server. Clique em Instalar ou Atualizar Sistema do Lync Server; em seguida, clique em Instalação ou Remover Componentes do Lync Server. Clique em Executar Novamente.</span><span class="sxs-lookup"><span data-stu-id="7ca03-p106">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="7ca03-p107">Em Instalar Componentes do Lync Server, clique em Avançar. A tela de resumo mostrará as ações conforme forem executadas. Depois que a implantação estiver concluída, clique em Exibir Log para exibir os arquivos de log disponíveis. Clique em Concluir para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="7ca03-p107">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7ca03-p108">É possível selecionar esta opção, mas apenas um pool de borda ou servidor de borda de sua organização pode ser publicado externamente para federação. Todo o acesso de usuários federados, inclusive usuários públicos de IM (mensagens instantâneas), atravessa o mesmo pool de borda ou servidor de borda único. Por exemplo, se sua implantação contém um pool de borda ou servidor de borda único implantado em Nova Iorque e outro implantado um Londres e você habilita o suporte à federação no pool de borda ou servidor de borda único de Nova Iorque, o tráfego do sinal para os usuários federados atravessará o pool de borda ou servidor de borda único de Nova Iorque. Isso é verdadeiro até mesmo para comunicações com os usuários de Londres, embora um usuário interno de Londres que liga para um usuário federado do Nova Iorque use um pool ou servidor de borda de Londres para o tráfego de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="7ca03-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="7ca03-129">Configurando a federação com parceiros</span><span class="sxs-lookup"><span data-stu-id="7ca03-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="7ca03-130">Para configurar uma federação bem-sucedida com outro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 ou Office Communicator 2007, selecione o tipo de Federação da tabela a seguir e defina Registros SRV DNS, host DNS (A ou AAAA para IPv6) e configurar políticas aplicáveis ao tipo de Federação:</span><span class="sxs-lookup"><span data-stu-id="7ca03-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="7ca03-131">Tipo de federação</span><span class="sxs-lookup"><span data-stu-id="7ca03-131">Federation type</span></span></th>
    <th><span data-ttu-id="7ca03-132">Registros DNS</span><span class="sxs-lookup"><span data-stu-id="7ca03-132">DNS Records</span></span></th>
    <th><span data-ttu-id="7ca03-133">Definição de política</span><span class="sxs-lookup"><span data-stu-id="7ca03-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="7ca03-134">Observações</span><span class="sxs-lookup"><span data-stu-id="7ca03-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="7ca03-135">Domínio do parceiro descoberto</span><span class="sxs-lookup"><span data-stu-id="7ca03-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="7ca03-136">Configure o registro SRV do formato _sipfederationtls. _tcp. &lt;nome&gt;de domínio externo onde o valor de porta para o registro SRV é TCP 5061 e o <strong>host que oferece esse serviço</strong> é definido como SIP.</span><span class="sxs-lookup"><span data-stu-id="7ca03-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="7ca03-137">&lt;nome&gt; do domínio externo – o FQDN do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="7ca03-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="7ca03-138">Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte à borda no Lync Server 2013</a> para obter detalhes sobre como criar o registro SRV</span><span class="sxs-lookup"><span data-stu-id="7ca03-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7ca03-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7ca03-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7ca03-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7ca03-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7ca03-p110">As versões anteriores se referiam a esse tipo de federação como <strong>Federação avançada aberta</strong>. A criação do registro SRV é obrigatória para esse tipo de federação e serve para permitir que outros parceiros descubram sua federação.</span><span class="sxs-lookup"><span data-stu-id="7ca03-p110">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>. The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7ca03-143">Domínio de parceiro permitido</span><span class="sxs-lookup"><span data-stu-id="7ca03-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="7ca03-144">Configure o registro SRV do formato _sipfederationtls. _tcp. &lt;nome&gt;de domínio externo onde o valor de porta para o registro SRV é TCP 5061 e o <strong>host que oferece esse serviço</strong> é definido como SIP.</span><span class="sxs-lookup"><span data-stu-id="7ca03-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="7ca03-145">&lt;nome&gt; do domínio externo – o FQDN do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="7ca03-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="7ca03-146">Consulte <a href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte à borda no Lync Server 2013</a> para obter detalhes sobre como criar o registro SRV</span><span class="sxs-lookup"><span data-stu-id="7ca03-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7ca03-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7ca03-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7ca03-148">Versões anteriores mencionadas nesse tipo de Federação como <strong>Federação aprimorada</strong>.</span><span class="sxs-lookup"><span data-stu-id="7ca03-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="7ca03-149">A criação do registro SRV é opcional para esse tipo de federação e serve para permitir que outros parceiros descubram sua federação.</span><span class="sxs-lookup"><span data-stu-id="7ca03-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="7ca03-150">Isso é obviamente uma <strong>Federação avançada aberta</strong> ou um <strong>Domínio de parceiro descoberto</strong></span><span class="sxs-lookup"><span data-stu-id="7ca03-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7ca03-151">Servidor de parceiro permitido</span><span class="sxs-lookup"><span data-stu-id="7ca03-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="7ca03-152">Configurar o nome de domínio SIP e o FQDN do servidor de borda de parceiro como um parceiro de Federação em políticas</span><span class="sxs-lookup"><span data-stu-id="7ca03-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7ca03-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7ca03-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7ca03-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurar suporte para domínios externos permitidos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7ca03-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7ca03-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurar suporte para domínios externos bloqueados no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7ca03-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7ca03-p113">Esse tipo de federação é a definição de uma relação um-para-um e não permite a descoberta de outros parceiros de federação. Cada parceiro de federação é configurado explicitamente. Nas versões anteriores, isso era conhecido como <strong>Federação direta</strong></span><span class="sxs-lookup"><span data-stu-id="7ca03-p113">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners. Each federation partner is configured explicitly. In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7ca03-159">Hospedando provedor e provedor de IM público</span><span class="sxs-lookup"><span data-stu-id="7ca03-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="7ca03-160">Nenhum requisito específico de DNS é definido para esse tipo de federação</span><span class="sxs-lookup"><span data-stu-id="7ca03-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7ca03-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7ca03-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7ca03-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Criar ou editar provedores federados SIP públicos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7ca03-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7ca03-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Criar ou editar provedores federados SIP hospedados Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7ca03-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7ca03-164">Esse tipo de federação define os provedores de serviços e hospedagem que você deseja configurar para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="7ca03-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="7ca03-165">Os usos mais comuns incluem a configuração de provedores de IM públicos como Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7ca03-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="7ca03-166">e AOL, bem como provedores de hospedagem como o Lync Online e o Office 365</span><span class="sxs-lookup"><span data-stu-id="7ca03-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="7ca03-167">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="7ca03-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="7ca03-168">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7ca03-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="7ca03-169">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="7ca03-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="7ca03-170">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7ca03-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="7ca03-171">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="7ca03-171">has been announced.</span></span> <span data-ttu-id="7ca03-172">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7ca03-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7ca03-173">O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7ca03-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="7ca03-174">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="7ca03-174">Messenger.</span></span> <span data-ttu-id="7ca03-175">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</span><span class="sxs-lookup"><span data-stu-id="7ca03-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7ca03-176">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="7ca03-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="7ca03-177">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="7ca03-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="7ca03-178">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="7ca03-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="7ca03-179">Defina e configure todos os hosts DNS exigidos (A ou AAAA para IPv6) e registros SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="7ca03-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="7ca03-180">Defina e configure qualquer política usando o painel de controle do Lync Server ou usando o Shell de gerenciamento do Lync Server e os cmdlets apropriados.</span><span class="sxs-lookup"><span data-stu-id="7ca03-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="7ca03-181">Para obter detalhes sobre os cmdlets do Shell de gerenciamento do Lync Server, confira [cmdlets de Federação e acesso externo no Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="7ca03-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ca03-182">O Lync Room System (LRS) não mostra o botão ingressar para reuniões enviadas por organizadores em parceiros federados do Lync.</span><span class="sxs-lookup"><span data-stu-id="7ca03-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="7ca03-183">Para que um link de ingresso na reunião apareça no LRS, a organização de envio deve habilitar o TNEF usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7ca03-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="7ca03-184">Observe que isso não é LRS específico.</span><span class="sxs-lookup"><span data-stu-id="7ca03-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="7ca03-185">O Outlook e o Lync também não mostraram links de ingresso nesse caso, pois as propriedades MAPI não são transportadas, mas no caso do Outlook, o usuário pode abrir o convite da reunião e clicar na URL da reunião.</span><span class="sxs-lookup"><span data-stu-id="7ca03-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="7ca03-186">Quando TNEFEnabled é definido como true, o Exchange 2013 não distribui propriedades MAPI, incluindo OnlineMeetingExternalLink e o botão de associação será mostrado no lembrete.</span><span class="sxs-lookup"><span data-stu-id="7ca03-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ca03-187">Confira também</span><span class="sxs-lookup"><span data-stu-id="7ca03-187">See Also</span></span>


[<span data-ttu-id="7ca03-188">Planejamento para SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ca03-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="7ca03-189">Gerenciamento de Federação e acesso externo ao Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ca03-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

