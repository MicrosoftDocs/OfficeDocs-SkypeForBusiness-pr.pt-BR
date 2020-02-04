---
title: 'Lync Server 2013: alterar a URL dos serviços Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934e448f48413df2938deab8a0d08389cfad37bd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="0598a-102">Alterar a URL dos serviços Web no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0598a-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0598a-103">_**Tópico da última modificação:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="0598a-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="0598a-104">Ao configurar os seus pools front-end e os servidores padrão da edição, você tem a opção de configurar um FQDN (nome de domínio totalmente qualificado) do Web farm externo e portas associadas.</span><span class="sxs-lookup"><span data-stu-id="0598a-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="0598a-105">Se você não configurou esta URL ao executar o assistente de implantação do Lync Server, será necessário definir manualmente essas configurações.</span><span class="sxs-lookup"><span data-stu-id="0598a-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="0598a-106">Geralmente, um administrador não precisa modificar essas configurações, pois essas são as portas recomendadas e padrão.</span><span class="sxs-lookup"><span data-stu-id="0598a-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0598a-107">A captura de tela a seguir foi realizada durante a configuração de um servidor Standard Edition, portanto, a opção substituir FQDN está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="0598a-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="0598a-108">Essa opção é habilitada ao configurar um servidor Enterprise Edition em um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="0598a-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="0598a-109">![Editar configurações do pool de serviços Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Editar configurações do pool de serviços Web")</span><span class="sxs-lookup"><span data-stu-id="0598a-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="0598a-110">Para configurar serviços Web</span><span class="sxs-lookup"><span data-stu-id="0598a-110">To configure web services</span></span>

1.  <span data-ttu-id="0598a-111">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0598a-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="0598a-112">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0598a-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="0598a-113">No construtor de topologia, na árvore de console, em **servidores front-end da edição padrão**, **pools front-end do Enterprise Edition**e **pools de diretórios**, selecione o nome do pool.</span><span class="sxs-lookup"><span data-stu-id="0598a-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="0598a-114">Clique com o botão direito do mouse no nome, clique em **Editar propriedades**e, em seguida, clique em **Serviços Web**.</span><span class="sxs-lookup"><span data-stu-id="0598a-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="0598a-115">Adicione ou edite o **FQDN dos serviços Web externos**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0598a-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0598a-116">Se você tiver mais de um servidor front-end ou servidor front-end, os serviços Web externos FQDN deverão ser exclusivos.</span><span class="sxs-lookup"><span data-stu-id="0598a-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="0598a-117">Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-end ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="0598a-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="0598a-118">Se você também estiver implantando diretores, os serviços Web externos FQDN definidos para qualquer diretor de director ou diretor devem ser exclusivos de qualquer outro diretor ou pool de director, bem como qualquer pool de front-end ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="0598a-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="0598a-119">Verifique se as portas de escuta e publicadas estão configuradas corretamente para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="0598a-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="0598a-120">Repita essas etapas para todos os servidores de edição padrão, pools de front-end e pools de directors em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="0598a-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="0598a-121">Na árvore de console, clique em **Lync Server 2013**e, em seguida, no painel **ações** , clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="0598a-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="0598a-122">Há alguns requisitos dos quais você deve estar ciente ao configurar as portas de escuta e publicação:</span><span class="sxs-lookup"><span data-stu-id="0598a-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="0598a-123">As portas de escuta mostradas são as portas configuradas para o IIS (servidor de informações da Internet) em cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="0598a-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="0598a-124">As portas de escuta internas e externas devem ser diferentes para o IIS.</span><span class="sxs-lookup"><span data-stu-id="0598a-124">The internal and external listening ports must be different for IIS.</span></span> <span data-ttu-id="0598a-125">Para as portas de escuta externas, elas são geralmente iguais porque representam o balanceador de carga de hardware para tráfego da Web interno e um representa o servidor proxy reverso para tráfego da Web externo.</span><span class="sxs-lookup"><span data-stu-id="0598a-125">For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="0598a-126">Você pode substituir os serviços Web internos em um pool de front-end, diretor ou um pool de directors e definir seu próprio FQDN.</span><span class="sxs-lookup"><span data-stu-id="0598a-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0598a-127">Se você decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.</span><span class="sxs-lookup"><span data-stu-id="0598a-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="0598a-128">As portas publicadas devem ser configuradas no balanceamento de carga de hardware ou proxy reverso como portas de escuta.</span><span class="sxs-lookup"><span data-stu-id="0598a-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="0598a-129">Para um pool de front-ends (não mostrado no exemplo), o FQDN do pool de SIP interno deve ser diferente do FQDN de serviços Web internos, porque o tráfego da Web chega ao balanceador de carga de hardware e o tráfego do pool SIP interno percorre o balanceador de carga de DNS .</span><span class="sxs-lookup"><span data-stu-id="0598a-129">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer.</span></span> <span data-ttu-id="0598a-130">Este requisito deve ser atendido.</span><span class="sxs-lookup"><span data-stu-id="0598a-130">This requirement must be met.</span></span>

  - <span data-ttu-id="0598a-131">Uma implantação do Lync Server Standard Edition não precisa ou permite que um FQDN de serviços Web internos seja substituído porque esse servidor não pode ter o balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="0598a-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="0598a-132">Se você tiver um balanceador de carga de hardware em seu ambiente que você usa para tráfego da Web e SIP internos, o construtor de topologias não pode fazer a distinção.</span><span class="sxs-lookup"><span data-stu-id="0598a-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="0598a-133">Os FQDNs do serviço Web devem ser facilmente diferenciados um do outro; Isso ajuda a garantir que o redirecionamento de URL aponte para os clientes em direção ao servidor apropriado.</span><span class="sxs-lookup"><span data-stu-id="0598a-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="0598a-134">Por exemplo, se você tiver dois FQDNs, talvez considere nomear um meeting.contoso.com e o outro conferencing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0598a-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="0598a-135">Você pode potencialmente executar problemas de redirecionamento se tiver FQDNs com nomes mais semelhantes, como meet1.contoso.com e meet2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0598a-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="0598a-136">Os serviços Web externos funcionam em conjunto com um proxy reverso na rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="0598a-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="0598a-137">Ele fornece aos clientes acesso externo ao uso desses serviços Web.</span><span class="sxs-lookup"><span data-stu-id="0598a-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="0598a-138">Os FQDNs configurados aqui são enviados para os clientes quando eles fazem logon e são usados para fazer uma conexão HTTPS de volta ao proxy inverso quando se conecta remotamente.</span><span class="sxs-lookup"><span data-stu-id="0598a-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="0598a-139">O servidor de proxy reverso encaminha o FQDN do serviço Web externo para um balanceador de carga de hardware interno ou diretamente para o pool.</span><span class="sxs-lookup"><span data-stu-id="0598a-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="0598a-140">O proxy reverso deve ser capaz de resolver o FQDN dos serviços Web externos para o endereço IP do servidor Web interno.</span><span class="sxs-lookup"><span data-stu-id="0598a-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="0598a-141">O FDQN de serviços Web externos deve ser resolvível na Internet pública.</span><span class="sxs-lookup"><span data-stu-id="0598a-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="0598a-142">Se o seu servidor interno for um servidor de edição padrão, o FQDN interno será o FQDN do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0598a-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="0598a-143">Se o seu servidor interno for um pool de front-ends, o FQDN será um VIP (IP virtual) do balanceador de carga de hardware que carrega o balanceamento de servidores internos de Web farm.</span><span class="sxs-lookup"><span data-stu-id="0598a-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="0598a-144">Um balanceador de carga de hardware é necessário em um pool de front-ends com mais de um servidor Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="0598a-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="0598a-145">Um balanceador de carga não é necessário para um servidor Standard Edition ou um servidor front-end da Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="0598a-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

