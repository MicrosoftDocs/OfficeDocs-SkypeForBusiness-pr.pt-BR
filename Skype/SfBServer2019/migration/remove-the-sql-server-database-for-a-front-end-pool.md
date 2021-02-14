---
title: Remover o banco de dados do SQL Server para um pool Front-End
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Depois de remover um pool de #A0 ou reconfigurar o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedaram os dados do pool. Use os procedimentos a seguir para remover as definições do Construtor de Topologias e, em seguida, remova o banco de dados e os arquivos de log do servidor de banco de dados.'
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753403"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="fcaf9-104">Remover o banco de dados do SQL Server para um pool Front-End</span><span class="sxs-lookup"><span data-stu-id="fcaf9-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="fcaf9-105">Depois de remover um pool de #A0 ou reconfigurar o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedaram os dados do pool.</span><span class="sxs-lookup"><span data-stu-id="fcaf9-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="fcaf9-106">Use os procedimentos a seguir para remover as definições do Construtor de Topologias e, em seguida, remova o banco de dados e os arquivos de log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fcaf9-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="fcaf9-107">Para remover o banco de dados do SQL Server usando o Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="fcaf9-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="fcaf9-108">No Servidor front-end do Skype for Business Server 2019, abra o Construtor de Topologias e baixe a topologia existente.</span><span class="sxs-lookup"><span data-stu-id="fcaf9-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="fcaf9-109">No Construtor de Topologias, navegue até **Componentes Compartilhados** e, em seguida, Armazenamentos do SQL Server, clique com o botão direito do mouse na instância do SQL Server associada ao pool de #A0 removido ou reconfigurado e clique em  **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="fcaf9-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="fcaf9-110">Publique a topologia e verifique o status da replicação.</span><span class="sxs-lookup"><span data-stu-id="fcaf9-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="fcaf9-111">Para remover bancos de dados de usuários e aplicativos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="fcaf9-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="fcaf9-112">Para remover os bancos de dados no sql server, você deve ser membro do grupo sysadmins do SQL Server para o sql server onde você está removendo os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fcaf9-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="fcaf9-113">Abra o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fcaf9-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="fcaf9-114">Para remover o banco de dados do repositório de usuários do pool, digite:</span><span class="sxs-lookup"><span data-stu-id="fcaf9-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="fcaf9-115">Onde está o FQDN (nome de domínio totalmente qualificado) do servidor de banco de dados e é a instância nomeada do banco de dados  _\<FQDN\>_  _\<instance\>_ (ou seja, se uma foi definida).</span><span class="sxs-lookup"><span data-stu-id="fcaf9-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="fcaf9-116">Para remover o banco de dados do repositório de aplicativos do pool, digite:</span><span class="sxs-lookup"><span data-stu-id="fcaf9-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="fcaf9-117">Onde está o FQDN do servidor de banco de dados e é a instância nomeada do banco de dados  _\<FQDN\>_  _\<instance\>_ (ou seja, se uma foi definida).</span><span class="sxs-lookup"><span data-stu-id="fcaf9-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="fcaf9-118">Quando o cmdlet **Uninstall-CsDataBase** solicitar que você confirme as ações, leia as informações e pressione Y (ou Enter) para continuar ou pressione N e Enter se quiser interromper o cmdlet (se houver erros).</span><span class="sxs-lookup"><span data-stu-id="fcaf9-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

