---
title: 'Lync Server 2013: adicionando bancos de dados de arquivamento à topologia 2013 do Lync Server'
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
ms.openlocfilehash: ebc2f06e6e3fa2646989e4697354c71f7f0249da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521388"
---
# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="5d9de-102">Adicionando bancos de dados de arquivamento à topologia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d9de-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d9de-103">_**Última modificação do tópico:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="5d9de-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="5d9de-104">É necessário incorporar o arquivamento à sua topologia antes de poder configurar sua implantação para suportar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="5d9de-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="5d9de-105">As informações neste tópico explicam como usar o construtor de topologias para adicionar o arquivamento à sua topologia existente.</span><span class="sxs-lookup"><span data-stu-id="5d9de-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d9de-106">Se você quiser usar a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange 2013 para todos os usuários em sua implantação, não especifique o <STRONG>repositório do SQL Server</STRONG> ou use as informações de <STRONG>espelhamento do repositório do SQL Server</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5d9de-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="5d9de-107">Para adicionar suporte ao banco de dados de Arquivamento à sua topologia</span><span class="sxs-lookup"><span data-stu-id="5d9de-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="5d9de-108">Em um computador que está executando o Lync Server 2013, ou em que as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="5d9de-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d9de-109">Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo <STRONG>Administradores de domínio</STRONG> e do grupo <STRONG>RTCUniversalServerAdmins</STRONG> , e que tem permissões de controle total (ou seja, leitura, gravação e modificação) no compartilhamento de arquivos que você está usando para o repositório de arquivos do Lync Server 2013 (ou seja, o construtor de topologias pode configurar a lista de controle de acesso discricional (DACLs) necessária ou uma conta com direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="5d9de-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="5d9de-110">Inicie o Construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="5d9de-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="5d9de-111">Na árvore do console, navegue até o pool de Front-Ends no qual você deseja implantar o Arquivamento e clique no nome do pool.</span><span class="sxs-lookup"><span data-stu-id="5d9de-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="5d9de-112">No menu **Ação**, clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5d9de-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="5d9de-113">Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="5d9de-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="5d9de-114">Role a tela para baixo até **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="5d9de-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="5d9de-115">Marque a caixa de seleção **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="5d9de-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="5d9de-116">Em **arquivar repositório do SQL Server,** siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5d9de-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="5d9de-117">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="5d9de-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="5d9de-118">Se todos os seus usuários estiverem hospedados no Microsoft Exchange Server 2013 ou superior, você poderá arquivar as comunicações do Lync para todos os seus usuários no Exchange.</span><span class="sxs-lookup"><span data-stu-id="5d9de-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="5d9de-119">Nesse caso, você não precisa configurar o repositório de arquivamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d9de-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="5d9de-120">Para especificar um novo repositório do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **definir novo repositório do SQL Server** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5d9de-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="5d9de-121">Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d9de-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="5d9de-122">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="5d9de-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="5d9de-123">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="5d9de-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="5d9de-124">Se você quiser usar o espelhamento do repositório do SQL Server, selecione **habilitar espelhamento do repositório do SQL Server**e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5d9de-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="5d9de-125">Para usar um repositório existente do SQL Server para espelhamento, na caixa de listagem suspensa **espelhamento do repositório do SQL Server Store** , clique no nome do repositório do SQL Server que você deseja usar para espelhamento.</span><span class="sxs-lookup"><span data-stu-id="5d9de-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="5d9de-126">Para especificar um novo repositório do SQL Server para espelhamento, clique em **novo**e, em seguida, na caixa de diálogo **definir novo repositório do SQL Server** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5d9de-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="5d9de-127">Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d9de-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="5d9de-128">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="5d9de-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="5d9de-129">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="5d9de-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="5d9de-130">Se você habilitar o espelhamento do SQL Server e quiser incluir uma testemunha de espelhamento do SQL Server (uma terceira instância separada do SQL Server que possa detectar a integridade do servidor SQL Server principal e das instâncias de espelho), marque a caixa de seleção **usar testemunha de espelhamento do SQL Server para habilitar failover automático** e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5d9de-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="5d9de-131">Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d9de-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="5d9de-132">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="5d9de-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="5d9de-133">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="5d9de-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="5d9de-134">Para salvar a configuração, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d9de-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

