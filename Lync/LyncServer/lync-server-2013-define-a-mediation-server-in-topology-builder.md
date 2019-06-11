---
title: 'Lync Server 2013: definir um servidor de mediação no construtor de topologias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1356217b9effe3f2282f6931b601e84aa46770
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="f8146-102">Definir um servidor de mediação no construtor de topologias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8146-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8146-103">_**Tópico da última modificação:** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="f8146-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="f8146-104">Siga as etapas deste tópico para usar o construtor de topologias para definir um servidor de mediação autônomo ou um pool posicionado com um pool de front-ends em um site para o qual você não tenha implantado anteriormente no Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f8146-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="f8146-105">Você pode definir uma topologia usando uma conta que seja membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="f8146-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="f8146-106">Definir o servidor de mediação posicionado em um pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="f8146-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="f8146-107">Siga as etapas neste tópico para usar o construtor de topologias para definir um servidor de mediação posicionado em um pool de front-end em um site em que o Enterprise Voice não foi implantado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8146-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="f8146-108">Para adicionar um servidor de mediação a um pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="f8146-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="f8146-109">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f8146-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="f8146-110">No construtor de topologias, na árvore de console, expanda o nome do site para o qual você deseja definir um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="f8146-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="f8146-111">Na árvore do console, clique com o botão direito do mouse no tipo de pool de front-end desejado e, em seguida, clique em **novo pool de front-ends..**.</span><span class="sxs-lookup"><span data-stu-id="f8146-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="f8146-112">Navegue pelo assistente **Definir Novo Pool de Front-Ends** até chegar à página **Selecionar funções de servidor colocadas**.</span><span class="sxs-lookup"><span data-stu-id="f8146-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="f8146-113">Em **selecionar funções de servidor posicionadas**, marque a opção **posicionar servidor**de mediação.</span><span class="sxs-lookup"><span data-stu-id="f8146-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="f8146-114">Se o tipo de pool de front-end selecionado for a edição Enterprise, o componente servidor de mediação será instalado em todos os servidores front-end desse pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="f8146-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f8146-115">O <STRONG>próximo pool de saltos</STRONG> usado pelo servidor de mediação será o pool de front-ends em que o servidor de mediação está posicionado.</span><span class="sxs-lookup"><span data-stu-id="f8146-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f8146-116">O <STRONG>pool de bordas</STRONG> usado pelo servidor de mediação será o mesmo pool de bordas associado ao pool de front-ends em que o servidor de mediação está posicionado.</span><span class="sxs-lookup"><span data-stu-id="f8146-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="f8146-117">Clique em **criar padrão** para usar este pool de front-end para direcionar chamadas do Microsoft Office Communications Server 2007 R2 para a PSTN.</span><span class="sxs-lookup"><span data-stu-id="f8146-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="f8146-118">Clique em **concluir** quando terminar de associar um ou mais pares ao pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="f8146-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8146-119">Antes de prosseguir para a próxima etapa no processo de implantação do Enterprise Voice, verifique se o pool do servidor de mediação (ou seja, o pool do front-end com o componente do servidor de mediação está posicionado) está usando os FQDNs que você especificou.</span><span class="sxs-lookup"><span data-stu-id="f8146-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="f8146-120">Em seguida, siga os procedimentos em [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação do guia de implantação para adicionar o servidor de mediação à sua topologia antes de prosseguir para a próxima etapa de modificação das portas de escuta do servidor de mediação, se necessário.</span><span class="sxs-lookup"><span data-stu-id="f8146-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="f8146-121">Você deve publicar sua topologia toda vez que usar o construtor de topologias para definir ou modificar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="f8146-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="f8146-122">Definir servidor de mediação autônomo</span><span class="sxs-lookup"><span data-stu-id="f8146-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="f8146-123">Siga as etapas deste tópico para usar o construtor de topologias a fim de definir um servidor ou pool autônomo de mediação em um site em que o Enterprise Voice não foi implantado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8146-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="f8146-124">Se você já implantou servidores de mediação posicionados em pools front-ends neste site, ignore esta seção e [Instale os arquivos do servidor de mediação no Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) antes de prosseguir com a [configuração de troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="f8146-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8146-125">Esta seção pressupõe que você já tenha configurado pelo menos um pool de front-end, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir e configurar um pool de front-end ou um servidor Standard Edition no Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publicar a topologia no Lync Server 2013</A> no guia de implantação documentação.</span><span class="sxs-lookup"><span data-stu-id="f8146-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="f8146-126">Para adicionar um servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="f8146-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="f8146-127">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f8146-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="f8146-128">No construtor de topologias, na árvore de console, expanda o nome do site para o qual você deseja definir um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="f8146-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="f8146-129">Na árvore de console, clique com o botão \*\*\*\* direito do mouse no nó de pools de mediação e clique em **pool do servidor**de mediação.</span><span class="sxs-lookup"><span data-stu-id="f8146-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="f8146-130">Em **definir novo pool**de mediação, digite o nome de domínio totalmente qualificado (FQDN) do pool do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="f8146-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="f8146-131">Em seguida, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f8146-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="f8146-132">Se você quiser implantar vários servidores de mediação no pool para fornecer alta disponibilidade, selecione **vários pools de computadores**.</span><span class="sxs-lookup"><span data-stu-id="f8146-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f8146-133">Você deve implantar o balanceamento de carga de DNS para dar suporte a pools do servidor de mediação com vários servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="f8146-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="f8146-134">Para obter detalhes, consulte a seção usando o balanceamento de carga de DNS na seção de pools do servidor de mediação do <A href="lync-server-2013-dns-load-balancing.md">balanceamento de carga de DNS no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="f8146-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="f8146-135">Se você quiser implantar apenas um servidor de mediação no pool porque não requer alta disponibilidade, selecione um **único pool de computador**.</span><span class="sxs-lookup"><span data-stu-id="f8146-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="f8146-136">Ignore a etapa seguinte.</span><span class="sxs-lookup"><span data-stu-id="f8146-136">Skip the following step.</span></span>

6.  <span data-ttu-id="f8146-137">Se você selecionou **Pool de Vários Computadores** na etapa anterior, no item **Definir os computadores neste pool**, clique em **FQDN do Computador**, digite o FQDN de cada servidor no pool e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f8146-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="f8146-138">Repita esta etapa para todos os outros servidores de mediação que você deseja adicionar ao pool.</span><span class="sxs-lookup"><span data-stu-id="f8146-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="f8146-139">Quando tiver definido todos os computadores no pool, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f8146-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="f8146-140">Na página **selecionar o próximo salto** , clique em **próximo pool de saltos**, clique no FQDN do pool de front-ends que usará esse pool do servidor de mediação e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f8146-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="f8146-141">Na página **Selecionar um Servidor de Borda**, execute um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f8146-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f8146-142">Se você quiser fornecer conectividade PSTN a usuários externos habilitados para o Enterprise Voice, em **Selecione o pool de bordas usado por este servidor**de mediação, clique no FQDN do pool do servidor de borda que usará esse pool de servidores de mediação para fornecer conectividade PSTN a esses usuários externos e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f8146-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="f8146-143">Se você não planeja habilitar usuários externos para o Enterprise Voice ou se não quiser fornecer conectividade PSTN aos usuários quando eles estiverem fora da rede interna, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f8146-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="f8146-144">Em seguida, siga os procedimentos em [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação de implantação para adicionar o servidor de mediação à topologia.</span><span class="sxs-lookup"><span data-stu-id="f8146-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="f8146-145">Você deve publicar sua topologia toda vez que usar o construtor de topologias para criar ou modificar sua topologia, de modo que os dados possam ser usados para instalar os arquivos para os servidores que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8146-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="f8146-146">Em seguida, prossiga para as próximas etapas para modificar as portas de escuta no servidor de mediação, se necessário.</span><span class="sxs-lookup"><span data-stu-id="f8146-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="f8146-147">Definir as portas de escuta do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="f8146-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="f8146-148">Siga as etapas deste tópico para usar o construtor de topologias a fim de definir as portas de escuta que um servidor ou um pool de mediação aceitará conexões de entrada de um ponto de gateway.</span><span class="sxs-lookup"><span data-stu-id="f8146-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="f8146-149">Para modificar as portas de escuta do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="f8146-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="f8146-150">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f8146-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="f8146-151">No construtor de topologias, na árvore de console, \*\*\*\* expanda o nó de pools de mediação e clique com o botão direito do mouse no servidor de mediação anteriormente criado.</span><span class="sxs-lookup"><span data-stu-id="f8146-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="f8146-152">Por padrão, as portas ouvidas SIP no servidor de mediação são 5070 para tráfego TLS do Lync Server, 5067 para tráfego TLS de pares (gateways, PBXes ou SBCs).</span><span class="sxs-lookup"><span data-stu-id="f8146-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="f8146-153">A porta TCP é desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="f8146-153">TCP port is disabled by default.</span></span> <span data-ttu-id="f8146-154">Você deve habilitar a porta TCP se tiver gateways que não oferecem suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="f8146-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="f8146-155">Especificar o intervalo de portas de escuta de TLS ou TCP desejadas o servidor de mediação aceitará conexões de entrada de gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="f8146-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8146-156">Não é necessário inserir um intervalo de portas TCP se a opção <STRONG>Habilitar porta TCP</STRONG> não estiver marcada.</span><span class="sxs-lookup"><span data-stu-id="f8146-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="f8146-157">Essa configuração é opcional.</span><span class="sxs-lookup"><span data-stu-id="f8146-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="f8146-158">Em seguida, [defina um gateway no construtor de topologias no Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) e instale os arquivos em cada servidor de mediação no pool, seguindo os procedimentos em [instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="f8146-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

