---
title: Alterar opções de banco de dados de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumo: saiba como alterar as opções de banco de dados de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: 56aa29ef185176ce3b080572723c566455731dc4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299983"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="47f01-103">Alterar opções de banco de dados de arquivamento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="47f01-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="47f01-104">**Resumo:** Saiba como alterar as opções de arquivamento de banco de dados para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="47f01-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="47f01-105">Se você implantar o arquivamento usando o armazenamento do SQL Server para arquivar o armazenamento para qualquer um dos seus usuários, poderá fazer as seguintes alterações de armazenamento de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="47f01-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="47f01-106">Use um banco de dados do SQL Server diferente para arquivar o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="47f01-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="47f01-107">Isso inclui o banco de dados de arquivamento principal e qualquer banco de dados que você usa para o espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="47f01-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="47f01-108">Alterne para a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange.</span><span class="sxs-lookup"><span data-stu-id="47f01-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="47f01-109">Se todos os usuários estiverem hospedados em seus servidores Exchange e você quiser usar o armazenamento do Microsoft Exchange para todos os usuários em sua implantação, remova os bancos de dados da loja do SQL Server da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="47f01-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="47f01-110">Para fazer uma dessas alterações, você deve executar o construtor de topologias, fazer as alterações e, em seguida, publicar a topologia novamente.</span><span class="sxs-lookup"><span data-stu-id="47f01-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="47f01-111">Não especifique o **arquivamento do SQL Server Store** ou habilite as informações de espelhamento da **loja do SQL Server** , a menos que você tenha usuários do Skype for Business que não são hospedados nos Exchange Servers.</span><span class="sxs-lookup"><span data-stu-id="47f01-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="47f01-112">Modificando opções do banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="47f01-112">Change Archiving database options</span></span>

1. <span data-ttu-id="47f01-113">Em um computador que esteja executando o Skype for Business Server, ou no qual as ferramentas administrativas do Skype for Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo usuários local (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="47f01-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47f01-114">Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para publicar uma topologia, que é necessária para adicionar um componente à topologia, você deve usar uma conta que seja membro do grupo **Administradores de domínio** e o **RTCUniversalSer verAdmins** grupo, e que tem permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o repositório de arquivos do Skype for Business Server (ou seja, o construtor de topologia pode configurar o controle de acesso discricional necessário listas (DACLs) ou uma conta com direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="47f01-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="47f01-115">Iniciar o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="47f01-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="47f01-116">Na árvore de console, navegue até o pool de front-ends no qual o arquivamento foi implantado e clique no nome do pool de front-ends no qual deseja alterar as opções de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="47f01-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="47f01-117">No menu **Ação**, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="47f01-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="47f01-118">Na caixa de diálogo **Editar propriedades**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="47f01-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="47f01-119">Role a tela para baixo até **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="47f01-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="47f01-120">Em **Arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47f01-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="47f01-121">Para alterar para um armazenamento existente diferente do SQL Server, em **Armazenamento de arquivamento do SQL Server**, na caixa de listagem suspensa, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47f01-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="47f01-122">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="47f01-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="47f01-123">Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, depois, na caixa de diálogo **Definir novo armazenamento do SQL Server** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47f01-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="47f01-124">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="47f01-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="47f01-125">Para especificar uma nova loja do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **definir novo SQL Server Store** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47f01-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="47f01-126">Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="47f01-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="47f01-127">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="47f01-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="47f01-128">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="47f01-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="47f01-129">Para adicionar um armazenamento do SQL Server de espelhamento ou alteração a um armazenamento existente diferente do SQL Server, selecione **Habilitar espelhamento do armazenamento do SQL Server** e, em seguida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47f01-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="47f01-130">Para usar uma loja existente do SQL Server para espelhamento, na caixa de listagem suspensa de espelhamento do **repositório do SQL Server** , clique no nome da loja do SQL Server que você deseja usar para espelhamento.</span><span class="sxs-lookup"><span data-stu-id="47f01-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="47f01-131">Para especificar uma nova loja do SQL Server para espelhamento, clique em **novo**e, na caixa de diálogo **definir novo repositório do SQL Server** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="47f01-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="47f01-132">a.</span><span class="sxs-lookup"><span data-stu-id="47f01-132">a.</span></span> <span data-ttu-id="47f01-133">No **FQDN do SQL Server**, ESPECIFIQUE o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="47f01-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="47f01-134">b.</span><span class="sxs-lookup"><span data-stu-id="47f01-134">b.</span></span> <span data-ttu-id="47f01-135">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="47f01-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="47f01-136">c.</span><span class="sxs-lookup"><span data-stu-id="47f01-136">c.</span></span> <span data-ttu-id="47f01-137">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="47f01-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="47f01-138">Se você habilitar o espelhamento do SQL Server e quiser adicionar ou alterar uma testemunha de espelhamento do SQL Server (uma terceira instância do SQL Server separada que pode detectar a integridade do servidor do SQL Server e das instâncias de espelhamento principais), selecione a **testemunha usar o espelhamento do SQL Server para Habilite** a caixa de seleção failover automático e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="47f01-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="47f01-139">a.</span><span class="sxs-lookup"><span data-stu-id="47f01-139">a.</span></span> <span data-ttu-id="47f01-140">Em **FQDN do SQL Server**, ESPECIFIQUE o FQDN do servidor no qual você deseja criar a nova testemunha de espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="47f01-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="47f01-141">b.</span><span class="sxs-lookup"><span data-stu-id="47f01-141">b.</span></span> <span data-ttu-id="47f01-142">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="47f01-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="47f01-143">c.</span><span class="sxs-lookup"><span data-stu-id="47f01-143">c.</span></span> <span data-ttu-id="47f01-144">Se a instância do SQL Server especificada estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação** ao espelhamento e, em seguida, em **número de porta espelhada**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="47f01-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="47f01-145">Para alternar para a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento em servidores Exchange (se todos os usuários na sua implantação estiverem hospedados em seus servidores Exchange), exclua todas as informações para arquivar bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="47f01-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="47f01-146">Se você tiver usuários do Skype for Business que não são hospedados nos Exchange Servers, não exclua as informações da loja do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="47f01-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="47f01-147">Para salvar a configuração, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="47f01-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="47f01-148">As alterações feitas no construtor de topologias não entram em vigor até que você publique a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="47f01-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="47f01-149">Para obter detalhes, consulte [Adicionar bancos de dados de arquivamento a uma implantação existente no Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span><span class="sxs-lookup"><span data-stu-id="47f01-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="47f01-150">Alterar a localização do banco de dados de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47f01-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="47f01-151">Na maioria dos casos, você não precisará mudar a localização do banco de dados de arquivamento, que é especificado ao instalar o servidor de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="47f01-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="47f01-152">Mas se ocorrer uma falha de hardware ou outro problema, você poderá apontar o servidor de arquivamento para um novo banco de dados usando o cmdlet **Set-CsArchivingServer**.</span><span class="sxs-lookup"><span data-stu-id="47f01-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="47f01-153">O exemplo a seguir altera a localização do banco de dados de arquivamento para o servidor de arquivamento ArchivingServer: ATL-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="47f01-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="47f01-154">Neste exemplo, o novo banco de dados está localizado em ArchivingDatabase:atl-sql-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="47f01-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


