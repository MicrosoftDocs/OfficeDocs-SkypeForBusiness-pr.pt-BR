---
title: Implantar o pool piloto do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c97ea5304309aaf635ac284e792a73634c5ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="1498c-102">Implantar o pool piloto do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1498c-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1498c-103">_**Última modificação do tópico:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="1498c-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="1498c-104">Uma das primeiras etapas necessárias para a migração para o Lync Server 2013 é implantar um pool piloto.</span><span class="sxs-lookup"><span data-stu-id="1498c-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="1498c-105">O pool piloto é onde você testar a coexistência do Lync Server 2013 com a implantação do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1498c-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="1498c-106">A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1498c-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="1498c-107">Ao implantar um pool piloto, você usa o Assistente Definir novo pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="1498c-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="1498c-108">Você deve implantar os mesmos recursos e cargas de trabalho no pool piloto do Lync Server 2013 que você tem no pool do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1498c-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="1498c-109">Se você implantou o servidor de arquivamento, o Monitoring Server ou o System Center Operations Manager para arquivamento ou monitoramento do seu ambiente do Office Communications Server 2007 R2 e deseja continuar arquivando ou monitorando durante a migração, precisará Além disso, implante esses recursos no seu ambiente piloto.</span><span class="sxs-lookup"><span data-stu-id="1498c-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="1498c-110">A versão implantada para arquivar ou monitorar o ambiente do Office Communications Server 2007 R2 não capturará dados no seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1498c-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1498c-111">O procedimento a seguir discute os recursos e configurações que você deve considerar como parte do processo de implantação do pool piloto.</span><span class="sxs-lookup"><span data-stu-id="1498c-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="1498c-112">Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto.</span><span class="sxs-lookup"><span data-stu-id="1498c-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="1498c-113">Para obter etapas detalhadas, consulte o guia de implantação do <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 de implantação</A> .</span><span class="sxs-lookup"><span data-stu-id="1498c-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="1498c-114">**Para implantar um pool piloto do Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="1498c-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="1498c-115">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1498c-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="1498c-116">Abra o Construtor de Topologia e selecione criar uma nova topologia.</span><span class="sxs-lookup"><span data-stu-id="1498c-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="1498c-117">Insira o domínio SIP primário.</span><span class="sxs-lookup"><span data-stu-id="1498c-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="1498c-118">![Criar nova topologia, definir página de domínio primário](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Criar nova topologia, definir página de domínio primário")</span><span class="sxs-lookup"><span data-stu-id="1498c-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="1498c-119">Continue completando o assistente até que chegue no assistente **Assistente Definir o novo pool de Front-Ends**.</span><span class="sxs-lookup"><span data-stu-id="1498c-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="1498c-120">Clique em Próximo.</span><span class="sxs-lookup"><span data-stu-id="1498c-120">Click Next.</span></span>

5.  <span data-ttu-id="1498c-121">Insira o FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="1498c-121">Enter the pool FQDN.</span></span> <span data-ttu-id="1498c-122">Ao definir o pool piloto, você pode optar por implantar um pool de front-ends Enterprise Edition ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1498c-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="1498c-123">O Lync Server 2013 não exige que os recursos do pool piloto correspondam ao que foi implantado em seu pool herdado.</span><span class="sxs-lookup"><span data-stu-id="1498c-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1498c-124">O pool ou o FQDN definido para seu pool piloto deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="1498c-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="1498c-125">Ele não pode corresponder ao nome do pool do Office Communications Server 2007 R2 atualmente implantado ou de qualquer outro servidor atualmente implantado.</span><span class="sxs-lookup"><span data-stu-id="1498c-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="1498c-126">![Definir a página FQDN do pool de front-ends](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definir a página FQDN do pool de front-ends")</span><span class="sxs-lookup"><span data-stu-id="1498c-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="1498c-127">Defina o computador que será adicionado ao pool.</span><span class="sxs-lookup"><span data-stu-id="1498c-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="1498c-128">![Caixa de diálogo Definir novo pool de front-ends](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Caixa de diálogo Definir novo pool de front-ends")</span><span class="sxs-lookup"><span data-stu-id="1498c-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="1498c-129">Na página **Selecionar recursos**, marque as caixas de seleção para os recursos que você deseja neste pool de Front-Ends.</span><span class="sxs-lookup"><span data-stu-id="1498c-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="1498c-130">Por exemplo, se estiver implantando apenas mensagens instantâneas e recursos de presença, você deve selecionar a caixa de seleção Conferência para permitir as mensagens instantâneas com vários participantes, mas não marca as caixas de seleção Conferência discada (PSTN), Enterprise Voice ou Controle de Admissão de Chamadas, porque estas representam voz, vídeo e recursos de conferência colaborativos.</span><span class="sxs-lookup"><span data-stu-id="1498c-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="1498c-131">Para obter informações adicionais sobre como selecionar recursos, consulte [define and configure a front end pool or Standard Edition Server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="1498c-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="1498c-132">![Página de seleção de recursos do pool de front-ends](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de seleção de recursos do pool de front-ends")</span><span class="sxs-lookup"><span data-stu-id="1498c-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="1498c-133">Na página **selecionar funções de servidor posicionadas** , recomendamos colocar o servidor de mediação no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1498c-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="1498c-134">Ao mesclar uma topologia herdada com o Lync Server 2013, exige que você primeiro coloque o servidor de mediação do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1498c-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="1498c-135">Após mesclar as topologias e configurar o servidor de mediação do Lync Server 2013, você pode decidir se deseja manter o servidor de mediação posicionado ou alterá-lo para um servidor autônomo quando mover a função de servidor de mediação para o Lync Server 2013 mais tarde na implantação -.</span><span class="sxs-lookup"><span data-stu-id="1498c-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="1498c-136">![Página de funções de servidor do pool de front-ends selecionar](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página de funções de servidor do pool de front-ends selecionar")</span><span class="sxs-lookup"><span data-stu-id="1498c-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="1498c-p109">Na página **Associar Funções de Servidor com este Pool de Front End**, durante a implantação do pool piloto, não escolha a opção **Habilitar um pool de Borda a ser usado pelo componente de mídia deste pool de front-end**. Esse recurso será ativado e colocado online em uma fase posterior da migração. Mantenha essa configuração desmarcada por enquanto.</span><span class="sxs-lookup"><span data-stu-id="1498c-p109">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="1498c-140">![Página associar funções de servidor com pool de front-ends](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página associar funções de servidor com pool de front-ends")</span><span class="sxs-lookup"><span data-stu-id="1498c-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="1498c-141">Na página**Selecione um servidor dos aplicativos web do Office**, clique em **Novo**, e especifique o FQDN do servidor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="1498c-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="1498c-142">![Definir novas propriedades de FQDN do servidor do Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir novas propriedades de FQDN do servidor do Office Web Apps")</span><span class="sxs-lookup"><span data-stu-id="1498c-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="1498c-143">Na página **definir o repositório de arquivamento do SQL Server** , selecione a instância do SQL Server criada anteriormente para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1498c-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="1498c-144">![Página Definir repositório do SQL Server de arquivamento](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Página Definir repositório do SQL Server de arquivamento")</span><span class="sxs-lookup"><span data-stu-id="1498c-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="1498c-145">Na página **definir o repositório do SQL Server de monitoramento** , selecione a instância do SQL Server criada anteriormente para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1498c-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="1498c-146">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="1498c-146">Click **Finish**.</span></span>

13. <span data-ttu-id="1498c-p111">A partir do nó do topo do Construtor de Topologia, clique com o botão direito em **Lync Server** e clique em **Editar Propriedades.** Clique em **URLs simples**.</span><span class="sxs-lookup"><span data-stu-id="1498c-p111">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.** Click **Simple URLs**.</span></span>

14. <span data-ttu-id="1498c-149">Atualize a **URL de acesso administrativo**.</span><span class="sxs-lookup"><span data-stu-id="1498c-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="1498c-150">![Editar propriedades, página de URLs simples](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Editar propriedades, página de URLs simples")</span><span class="sxs-lookup"><span data-stu-id="1498c-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="1498c-151">Para obter informações adicionais sobre URLs simples, consulte o tópico [Editar ou configurar URLs simples no Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="1498c-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="1498c-152">A partir de **Editar Propriedades**, clique em **Servidor de Gerenciamento Central**.</span><span class="sxs-lookup"><span data-stu-id="1498c-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="1498c-153">Na lista suspensa, selecione o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1498c-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="1498c-154">![Página Editar propriedades, servidor de gerenciamento central](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Página Editar propriedades, servidor de gerenciamento central")</span><span class="sxs-lookup"><span data-stu-id="1498c-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="1498c-155">Clique em OK para fechar a página**Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1498c-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="1498c-156">A partir do menu **Ação**, selecione **Publicar Topologia**.</span><span class="sxs-lookup"><span data-stu-id="1498c-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="1498c-157">Quando o processo de publicação for concluído, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1498c-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="1498c-158">Retornando ao assistente de implantação do Lync Server 2013, clique em **instalar ou atualizar o sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1498c-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="1498c-159">![Assistente de implantação do Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Assistente de implantação do Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="1498c-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="1498c-160">Para instalar uma cópia local do repositório de configuração e iniciar os serviços necessários, consulte [setting up front end Servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="1498c-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

