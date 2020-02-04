---
title: 'Lync Server 2013: definir sua topologia de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a04dca4b935caf8f07546babd2c53f65fff4e89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="c1174-102">Definir sua topologia de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1174-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1174-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c1174-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c1174-104">Você deve usar o construtor de topologias para criar sua topologia e deve configurar pelo menos um pool de front-end interno ou um servidor Standard Edition para poder implantar o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="c1174-105">Use o procedimento a seguir para definir a topologia de borda para um único servidor de borda e, em seguida, use os procedimentos em [publicar sua topologia no Lync server 2013](lync-server-2013-publish-your-topology.md) e [exportar sua topologia do Lync Server 2013 e copiá-la para a mídia externa para a instalação do Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) para publicar a topologia e disponibilizá-la para o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c1174-106">As interfaces de Borda interna e externa precisam usar o mesmo tipo de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="c1174-106">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="c1174-107">Não é possível usar balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de Borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-107">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="c1174-108">Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio.</span><span class="sxs-lookup"><span data-stu-id="c1174-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="c1174-109">Você também pode conceder direitos e permissões de administrador necessários para adicionar funções de servidor a uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="c1174-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="c1174-110">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="c1174-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="c1174-111">Para outras alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é necessária.</span><span class="sxs-lookup"><span data-stu-id="c1174-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="c1174-112">Se você definiu a topologia de borda quando definiu e publicou sua topologia interna, e nenhuma alteração é necessária para a topologia de borda que você definiu anteriormente, você não precisa defini-la e publicá-la novamente.</span><span class="sxs-lookup"><span data-stu-id="c1174-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="c1174-113">Use o procedimento a seguir somente se precisar fazer alterações na sua topologia de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="c1174-114">Você deve disponibilizar a topologia previamente definida e publicada para seus servidores de borda, usando o procedimento em [exportar sua topologia do Lync Server 2013 e copiá-la para a mídia externa para instalação do Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="c1174-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c1174-115">Não é possível executar o construtor de topologias a partir de um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="c1174-116">Você deve executá-lo a partir de seu servidor front-end ou servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c1174-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="c1174-117">O processo para definir a topologia do servidor de borda é feito no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="c1174-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="c1174-118">Os três tipos principais de topologias de servidor de borda que você planeja e configura estão listados abaixo:</span><span class="sxs-lookup"><span data-stu-id="c1174-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="c1174-119">Para definir a topologia para um servidor de borda único</span><span class="sxs-lookup"><span data-stu-id="c1174-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="c1174-120">Para definir a topologia de um pool de servidores de borda com balanceamento de carga</span><span class="sxs-lookup"><span data-stu-id="c1174-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="c1174-121">Para definir a topologia de um pool de bordas com carga balanceada de hardware</span><span class="sxs-lookup"><span data-stu-id="c1174-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="c1174-122">Para definir a topologia para um servidor de borda único</span><span class="sxs-lookup"><span data-stu-id="c1174-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="c1174-123">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c1174-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c1174-124">Na árvore de console, expanda o site no qual você deseja implantar um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="c1174-125">Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.</span><span class="sxs-lookup"><span data-stu-id="c1174-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="c1174-126">Em **definir o novo pool de bordas**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="c1174-127">Em **definir o FQDN do pool de bordas**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-128">Em **pool FQDN**, digite o nome de domínio totalmente qualificado (FQDN) da interface interna do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="c1174-129">O nome que você especificar dever ser idêntico ao nome de computador configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="c1174-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="c1174-130">Por padrão, o nome do computador de um computador que não está associado a um domínio é um nome curto, e não um FQDN.</span><span class="sxs-lookup"><span data-stu-id="c1174-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="c1174-131">O Construtor de Topologias usa FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="c1174-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="c1174-132">Portanto, você deverá configurar um sufixo DNS no nome do computador a ser implantado no Servidor de Borda que não ingressou no domínio.</span><span class="sxs-lookup"><span data-stu-id="c1174-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="c1174-133">Use apenas caracteres padrão (incluindo A–Z, a–z, 0–9 e hifens) ao atribuir FQDNs de seus Lync Servers, Servidores de Borda e pools.</span><span class="sxs-lookup"><span data-stu-id="c1174-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="c1174-134">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="c1174-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="c1174-135">Os caracteres não padrão em um FQDN geralmente não são compatíveis com o DNS externo e CAs públicas (quando o FQDN deve ser atribuído ao SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="c1174-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="c1174-136">Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c1174-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="c1174-137">Clique em **pool de computador único**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="c1174-138">Em **selecionar recursos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-139">Se você pretende usar um único FQDN e um único endereço IP para o serviço de acesso SIP, serviço de Webconferência do Lync Server 2013 e os/V Edge Services, marque a caixa de seleção **usar um único FQDN e endereço IP** .</span><span class="sxs-lookup"><span data-stu-id="c1174-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="c1174-140">Se você planeja habilitar a Federação, marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** .</span><span class="sxs-lookup"><span data-stu-id="c1174-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1174-141">Você pode selecionar essa opção, mas somente um pool de bordas ou um servidor de borda em sua organização pode ser publicado externamente para Federação.</span><span class="sxs-lookup"><span data-stu-id="c1174-141">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="c1174-142">Todo o acesso de usuários federados, incluindo usuários públicos de mensagens instantâneas (IM), passam pelo mesmo pool de bordas ou servidor de borda única.</span><span class="sxs-lookup"><span data-stu-id="c1174-142">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="c1174-143">Por exemplo, se sua implantação inclui um pool de bordas ou um servidor de borda única implantado em Nova York e um implantado em Londres e você habilitar o suporte de Federação no pool de bordas de Nova York ou no servidor de borda único, o tráfego de sinal para usuários federados passará pela Nova York Pool de bordas ou servidor de borda único.</span><span class="sxs-lookup"><span data-stu-id="c1174-143">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="c1174-144">Isso se aplica inclusive para comunicações com usuários de Londres, embora um usuário interno de Londres chamando um usuário federado de Londres use o pool de Londres ou Servidor de Borda para tráfego de A/V.</span><span class="sxs-lookup"><span data-stu-id="c1174-144">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="c1174-145">Se você planeja dar suporte ao protocolo de mensagens extensíveis e presença (XMPP) para a sua implantação, marque a caixa de seleção **habilitar Federação de XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="c1174-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="c1174-146">Em **selecionar opções de IP**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-147">**Habilitar IPv4 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="c1174-148">**Habilitar o IPv6 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="c1174-149">**Habilitar IPv4 na interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="c1174-150">**Habilitar o IPv6 em uma interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="c1174-151">Você também pode configurar o servidor de borda ou o pool de bordas para usar um endereço de conversão de endereços de rede para os endereços IP externos.</span><span class="sxs-lookup"><span data-stu-id="c1174-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="c1174-152">Para fazer isso, marque a caixa de seleção **o endereço IP externo deste pool de bordas é convertido pela NAT**.</span><span class="sxs-lookup"><span data-stu-id="c1174-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="c1174-153">Em **FQDNs externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-154">Se, em **Selecione os recursos** , você optar por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o FQDN externo no **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1174-155">Se você escolher essa opção, especifique um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de borda de acesso, 444 para serviço de borda de Webconferência e 443 para serviço de borda A/V).</span><span class="sxs-lookup"><span data-stu-id="c1174-155">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="c1174-156">Selecionar essa opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode usar o mesmo número de porta (por exemplo, 443) para todos os três serviços.</span><span class="sxs-lookup"><span data-stu-id="c1174-156">Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="c1174-157">Se, **em Selecione os recursos** , você não tiver optado por usar um único FQDN e endereço IP, digite os FQDNs externos para **acesso SIP**, **conferência na Web** e **vídeo de áudio**, mantendo as portas padrão.</span><span class="sxs-lookup"><span data-stu-id="c1174-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="c1174-158">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c1174-158">Click **Next**.</span></span>

10. <span data-ttu-id="c1174-159">Em **definir o endereço IP interno**, digite o endereço IP do seu servidor de borda em **endereço IPv4 interno** e **endereço IPv6 interno** como apropriado para seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="c1174-159">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements.</span></span> <span data-ttu-id="c1174-160">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c1174-160">Click **Next**.</span></span>

11. <span data-ttu-id="c1174-161">Em **definir o endereço IP externo**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-162">Se você optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e A/V Edge, digite o endereço IPv4 externo do servidor de borda no **acesso SIP**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="c1174-163">Se você optou por usar endereços IPv6, digite o endereço IPv6 externo do servidor de borda em **acesso SIP**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="c1174-164">Se você não optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite os endereços IPv4 externos do servidor de borda no **acesso SIP**, **conferência via Web**e **conferência a/v**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="c1174-165">Se você optou por usar endereços IPv6 e não optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite os endereços IPv6 externos do servidor de borda em **acesso SIP**, **conferência via Web**e **conferência a/v**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1174-166">Se você não optou por habilitar e atribuir endereçamento IPv6, esta caixa de diálogo não será exibida.</span><span class="sxs-lookup"><span data-stu-id="c1174-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="c1174-167">Se você optou por usar o NAT, será exibida uma caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c1174-167">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="c1174-168">Em **endereço IPv4 público para o serviço de borda a/V**, digite o endereço IPv4 público a ser traduzido por Nat e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-168">In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-169">Este deve ser o endereço IP externo do serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="c1174-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="c1174-170">Se você optou por usar o NAT e endereços IPv6, será exibida uma caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c1174-170">If you chose to use NAT and IPv6 addresses, a dialog box appears.</span></span> <span data-ttu-id="c1174-171">Em **endereço IPv6 público para o serviço de borda a/V**, digite o endereço IPv6 público a ser traduzido por Nat e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-171">In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-172">Este deve ser o endereço IP externo do serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="c1174-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="c1174-173">Em **definir o próximo salto**, no **próximo pool de saltos**, selecione o nome do pool interno, que pode ser um pool de front-ends ou um pool padrão de edição.</span><span class="sxs-lookup"><span data-stu-id="c1174-173">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="c1174-174">Ou, se a sua implantação incluir um director, selecione o diretor.</span><span class="sxs-lookup"><span data-stu-id="c1174-174">Or, if your deployment includes a Director, select the Director.</span></span> <span data-ttu-id="c1174-175">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-175">Then, click **Next**.</span></span>

15. <span data-ttu-id="c1174-176">Em **pools de front-end**, especifique um ou mais pools internos, que podem incluir pools front-ends e servidores Standard Edition, a serem associados a esse servidor de borda, selecionando os nomes dos pools internos que devem usar esse servidor de borda para comunicação com usuários externos com suporte.</span><span class="sxs-lookup"><span data-stu-id="c1174-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-177">Somente um pool de bordas com carga balanceada ou um servidor de borda única pode ser associado a cada pool interno para o tráfego A/V.</span><span class="sxs-lookup"><span data-stu-id="c1174-177">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="c1174-178">Se você já tiver um pool interno associado a um pool de bordas ou servidor de borda, um aviso será exibido indicando que o pool interno já está associado a um pool de bordas ou um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-178">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="c1174-179">Se você selecionar um pool que já esteja associado a outro servidor de borda, ele alterará a associação.</span><span class="sxs-lookup"><span data-stu-id="c1174-179">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="c1174-180">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c1174-180">Click **Finish**.</span></span>

17. <span data-ttu-id="c1174-181">Publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="c1174-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="c1174-182">Para definir a topologia de um pool de servidores de borda balanceada para carga de DNS</span><span class="sxs-lookup"><span data-stu-id="c1174-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="c1174-183">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c1174-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c1174-184">Na árvore de console, expanda o site no qual você deseja implantar servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="c1174-185">Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.</span><span class="sxs-lookup"><span data-stu-id="c1174-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="c1174-186">Em **definir o novo pool de bordas**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="c1174-187">Em **definir o FQDN do pool de bordas**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-188">Em **pool FQDN**, digite o nome de domínio totalmente qualificado (FQDN) para a conexão interna do pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="c1174-189">O nome que você especificar para o pool deve ser o nome do pool de bordas internas.</span><span class="sxs-lookup"><span data-stu-id="c1174-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="c1174-190">Isso deve ser definido como um FQDN.</span><span class="sxs-lookup"><span data-stu-id="c1174-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="c1174-191">O Construtor de Topologias usa FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="c1174-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="c1174-192">Use apenas caracteres padrão (incluindo A–Z, a–z, 0–9 e hifens) ao atribuir FQDNs de seus Lync Servers, Servidores de Borda e pools.</span><span class="sxs-lookup"><span data-stu-id="c1174-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="c1174-193">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="c1174-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="c1174-194">Os caracteres não padrão em um FQDN geralmente não são compatíveis com o DNS externo e CAs públicas (quando o FQDN deve ser atribuído ao SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="c1174-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="c1174-195">Clique em **vários pools de computador**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="c1174-196">Em **selecionar recursos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-197">Se você pretende usar um único FQDN e endereço IP para o acesso SIP, serviço de Webconferência do Lync Server 2013 e serviços de borda A/V, marque a caixa de seleção **usar um único FQDN e endereço IP** .</span><span class="sxs-lookup"><span data-stu-id="c1174-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="c1174-198">Se você planeja habilitar a Federação, marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** .</span><span class="sxs-lookup"><span data-stu-id="c1174-198">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span> <span data-ttu-id="c1174-199">Clique em **Avançar**</span><span class="sxs-lookup"><span data-stu-id="c1174-199">Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1174-200">Você pode selecionar essa opção, mas somente um pool de bordas ou um servidor de borda em sua organização pode ser publicado externamente para Federação.</span><span class="sxs-lookup"><span data-stu-id="c1174-200">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="c1174-201">Todo o acesso de usuários federados, incluindo usuários públicos de mensagens instantâneas (IM), passam pelo mesmo pool de bordas ou servidor de borda única.</span><span class="sxs-lookup"><span data-stu-id="c1174-201">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="c1174-202">Por exemplo, se sua implantação incluir um pool de Borda ou um único Servidor de Borda implantado em Nova York e outro implantado em Londres e você habilitar o suporte para federação no pool de Borda de Nova York ou único Servidor de Borda, o tráfego do sinal para usuários federados passará pelo pool de Borda ou único Servidor de Borda de Nova York.</span><span class="sxs-lookup"><span data-stu-id="c1174-202">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="c1174-203">Isso se aplica inclusive para comunicações com usuários de Londres, embora um usuário interno de Londres chamando um usuário federado de Londres use o pool de Londres ou Servidor de Borda para tráfego de A/V.</span><span class="sxs-lookup"><span data-stu-id="c1174-203">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="c1174-204">Se você planeja dar suporte ao protocolo de mensagens extensíveis e presença (XMPP) para a sua implantação, marque a caixa de seleção **habilitar Federação de XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="c1174-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="c1174-205">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c1174-205">Click **Next**.</span></span>

8.  <span data-ttu-id="c1174-206">Em **selecionar opções de IP**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-207">**Habilitar IPv4 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="c1174-208">**Habilitar o IPv6 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="c1174-209">**Habilitar IPv4 na interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="c1174-210">**Habilitar o IPv6 em uma interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="c1174-211">Você também pode configurar o servidor de borda ou o pool de bordas para usar um endereço de conversão de endereços de rede para os endereços IP externos.</span><span class="sxs-lookup"><span data-stu-id="c1174-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="c1174-212">Para fazer isso, marque a caixa de seleção **o endereço IP externo deste pool de bordas é convertido pela NAT**.</span><span class="sxs-lookup"><span data-stu-id="c1174-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="c1174-213">Em **FQDNs externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-214">Se, em **Selecione os recursos** , você optar por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o FQDN externo no **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1174-215">Se você escolher essa opção, especifique um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de borda de acesso, 444 para serviço de borda de Webconferência e 443 para serviço de borda A/V).</span><span class="sxs-lookup"><span data-stu-id="c1174-215">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="c1174-216">Ao selecionar essa opção, você pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque pode usar o mesmo número de porta (por exemplo, 443) para todos os três serviços.</span><span class="sxs-lookup"><span data-stu-id="c1174-216">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="c1174-217">Se, em **Selecione os recursos** , você não tiver optado por usar um único FQDN e endereço IP, digite o FQDN escolhido para seu lado público do pool de bordas no **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-217">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="c1174-218">Em **Webconferência**, digite o FQDN escolhido para o seu lado público do lado do pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-218">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="c1174-219">Em **áudio/vídeo**, digite o FQDN escolhido para seu lado público do lado do pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-219">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="c1174-220">Use as portas padrão.</span><span class="sxs-lookup"><span data-stu-id="c1174-220">Use the default ports.</span></span>

10. <span data-ttu-id="c1174-221">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c1174-221">Click **Next**.</span></span>

11. <span data-ttu-id="c1174-222">Em **definir os computadores neste pool**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="c1174-223">Em **endereço IP e FQDN internos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-224">Em **endereço IPv4 interno**, digite o endereço IPv4 e o **endereço IPv6 interno** como apropriado para seus requisitos para o primeiro servidor de borda que você deseja criar nesse pool.</span><span class="sxs-lookup"><span data-stu-id="c1174-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="c1174-225">Em **FQDN interno**, digite o FQDN do primeiro servidor de borda que você deseja criar nesse pool.</span><span class="sxs-lookup"><span data-stu-id="c1174-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1174-226">O nome que você especificar dever ser idêntico ao nome de computador configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="c1174-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="c1174-227">Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN.</span><span class="sxs-lookup"><span data-stu-id="c1174-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="c1174-228">O Construtor de Topologias usa FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="c1174-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="c1174-229">Portanto, você deverá configurar um sufixo DNS no nome do computador a ser implantado no Servidor de Borda que não ingressou no domínio.</span><span class="sxs-lookup"><span data-stu-id="c1174-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="c1174-230">Use somente caracteres padrão (incluindo A – Z, A – z, 0 – 9 e hifens) ao atribuir FQDNs dos seus servidores, servidores de borda, pools e matrizes do Lync.</span><span class="sxs-lookup"><span data-stu-id="c1174-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="c1174-231">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="c1174-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="c1174-232">Os caracteres não padrão em um FQDN geralmente não são compatíveis com o DNS externo e CAs públicas (quando o FQDN deve ser atribuído ao SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="c1174-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="c1174-233">Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c1174-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="c1174-234">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c1174-234">Click **Next**.</span></span>

14. <span data-ttu-id="c1174-235">Em **definir os endereços IP externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-236">Se você optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o endereço IP externo do servidor de borda no **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="c1174-237">Se você não optou por usar um único FQDN e um único endereço IP para o serviço de acesso SIP, Web de Webconferência e o/V referencing, digite o endereço IP que você escolheu para o seu lado público deste servidor de pool de borda para **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-237">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="c1174-238">Em **Webconferência**, digite o endereço IP que você escolheu para o seu lado público deste servidor de pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-238">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="c1174-239">Em **conferência A/V**, digite o endereço IP escolhido para o seu lado público do lado público deste servidor de pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-239">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="c1174-240">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c1174-240">Click **Next**.</span></span>

16. <span data-ttu-id="c1174-241">Se você optou por habilitar endereços IPv6, em **definir os endereços IP externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-242">Se você optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o endereço IPv6 externo do servidor de borda no **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="c1174-243">Se você não optou por usar um único FQDN e um único endereço IP para o serviço de acesso SIP, Web de Webconferência e o/V referencing, digite o endereço IPv6 que você escolheu para o seu lado público deste servidor de pool de borda para **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-243">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="c1174-244">Em **Webconferência**, digite o endereço IPv6 que você escolheu para seu lado público do lado público deste servidor de pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-244">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="c1174-245">Em **conferência A/V**, digite o endereço IPv6 que você escolheu para seu lado público do lado público deste servidor de pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-245">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-246">Se você não optou por habilitar e atribuir endereçamento IPv6, esta caixa de diálogo não será exibida.</span><span class="sxs-lookup"><span data-stu-id="c1174-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="c1174-247">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c1174-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-248">Agora, você verá o primeiro servidor de borda que você criou no pool na caixa de diálogo <STRONG>definir os computadores neste pool</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c1174-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="c1174-249">Em **definir os computadores nesse pool**, clique em **Adicionar**e, em seguida, repita as etapas 11 a 14 para o segundo servidor de borda que você deseja adicionar ao seu pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="c1174-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="c1174-250">Após repetir as etapas 11 a 14, clique em **Avançar** em **definir os computadores nesse pool**.</span><span class="sxs-lookup"><span data-stu-id="c1174-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-251">Nesse ponto, você pode ver os dois servidores de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="c1174-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="c1174-252">Se você optou por usar o NAT, será exibida uma caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c1174-252">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="c1174-253">Em **endereço IP público**, digite os endereços IPv4 e IPv6 públicos (conforme apropriado) a serem convertidos por Nat e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-253">In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-254">Deve ser o endereço IP externo da borda A/V.</span><span class="sxs-lookup"><span data-stu-id="c1174-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="c1174-255">Em **definir o próximo salto**, na lista **próximo pool de saltos** , selecione o nome do pool interno, que pode ser um pool de front-ends ou um pool padrão de edição.</span><span class="sxs-lookup"><span data-stu-id="c1174-255">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="c1174-256">Ou, se a sua implantação incluir um director, selecione o nome do diretor.</span><span class="sxs-lookup"><span data-stu-id="c1174-256">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="c1174-257">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-257">Then, click **Next**.</span></span>

22. <span data-ttu-id="c1174-258">Em **pools de front-end**, especifique um ou mais pools internos, que podem incluir pools front-ends e servidores Standard Edition, a serem associados a esse servidor de borda, selecionando os nomes dos pools internos que serão usados neste servidor de borda para comunicação com usuários externos com suporte.</span><span class="sxs-lookup"><span data-stu-id="c1174-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-259">Somente um pool de bordas com carga balanceada ou um servidor de borda única pode ser associado a cada pool interno para o tráfego A/V.</span><span class="sxs-lookup"><span data-stu-id="c1174-259">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="c1174-260">Se você já tiver um pool interno associado a um pool de bordas ou servidor de borda, um aviso será exibido indicando que o pool interno já está associado a um pool de bordas ou um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-260">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="c1174-261">Se você selecionar um pool que já esteja associado a outro servidor de borda, ele alterará a associação.</span><span class="sxs-lookup"><span data-stu-id="c1174-261">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="c1174-262">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c1174-262">Click **Finish**.</span></span>

24. <span data-ttu-id="c1174-263">Publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="c1174-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="c1174-264">Para definir a topologia de um pool de servidores de borda com carga balanceada de hardware</span><span class="sxs-lookup"><span data-stu-id="c1174-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="c1174-265">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c1174-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c1174-266">Na árvore de console, expanda o site no qual você deseja implantar servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="c1174-267">Clique com o botão direito do mouse em **conjuntos de bordas**e selecione **novo pool de bordas**.</span><span class="sxs-lookup"><span data-stu-id="c1174-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="c1174-268">Em **definir o novo pool de bordas**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="c1174-269">Em **definir o FQDN do pool de bordas**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-270">Em **FQDN**, digite o nome de domínio totalmente qualificado (FQDN) escolhido para o lado interno do pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="c1174-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="c1174-271">O nome que você especificar para o pool deve ser o nome do pool de bordas internas.</span><span class="sxs-lookup"><span data-stu-id="c1174-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="c1174-272">Isso deve ser definido como um FQDN.</span><span class="sxs-lookup"><span data-stu-id="c1174-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="c1174-273">O Construtor de Topologias usa FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="c1174-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="c1174-274">Use apenas caracteres padrão (incluindo A–Z, a–z, 0–9 e hifens) ao atribuir FQDNs de seus Lync Servers, Servidores de Borda e pools.</span><span class="sxs-lookup"><span data-stu-id="c1174-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="c1174-275">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="c1174-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="c1174-276">Os caracteres não padrão em um FQDN geralmente não são compatíveis com o DNS externo e CAs públicas (quando o FQDN deve ser atribuído ao SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="c1174-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="c1174-277">Clique em **vários pool de computador**e, em seguida, em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="c1174-278">Em **selecionar recursos** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="c1174-279">Se você pretende usar um único FQDN e endereço IP para o serviço de acesso SIP, serviço de Webconferência do Lync Server e A/V Edge, marque a caixa de seleção **usar um único fqdn & endereço IP** .</span><span class="sxs-lookup"><span data-stu-id="c1174-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="c1174-280">Se você planeja habilitar a Federação, marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** .</span><span class="sxs-lookup"><span data-stu-id="c1174-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1174-281">Você pode selecionar essa opção, mas somente um pool de bordas ou um servidor de borda em sua organização pode ser publicado externamente para Federação.</span><span class="sxs-lookup"><span data-stu-id="c1174-281">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation.</span></span> <span data-ttu-id="c1174-282">Todo o acesso de usuários federados, incluindo usuários públicos de mensagens instantâneas (IM), passam pelo mesmo pool de bordas ou servidor de borda única.</span><span class="sxs-lookup"><span data-stu-id="c1174-282">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="c1174-283">Por exemplo, se sua implantação incluir um pool de Borda ou um único Servidor de Borda implantado em Nova York e outro implantado em Londres e você habilitar o suporte para federação no pool de Borda de Nova York ou único Servidor de Borda, o tráfego do sinal para usuários federados passará pelo pool de Borda ou único Servidor de Borda de Nova York.</span><span class="sxs-lookup"><span data-stu-id="c1174-283">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="c1174-284">Isso se aplica inclusive para comunicações com usuários de Londres, embora um usuário interno de Londres chamando um usuário federado de Londres use o pool de Londres ou Servidor de Borda para tráfego de A/V.</span><span class="sxs-lookup"><span data-stu-id="c1174-284">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="c1174-285">Se você planeja dar suporte ao protocolo de mensagens extensíveis e presença (XMPP) para a sua implantação, marque a caixa de seleção **habilitar Federação de XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="c1174-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="c1174-286">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c1174-286">Click **Next**.</span></span>

8.  <span data-ttu-id="c1174-287">Em **selecionar opções de IP**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-288">**Habilitar IPv4 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="c1174-289">**Habilitar o IPv6 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="c1174-290">**Habilitar IPv4 na interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="c1174-291">**Habilitar o IPv6 em uma interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="c1174-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c1174-292"><STRONG>Não</STRONG> marque a caixa de seleção <STRONG>o endereço IP externo do pool de bordas é traduzido pela NAT</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c1174-292"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box.</span></span> <span data-ttu-id="c1174-293">Não há suporte para a conversão de endereços de rede (NAT) quando você está usando o balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="c1174-293">Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="c1174-294">Em **FQDNs externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-295">Se, em **Selecione os recursos** , você optar por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o FQDN externo no **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1174-296">Se optar por selecionar essa opção, você deve especificar um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de borda de acesso, 444 para serviço de borda de Webconferência e 443 para serviço de borda A/V).</span><span class="sxs-lookup"><span data-stu-id="c1174-296">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="c1174-297">Ao selecionar essa opção, você pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque pode usar o mesmo número de porta (por exemplo, 443) para todos os três serviços.</span><span class="sxs-lookup"><span data-stu-id="c1174-297">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="c1174-298">Se, em **Selecione os recursos** , você não tiver optado por usar um único FQDN e endereço IP, digite o FQDN escolhido para seu lado público do pool de bordas no **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-298">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="c1174-299">Em **Webconferência**, digite o FQDN escolhido para o seu lado público do lado do pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-299">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="c1174-300">Em **áudio/vídeo**, digite o FQDN escolhido para seu lado público do lado do pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-300">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="c1174-301">Use as portas padrão.</span><span class="sxs-lookup"><span data-stu-id="c1174-301">Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1174-302">Estes serão os FQDNs VIP (IP virtual) de voltagem pública para o pool.</span><span class="sxs-lookup"><span data-stu-id="c1174-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="c1174-303">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c1174-303">Click **Next**.</span></span>

11. <span data-ttu-id="c1174-304">Em **definir os computadores neste pool**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="c1174-305">Em **definir os endereços IP externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-306">Se você optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o endereço IPv4 externo do servidor de borda no **acesso SIP**. endereço IP externo do servidor de borda no **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="c1174-307">Se você não optou por usar um único FQDN e um único endereço IP para o serviço de acesso SIP, Web de Webconferência e o/V referencing, digite o endereço IP que você escolheu para o seu lado público deste servidor de pool de borda para **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-307">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="c1174-308">Em **Webconferência**, digite o endereço IP que você escolheu para o seu lado público deste servidor de pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-308">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="c1174-309">Em **conferência A/V**, digite o endereço IP escolhido para o seu lado público do lado público deste servidor de pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-309">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="c1174-310">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c1174-310">Click **Next**.</span></span>

14. <span data-ttu-id="c1174-311">Se você optou por habilitar endereços IPv6, em **definir os endereços IP externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1174-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="c1174-312">Se você optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o endereço IPv6 externo do servidor de borda no **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="c1174-313">Se você não optou por usar um único FQDN e um único endereço IP para o serviço de acesso SIP, Web de Webconferência e o/V referencing, digite o endereço IPv6 que você escolheu para o seu lado público deste servidor de pool de borda para **acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="c1174-313">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="c1174-314">Em **Webconferência**, digite o endereço IPv6 que você escolheu para seu lado público do lado público deste servidor de pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-314">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="c1174-315">Em **conferência A/V**, digite o endereço IPv6 que você escolheu para seu lado público do lado público deste servidor de pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-315">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-316">Se você não optou por habilitar e atribuir endereçamento IPv6, esta caixa de diálogo não será exibida.</span><span class="sxs-lookup"><span data-stu-id="c1174-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="c1174-317">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c1174-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-318">Agora, você verá o primeiro servidor de borda que você criou no pool na caixa de diálogo <STRONG>definir os computadores neste pool</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c1174-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="c1174-319">Em **definir os computadores nesse pool**, clique em **Adicionar**e, em seguida, repita as etapas 11 a 14 para o segundo servidor de borda que você deseja adicionar ao seu pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="c1174-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="c1174-320">Após repetir as etapas 11 a 14, clique em **Avançar** em **definir os computadores nesse pool**.</span><span class="sxs-lookup"><span data-stu-id="c1174-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-321">Nesse ponto, você pode ver os dois servidores de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="c1174-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="c1174-322">Em **definir o próximo salto**, na lista **próximo pool de saltos** , selecione o nome do pool interno, que pode ser um pool de front-ends ou um pool padrão de edição.</span><span class="sxs-lookup"><span data-stu-id="c1174-322">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="c1174-323">Ou, se a sua implantação incluir um director, selecione o nome do diretor.</span><span class="sxs-lookup"><span data-stu-id="c1174-323">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="c1174-324">Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c1174-324">Then, click **Next**.</span></span>

19. <span data-ttu-id="c1174-325">Em **pools de front-end**, especifique um ou mais pools internos, que podem incluir pools front-ends e servidores Standard Edition, a serem associados a esse servidor de borda, selecionando os nomes dos pools internos que serão usados neste servidor de borda para comunicação com usuários externos com suporte.</span><span class="sxs-lookup"><span data-stu-id="c1174-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1174-326">Somente um pool de bordas com carga balanceada ou um servidor de borda única pode ser associado a cada pool interno para o tráfego A/V.</span><span class="sxs-lookup"><span data-stu-id="c1174-326">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="c1174-327">Se você já tiver um pool interno associado a um pool de bordas ou servidor de borda, um aviso será exibido indicando que o pool interno já está associado a um pool de bordas ou um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c1174-327">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="c1174-328">Se você selecionar um pool que já esteja associado a outro servidor de borda, ele alterará a associação.</span><span class="sxs-lookup"><span data-stu-id="c1174-328">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="c1174-329">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c1174-329">Click **Finish**.</span></span>

21. <span data-ttu-id="c1174-330">Publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="c1174-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

