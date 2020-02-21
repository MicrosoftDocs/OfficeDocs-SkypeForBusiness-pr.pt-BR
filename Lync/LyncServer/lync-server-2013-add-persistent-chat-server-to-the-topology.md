---
title: 'Lync Server 2013: Adicionar servidor de chat persistente à topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ae7ca7e475fd106608dea09fedf250ef541a5c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="789b6-102">Adicionar servidor de chat persistente à topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="789b6-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="789b6-103">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="789b6-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="789b6-104">Você deve incorporar o suporte do Lync Server 2013, persistent chat Server em sua topologia antes de poder configurar sua implantação para suportar o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="789b6-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="789b6-105">As informações neste tópico descrevem como usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à sua topologia existente.</span><span class="sxs-lookup"><span data-stu-id="789b6-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="789b6-106">Para adicionar um servidor de chat persistente a uma topologia</span><span class="sxs-lookup"><span data-stu-id="789b6-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="789b6-107">Execute as seguintes etapas para instalar um único pool de servidores de chat persistente sem uma configuração de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="789b6-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="789b6-108">Para configurar um pool de servidor de chat persistente estendido para alta disponibilidade e recuperação de desastre, confira [Configurando servidor de chat persistente para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="789b6-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="789b6-109">Para implantar vários pools do servidor de chat persistente, repita o mesmo processo para cada pool.</span><span class="sxs-lookup"><span data-stu-id="789b6-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="789b6-110">Em um computador que está executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="789b6-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="789b6-111">Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para instalar um servidor do Lync Server 2013, você deve usar uma conta que seja membro do grupo <STRONG>Administradores de domínio</STRONG> e do grupo <STRONG>RTCUniversalServerAdmins</STRONG> e que tenha permissões de controle total (ou seja, ler, gravar e modificar) no repositório de arquivos que você usará para o repositório de arquivos do servidor de chat persistente (ou seja, para que o construtor de topologias possa configurar as DACLs necessárias) ou uma conta com direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="789b6-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="789b6-112">Inicie o Construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="789b6-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="789b6-113">Na árvore do console, navegue até o nó **pools de chat persistente** e expanda-o para selecionar um pool de servidor de chat persistente ou clique com o botão direito do mouse no nó e selecione **novo pool de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="789b6-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="789b6-114">Você deve definir o FQDN (nome de domínio totalmente qualificado) do pool e indicar se o pool será um pool de servidor único ou uma implantação de pool de vários servidores.</span><span class="sxs-lookup"><span data-stu-id="789b6-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="789b6-115">Você pode escolher um **pool de vários computadores** ou um **pool de computador único**.</span><span class="sxs-lookup"><span data-stu-id="789b6-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="789b6-116">Escolha a primeira vez se estiver planejando ter mais de um servidor front-end do servidor de chat persistente em seu pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="789b6-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="789b6-117">Faça esta escolha agora ou posteriormente, porque depois de criar um pool de computador único, não será possível adicionar mais servidores a ele posteriormente.</span><span class="sxs-lookup"><span data-stu-id="789b6-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="789b6-118">Se você escolher um pool de vários computadores, insira os nomes dos servidores de front-end do servidor de chat persistente individuais que compõem o pool.</span><span class="sxs-lookup"><span data-stu-id="789b6-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="789b6-119">Se a função de servidor de chat persistente estiver sendo instalada em um servidor&nbsp;do Lync Server 2013 Standard Edition, o FQDN precisará corresponder ao FQDN do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="789b6-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="789b6-120">Defina um **nome de exibição** simples para o pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="789b6-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="789b6-121">O nome de exibição pode ser usado por clientes personalizados, especialmente quando há vários pools de servidores de chat persistentes, para diferenciar salas.</span><span class="sxs-lookup"><span data-stu-id="789b6-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="789b6-122">Definir a porta usada pelo servidor de chat persistente para se comunicar com os servidores front-end do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="789b6-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="789b6-123">A porta padrão é 5041.</span><span class="sxs-lookup"><span data-stu-id="789b6-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="789b6-124">Se sua organização requer suporte de conformidade, marque a caixa de seleção **habilitar conformidade** .</span><span class="sxs-lookup"><span data-stu-id="789b6-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="789b6-125">Se escolhido, o serviço de conformidade do servidor de chat persistente é instalado no mesmo computador que o servidor de front-end do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="789b6-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="789b6-126">Você será solicitado a selecionar um servidor back-end do SQL Server para conformidade do servidor de chat persistente mais tarde.</span><span class="sxs-lookup"><span data-stu-id="789b6-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="789b6-127">Atribua afinidade de site para o pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="789b6-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="789b6-128">Marque a caixa de seleção **usar este pool como \<padrão\> para o site SiteName** ou **Use este pool como padrão para todos os sites** para designar esse pool de servidor de chat persistente como o pool padrão para o site atual ou todos os sites.</span><span class="sxs-lookup"><span data-stu-id="789b6-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="789b6-129">Quando o cliente Lync 2013 é usado para criar e gerenciar salas, o pool padrão associado ao site do usuário é usado pela experiência de criação e gerenciamento da sala para que possa encaminhar operações de criação e gerenciamento de salas a esse pool.</span><span class="sxs-lookup"><span data-stu-id="789b6-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="789b6-130">Isso só se aplica quando você tem vários pools de servidores de chat persistente implantados e deseja usar os recursos de criação e gerenciamento de sala do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="789b6-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="789b6-131">Você pode personalizar os recursos de criação e gerenciamento de sala usando o Software Development Kit (SDK) do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="789b6-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="789b6-132">Para obter detalhes sobre como configurar bancos de dados de backup do SQL Server para recuperação de desastre, consulte <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="789b6-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="789b6-133">Defina o **repositório SQL para back-end do servidor de chat persistente (onde o conteúdo da sala de bate-papo é armazenado)** executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="789b6-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="789b6-134">Para usar um banco de dados existente do SQL Server, na lista suspensa, clique no nome do banco de dados do SQL Server que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="789b6-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="789b6-135">Para especificar um novo banco de dados do SQL Server, clique em **novo**e em **definir novo repositório SQL**, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="789b6-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="789b6-136">Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="789b6-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="789b6-137">Selecione **instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, selecione **instância nomeada**e especifique a instância que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="789b6-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="789b6-138">Defina o banco de dados de conformidade do SQL Server se você tiver habilitado a conformidade.</span><span class="sxs-lookup"><span data-stu-id="789b6-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="789b6-139">Para obter detalhes sobre como configurar os espelhos do SQL Server para alta disponibilidade para o banco de dados do servidor de chat persistente e o banco de dados de conformidade do servidor de chat persistente, consulte <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="789b6-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="789b6-140">Defina o repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="789b6-140">Define the file store.</span></span> <span data-ttu-id="789b6-141">Um repositório de arquivos é uma pasta onde uma cópia de qualquer arquivo carregado no repositório de arquivos é armazenada (por exemplo, armazenando anexos de arquivo postados em uma sala de chat).</span><span class="sxs-lookup"><span data-stu-id="789b6-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="789b6-142">No caso de uma topologia de servidor de chat persistente de vários servidores, este deve ser um caminho UNC (Convenção de nomenclatura universal); e para uma topologia de servidor de chat persistente de servidor único, pode ser um caminho de arquivo local.</span><span class="sxs-lookup"><span data-stu-id="789b6-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="789b6-143">Para usar um repositório de arquivos existente, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="789b6-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="789b6-144">Em **FQDN do servidor de arquivos**, ESPECIFIQUE o FQDN do repositório de arquivos em que você deseja criar o novo repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="789b6-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="789b6-145">Em **compartilhamento de arquivos**, especifique o repositório de arquivos que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="789b6-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="789b6-146">Você pode definir o repositório de arquivos no construtor de topologias antes de criar o repositório de arquivos, mas deve criar o repositório de arquivos no local definido antes de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="789b6-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="789b6-147">Selecione o pool de servidor front-end a ser usado como próximo salto para este pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="789b6-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="789b6-148">Este é o pool do servidor front-end que poderá rotear solicitações persistentes do servidor de chat para este pool.</span><span class="sxs-lookup"><span data-stu-id="789b6-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="789b6-149">Para salvar a configuração, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="789b6-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="789b6-150">O pool do servidor de chat persistente aparece no construtor de topologia acompanhado por suas configurações de pool específicas.</span><span class="sxs-lookup"><span data-stu-id="789b6-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="789b6-151">Para publicar agora sua topologia atualizada para a qual você tem o servidor de chat persistente, confira [publicar a topologia atualizada no Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="789b6-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="789b6-152">Com o construtor de topologias já aberto, você pode prosseguir para a etapa 3 em <A href="lync-server-2013-publish-the-updated-topology.md">publicar a topologia atualizada no Lync Server 2013</A> para começar a publicar sua topologia atualizada.</span><span class="sxs-lookup"><span data-stu-id="789b6-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

