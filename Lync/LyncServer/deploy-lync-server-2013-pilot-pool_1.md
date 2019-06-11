---
title: Implantar o pool piloto do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e9068ca3ff5a2827991869598a2066473cc5af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="b93a6-102">Implantar o pool piloto do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b93a6-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b93a6-103">_**Tópico da última modificação:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="b93a6-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="b93a6-104">Uma das primeiras etapas necessárias para a migração para o Lync Server 2013 é implantar um pool piloto.</span><span class="sxs-lookup"><span data-stu-id="b93a6-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="b93a6-105">O pool piloto é onde você testa a coexistência do Lync Server 2013 com a implantação do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b93a6-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="b93a6-106">A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b93a6-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="b93a6-107">Ao implantar um pool piloto, use o assistente para definir novo pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="b93a6-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="b93a6-108">Você deve implantar os mesmos recursos e cargas de trabalho no pool piloto do Lync Server 2013 que você tem no pool do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b93a6-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="b93a6-109">Se você implantou o arquivamento do servidor, o Monitoring Server ou o System Center Operations Manager para arquivar ou monitorar seu ambiente do Office Communications Server 2007 R2 e deseja continuar a arquivar ou monitorar durante a migração, é preciso Além disso, implante esses recursos em seu ambiente piloto.</span><span class="sxs-lookup"><span data-stu-id="b93a6-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="b93a6-110">A versão que você implantou para arquivar ou monitorar seu ambiente do Office Communications Server 2007 R2 não capturará dados em seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b93a6-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b93a6-111">O procedimento a seguir discute os recursos e configurações que devem ser considerados como parte do processo de implantação do pool piloto geral.</span><span class="sxs-lookup"><span data-stu-id="b93a6-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="b93a6-112">Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto.</span><span class="sxs-lookup"><span data-stu-id="b93a6-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="b93a6-113">Para obter etapas detalhadas, consulte o guia de implantação implantando o <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="b93a6-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="b93a6-114">**Para implantar um pool piloto do Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="b93a6-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="b93a6-115">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b93a6-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b93a6-116">Abra o construtor de topologias e escolha criar uma nova topologia.</span><span class="sxs-lookup"><span data-stu-id="b93a6-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="b93a6-117">Digite o domínio SIP primário.</span><span class="sxs-lookup"><span data-stu-id="b93a6-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="b93a6-118">![Criar nova topologia, definir página de domínio primário] (images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Criar nova topologia, definir página de domínio primário")</span><span class="sxs-lookup"><span data-stu-id="b93a6-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="b93a6-119">Continue a preencher o assistente até chegar ao assistente **definir o novo pool de front-end** .</span><span class="sxs-lookup"><span data-stu-id="b93a6-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="b93a6-120">Click Next.</span><span class="sxs-lookup"><span data-stu-id="b93a6-120">Click Next.</span></span>

5.  <span data-ttu-id="b93a6-121">Digite o FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="b93a6-121">Enter the pool FQDN.</span></span> <span data-ttu-id="b93a6-122">Ao definir o pool piloto, você pode optar por implantar um pool de front-end do Enterprise Edition ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b93a6-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="b93a6-123">O Lync Server 2013 não requer que seus recursos de pool piloto correspondam ao que foi implantado em seu pool herdado.</span><span class="sxs-lookup"><span data-stu-id="b93a6-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b93a6-124">O nome de domínio totalmente qualificado (FQDN) do pool ou do servidor que você define para o pool piloto deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="b93a6-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="b93a6-125">Ele não pode corresponder ao nome do pool do Office Communications Server 2007 R2 atualmente implantado ou de qualquer outro servidor atualmente implantado.</span><span class="sxs-lookup"><span data-stu-id="b93a6-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="b93a6-126">![Definir a página de FQDN do pool de front-end] (images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definir a página de FQDN do pool de front-end")</span><span class="sxs-lookup"><span data-stu-id="b93a6-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="b93a6-127">Defina o computador que será adicionado ao pool.</span><span class="sxs-lookup"><span data-stu-id="b93a6-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="b93a6-128">![Caixa de diálogo Definir novo pool de front-end] (images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Caixa de diálogo Definir novo pool de front-end")</span><span class="sxs-lookup"><span data-stu-id="b93a6-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="b93a6-129">Na página **selecionar recursos** , marque as caixas de seleção dos recursos que você deseja neste pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="b93a6-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="b93a6-130">Por exemplo, se você estiver implantando apenas mensagens instantâneas e recursos de presença, marque a caixa de seleção conferência para permitir mensagens instantâneas com vários participantes, mas não marque as caixas de seleção conferência discada (PSTN), Enterprise Voice ou controle de admissão de chamadas, Porque elas representam recursos de voz, vídeo e conferência colaborativa.</span><span class="sxs-lookup"><span data-stu-id="b93a6-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="b93a6-131">Para obter informações adicionais sobre a seleção de recursos, consulte [definir e configurar um servidor front-end ou um servidor Standard Edition no Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b93a6-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="b93a6-132">![Página de seleção de recursos do pool de front-end] (images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de seleção de recursos do pool de front-end")</span><span class="sxs-lookup"><span data-stu-id="b93a6-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="b93a6-133">Na página **selecionar funções de servidor posicionadas** , recomendamos posicionar o servidor de mediação no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b93a6-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="b93a6-134">Ao mesclar uma topologia herdada com o Lync Server 2013, precisamos primeiro colocar o servidor de mediação do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b93a6-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="b93a6-135">Depois de mesclar as topologias e configurar o servidor de mediação do Lync Server 2013, você pode decidir se deseja manter o servidor de mediação posicionado ou alterá-lo para um servidor autônomo ao mover a função do servidor de mediação para o Lync Server 2013 mais tarde na implantação com.</span><span class="sxs-lookup"><span data-stu-id="b93a6-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="b93a6-136">![Grupo de front-end selecionar página de funções de servidor posicionada] (images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Grupo de front-end selecionar página de funções de servidor posicionada")</span><span class="sxs-lookup"><span data-stu-id="b93a6-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="b93a6-137">Na página **associar funções de servidor a este pool de front-end** , durante a implantação do pool piloto, não escolha **habilitar um pool de bordas para ser usado pelo componente de mídia dessa opção do pool de front-end** .</span><span class="sxs-lookup"><span data-stu-id="b93a6-137">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="b93a6-138">Este é um recurso que você habilitará e colocará online em uma fase posterior da migração.</span><span class="sxs-lookup"><span data-stu-id="b93a6-138">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="b93a6-139">Mantenha essa configuração desmarcada por enquanto.</span><span class="sxs-lookup"><span data-stu-id="b93a6-139">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="b93a6-140">![Associar funções de servidor com a página de pool de front-end] (images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associar funções de servidor com a página de pool de front-end")</span><span class="sxs-lookup"><span data-stu-id="b93a6-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="b93a6-141">Na página **selecionar um servidor dos Office Web Apps** , clique em **novo**e especifique o FQDN do servidor de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b93a6-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="b93a6-142">![Definir novas propriedades de FQDN do servidor do Office Web Apps] (images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir novas propriedades de FQDN do servidor do Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="b93a6-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="b93a6-143">Na página **definir a loja do SQL Server Store** , selecione a instância do SQL Server criada anteriormente para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b93a6-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="b93a6-144">![Página definir o arquivamento da loja do SQL Server] (images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Página definir o arquivamento da loja do SQL Server")</span><span class="sxs-lookup"><span data-stu-id="b93a6-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="b93a6-145">Na página **definir o monitoramento do SQL Server Store** , selecione a instância do SQL Server criada anteriormente para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b93a6-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="b93a6-146">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b93a6-146">Click **Finish**.</span></span>

13. <span data-ttu-id="b93a6-147">No nó superior do construtor de topologias, clique com o botão direito do mouse no **Lync Server** e clique em **Editar propriedades.**</span><span class="sxs-lookup"><span data-stu-id="b93a6-147">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.**</span></span> <span data-ttu-id="b93a6-148">Clique em **URLs simples**.</span><span class="sxs-lookup"><span data-stu-id="b93a6-148">Click **Simple URLs**.</span></span>

14. <span data-ttu-id="b93a6-149">Atualize a **URL de acesso administrativo**.</span><span class="sxs-lookup"><span data-stu-id="b93a6-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="b93a6-150">![Editar propriedades, página de URLs simples] (images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Editar propriedades, página de URLs simples")</span><span class="sxs-lookup"><span data-stu-id="b93a6-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="b93a6-151">Para obter informações adicionais sobre URLs simples, consulte o tópico [Editar ou configurar URLs simples no Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b93a6-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="b93a6-152">Em **Editar propriedades**, clique em **servidor de gerenciamento central**.</span><span class="sxs-lookup"><span data-stu-id="b93a6-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="b93a6-153">Na lista suspensa, selecione o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b93a6-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="b93a6-154">![Editar propriedades, página do servidor de gerenciamento central] (images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Editar propriedades, página do servidor de gerenciamento central")</span><span class="sxs-lookup"><span data-stu-id="b93a6-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="b93a6-155">Clique em OK para fechar **a página Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="b93a6-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="b93a6-156">No menu **ação** , selecione **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="b93a6-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="b93a6-157">Quando o processo de publicação for concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="b93a6-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="b93a6-158">Retornando ao assistente de implantação do Lync Server 2013, clique em **instalar ou atualizar o sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b93a6-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="b93a6-159">![Assistente de implantação do Lync Server 2013] (images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Assistente de implantação do Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="b93a6-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="b93a6-160">Para instalar uma cópia local do repositório de configurações e iniciar os serviços necessários, consulte [Configurando servidores front-end e pools front-end para o Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b93a6-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

