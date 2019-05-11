---
title: Alterar as opções de banco de dados de arquivamento no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 'Resumo: Saiba como alterar as opções de banco de dados arquivamento para Skype para Business Server.'
ms.openlocfilehash: b2ffa1cfd9686be941cca2a1ffdc2684006dde50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884962"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="daf19-103">Alterar as opções de banco de dados de arquivamento no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="daf19-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="daf19-104">**Resumo:** Saiba como alterar as opções de banco de dados arquivamento para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="daf19-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="daf19-105">Se você implantar o arquivamento usando o armazenamento do SQL Server para armazenamento de arquivamento para qualquer um dos seus usuários, você pode fazer o seguinte banco de dados alterações de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="daf19-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="daf19-106">Use outro banco de dados do SQL Server para armazenamento de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="daf19-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="daf19-107">Isso inclui o banco de dados de arquivamento primário e de qualquer banco de dados que você pode usar para espelhamento do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="daf19-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="daf19-108">Alterne para a integração do Microsoft Exchange para armazenar arquivos nos servidores do Exchange e dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="daf19-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="daf19-109">Se todos os usuários estão hospedados em seus servidores Exchange e você deseja usar o armazenamento do Microsoft Exchange para todos os usuários em sua implantação, você deve remover os bancos de dados de repositório do SQL Server da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="daf19-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="daf19-110">Para tornar qualquer uma dessas alterações, você deve executar o construtor de topologias, faça as alterações e publique a topologia novamente.</span><span class="sxs-lookup"><span data-stu-id="daf19-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="daf19-111">Não especifica informações do **repositório de arquivamento do SQL Server** ou **espelhamento do repositório de habilitar o SQL Server** , a menos que tenha Skype para usuários corporativos que não esteja hospedados em servidores do Exchange.</span><span class="sxs-lookup"><span data-stu-id="daf19-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="daf19-112">Modificando opções do banco de dados de arquivamento</span><span class="sxs-lookup"><span data-stu-id="daf19-112">Change Archiving database options</span></span>

1. <span data-ttu-id="daf19-113">Em um computador que esteja executando o Skype para Business Server ou em que o Skype para ferramentas administrativas do Business Server estão instaladas, faça logon usando uma conta que seja membro do grupo local de usuários (ou uma conta com direitos de usuário equivalentes).</span><span class="sxs-lookup"><span data-stu-id="daf19-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="daf19-114">Você pode definir uma topologia usando uma conta que seja membro do grupo de usuários local, mas para publicar uma topologia, o que é necessário para adicionar um componente à topologia, você deve usar uma conta que seja membro do grupo **Administradores** de domínio e o **RTCUniversalSer verAdmins** grupo e que tem permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você está usando para o Skype para repositório de arquivos do servidor de negócios (ou seja, de modo que o construtor de topologia pode configurar o controle de acesso discricionário necessários listas (DACLs) ou uma conta com direitos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="daf19-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="daf19-115">Inicie o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="daf19-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="daf19-116">Na árvore de console, navegue até o pool de front-ends no qual o arquivamento foi implantado e clique no nome do pool de front-ends no qual deseja alterar as opções de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="daf19-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="daf19-117">No menu **Ação**, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="daf19-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="daf19-118">Na caixa de diálogo **Editar propriedades**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="daf19-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="daf19-119">Role a tela para baixo até **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="daf19-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="daf19-120">Em **Arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="daf19-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="daf19-121">Para alterar para um armazenamento existente diferente do SQL Server, em **Armazenamento de arquivamento do SQL Server**, na caixa de listagem suspensa, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="daf19-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="daf19-122">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="daf19-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="daf19-123">Para especificar um novo armazenamento do SQL Server, clique em **Novo** e, depois, na caixa de diálogo **Definir novo armazenamento do SQL Server** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="daf19-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="daf19-124">Para usar um armazenamento existente do SQL Server, na caixa de listagem suspensa, clique no nome do armazenamento do SQL Server que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="daf19-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="daf19-125">Para especificar um novo repositório do SQL Server, clique em **novo**e, em seguida, na caixa de diálogo **Definir novo repositório do SQL Server** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="daf19-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="daf19-126">Em **FQDN do SQL Server**, especifique o FQDN do servidor no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="daf19-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="daf19-127">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="daf19-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="daf19-128">Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="daf19-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="daf19-129">Para adicionar um armazenamento do SQL Server de espelhamento ou alteração a um armazenamento existente diferente do SQL Server, selecione **Habilitar espelhamento do armazenamento do SQL Server** e, em seguida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="daf19-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="daf19-130">Para usar um armazenamento existente do SQL Server para espelhamento, na caixa de listagem suspensa **espelho do repositório de arquivamento do SQL Server** , clique no nome do repositório do SQL Server que você deseja usar para espelhamento.</span><span class="sxs-lookup"><span data-stu-id="daf19-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="daf19-131">Para especificar um novo repositório do SQL Server para espelhamento, clique em **novo**e, em seguida, na caixa de diálogo **Definir novo repositório do SQL Server** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="daf19-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="daf19-132">a.</span><span class="sxs-lookup"><span data-stu-id="daf19-132">a.</span></span> <span data-ttu-id="daf19-133">Em **FQDN do SQL Server**, especifique o FQDN do SQL Server no qual você deseja criar o novo repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="daf19-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="daf19-134">b.</span><span class="sxs-lookup"><span data-stu-id="daf19-134">b.</span></span> <span data-ttu-id="daf19-135">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="daf19-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="daf19-136">c.</span><span class="sxs-lookup"><span data-stu-id="daf19-136">c.</span></span> <span data-ttu-id="daf19-137">Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="daf19-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="daf19-138">Se você habilitar o espelhamento do SQL Server e deseja adicionar ou alterar um (uma terceira, separada instância do SQL Server que pode detectar a integridade das instâncias principais do SQL Server server e espelho) de testemunha de espelhamento do SQL Server, selecione a testemunha de espelhamento do SQL Server do uso de **para Habilitar o failover automático** caixa de seleção e, em seguida, execute um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="daf19-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="daf19-139">a.</span><span class="sxs-lookup"><span data-stu-id="daf19-139">a.</span></span> <span data-ttu-id="daf19-140">Em **FQDN do SQL Server**, especifique o FQDN do servidor no qual você deseja criar o novo SQL Server testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="daf19-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="daf19-141">b.</span><span class="sxs-lookup"><span data-stu-id="daf19-141">b.</span></span> <span data-ttu-id="daf19-142">Clique em **Instância padrão** para usar a instância padrão ou, para especificar uma instância diferente, clique em **Instância nomeada** e especifique a instância que deseja usar para a testemunha de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="daf19-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="daf19-143">c.</span><span class="sxs-lookup"><span data-stu-id="daf19-143">c.</span></span> <span data-ttu-id="daf19-144">Se a instância especificada do SQL Server estiver em uma relação de espelhamento, marque a caixa de seleção **esta instância SQL está em relação de espelhamento** e, em seguida, em **número da porta espelho**, especifique o número da porta.</span><span class="sxs-lookup"><span data-stu-id="daf19-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="daf19-145">Para alternar para a integração do Microsoft Exchange para armazenar dados de arquivamento e arquivos nos servidores do Exchange (se todos os usuários em sua implantação são hospedados em seus servidores do Exchange), exclua todas as informações de bancos de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="daf19-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="daf19-146">Se você tiver quaisquer Skype para usuários corporativos que não esteja hospedado em servidores do Exchange, não exclua as informações de repositório do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="daf19-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="daf19-147">Para salvar a configuração, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="daf19-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="daf19-148">As alterações feitas no construtor de topologia não entrarão em vigor até que você publica a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="daf19-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="daf19-149">Para obter detalhes, consulte [bancos de dados de arquivamento de adicionar a uma implantação existente no Skype para Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span><span class="sxs-lookup"><span data-stu-id="daf19-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="daf19-150">Alterar a localização do banco de dados de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="daf19-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="daf19-151">Na maioria dos casos, você não precisará mudar a localização do banco de dados de arquivamento, que é especificado ao instalar o servidor de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="daf19-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="daf19-152">Mas se ocorrer uma falha de hardware ou outro problema, você poderá apontar o servidor de arquivamento para um novo banco de dados usando o cmdlet **Set-CsArchivingServer**.</span><span class="sxs-lookup"><span data-stu-id="daf19-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="daf19-153">O exemplo a seguir altera o local do banco de dados de arquivamento para o archivingserver: ATL-cs-001.contoso.com o servidor de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="daf19-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="daf19-154">Neste exemplo, o novo banco de dados está localizado em ArchivingDatabase:atl-sql-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="daf19-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


