---
title: Remover o banco de dados do Servidor SQL de um servidor de Arquivamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de remover um servidor de arquivamento, você pode remover os bancos de dados do SQL Server que hospedava os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologia e, em seguida, remover os arquivos de banco de dados e log do servidor de banco de dados.
ms.openlocfilehash: acb402dd6cb28be5b607b8a358524dfc0c1fea69
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875437"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="f3d64-104">Remover o banco de dados do Servidor SQL de um servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="f3d64-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="f3d64-105">Depois de remover um servidor de arquivamento, você pode remover os bancos de dados do SQL Server que hospedava os dados do pool.</span><span class="sxs-lookup"><span data-stu-id="f3d64-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="f3d64-106">Use os procedimentos a seguir para remover as definições do construtor de topologia e, em seguida, remover os arquivos de banco de dados e log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f3d64-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="f3d64-107">Para remover o banco de dados do SQL Server usando o construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="f3d64-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="f3d64-108">No Skype para Business Server 2019 servidor Front-End, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f3d64-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="f3d64-109">No construtor de topologias, navegue até **Componentes compartilhados** e depois **Repositórios do SQL Server**, com o botão direito do SQL Server instância associados a removido ou reconfigurado o servidor de arquivamento e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="f3d64-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="f3d64-110">Publique a topologia e verifique o status de replicação.</span><span class="sxs-lookup"><span data-stu-id="f3d64-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="f3d64-111">Para remover os arquivos de banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3d64-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="f3d64-112">Para remover os bancos de dados no SQL Server, você deve ser membro do grupo de sysadmins do SQL Server para o qual você está removendo os arquivos de banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f3d64-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="f3d64-113">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f3d64-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="f3d64-114">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f3d64-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="f3d64-115">Onde _ \<FQDN\> _ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de dados, e _ \<instância\> _ é a instância do banco de dados nomeado (isto é, se houver uma definida).</span><span class="sxs-lookup"><span data-stu-id="f3d64-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="f3d64-116">Quando o cmdlet **Uninstall-CsDataBase** solicita a confirmação de ações, leia as informações e pressione Y (ou Enter) para continuar ou pressione N e Enter se você deseja parar o cmdlet (se houver erros).</span><span class="sxs-lookup"><span data-stu-id="f3d64-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

