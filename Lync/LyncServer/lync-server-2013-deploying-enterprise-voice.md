---
title: 'Lync Server 2013: Implantando o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c49eeb26e17b337dae3f8b6944f25f2d41906f3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="a1e73-102">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1e73-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a1e73-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a1e73-104">Lync Server 2013, o Enterprise Voice é parte da infraestrutura 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1e73-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="a1e73-105">A implantação do Enterprise Voice requer que você:</span><span class="sxs-lookup"><span data-stu-id="a1e73-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="a1e73-106">Examine a seção [planejamento do Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) da documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a1e73-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="a1e73-107">Finalize os planos de recursos e componentes para implantação com essa carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a1e73-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="a1e73-108">Execute a ferramenta de planejamento para projetar uma topologia que reflita suas decisões de implantação.</span><span class="sxs-lookup"><span data-stu-id="a1e73-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="a1e73-109">Abra o design de topologia no construtor de topologias, conforme descrito em [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a1e73-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1e73-110">A instalação do construtor de topologias faz parte do processo de implantação do pool interno.</span><span class="sxs-lookup"><span data-stu-id="a1e73-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="a1e73-111">Para obter detalhes, consulte <A href="lync-server-2013-install-lync-server-administrative-tools.md">install Lync Server 2013 Administrative Tools</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a1e73-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="a1e73-112">Além disso, você já deve ter implantado o Lync Server, Enterprise Edition em sites centrais e sites de filial que correspondem à topologia de referência que você escolhe implantar.</span><span class="sxs-lookup"><span data-stu-id="a1e73-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="a1e73-113">Não é possível implantar componentes do Enterprise Voice até que você tenha definido, publicado e instalado arquivos para pelo menos um pool interno, e você deve usar o construtor de topologias para definir e publicar um pool interno.</span><span class="sxs-lookup"><span data-stu-id="a1e73-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="a1e73-114">Para exibir as topologias de referência com exemplos de onde as funções de servidor Enterprise Voice podem ser implantadas (e sua relação com outras funções de servidor do Lync Server 2013), consulte [Reference topologias in Lync server 2013](lync-server-2013-reference-topologies.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a1e73-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="a1e73-115">Para exibir uma topologia de referência que ilustra e explica um exemplo de implantação de controle de admissão de chamadas, incluindo regiões de rede, sites de rede e sub-redes, consulte [exemplo: reunindo seus requisitos para controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a1e73-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a1e73-116">Para implantar o Enterprise Voice em um site central, continue lendo os tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="a1e73-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="a1e73-117">Para implantar o Enterprise Voice em um site de filial, vá para <A href="lync-server-2013-deploying-branch-sites.md">implantando sites de filial no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a1e73-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="a1e73-118">Esta seção inclui procedimentos para implantações nas quais um Servidor de mediação é colocado em cada Servidor Front-End ou servidor Standard Edition, conforme recomendado, e também para implantações com um pool de Servidor de mediação autônomo.</span><span class="sxs-lookup"><span data-stu-id="a1e73-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="a1e73-119">Você pode ignorar o seguinte conteúdo se você usou o construtor de topologias para definir e publicar uma topologia que coloca um servidor de mediação em cada servidor front-end ou servidor Standard Edition, porque o assistente de implantação já instalou automaticamente os arquivos para Servidor de mediação quando você instalou arquivos para o pool de servidores front-end ou servidor Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="a1e73-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="a1e73-120">Configurando troncos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="a1e73-121">Se você usou o construtor de topologias para definir e publicar um servidor de mediação em um pool autônomo, você pode usar o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="a1e73-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="a1e73-122">Verifique se a topologia atende aos pré-requisitos de software e de ambiente, conforme descrito em [pré-requisitos do Enterprise Voice para Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a1e73-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1e73-123">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a1e73-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="a1e73-124">Pré-requisitos do Enterprise Voice para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-125">Implantando servidores de mediação e definindo pares no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-126">Configurando troncos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-127">Configurando planos de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-128">Configurando políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-129">Exportando e importando a configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-130">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-131">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-132">Implantando a UM do Exchange local para fornecer correio de voz do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-133">Fornecimento de mensagens de voz para usuários do Lync Server 2013 no Exchange UM hospedado</span><span class="sxs-lookup"><span data-stu-id="a1e73-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-134">Configurando a integração do Lync Server 2013 local com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a1e73-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-135">Implantando recursos avançados do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="a1e73-136">Sobre regiões de rede, sites e sub-redes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="a1e73-137">Criar ou modificar uma região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="a1e73-138">Criar ou modificar um site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="a1e73-139">Associar uma sub-rede a um site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="a1e73-140">Configurar o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="a1e73-141">Configurar o 9-1-1 avançado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="a1e73-142">Configurar bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="a1e73-143">Habilitar usuários para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1e73-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="a1e73-144">See Also</span></span>


[<span data-ttu-id="a1e73-145">Implantando sites de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="a1e73-146">Configurando a conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="a1e73-147">Configurando o estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="a1e73-148">Configurando comunicados para números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="a1e73-149">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e73-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

