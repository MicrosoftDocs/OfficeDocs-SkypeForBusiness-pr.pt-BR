---
title: Adicionar bancos de dados de arquivamento a uma implantação existente no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Resumo: Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua Skype para implantação de servidor de negócios.'
ms.openlocfilehash: a437da69db0fc1c57c39a1fa1a61f7dead1fdaa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894166"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="7fdaf-103">Adicionar bancos de dados de arquivamento a uma implantação existente no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7fdaf-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="7fdaf-104">**Resumo:** Leia este tópico para saber como adicionar bancos de dados de arquivamento à sua Skype para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="7fdaf-105">É necessário incorporar o arquivamento à sua topologia antes de configurar sua implantação para suportar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="7fdaf-106">As informações neste tópico explicam como usar o construtor de topologias para:</span><span class="sxs-lookup"><span data-stu-id="7fdaf-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="7fdaf-107">Adicionar um banco de dados de arquivamento à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="7fdaf-108">Publica a topologia atualizada para adicionar o banco de dados de arquivamento à sua Skype para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7fdaf-109">Se desejar usar a integração do Microsoft Exchange para armazenar arquivos nos servidores do Exchange para todos os seus usuários e dados de arquivamento em sua implantação, não especifique as informações de **repositório de arquivamento do SQL Server** ou **espelhamento do repositório de servidor SQL de uso** .</span><span class="sxs-lookup"><span data-stu-id="7fdaf-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="7fdaf-110">Adicionar um banco de dados de arquivamento à sua topologia</span><span class="sxs-lookup"><span data-stu-id="7fdaf-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="7fdaf-111">Em um computador que esteja executando o Skype para Business Server ou em que o Skype para ferramentas administrativas do Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo local de usuários (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="7fdaf-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="7fdaf-112">Inicie o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="7fdaf-113">Na árvore do console, navegue até o pool de Front-Ends no qual você deseja implantar o arquivamento e clique no nome do pool.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="7fdaf-114">No menu **Ação**, clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="7fdaf-115">Na caixa de diálogo **Editar Propriedades**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="7fdaf-116">Role a tela para baixo até **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="7fdaf-117">Marque a caixa de seleção **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="7fdaf-118">Em **repositório de arquivamento do SQL Server,** siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7fdaf-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="7fdaf-119">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="7fdaf-120">Se todos os usuários estão hospedados no Microsoft Exchange Server 2013 ou acima, você pode arquivar Skype para comunicações comerciais de todos os usuários do Exchange.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="7fdaf-121">Nesse caso, você não precisará configurar o repositório de arquivamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="7fdaf-122">Para especificar um novo repositório do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **Definir novo repositório do SQL Server** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7fdaf-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="7fdaf-123">Em **FQDN do SQL Server**, especifique o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="7fdaf-124">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="7fdaf-125">Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="7fdaf-126">Se você quiser usar o espelhamento do repositório do SQL Server, selecione **Habilitar SQL Server Store espelhamento**e, em seguida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7fdaf-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="7fdaf-127">Para usar um armazenamento existente do SQL Server para espelhamento, na caixa de listagem suspensa **espelho do repositório de arquivamento do SQL Server** , clique no nome do repositório do SQL Server que você deseja usar para espelhamento.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="7fdaf-128">Para especificar um novo repositório do SQL Server para espelhamento, clique em **novo**e, em seguida, na caixa de diálogo **Definir novo repositório do SQL Server** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7fdaf-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="7fdaf-129">a.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-129">a.</span></span> <span data-ttu-id="7fdaf-130">Em **FQDN do SQL Server**, especifique o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="7fdaf-131">b.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-131">b.</span></span> <span data-ttu-id="7fdaf-132">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="7fdaf-133">c.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-133">c.</span></span> <span data-ttu-id="7fdaf-134">Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="7fdaf-135">Se você habilitar o espelhamento do SQL Server e deseja incluir um (uma terceira, separada instância do SQL Server que pode detectar a integridade das instâncias do SQL Server e espelho primárias) de testemunha de espelhamento do SQL Server, selecione o **testemunha de espelhamento de usar do SQL Server para habilitar automática failover** caixa de seleção e, em seguida, execute um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7fdaf-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="7fdaf-136">a.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-136">a.</span></span> <span data-ttu-id="7fdaf-137">Em **FQDN do SQL Server**, especifique o FQDN do servidor no qual você deseja criar o novo SQL Server testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="7fdaf-138">b.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-138">b.</span></span> <span data-ttu-id="7fdaf-139">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="7fdaf-140">c.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-140">c.</span></span> <span data-ttu-id="7fdaf-141">Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="7fdaf-142">Para salvar a configuração, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="7fdaf-143">Publique a topologia atualizada para adicionar o banco de dados de arquivamento à sua implantação</span><span class="sxs-lookup"><span data-stu-id="7fdaf-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="7fdaf-144">Em um computador que esteja executando o Skype para Business Server ou em que o Skype para ferramentas administrativas do Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo local de usuários (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="7fdaf-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7fdaf-145">Você pode definir uma topologia usando uma conta que seja membro do grupo de usuários local, mas para publicar uma topologia, o que é necessário para adicionar um servidor à topologia, você deve usar uma conta que seja membro do grupo **Administradores** de domínio e o **RTCUniversalServer Os administradores** grupo e que tem permissões de controle total (leitura, gravação e modificar) no compartilhamento de arquivos que você está usando para o Skype para repositório de arquivos do servidor de negócios (para que o construtor de topologias possa configurar a lista de controle de acesso discricionário necessária (DACLs) ou uma conta com direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="7fdaf-146">Abra a topologia que você criou na seção anterior utilizando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="7fdaf-147">Na árvore de console, clique com o botão **Skype para Business Server**e, em seguida, clique em **Publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="7fdaf-148">Na página **Publicar a topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="7fdaf-149">Na página **Criar banco de dados**, verifique se o banco de dados está selecionado e, então, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="7fdaf-150">Se você não possuir as permissões adequadas para criar bancos de dados, você pode cancelar a seleção do banco de dados e alguém com as permissões adequadas podem criar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="7fdaf-151">bancos de dados somente em servidores dedicados do SQL gt _ podem ser instalados usando o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="7fdaf-152">Bancos de dados em SQL Servers que são colocados com outros componentes de servidor devem ser instalados executando a instalação local em tal computador.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="7fdaf-153">Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7fdaf-154">Após publicar a topologia, você deve configurar as opções e políticas de Arquivamento antes que qualquer conteúdo seja arquivado.</span><span class="sxs-lookup"><span data-stu-id="7fdaf-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="7fdaf-155">Para obter detalhes, consulte [Configurar opções de arquivamento para Skype para Business Server](configure-archiving-options.md) e [Configurar políticas para Skype para Business Server de arquivamento](configure-archiving-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7fdaf-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

