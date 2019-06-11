---
title: Implantar o pool piloto do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fb3c5062cc1f817d3de7b869f57600178ad454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="da321-102">Implantar o pool piloto do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da321-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da321-103">_**Tópico da última modificação:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="da321-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="da321-104">Uma das primeiras etapas necessárias para a migração para o Lync Server 2013 é implantar um pool piloto.</span><span class="sxs-lookup"><span data-stu-id="da321-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="da321-105">O pool piloto é onde você testa a coexistência do Lync Server 2013 com a implantação do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="da321-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="da321-106">A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da321-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="da321-107">Ao implantar um pool piloto, use o assistente para definir novo pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="da321-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="da321-108">Você deve implantar os mesmos recursos e cargas de trabalho no pool piloto do Lync Server 2013 que você tem no pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="da321-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="da321-109">Se você implantou o arquivamento do servidor, o Monitoring Server ou o System Center Operations Manager para arquivar ou monitorar seu ambiente do Lync Server 2010 e deseja continuar a arquivar ou monitorar durante a migração, também é necessário implantar esses recursos em seu ambiente piloto.</span><span class="sxs-lookup"><span data-stu-id="da321-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="da321-110">A versão que você implantou para arquivar ou monitorar seu ambiente do Lync Server 2010 não capturará dados em seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da321-110">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da321-111">O procedimento a seguir discute os recursos e configurações que devem ser considerados como parte do processo de implantação do pool piloto geral.</span><span class="sxs-lookup"><span data-stu-id="da321-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="da321-112">Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto.</span><span class="sxs-lookup"><span data-stu-id="da321-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="da321-113">Para obter etapas detalhadas, consulte o guia de implantação implantando o <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="da321-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="da321-114">**Para implantar um pool piloto do Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="da321-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="da321-115">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="da321-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="da321-116">Expanda a árvore até acessar os pools de **front-end**do **Lync Server 2013** Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="da321-116">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="da321-117">Clique com o botão direito do mouse em **pools front end do Enterprise Edition**e selecione **novo pool de front-end**.</span><span class="sxs-lookup"><span data-stu-id="da321-117">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="da321-118">![Submenu de seleção do pool de servidores do construtor de topologia] (images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Submenu de seleção do pool de servidores do construtor de topologia")</span><span class="sxs-lookup"><span data-stu-id="da321-118">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="da321-119">Digite o FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="da321-119">Enter the pool FQDN.</span></span> <span data-ttu-id="da321-120">Ao definir o pool piloto, você pode optar por implantar um pool de front-end do Enterprise Edition ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="da321-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="da321-121">O Lync Server 2013 não requer que seus recursos de pool piloto correspondam ao que foi implantado em seu pool herdado.</span><span class="sxs-lookup"><span data-stu-id="da321-121">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="da321-122">O nome de domínio totalmente qualificado (FQDN) do pool ou do servidor que você define para o pool piloto deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="da321-122">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="da321-123">Ele não pode corresponder ao nome do pool do Lync Server 2010 implantado no momento ou a qualquer outro servidor atualmente implantado.</span><span class="sxs-lookup"><span data-stu-id="da321-123">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="da321-124">![Assistente para definir novo pool de front-ends. página FQDN] (images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Assistente para definir novo pool de front-ends. página FQDN")</span><span class="sxs-lookup"><span data-stu-id="da321-124">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="da321-125">Na página **selecionar recursos** , marque as caixas de seleção dos recursos que você deseja neste pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="da321-125">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="da321-126">Por exemplo, se você estiver implantando apenas mensagens instantâneas e recursos de presença, marque a caixa de seleção conferência para permitir mensagens instantâneas com vários participantes, mas não marque as caixas de seleção conferência discada (PSTN), Enterprise Voice ou controle de admissão de chamadas, Porque elas representam recursos de voz, vídeo e conferência colaborativa.</span><span class="sxs-lookup"><span data-stu-id="da321-126">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="da321-127">Para obter informações adicionais sobre a seleção de recursos, consulte [definir e configurar um servidor front-end ou um servidor Standard Edition no Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="da321-127">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="da321-128">![Página de seleção de recursos do pool de front-end] (images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de seleção de recursos do pool de front-end")</span><span class="sxs-lookup"><span data-stu-id="da321-128">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="da321-129">Na página **selecionar funções de servidor posicionadas** , recomendamos posicionar o servidor de mediação no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da321-129">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="da321-130">Ao mesclar uma topologia herdada com o Lync Server 2013, precisamos primeiro colocar o servidor de mediação do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="da321-130">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="da321-131">Depois de mesclar as topologias e configurar o servidor de mediação do Lync Server 2013, você pode decidir se deseja manter o servidor de mediação posicionado ou alterá-lo para um servidor autônomo ao mover a função do servidor de mediação para o Lync Server 2013 mais tarde na implantação com.</span><span class="sxs-lookup"><span data-stu-id="da321-131">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="da321-132">![Grupo de front-end selecionar página de funções de servidor posicionada] (images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Grupo de front-end selecionar página de funções de servidor posicionada")</span><span class="sxs-lookup"><span data-stu-id="da321-132">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="da321-133">Na página **associar funções de servidor a este pool de front-end** , durante a implantação do pool piloto, não escolha **habilitar um pool de bordas para ser usado pelo componente de mídia dessa opção do pool de front-end** .</span><span class="sxs-lookup"><span data-stu-id="da321-133">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="da321-134">Este é um recurso que você habilitará e colocará online em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="da321-134">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="da321-135">Mantenha essa configuração desmarcada por enquanto.</span><span class="sxs-lookup"><span data-stu-id="da321-135">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="da321-136">![Associar funções de servidor com a página de pool de front-end] (images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associar funções de servidor com a página de pool de front-end")</span><span class="sxs-lookup"><span data-stu-id="da321-136">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="da321-137">Na página **selecionar um servidor dos Office Web Apps** , clique em **novo**e especifique o FQDN do servidor de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="da321-137">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="da321-138">![Definir novas propriedades de FQDN do servidor do Office Web Apps] (images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir novas propriedades de FQDN do servidor do Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="da321-138">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="da321-139">Na página **definir a loja do SQL Server Store** , ao definir a loja do SQL Server para o arquivamento e o monitoramento do Lync Server, selecione a instância do SQL Server criada anteriormente para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da321-139">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="da321-140">![Página definir o arquivamento da loja do SQL Server] (images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Página definir o arquivamento da loja do SQL Server")</span><span class="sxs-lookup"><span data-stu-id="da321-140">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="da321-141">Para publicar sua topologia, clique com o botão direito do mouse no nó do **Lync Server** e, em seguida, clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="da321-141">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="da321-142">![Construtor de topologias exibindo uma topologia] configurada (images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Construtor de topologias exibindo uma topologia") configurada</span><span class="sxs-lookup"><span data-stu-id="da321-142">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="da321-143">Quando o processo de publicação for concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="da321-143">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="da321-144">Para instalar uma cópia local do repositório de configurações e iniciar os serviços necessários, consulte [Configurando servidores front-end e pools front-end para o Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="da321-144">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

