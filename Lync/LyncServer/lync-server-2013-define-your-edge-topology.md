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
ms.openlocfilehash: ceba1f397493ac0ef6961099877643f802c11d93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504558"
---
# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="b273e-102">Definir sua topologia de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b273e-102">Define your edge topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b273e-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b273e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b273e-104">Você deve usar o construtor de topologias para criar sua topologia e deve configurar pelo menos um pool de front-ends interno ou servidor Standard Edition antes de poder implantar o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="b273e-105">Use o procedimento a seguir para definir a topologia de borda de um servidor de borda único e, em seguida, use os procedimentos em [publicar sua topologia no Lync server 2013](lync-server-2013-publish-your-topology.md) e [exporte sua topologia do Lync Server 2013 e copie-o para a mídia externa para instalação de borda](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) para publicar a topologia e torná-la disponível para o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b273e-p102">A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS na interface de Borda e o balanceamento de carga de hardware na outra interface de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="b273e-108">Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função do servidor, você deve estar conectado a um usuário membro dos grupos RTCUniversalServerAdmins e de Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="b273e-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="b273e-109">Também é possível conceder direitos e permissões do administrador exigidos para adicionar funções do servidor a uma conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="b273e-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="b273e-110">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="b273e-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="b273e-111">Para outras alterações na configuração, apenas a associação no grupo RTCUniversalServerAdmins é necessária.</span><span class="sxs-lookup"><span data-stu-id="b273e-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="b273e-112">Se você definiu sua topologia de borda quando definiu e publicou sua topologia interna, e nenhuma alteração for necessária para a topologia de borda que você definiu anteriormente, não será necessário defini-la e publicá-la novamente.</span><span class="sxs-lookup"><span data-stu-id="b273e-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="b273e-113">Use o procedimento a seguir somente caso seja necessário fazer alterações em sua topologia de borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="b273e-114">Você deve tornar a topologia previamente definida e publicada disponível para os servidores de borda, que você faz usando o procedimento em [exportar sua topologia do Lync Server 2013 e copiá-la para a mídia externa para instalação de borda](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="b273e-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b273e-115">Não é possível executar o construtor de topologias de um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="b273e-116">Você deve executá-lo do seu Servidor Front-End ou servidores do Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b273e-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="b273e-117">O processo para definir a topologia do servidor de borda é feito no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="b273e-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="b273e-118">os três tipos principais de topologias de servidor de borda que você pode planejar e configurar são listados a seguir:</span><span class="sxs-lookup"><span data-stu-id="b273e-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="b273e-119">Para definir a topologia de um único servidor de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="b273e-120">Para definir a topologia de um pool de servidor de borda de balanceamento de carga</span><span class="sxs-lookup"><span data-stu-id="b273e-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="b273e-121">Para definir a topologia de um pool de borda com carga de hardware balanceada</span><span class="sxs-lookup"><span data-stu-id="b273e-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="b273e-122">Para definir a topologia para um único Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="b273e-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="b273e-123">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b273e-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b273e-124">Na árvore de console, expanda o site no qual você deseja implantar um Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="b273e-125">Clique com o botão direito do mouse em **pools de borda**e clique em **novo pool de borda**.</span><span class="sxs-lookup"><span data-stu-id="b273e-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="b273e-126">Em **Definir o Novo Pool de Borda**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="b273e-127">Em **Definir o FQDN do pool de borda**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-128">Em **FQDN do Pool**, digite o FQDN (nome de domínio totalmente qualificado) da interface interna do Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="b273e-129">O nome especificado deve ser idêntico ao nome do computador configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="b273e-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="b273e-130">Por padrão, o nome de um computador que não é atribuído a um domínio é um nome curto, não um FQDN.</span><span class="sxs-lookup"><span data-stu-id="b273e-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="b273e-131">O Construtor de Topologia utiliza FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="b273e-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="b273e-132">Portanto, você deve configurar um sufixo DNS no nome do computador para ser implantado como um Servidor de Borda que não é vinculado a um domínio.</span><span class="sxs-lookup"><span data-stu-id="b273e-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="b273e-133">Use apenas caracteres padrões (incluindo A–Z, a–z, 0–9 e hífens) quando atribuir FQDNs a seus Lync Servers, Servidores de Borda e pools.</span><span class="sxs-lookup"><span data-stu-id="b273e-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="b273e-134">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="b273e-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="b273e-135">Os caracteres não padrões em um FQDN frequentemente não são suportados pelo DNS externo e CAs públicos (quando o FQDN deve ser atribuído para o SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="b273e-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="b273e-136">Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b273e-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="b273e-137">Clique em **Pool de computador único** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="b273e-138">Em **Selecionar recursos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-139">Se você planeja usar um único FQDN e endereço IP para o serviço de acesso SIP, o serviço de Webconferência do Lync Server 2013 e os serviços de borda de A/V, marque a caixa de seleção **usar um único FQDN e endereço IP** .</span><span class="sxs-lookup"><span data-stu-id="b273e-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="b273e-140">Caso planeje habilitar a federação, marque a caixa de seleção **Habilitar federação para este pool de Borda (porta 5061)**</span><span class="sxs-lookup"><span data-stu-id="b273e-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b273e-p108">Você pode selecionar esta opção, mas somente um pool de Borda ou Servidor de Borda em sua organização pode ser publicado externamente para federação. Todo o acesso por usuários federados, incluindo as mensagens instantâneas públicas de usuários, percorrem o mesmo pool de borda ou um único servidor de borda. Por exemplo, se sua implantação incluir um pool de Borda ou um único Servidor de Borda implantado em Nova York e um implantado em Londres e você ativar o suporte à federação no pool de Borda de Nova York ou no Servidor de Borda único, o tráfego de sinal para os usuários federados passará através do pool de Borda de Nova York ou do Servidor de Borda único. Isso se aplica mesmo para a comunicação com os usuários de Londres, embora um usuário interno de Londres que chama um usuário federado de Londres use o pool de Londres ou o Servidor de Borda para um tráfego de A/V.</span><span class="sxs-lookup"><span data-stu-id="b273e-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="b273e-145">Caso planeje oferecer suporte ao protocolo XMPP em sua implantação, marque a caixa de seleção **Habilitar federação XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="b273e-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="b273e-146">Em **Selecionar Opções de IP**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-147">**Habilitar IPv4 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b273e-148">**Habilitar IPv6 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b273e-149">**Habilitar IPv4 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="b273e-150">**Habilitar IPv6 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="b273e-151">Você também pode configurar o servidor de borda ou o pool de borda para usar um endereço de conversão de endereço de rede para endereços IP externos.</span><span class="sxs-lookup"><span data-stu-id="b273e-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="b273e-152">Faça isso marcando a caixa de seleção **O endereço IP externo desse pool de Borda é convertido pelo NAT**.</span><span class="sxs-lookup"><span data-stu-id="b273e-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="b273e-153">Em **FQDNs Externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-154">Se em **Selecionar recursos** você escolher usar um FQDN único e o endereço IP para o acesso SIP, o serviço de Conferência Web e um serviço de borda A/V, digite o FQDN externo em **Acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="b273e-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b273e-p110">Se você escolher esta opção, deverá especificar um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de Acesso de Borda, 444 para serviço de Borda de Conferência Web e 443 para serviço de Borda A/V). Esta opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode usar o mesmo número de porta (por exemplo, 443) para os três serviços.</span><span class="sxs-lookup"><span data-stu-id="b273e-p110">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="b273e-157">Se em **Selecionar recursos** você não escolheu usar um FQDN e endereço IP único, digite os FQDNs externo para o **Acesso SIP**,   **Conferência Web** e **Áudio vídeo**, mantendo as portas padrão.</span><span class="sxs-lookup"><span data-stu-id="b273e-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="b273e-158">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-158">Click **Next**.</span></span>

10. <span data-ttu-id="b273e-p111">Em **Definir o endereço IP interno**, digite o endereço IP do seu Servidor de Borda em **Endereço IPv4 interno** e **Endereço IPv6 interno** conforme apropriado para seus requisitos. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-p111">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements. Click **Next**.</span></span>

11. <span data-ttu-id="b273e-161">Em **Definir endereço IP externo**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-162">Caso opte por usar um único FQDN e endereço IP para o acesso SIP, serviço de Webconferência e serviço de borda A/V, digite o endereço IPv4 externo do servidor de borda em **Acesso SIP** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="b273e-163">Caso opte por usar endereços IPv6, digite o endereço IPv6 externo do servidor de borda em **Acesso SIP** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="b273e-164">Se você não escolheu usar um FQDN e endereço IP único para o acesso SIP, o serviço de Webconferência e o serviço de Borda A/V, digite os endereços IPv4 externos do Servidor de Borda em **Acesso SIP**, **Webconferência** e **Conferência A/V**, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="b273e-165">Se você optou por usar endereços IPv6 e não escolheu usar um FQDN e endereço IPv6 único para o acesso SIP, o serviço de Webconferência e o serviço de Borda A/V, digite os endereços IP externos do Servidor de Borda em **Acesso SIP**, **Webconferência** e **Conferência A/V**, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b273e-166">Caso não tenha optado por habilitar e atribuir endereços IPv6, você não verá esta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b273e-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="b273e-p112">Se você optou por usar NAT, uma caixa de diálogo será aberta. Em **Endereço IPv4 público para o serviço de Borda A/V**, digite o endereço IPv4 público a ser convertido pelo NAT e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-p112">If you chose to use NAT, a dialog box appears. In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-169">Esse endereço deve ser o endereço IP externo do serviço de Borda A/V.</span><span class="sxs-lookup"><span data-stu-id="b273e-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="b273e-p113">Se você optou por usar NAT e endereços IPv6, uma caixa de diálogo será aberta. Em **Endereço IPv6 público para o serviço de Borda A/V**, digite o endereço IPv6 público a ser convertido pelo NAT e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-p113">If you chose to use NAT and IPv6 addresses, a dialog box appears. In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-172">Esse endereço deve ser o endereço IP externo do serviço de Borda. A/V.</span><span class="sxs-lookup"><span data-stu-id="b273e-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="b273e-p114">Em **Definir o próximo salto**, em **Próximo pool de salto**, selecione o nome do pool interno, que pode ser um pool de Front-Ends ou um pool do Standard Edition. Em alternativa, se sua implantação incluir um Diretor, selecione o Diretor e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-p114">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the Director. Then, click **Next**.</span></span>

15. <span data-ttu-id="b273e-176">Em **Associar pools de Front-Ends**, especifique um ou mais pools internos, que podem incluir pools de Front-Ends e servidores Standard Edition, para serem associados com este Servidor de Borda selecionando os nomes dos pools internos que devem usar este Servidor de Borda para comunicação com os usuários externos suportados.</span><span class="sxs-lookup"><span data-stu-id="b273e-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-p115">Apenas um pool de Borda com carga balanceada ou um Servidor de Borda exclusivo pode ser associado a cada pool interno para o tráfego A/V. Se você já possui um pool interno associado a um pool de Borda ou Servidor de Borda, um aviso é exibido indicando que o pool interno já esteja associado com um pool de Borda ou um Servidor de Borda. Se você selecionar um pool já associado com outro servidor de borda, a associação será alterada.</span><span class="sxs-lookup"><span data-stu-id="b273e-p115">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="b273e-180">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b273e-180">Click **Finish**.</span></span>

17. <span data-ttu-id="b273e-181">Publique sua topologia.</span><span class="sxs-lookup"><span data-stu-id="b273e-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="b273e-182">Para definir a topologia para um pool de Servidor de Borda com balanceamento de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="b273e-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="b273e-183">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b273e-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b273e-184">Na árvore do console, expanda o site em que deseja implantar Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="b273e-185">Clique com o botão direito em **Pools de Borda** e clique em **Novo Pool de Borda**.</span><span class="sxs-lookup"><span data-stu-id="b273e-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="b273e-186">Em**Definir o Novo Pool de Borda**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="b273e-187">Em **Definir o FQDN do pool de Borda**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-188">Em **FQDN do pool**, digite o nome de domínio totalmente qualificado (FQDN) para a conexão interna do pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="b273e-189">O nome especificado para o pool deve ser o nome do pool de borda interno.</span><span class="sxs-lookup"><span data-stu-id="b273e-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="b273e-190">Ele deve ser definido como um FQDN.</span><span class="sxs-lookup"><span data-stu-id="b273e-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="b273e-191">O Construtor de Topologia utiliza FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="b273e-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="b273e-192">Use apenas caracteres padrões (incluindo A–Z, a–z, 0–9 e hífens) ao atribuir FQDNs dos seus Lync Servers, Servidores de Borda e pools.</span><span class="sxs-lookup"><span data-stu-id="b273e-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="b273e-193">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="b273e-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="b273e-194">Muitas vezes, o DNS externo e as autoridades de certificação públicas não oferecem suporte a caracteres diferentes do padrão em um FQDN (quando o FQDN deve ser atribuído ao SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="b273e-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="b273e-195">Clique em **Pool de vários computadores** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="b273e-196">Em **Selecionar recursos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-197">Se você planeja usar um único FQDN e endereço IP para o acesso SIP, o serviço de Webconferência do Lync Server 2013 e os serviços de borda de A/V, marque a caixa de seleção **usar um único FQDN e endereço IP** .</span><span class="sxs-lookup"><span data-stu-id="b273e-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="b273e-p117">Se você planeja habilitar a federação, marque a caixa de seleção **Habilitar federação para este pool de Borda (porta 5061)**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-p117">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box. Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b273e-p118">Você pode selecionar esta opção, mas somente um pool de Borda ou Servidor de Borda em sua organização pode ser publicado externamente para federação. Todo o acesso por usuários federados, incluindo sistemas de mensagens instantâneas (IM) públicos, passam pelo mesmo pool de Borda ou Servidor de Borda único. Por exemplo, se sua implantação inclui um pool de Borda ou Servidor de Borda único implantado em Nova York e um implantado em Londres e você habilitar o suporte a federação no pool de Borda de Nova York ou no Servidor de Borda único, o tráfego do sinal para usuários federados passará pelo pool de Borda de Nova York ou Servidor de Borda único. Isto é verdade mesmo para comunicações com usuários de Londres, embora um usuário interno de Londres ligando para um usuário federado de Londres use o pool desta cidade ou o Servidor de Borda para tráfego de A/V.</span><span class="sxs-lookup"><span data-stu-id="b273e-p118">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="b273e-204">Caso planeje oferecer suporte ao protocolo XMPP em sua implantação, marque a caixa de seleção **Habilitar federação XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="b273e-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="b273e-205">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-205">Click **Next**.</span></span>

8.  <span data-ttu-id="b273e-206">Em **Selecionar Opções de IP**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-207">**Habilitar IPv4 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b273e-208">**Habilitar IPv6 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b273e-209">**Habilitar IPv4 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="b273e-210">**Habilitar IPv6 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="b273e-211">Você também pode configurar o servidor de borda ou o pool de borda para usar um endereço de conversão de endereço de rede para endereços IP externos.</span><span class="sxs-lookup"><span data-stu-id="b273e-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="b273e-212">Faça isso marcando a caixa de seleção **O endereço IP externo desse pool de Borda é convertido pelo NAT**.</span><span class="sxs-lookup"><span data-stu-id="b273e-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="b273e-213">Em **FQDNs externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-214">Se em **Selecionar recursos** você optou por usar um único FQDN e Endereço IP para o acesso SIP, serviço de Webconferências e serviço de Borda de A/V, digite o FQDN externo em **Acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="b273e-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b273e-p120">Se você escolher esta opção, deverá especificar um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de Acesso de Borda, 444 para serviço de Borda de Conferência Web e 443 para serviço de Borda A/V). Esta opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode usar o mesmo número de porta (por exemplo, 443) para os três serviços.</span><span class="sxs-lookup"><span data-stu-id="b273e-p120">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="b273e-p121">Se em **Selecionar recursos** você não optou por usar um único FQDN e Endereço IP, digite o FQDN escolhido para o lado voltado ao público do pool de borda em **Acesso SIP**. Em **Webconferências**, digite o FQDN escolhido para o lado voltado ao público do pool de Borda. Em **Áudio/Vídeo**, digite o FQDN escolhido para o lado voltado ao público do pool de Borda. Use as portas padrão.</span><span class="sxs-lookup"><span data-stu-id="b273e-p121">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>

10. <span data-ttu-id="b273e-221">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-221">Click **Next**.</span></span>

11. <span data-ttu-id="b273e-222">Em **Definir computadores neste pool**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="b273e-223">Em **FQDN e endereço IP internos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-224">Em **Endereço IPv4 interno**, digite o endereço IPv4 e o  **Endereço IPv6 interno** conforme apropriado para seus requisitos para o primeiro servidor de borda que deseja criar no pool.</span><span class="sxs-lookup"><span data-stu-id="b273e-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="b273e-225">Em **FQDN Interno**, digite o FQDN do primeiro Servidor de Borda que deseja criar neste pool.</span><span class="sxs-lookup"><span data-stu-id="b273e-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b273e-226">O nome especificado deve ser idêntico ao nome do computador configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="b273e-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="b273e-227">Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN.</span><span class="sxs-lookup"><span data-stu-id="b273e-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="b273e-228">O Construtor de Topologia utiliza FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="b273e-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="b273e-229">Portanto, você deve configurar um sufixo DNS no nome do computador para ser implantado como um Servidor de Borda que não é vinculado a um domínio.</span><span class="sxs-lookup"><span data-stu-id="b273e-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="b273e-230">Use apenas caracteres padrões (incluindo A–Z, a–z, 0–9 e hífens) quando atribuir FQDNs a seus Lync Servers, Servidores de Borda, pools e matrizes.</span><span class="sxs-lookup"><span data-stu-id="b273e-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="b273e-231">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="b273e-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="b273e-232">Os caracteres não padrões em um FQDN frequentemente não são suportados pelo DNS externo e CAs públicos (quando o FQDN deve ser atribuído para o SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="b273e-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="b273e-233">Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b273e-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="b273e-234">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-234">Click **Next**.</span></span>

14. <span data-ttu-id="b273e-235">Em **Definir endereços IP externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-236">Se você escolher usar um FQDN único e Endereço IP para o acesso SIP, o serviço de Webconferência e o serviço de Borda A/V, digite o endereço IP externo do Servidor de Borda em **Acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="b273e-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="b273e-p123">Se você não optou por usar um único FQDN e Endereço IP para o acesso SIP, serviço de Webconferências e serviço de Conferências de A/V, digite o endereço IP escolhido para o lado voltado ao público deste servidor de pool de Borda no **Acesso SIP**. Em **Webconferências**, digite o endereço IP escolhido para o lado voltado ao público deste servidor de pool de Borda. Em **Conferências de A/V**, digite o endereço IP escolhido para o lado voltado ao público deste servidor de pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-p123">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="b273e-240">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-240">Click **Next**.</span></span>

16. <span data-ttu-id="b273e-241">Caso opte por habilitar endereços IPv6, em **Definir endereços IP externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-242">Se você optou por usar um único FQDN e Endereço IPv6 para o acesso SIP, serviço de Webconferências e serviço de Borda de A/V, digite o endereço IP externo do Servidor de Borda em **Acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="b273e-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="b273e-p124">Se você não optou por usar um único FQDN e Endereço IP para o acesso SIP, serviço de Webconferências e serviço de Conferências de A/V, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda no **Acesso SIP**. Em **Webconferências**, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda. Em **Conferências de A/V**, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-p124">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-246">Caso não tenha optado por habilitar e atribuir endereços IPv6, você não verá esta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b273e-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="b273e-247">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b273e-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-248">Agora você verá o primeiro Servidor de Borda criado em seu pool na caixa de diálogo <STRONG>Definir os computadores neste pool</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b273e-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="b273e-249">Em **Definir os computadores neste pool**, clique em **Adicionar** e repita as etapas 11 até 14 para o segundo Servidor de Borda que deseja adicionar ao seu pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="b273e-250">Depois de repetir as etapas 11 a 14, clique em **Avançar** em **Definir os computadores neste pool**.</span><span class="sxs-lookup"><span data-stu-id="b273e-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-251">Neste ponto, você poderá ver ambos os Servidores de Borda em seu pool.</span><span class="sxs-lookup"><span data-stu-id="b273e-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="b273e-p125">Se você optou por usar NAT, uma caixa de diálogo será aberta. Em **Endereço IP público**, digite o endereço IPv4 e IPv6 público (se apropriado) a ser convertido pelo NAT e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-p125">If you chose to use NAT, a dialog box appears. In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-254">Este deve ser o endereço IP externo da Borda de A/V.</span><span class="sxs-lookup"><span data-stu-id="b273e-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="b273e-p126">Em **Definir o próximo salto**, na lista **Pool do próximo salto**, selecione o nome do pool interno, que pode ser um pool de Front-Ends ou um pool Standard Edition. Ou, se sua implantação inclui um Diretor, selecione o nome do Diretor. Em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-p126">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

22. <span data-ttu-id="b273e-258">Em **Associar pools de front-ends**, especifique um ou mais pools internos, que podem incluir pools de Front-Ends e servidores do Standard Edition, para serem associados a este Servidor de Borda selecionando os nomes dos pools internos que devem usar este Servidor de Borda para comunicação com os usuários externos suportados.</span><span class="sxs-lookup"><span data-stu-id="b273e-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-p127">Apenas um pool de Borda com carga balanceada ou um Servidor de Borda exclusivo pode ser associado com cada pool interno para o tráfego A/V. Se você já possui um pool interno associado a um pool de Borda ou Servidor de Borda, um aviso é exibido indicando que o pool interno já está associado a um pool de Borda ou um Servidor de Borda. Se você selecionar um pool já associado a outro servidor de borda, associação será alterada.</span><span class="sxs-lookup"><span data-stu-id="b273e-p127">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="b273e-262">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b273e-262">Click **Finish**.</span></span>

24. <span data-ttu-id="b273e-263">Publique sua topologia.</span><span class="sxs-lookup"><span data-stu-id="b273e-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="b273e-264">Para definir a topologia de um pool de Servidor de Borda com balanceamento de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="b273e-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="b273e-265">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b273e-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b273e-266">Na árvore de console, expanda o site no qual você deseja implantar os Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="b273e-267">Clique com o botão direito do mouse em **pools de borda**e selecione **novo pool de borda**.</span><span class="sxs-lookup"><span data-stu-id="b273e-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="b273e-268">Em **Definir o Novo Pool de Borda**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="b273e-269">Em **Definir o FQDN do pool de borda**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-270">Em **FQDN**, digite o FQDN (nome de domínio totalmente qualificado) escolhido para o lado interno do pool de borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="b273e-271">O nome especificado para o pool deve ser o nome do pool de borda interno.</span><span class="sxs-lookup"><span data-stu-id="b273e-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="b273e-272">Ele deve ser definido como um FQDN.</span><span class="sxs-lookup"><span data-stu-id="b273e-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="b273e-273">O Construtor de Topologia utiliza FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="b273e-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="b273e-274">Use apenas caracteres padrões (incluindo A–Z, a–z, 0–9 e hífens) ao atribuir FQDNs dos seus Lync Servers, Servidores de Borda e pools.</span><span class="sxs-lookup"><span data-stu-id="b273e-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="b273e-275">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="b273e-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="b273e-276">Os caracteres não padrões em um FQDN frequentemente não são suportados pelo DNS externo e CAs públicos (quando o FQDN deve ser atribuído para o SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="b273e-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="b273e-277">Clique em **pool de vários computadores**e, em seguida, em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="b273e-278">Em **Selecionar recursos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="b273e-279">Se você planeja usar um único FQDN e endereço IP para o serviço de acesso SIP, o serviço de conferência da Web do Lync Server e o serviço de borda A/V, marque a caixa de seleção **usar um único FQDN & endereço IP** .</span><span class="sxs-lookup"><span data-stu-id="b273e-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="b273e-280">Se você planeja habilitar a federação, marque a caixa de seleção **Habilitar federação (para esse pool de Borda (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="b273e-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b273e-p129">Você pode selecionar esta opção, mas somente um pool de Borda ou Servidor de Borda em sua organização pode ser publicado externamente para federação. Todo o acesso por usuários federados, incluindo as mensagens instantâneas públicas de usuários, percorrem o mesmo pool de Borda ou um único Servidor de Borda. Por exemplo, se sua implantação inclui um pool de Borda ou único Servidor de Borda implantado em Nova York e um implantado em Londres e você ativar o suporte à federação no pool de Borda de Nova York ou no Servidor de Borda único, o tráfego de sinal para os usuários federados passará através do pool de Borda de Nova York ou do Servidor de Borda único. Isso se aplica mesmo para a comunicação com os usuários de Londres, embora um usuário interno de Londres que chama um usuário federado de Londres use o pool de Londres ou o Servidor de Borda para um tráfego de A/V.</span><span class="sxs-lookup"><span data-stu-id="b273e-p129">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="b273e-285">Caso planeje oferecer suporte ao protocolo XMPP em sua implantação, marque a caixa de seleção **Habilitar federação XMPP (porta 5269)**</span><span class="sxs-lookup"><span data-stu-id="b273e-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="b273e-286">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-286">Click **Next**.</span></span>

8.  <span data-ttu-id="b273e-287">Em **Selecionar Opções de IP**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-288">**Habilitar IPv4 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b273e-289">**Habilitar IPv6 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="b273e-290">**Habilitar IPv4 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="b273e-291">**Habilitar IPv6 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de borda</span><span class="sxs-lookup"><span data-stu-id="b273e-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b273e-p130"><STRONG>Não</STRONG> marque a caixa de seleção <STRONG>O endereço IP externo do pool de Borda é convertido pelo NAT</STRONG>. A NAT (conversão de endereços de rede) não é suportada quando você está usando o balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="b273e-p130"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box. Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="b273e-294">Em **FQDNs externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-295">Se em **Selecionar recursos** você escolher usar um FQDN único e o endereço IP para o acesso SIP, o serviço de Webconferência e um serviço de Borda A/V, digite o FQDN externo em **Acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="b273e-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b273e-p131">Se você escolher esta opção, deverá especificar um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de Acesso de Borda, 444 para serviço de Borda de Conferência Web e 443 para serviço de Borda A/V). Esta opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode usar o mesmo número de porta (por exemplo, 443) para os três serviços.</span><span class="sxs-lookup"><span data-stu-id="b273e-p131">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="b273e-p132">Se em **Selecionar recursos** você não optou por usar um único FQDN e Endereço IP, digite o FQDN escolhido para o lado voltado ao público do pool de borda em **Acesso SIP**. Em **Webconferências**, digite o FQDN escolhido para o lado voltado ao público do pool de Borda. Em **Áudio/Vídeo**, digite o FQDN escolhido para o lado voltado ao público do pool de Borda. Use as portas padrão.</span><span class="sxs-lookup"><span data-stu-id="b273e-p132">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b273e-302">Estes serão os FQDNs de IP virtual (VIP) voltados ao público para o pool.</span><span class="sxs-lookup"><span data-stu-id="b273e-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="b273e-303">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-303">Click **Next**.</span></span>

11. <span data-ttu-id="b273e-304">Em **Definir os computadores neste pool**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="b273e-305">Em **Definir os endereços IP externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-306">Caso opte por usar um único FQDN e endereço IP para o acesso SIP, serviço de Webconferência e serviço de borda A/V, digite o endereço IPv4 externo do servidor de borda em **Acesso SIP**.endereço IP externo do servidor de borda em **Acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="b273e-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="b273e-p133">Se você não optou por usar um único FQDN e Endereço IP para o acesso SIP, serviço de Webconferências e serviço de Conferências de A/V, digite o endereço IP escolhido para o lado voltado ao público deste servidor de pool de Borda no **Acesso SIP**. Em **Webconferências**, digite o endereço IP escolhido para o lado voltado ao público deste servidor de pool de Borda. Em **Conferências de A/V**, digite o endereço IP escolhido para o lado voltado ao público deste servidor de pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-p133">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="b273e-310">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-310">Click **Next**.</span></span>

14. <span data-ttu-id="b273e-311">Caso opte por habilitar endereços IPv6, em **Definir endereços IP externos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b273e-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="b273e-312">Se você optou por usar um único FQDN e Endereço IPv6 para o acesso SIP, serviço de Webconferências e serviço de Borda de A/V, digite o endereço IP externo do Servidor de Borda em **Acesso SIP**.</span><span class="sxs-lookup"><span data-stu-id="b273e-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="b273e-p134">Se você não optou por usar um único FQDN e Endereço IP para o acesso SIP, serviço de Webconferências e serviço de Conferências de A/V, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda no **Acesso SIP**. Em **Webconferências**, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda. Em **Conferências de A/V**, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-p134">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-316">Caso não tenha optado por habilitar e atribuir endereços IPv6, você não verá esta caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b273e-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="b273e-317">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b273e-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-318">Você verá agora o primeiro Servidor de Borda criado no seu pool na caixa de diálogo <STRONG>Definir os computadores neste pool</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b273e-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="b273e-319">Em **Definir os computadores deste pool**, clique em **Adicionar** e repita as etapas de 11 a 14 para o segundo Servidor de Borda que você deseja adicionar ao pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="b273e-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="b273e-320">Após repetir as etapas 11 a 14, clique em **Avançar** em **Definir os computadores neste pool**.</span><span class="sxs-lookup"><span data-stu-id="b273e-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-321">Nesse ponto, é possível ver os dois Servidores de Borda em seu pool.</span><span class="sxs-lookup"><span data-stu-id="b273e-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="b273e-p135">Em **Definir o próximo salto**, na lista **Próximo pool de salto**, selecione o nome do pool interno, que pode ser um pool de Front-Ends ou um pool do Standard Edition. Em alternativa, se sua implantação inclui um Diretor, selecione o nome do Diretor. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b273e-p135">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

19. <span data-ttu-id="b273e-325">Em **Associar pools de front-ends**, especifique um ou mais pools internos, que podem incluir pools de Front-Ends e servidores do Standard Edition, para serem associados a este Servidor de Borda selecionando os nomes dos pools internos que devem usar este Servidor de Borda para comunicação com os usuários externos suportados.</span><span class="sxs-lookup"><span data-stu-id="b273e-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b273e-p136">Apenas um pool de Borda com carga balanceada ou um Servidor de Borda exclusivo pode ser associado com cada pool interno para o tráfego A/V. Se você já possui um pool interno associado a um pool de Borda ou Servidor de Borda, um aviso é exibido indicando que o pool interno já está associado a um pool de Borda ou um Servidor de Borda. Se você selecionar um pool já associado a outro servidor de borda, associação será alterada.</span><span class="sxs-lookup"><span data-stu-id="b273e-p136">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="b273e-329">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b273e-329">Click **Finish**.</span></span>

21. <span data-ttu-id="b273e-330">Publique sua topologia.</span><span class="sxs-lookup"><span data-stu-id="b273e-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

