---
title: 'Lync Server 2013: alterar as opções de banco de dados de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a98c2efc0dc956a6b8c33f2fcf065f629e5e57d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="425bf-102">Alterar as opções de banco de dados de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="425bf-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="425bf-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="425bf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="425bf-104">Se você implantar o arquivamento usando o armazenamento do SQL Server para arquivar o armazenamento para qualquer um dos seus usuários, poderá fazer as seguintes alterações de armazenamento de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="425bf-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="425bf-105">Use um banco de dados do SQL Server diferente para arquivar o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="425bf-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="425bf-106">Isso inclui o banco de dados de arquivamento principal e qualquer banco de dados que você usa para o espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="425bf-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="425bf-107">Alterne para a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="425bf-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="425bf-108">Se todos os usuários estiverem hospedados nos seus servidores Exchange 2013 e você quiser usar o armazenamento do Microsoft Exchange para todos os usuários em sua implantação, remova os bancos de dados da loja do SQL Server da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="425bf-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="425bf-109">Para fazer uma dessas alterações, você deve executar o construtor de topologias, fazer as alterações e, em seguida, publicar a topologia novamente.</span><span class="sxs-lookup"><span data-stu-id="425bf-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="425bf-110">Você pode usar o construtor de topologias para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="425bf-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="425bf-111">Não especifique o **arquivamento do SQL Server Store** ou habilite as informações de espelhamento da **loja do SQL Server** , a menos que você tenha usuários do Lync que não são hospedados nos servidores Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="425bf-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="425bf-112">Para alterar a opção de banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="425bf-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="425bf-113">Em um computador que esteja executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="425bf-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="425bf-114">Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um componente à topologia, você deve usar uma conta que seja membro do grupo <STRONG>Administradores de domínio</STRONG> e o <STRONG>RTCUniversalSer verAdmins</STRONG> grupo, e que tem permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivo que você está usando para o repositório de arquivos do Lync Server 2013 (ou seja, o construtor de topologia pode configurar as listas de controle de acesso discricional necessárias ( DACLs) ou uma conta com direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="425bf-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="425bf-115">Iniciar o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="425bf-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="425bf-116">Na árvore de console, navegue até o pool de front-ends no qual o arquivamento foi implantado e clique no nome do pool de front-ends no qual deseja alterar as opções de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="425bf-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="425bf-117">No menu **Ação**, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="425bf-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="425bf-118">Na caixa de diálogo **Editar propriedades**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="425bf-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="425bf-119">Role a tela para baixo até **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="425bf-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="425bf-120">Em **Arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="425bf-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="425bf-121">Para alterar para um armazenamento existente diferente do SQL Server, em **Armazenamento de arquivamento do SQL Server**, na caixa de listagem suspensa, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="425bf-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="425bf-122">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="425bf-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="425bf-123">Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, depois, na caixa de diálogo **Definir novo armazenamento do SQL Server** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="425bf-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="425bf-124">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="425bf-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="425bf-125">Para especificar uma nova loja do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **definir novo SQL Server Store** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="425bf-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="425bf-126">Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="425bf-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="425bf-127">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="425bf-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="425bf-128">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="425bf-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="425bf-129">Para adicionar um armazenamento do SQL Server de espelhamento ou alteração a um armazenamento existente diferente do SQL Server, selecione **Habilitar espelhamento do armazenamento do SQL Server** e, em seguida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="425bf-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="425bf-130">Para usar uma loja existente do SQL Server para espelhamento, na caixa de listagem suspensa de espelhamento do **repositório do SQL Server** , clique no nome da loja do SQL Server que você deseja usar para espelhamento.</span><span class="sxs-lookup"><span data-stu-id="425bf-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="425bf-131">Para especificar uma nova loja do SQL Server para espelhamento, clique em **novo**e, na caixa de diálogo **definir novo repositório do SQL Server** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="425bf-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="425bf-132">No **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="425bf-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="425bf-133">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="425bf-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="425bf-134">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="425bf-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="425bf-135">Se você habilitar o espelhamento do SQL Server e quiser adicionar ou alterar uma testemunha de espelhamento do SQL Server (uma terceira instância do SQL Server separada que pode detectar a integridade do servidor do SQL Server e das instâncias de espelhamento principais), selecione a **testemunha usar o espelhamento do SQL Server para Habilite** a caixa de seleção failover automático e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="425bf-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="425bf-136">Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="425bf-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="425bf-137">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="425bf-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="425bf-138">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="425bf-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="425bf-139">Para alternar para a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange 2013 (se todos os usuários na sua implantação estiverem hospedados em seus servidores Exchange 2013), exclua todas as informações para arquivar bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="425bf-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="425bf-140">Se você tiver usuários do Lync que não são hospedados nos servidores Exchange 2013, não exclua as informações da loja do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="425bf-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="425bf-141">Para salvar a configuração, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="425bf-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="425bf-142">As alterações feitas no construtor de topologias não entram em vigor até que você publique a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="425bf-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="425bf-143">Para obter detalhes, consulte <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">publicando a topologia atualizada para adicionar bancos de dados de arquivamento no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="425bf-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

