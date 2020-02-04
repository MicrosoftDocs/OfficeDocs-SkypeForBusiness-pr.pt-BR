---
title: 'Lync Server 2013: Adicionar bancos de dados de arquivamento à topologia 2013 do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7476107b064b45dbef74b03ff9d54e02fc9eee52
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="e480b-102">Adicionar bancos de dados de arquivamento à topologia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e480b-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e480b-103">_**Tópico da última modificação:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="e480b-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="e480b-104">É necessário incorporar o arquivamento à sua topologia antes de configurar sua implantação para suportar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e480b-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="e480b-105">As informações neste tópico explicam como usar o construtor de topologias para adicionar o arquivamento à sua topologia existente.</span><span class="sxs-lookup"><span data-stu-id="e480b-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e480b-106">Se você quiser usar a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange 2013 para todos os usuários em sua implantação, não especifique a <STRONG>loja do SQL Server</STRONG> do SQL Server ou use as informações de <STRONG>espelhamento da loja do SQL Server</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e480b-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="e480b-107">Para adicionar suporte a banco de dados de arquivamento à sua topologia</span><span class="sxs-lookup"><span data-stu-id="e480b-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="e480b-108">Em um computador que esteja executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="e480b-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e480b-109">Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo <STRONG>Domain admins</STRONG> e do grupo <STRONG>RTCUniversalServerAdmins</STRONG> e que tenha permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o repositório de arquivos do Lync Server 2013 (ou seja, o construtor de topologias pode configurar a lista de controle de acesso discricional (DACLs) necessária ou uma conta com direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="e480b-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="e480b-110">Iniciar o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="e480b-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="e480b-111">Na árvore de console, navegue até o pool de front-end no qual você deseja implantar o arquivamento e clique no nome do pool de front-ends em que deseja implantar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e480b-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="e480b-112">No menu **Ação**, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e480b-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="e480b-113">Na caixa de diálogo **Editar propriedades**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="e480b-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="e480b-114">Role a tela para baixo até **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="e480b-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="e480b-115">Marque a caixa de seleção **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="e480b-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="e480b-116">Em **arquivar repositório do SQL Server,** siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e480b-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="e480b-117">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="e480b-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="e480b-118">Se todos os seus usuários estiverem hospedados no Microsoft Exchange Server 2013 ou superior, você poderá arquivar as comunicações do Lync para todos os usuários no Exchange.</span><span class="sxs-lookup"><span data-stu-id="e480b-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="e480b-119">Nesse caso, você não precisa configurar o repositório de arquivamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e480b-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="e480b-120">Para especificar uma nova loja do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **definir novo SQL Server Store** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e480b-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="e480b-121">Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e480b-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="e480b-122">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="e480b-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="e480b-123">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação ao espelhamento** e, em seguida, em **número de porta espelhada**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="e480b-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="e480b-124">Se você quiser usar o espelhamento da loja do SQL Server, selecione **habilitar o espelhamento da loja do SQL Server**e, em seguida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e480b-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="e480b-125">Para usar uma loja existente do SQL Server para espelhamento, na caixa de listagem suspensa de **espelhamento do repositório do SQL Server** , clique no nome da loja do SQL Server que você deseja usar para espelhamento.</span><span class="sxs-lookup"><span data-stu-id="e480b-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="e480b-126">Para especificar uma nova loja do SQL Server para espelhamento, clique em **novo**e, na caixa de diálogo **definir novo repositório do SQL Server** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e480b-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="e480b-127">No **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e480b-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="e480b-128">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="e480b-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="e480b-129">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação ao espelhamento** e, em seguida, em **número de porta espelhada**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="e480b-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="e480b-130">Se você habilitar o espelhamento do SQL Server e quiser incluir uma testemunha de espelhamento do SQL Server (uma terceira instância do SQL Server separada que pode detectar a integridade do servidor do SQL Server e das instâncias de espelhamento principais), marque a caixa de seleção **usar a testemunha de espelhamento do SQL Server para habilitar o failover automático** e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e480b-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="e480b-131">Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e480b-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="e480b-132">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="e480b-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="e480b-133">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação ao espelhamento** e, em seguida, em **número de porta espelhada**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="e480b-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="e480b-134">Para salvar a configuração, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e480b-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

