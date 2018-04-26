---
title: Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumo: Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua implantação do .'
ms.openlocfilehash: 09185eed2a8bd0cc9b2a03fc6361abeadbd01829
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="92bbd-103">Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="92bbd-103">Add archiving databases to an existing deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="92bbd-104">Resumo: Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua implantação do .</span><span class="sxs-lookup"><span data-stu-id="92bbd-104">Summary: Read this topic to learn how to add archiving databases to your  deployment.</span></span>
  
<span data-ttu-id="92bbd-105">É necessário incorporar o arquivamento à sua topologia antes de configurar sua implantação para suportar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="92bbd-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="92bbd-106">As informações neste tópico explicam como usar o  para:</span><span class="sxs-lookup"><span data-stu-id="92bbd-106">The information in this topic explains how to use  to:</span></span>
  
- <span data-ttu-id="92bbd-107">Adicionar um banco de dados de arquivamento à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="92bbd-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="92bbd-108">Publicar a topologia atualizada para adicionar o banco de dados de arquivamento à sua implantação do .</span><span class="sxs-lookup"><span data-stu-id="92bbd-108">Publish the updated topology to add the archiving database to your  deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="92bbd-109">Se você quiser usar a integração do  para armazenar dados de arquivamento e arquivos nos servidores do  para todos seus usuários em sua implantação, não especifique informações do  ou .</span><span class="sxs-lookup"><span data-stu-id="92bbd-109">If you want to use  integration to store archiving data and files on  servers for all your users in your deployment, do not specify  or  information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="92bbd-110">Adicionar um banco de dados de arquivamento à sua topologia</span><span class="sxs-lookup"><span data-stu-id="92bbd-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="92bbd-111">Em um computador que está executando o  ou no qual as ferramentas administrativas do  estejam instaladas, faça logon usando uma conta que seja membro do grupo de usuários local (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="92bbd-111">On a computer that is running , or on which the  administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="92bbd-112">Start Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="92bbd-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="92bbd-113">Na árvore do console, navegue até o pool de Front-Ends no qual você deseja implantar o arquivamento e clique no nome do pool.</span><span class="sxs-lookup"><span data-stu-id="92bbd-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="92bbd-114">No menu **Ação**, clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="92bbd-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="92bbd-115">Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="92bbd-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="92bbd-116">Role a tela para baixo até **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="92bbd-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="92bbd-117">Marque a caixa de seleção **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="92bbd-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="92bbd-118">Under **Archiving SQL Server store,** do one of the following:</span><span class="sxs-lookup"><span data-stu-id="92bbd-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="92bbd-119">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="92bbd-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="92bbd-120">Se todos os seus usuários estiverem hospedados no  ou acima, você poderá arquivar as comunicações do  para todos os seus usuários no .</span><span class="sxs-lookup"><span data-stu-id="92bbd-120">If all of your users are homed on  or above, you can archive  communications for all your users in .</span></span> <span data-ttu-id="92bbd-121">Nesse caso, não é necessário configurar o repositório de Arquivamento do .</span><span class="sxs-lookup"><span data-stu-id="92bbd-121">In this case, you don’t need to configure  Archiving store.</span></span>
    
   - <span data-ttu-id="92bbd-122">Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, depois, na caixa de diálogo **Definir novo armazenamento do SQL Server** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="92bbd-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="92bbd-123">Em FQDN do SQL Server, especifique o FQDN do servidor no qual deseja criar o armazenamento do .</span><span class="sxs-lookup"><span data-stu-id="92bbd-123">In SQL Server FQDN, specify the FQDN of the server on which you want to create the new  store.</span></span>
    
   - <span data-ttu-id="92bbd-124">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="92bbd-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="92bbd-125">Na instância do  especificada em uma relação de espelhamento, marque a caixa de seleção Esta instância do SQL está em relação de espelhamento e, então, em Número da porta espelho, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="92bbd-125">If the specified  instance is in a mirroring relationship, select the This SQL instance is in mirroring relation check box, and then, in Mirror port number, specify the port number.</span></span>
    
9. <span data-ttu-id="92bbd-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span><span class="sxs-lookup"><span data-stu-id="92bbd-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="92bbd-127">Para usar um armazenamento existente do  para espelhamento, na caixa de listagem suspensa Espelho do armazenamento do SQL Server de arquivamento, clique no nome do armazenamento do  que deseja usar para espelhamento.</span><span class="sxs-lookup"><span data-stu-id="92bbd-127">To use an existing  store for mirroring, in the Archiving SQL Server store mirror drop-down list box, click the name of the  store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="92bbd-128">Para especificar um novo armazenamento do  para espelhamento, clique em Novo e, então, na caixa de diálogo Definir novo armazenamento do SQL Server, realize uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="92bbd-128">To specify a new  store for mirroring, click New, and then in the Define New SQL Server Store dialog box, do one of the following:</span></span>
    
    <span data-ttu-id="92bbd-129">a.</span><span class="sxs-lookup"><span data-stu-id="92bbd-129">a.</span></span> <span data-ttu-id="92bbd-130">Em FQDN do SQL Server, especifique o FQDN do SQL Server no qual deseja criar o novo armazenamento do .</span><span class="sxs-lookup"><span data-stu-id="92bbd-130">In SQL Server FQDN, specify the FQDN of the SQL Server on which you want to create the new  store.</span></span>
    
    <span data-ttu-id="92bbd-131">b.</span><span class="sxs-lookup"><span data-stu-id="92bbd-131">b.</span></span> <span data-ttu-id="92bbd-132">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="92bbd-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
    <span data-ttu-id="92bbd-133">c.</span><span class="sxs-lookup"><span data-stu-id="92bbd-133">c.</span></span> <span data-ttu-id="92bbd-134">Na instância do  especificada em uma relação de espelhamento, marque a caixa de seleção Esta instância do SQL está em relação de espelhamento e, então, em Número da porta espelho, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="92bbd-134">If the specified  instance is in a mirroring relationship, select the This SQL instance is in mirroring relation check box, and then, in Mirror port number, specify the port number.</span></span>
    
   - <span data-ttu-id="92bbd-135">Se você habilitar o espelhamento do  e quiser adicionar ou alterar uma testemunha de espelhamento do  (uma terceira instância do  separada, que possa detectar a integridade do servidor primário do  e as instâncias de espelho), marque a caixa de seleção Usar testemunha de espelhamento do SQL Server para habilitar failover automático e, em seguida, realize uma destas ações:</span><span class="sxs-lookup"><span data-stu-id="92bbd-135">If you enable  mirroring and want to add or change a  mirroring witness (a third, separate  instance that can detect the health of the primary  server and mirror instances), select the Use SQL Server mirroring witness to enable automatic failover check box, and then do one of the following:</span></span>
    
    <span data-ttu-id="92bbd-136">a.</span><span class="sxs-lookup"><span data-stu-id="92bbd-136">a.</span></span> <span data-ttu-id="92bbd-137">Em FQDN do SQL Server, especifique o FQDN do servidor no qual deseja criar a nova testemunha de espelhamento do .</span><span class="sxs-lookup"><span data-stu-id="92bbd-137">In SQL Server FQDN, specify the FQDN of the server on which you want to create the new  mirroring witness.</span></span>
    
    <span data-ttu-id="92bbd-138">b.</span><span class="sxs-lookup"><span data-stu-id="92bbd-138">b.</span></span> <span data-ttu-id="92bbd-139">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="92bbd-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
    <span data-ttu-id="92bbd-140">c.</span><span class="sxs-lookup"><span data-stu-id="92bbd-140">c.</span></span> <span data-ttu-id="92bbd-141">Na instância do  especificada em uma relação de espelhamento, marque a caixa de seleção Esta instância do SQL está em relação de espelhamento e, então, em Número da porta espelho, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="92bbd-141">If the specified  instance is in a mirroring relationship, select the This SQL instance is in mirroring relation check box, and then, in Mirror port number, specify the port number.</span></span>
    
10. <span data-ttu-id="92bbd-142">Para salvar a configuração, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="92bbd-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="92bbd-143">Publique a topologia atualizada para adicionar o banco de dados de arquivamento à sua implantação</span><span class="sxs-lookup"><span data-stu-id="92bbd-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="92bbd-144">Em um computador com o  em execução ou em que as ferramentas administrativas  estejam instaladas, faça logon usando uma conta que faça parte do grupo de usuários local (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="92bbd-144">On a computer that is running , or on which the  administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="92bbd-145">Você pode definir uma topologia utilizando uma conta que seja membro do grupo Usuários local, mas para publicar uma topologia (que é necessário para adicionar um servidor à topologia), você deve utilizar uma conta que seja membro do grupo Administradores de domínio e o grupo RTCUniversalServerAdmins e que possui permissões de controle total (ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o repositório de arquivo  (de forma que  possa configurar a lista de controle de acesso condicional (DACLs) ou uma conta com direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="92bbd-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (read, write, and modify) on the file share that you are using for the  file store (so that  can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="92bbd-146">Abra a topologia que você criou na seção anterior utilizando o .</span><span class="sxs-lookup"><span data-stu-id="92bbd-146">Open the topology you created in the previous section using .</span></span>
    
3. <span data-ttu-id="92bbd-147">Na árvore do console, clique com o botão direito do mouse em **** e depois em **Publicar Topologia**.</span><span class="sxs-lookup"><span data-stu-id="92bbd-147">In the console tree, right-click ****, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="92bbd-148">Na página **Publicar a topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="92bbd-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="92bbd-149">Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="92bbd-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="92bbd-150">Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="92bbd-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="92bbd-151">Apenas bancos de dados em SQL Servers dedicados podem ser instalados utilizando o .</span><span class="sxs-lookup"><span data-stu-id="92bbd-151">Only databases on dedicated SQL Servers can be installed by using .</span></span> <span data-ttu-id="92bbd-152">Bancos de dados em SQL Servers que são colocados com outros componentes de servidor devem ser instalados executando a instalação local em tal computador.</span><span class="sxs-lookup"><span data-stu-id="92bbd-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="92bbd-153">Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="92bbd-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="92bbd-154">Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado.</span><span class="sxs-lookup"><span data-stu-id="92bbd-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="92bbd-155">For details, see [Configure archiving options for Skype for Business Server 2015](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server 2015](configure-archiving-policies.md).</span><span class="sxs-lookup"><span data-stu-id="92bbd-155">For details, see [Configure archiving options for Skype for Business Server 2015](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server 2015](configure-archiving-policies.md).</span></span> 
  

