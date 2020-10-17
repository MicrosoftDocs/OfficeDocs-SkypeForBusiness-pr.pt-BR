---
title: Implantar o pool piloto do Lync Server 2013
description: Implantar o pool piloto do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a599cee1719f773ebbf3cf5a71405aa9b7259261
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550787"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="e406e-103">Implantar o pool piloto do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e406e-103">Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e406e-104">_**Última modificação do tópico:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="e406e-104">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="e406e-105">Uma das primeiras etapas necessárias para a migração para o Lync Server 2013 é implantar um pool piloto.</span><span class="sxs-lookup"><span data-stu-id="e406e-105">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="e406e-106">O pool piloto é onde você testar a coexistência do Lync Server 2013 com sua implantação do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e406e-106">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="e406e-107">A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e406e-107">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="e406e-108">Ao implantar um pool piloto, você usa o Assistente Definir novo pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e406e-108">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="e406e-109">Você deve implantar os mesmos recursos e cargas de trabalho no pool piloto do Lync Server 2013 que você tem no pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e406e-109">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="e406e-110">Se você implantou o servidor de arquivamento, o Monitoring Server ou o System Center Operations Manager para arquivamento ou monitoramento do seu ambiente do Lync Server 2010 e deseja continuar o arquivamento ou monitoramento durante a migração, também é necessário implantar esses recursos no seu ambiente piloto.</span><span class="sxs-lookup"><span data-stu-id="e406e-110">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="e406e-111">A versão que você implantou para arquivar ou monitorar seu ambiente do Lync Server 2010 não capturará dados no seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e406e-111">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e406e-112">O procedimento a seguir discute os recursos e configurações que você deve considerar como parte do processo de implantação do pool piloto.</span><span class="sxs-lookup"><span data-stu-id="e406e-112">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="e406e-113">Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto.</span><span class="sxs-lookup"><span data-stu-id="e406e-113">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="e406e-114">Para obter etapas detalhadas, consulte o guia de implantação do <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 de implantação</A> .</span><span class="sxs-lookup"><span data-stu-id="e406e-114">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="e406e-115">**Para implantar um pool piloto do Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="e406e-115">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="e406e-116">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e406e-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e406e-117">Expanda a árvore até atingir **pools de front-ends**do **Lync Server 2013** Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="e406e-117">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="e406e-118">Clique com o botão direito em **Pools de front end do Enterprise Edition**, e selecione **Novo pool de front end**.</span><span class="sxs-lookup"><span data-stu-id="e406e-118">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="e406e-119">![Submenu seleção do pool de servidores do construtor de topologia](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Submenu seleção do pool de servidores do construtor de topologia")</span><span class="sxs-lookup"><span data-stu-id="e406e-119">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="e406e-120">Insira FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="e406e-120">Enter the pool FQDN.</span></span> <span data-ttu-id="e406e-121">Ao definir o pool piloto, você pode optar por implantar um pool de front-ends Enterprise Edition ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e406e-121">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="e406e-122">O Lync Server 2013 não exige que os recursos do pool piloto correspondam ao que foi implantado em seu pool herdado.</span><span class="sxs-lookup"><span data-stu-id="e406e-122">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e406e-123">O pool ou o FQDN definido para seu pool piloto deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="e406e-123">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="e406e-124">Ele não pode corresponder ao nome do pool do Lync Server 2010 atualmente implantado ou de qualquer outro servidor atualmente implantado.</span><span class="sxs-lookup"><span data-stu-id="e406e-124">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="e406e-125">![Página Definir FQDN do assistente de novo pool de front-ends](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Página Definir FQDN do assistente de novo pool de front-ends")</span><span class="sxs-lookup"><span data-stu-id="e406e-125">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="e406e-126">Na página **Selecionar recursos**, marque as caixas de seleção para os recursos que você deseja neste pool de Front-Ends.</span><span class="sxs-lookup"><span data-stu-id="e406e-126">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="e406e-127">Por exemplo, se estiver implantando apenas mensagens instantâneas e recursos de presença, você deve selecionar a caixa de seleção Conferência para permitir as mensagens instantâneas com vários participantes, mas não marca as caixas de seleção Conferência discada (PSTN), Enterprise Voice ou Controle de Admissão de Chamadas, porque estas representam voz, vídeo e recursos de conferência colaborativos.</span><span class="sxs-lookup"><span data-stu-id="e406e-127">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="e406e-128">Para obter informações adicionais sobre como selecionar recursos, consulte [define and configure a front end pool or Standard Edition Server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="e406e-128">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="e406e-129">![Página de seleção de recursos do pool de front-ends](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de seleção de recursos do pool de front-ends")</span><span class="sxs-lookup"><span data-stu-id="e406e-129">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="e406e-130">Na página **selecionar funções de servidor posicionadas** , recomendamos colocar o servidor de mediação no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e406e-130">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="e406e-131">Ao mesclar uma topologia herdada com o Lync Server 2013, exigimos que você primeiro coloque o servidor de mediação do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e406e-131">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="e406e-132">Após mesclar as topologias e configurar o servidor de mediação do Lync Server 2013, você pode decidir se deseja manter o servidor de mediação colocado ou alterá-lo para um servidor autônomo quando mover a função de servidor de mediação para o Lync Server 2013 mais tarde no processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="e406e-132">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="e406e-133">![Página de funções de servidor do pool de front-ends selecionar](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página de funções de servidor do pool de front-ends selecionar")</span><span class="sxs-lookup"><span data-stu-id="e406e-133">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="e406e-p108">Na página **Associar Funções de Servidor com este Pool de Front End**, durante a implantação do pool piloto, não escolha a opção **Habilitar um pool de Borda a ser usado pelo componente de mídia deste pool de front-end**. Esse recurso será ativado e colocado online em uma fase posterior da migração. Mantenha essa configuração desmarcada por enquanto.</span><span class="sxs-lookup"><span data-stu-id="e406e-p108">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="e406e-137">![Página associar funções de servidor com pool de front-ends](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página associar funções de servidor com pool de front-ends")</span><span class="sxs-lookup"><span data-stu-id="e406e-137">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="e406e-138">Na página**Selecione um servidor dos aplicativos web do Office**, clique em **Novo**, e especifique o FQDN do servidor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e406e-138">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="e406e-139">![Definir novas propriedades de FQDN do servidor do Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir novas propriedades de FQDN do servidor do Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="e406e-139">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="e406e-140">Na página **definir o repositório de arquivamento do SQL Server** , ao definir o repositório do SQL Server para o arquivamento e o monitoramento do Lync Server, selecione a instância do SQL Server criada anteriormente para o lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e406e-140">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="e406e-141">![Página Definir repositório do SQL Server de arquivamento](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Página Definir repositório do SQL Server de arquivamento")</span><span class="sxs-lookup"><span data-stu-id="e406e-141">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="e406e-142">Para publicar sua topologia, clique com o botão direito no nó do **Lync Server** e clique em **Publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="e406e-142">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="e406e-143">![Construtor de topologia exibindo uma topologia configurada](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Construtor de topologia exibindo uma topologia configurada")</span><span class="sxs-lookup"><span data-stu-id="e406e-143">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="e406e-144">Quando o processo de publicação for concluído, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e406e-144">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="e406e-145">Para instalar uma cópia local do repositório de configuração e iniciar os serviços necessários, consulte [setting up front end Servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="e406e-145">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

