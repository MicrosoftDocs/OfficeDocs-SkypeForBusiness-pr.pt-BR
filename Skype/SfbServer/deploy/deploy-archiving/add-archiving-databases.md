---
title: Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumo: Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua implantação do Skype for Business Server.'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820671"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="a87c3-103">Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a87c3-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="a87c3-104">**Resumo:** Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a87c3-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="a87c3-105">É necessário incorporar o arquivamento à sua topologia antes de poder configurar sua implantação para suportar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="a87c3-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="a87c3-106">As informações neste tópico explicam como usar o Construtor de Topologias para:</span><span class="sxs-lookup"><span data-stu-id="a87c3-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="a87c3-107">Adicione um banco de dados de arquivamento à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="a87c3-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="a87c3-108">Publique a topologia atualizada para adicionar o banco de dados de arquivamento à sua implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a87c3-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a87c3-109">Se você quiser usar a integração com o Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores do Exchange para todos os usuários em sua implantação, não especifique o armazenamento do **SQL Server** de Arquivamento ou use as informações de espelhamento do SQL **Server Store.**</span><span class="sxs-lookup"><span data-stu-id="a87c3-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="a87c3-110">Adicionar um banco de dados de arquivamento à sua topologia</span><span class="sxs-lookup"><span data-stu-id="a87c3-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="a87c3-111">Em um computador que está executando o Skype for Business Server ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, faça logoff usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="a87c3-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="a87c3-112">Inicie o Construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="a87c3-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="a87c3-113">Na árvore de console, navegue até o pool de Front-End no qual você deseja implantar o Arquivamento e clique no nome do pool de Front-End onde deseja implantar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="a87c3-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="a87c3-114">No menu **Ação**, clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a87c3-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="a87c3-115">Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="a87c3-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="a87c3-116">Role a tela para baixo até **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="a87c3-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="a87c3-117">Marque a caixa de seleção **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="a87c3-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="a87c3-118">Em **Armazenamento de Arquivamento do SQL Server,** faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a87c3-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="a87c3-119">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="a87c3-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="a87c3-120">Se todos os seus usuários estão instalados no Microsoft Exchange Server 2013 ou acima, você pode arquivar comunicações do Skype for Business para todos os seus usuários no Exchange.</span><span class="sxs-lookup"><span data-stu-id="a87c3-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="a87c3-121">Nesse caso, você não precisa configurar o armazenamento de Arquivamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a87c3-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="a87c3-122">Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, na caixa de diálogo Definir Novo Armazenamento do **SQL Server,** faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a87c3-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="a87c3-123">No **FQDN do SQL Server,** especifique o FQDN do servidor no qual você deseja criar o novo armazenamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a87c3-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="a87c3-124">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="a87c3-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="a87c3-125">Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção Esta instância **SQL** está em relação de espelhamento e, em seguida, no número da porta **Espelho,** especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="a87c3-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="a87c3-126">Se você quiser usar o espelhamento do armazenamento do SQL Server, selecione Habilitar espelhamento do **SQL Server Store** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a87c3-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="a87c3-127">Para usar um armazenamento existente do SQL **Server** para espelhamento, na caixa de listagem de espelho do armazenamento do SQL Server de arquivamento, clique no nome do armazenamento do SQL Server que você deseja usar para espelhamento.</span><span class="sxs-lookup"><span data-stu-id="a87c3-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="a87c3-128">Para especificar um novo armazenamento do SQL Server para espelhamento, clique em Novo e, em seguida, na caixa de diálogo Definir Novo Armazenamento do **SQL Server,** faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a87c3-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="a87c3-129">a.</span><span class="sxs-lookup"><span data-stu-id="a87c3-129">a.</span></span> <span data-ttu-id="a87c3-130">No **FQDN do SQL Server,** especifique o FQDN do SQL Server no qual você deseja criar o novo armazenamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a87c3-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="a87c3-131">b.</span><span class="sxs-lookup"><span data-stu-id="a87c3-131">b.</span></span> <span data-ttu-id="a87c3-132">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="a87c3-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="a87c3-133">c.</span><span class="sxs-lookup"><span data-stu-id="a87c3-133">c.</span></span> <span data-ttu-id="a87c3-134">Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção Esta instância **SQL** está em relação de espelhamento e, em seguida, no número da porta **Espelho,** especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="a87c3-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="a87c3-135">Se você habilitar o espelhamento do SQL Server e quiser incluir uma testemunha de espelhamento do SQL Server (uma terceira instância separada do SQL Server que pode detectar a saúde do SQL Server primário e das instâncias espelho), selecione a caixa de seleção Usar espelhamento do SQL Server para habilitar a caixa de seleção de **failover** automático e, em seguida, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a87c3-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="a87c3-136">a.</span><span class="sxs-lookup"><span data-stu-id="a87c3-136">a.</span></span> <span data-ttu-id="a87c3-137">No **FQDN do SQL Server,** especifique o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a87c3-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="a87c3-138">b.</span><span class="sxs-lookup"><span data-stu-id="a87c3-138">b.</span></span> <span data-ttu-id="a87c3-139">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="a87c3-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="a87c3-140">c.</span><span class="sxs-lookup"><span data-stu-id="a87c3-140">c.</span></span> <span data-ttu-id="a87c3-141">Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção Esta instância **SQL** está em relação de espelhamento e, em seguida, no número da porta **Espelho,** especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="a87c3-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="a87c3-142">Para salvar a configuração, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a87c3-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="a87c3-143">Publicar a topologia atualizada para adicionar um banco de dados de arquivamento à sua implantação</span><span class="sxs-lookup"><span data-stu-id="a87c3-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="a87c3-144">Em um computador que está executando o Skype for Business Server ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, faça logoff usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="a87c3-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a87c3-145">Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessário para  adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo Administradores de Domínio e do grupo **RTCUniversalServerAdmins** e que tenha permissões de controle total (ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o armazenamento de arquivos do Skype for Business Server (para que o Construtor de Topologias possa configurar a lista de controle de acesso discricionário (DACLs) necessária ou uma conta com direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="a87c3-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="a87c3-146">Abra a topologia criada na seção anterior usando o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="a87c3-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="a87c3-147">Na árvore do console, clique com o botão direito do mouse **no Skype for Business Server** e clique em Publicar **Topologia.**</span><span class="sxs-lookup"><span data-stu-id="a87c3-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="a87c3-148">Na página **Publicar topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a87c3-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="a87c3-149">Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a87c3-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a87c3-150">Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a87c3-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="a87c3-151">> somente bancos de dados em SQL Servers dedicados podem ser instalados usando o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="a87c3-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="a87c3-152">Os bancos de dados em Servidores SQL que são colocados com outros componentes precisam ser instalados executando a configuração local nesse computador.</span><span class="sxs-lookup"><span data-stu-id="a87c3-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="a87c3-153">Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a87c3-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a87c3-154">Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado.</span><span class="sxs-lookup"><span data-stu-id="a87c3-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="a87c3-155">Para obter detalhes, [consulte Configure archiving options for Skype for Business Server](configure-archiving-options.md) and Configure [archiving policies for Skype for Business Server](configure-archiving-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a87c3-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

