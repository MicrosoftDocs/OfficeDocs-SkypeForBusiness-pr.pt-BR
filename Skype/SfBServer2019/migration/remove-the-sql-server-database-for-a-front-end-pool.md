---
title: Remover o banco de dados do Servidor SQL para um pool Front-End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de remover um pool de front-end ou reconfigurar o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedam os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.
ms.openlocfilehash: d22a90401bdfa4a2897a18805e8b9c588892c5fb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241560"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="d76f0-104">Remover o banco de dados do Servidor SQL para um pool Front-End</span><span class="sxs-lookup"><span data-stu-id="d76f0-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="d76f0-105">Depois de remover um pool de front-end ou reconfigurar o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedam os dados do pool.</span><span class="sxs-lookup"><span data-stu-id="d76f0-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="d76f0-106">Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d76f0-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="d76f0-107">Para remover o banco de dados do SQL Server usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="d76f0-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="d76f0-108">No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias e baixe a topologia existente.</span><span class="sxs-lookup"><span data-stu-id="d76f0-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="d76f0-109">No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, repositórios do **SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao pool de front-end removido ou reconfigurado e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="d76f0-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="d76f0-110">Publique a topologia e verifique o status de replicação.</span><span class="sxs-lookup"><span data-stu-id="d76f0-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="d76f0-111">Para Remover bancos de dados de usuários e aplicativos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="d76f0-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="d76f0-112">Para remover os bancos de dados no SQL Server, você deve ser membro do grupo Administradores do SQL Server do SQL Server no qual está removendo os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d76f0-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="d76f0-113">Abrir o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d76f0-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="d76f0-114">Para remover o banco de dados do armazenamento de usuários do pool, digite:</span><span class="sxs-lookup"><span data-stu-id="d76f0-114">To remove the database for the pool user store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="d76f0-115">Onde _ \<FQDN\> _ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de _ \<dados\> _ e a instância é a instância do banco de dados nomeado (ou seja, se foi definida uma).</span><span class="sxs-lookup"><span data-stu-id="d76f0-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="d76f0-116">Para remover o banco de dados do repositório de aplicativos do pool, digite:</span><span class="sxs-lookup"><span data-stu-id="d76f0-116">To remove the database for the pool application store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="d76f0-117">Onde _ \<FQDN\> _ é o FQDN do servidor de banco de dados, e _ \<instância\> _ é a instância do banco de dados nomeado (ou seja, se foi definida uma).</span><span class="sxs-lookup"><span data-stu-id="d76f0-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="d76f0-118">Quando o cmdlet **Uninstall-CsDataBase** solicita que você confirme as ações, leia as informações e, em seguida, pressione Y (ou Enter) para continuar, ou pressione N e, em seguida, insira se você deseja parar o cmdlet (se houver erros).</span><span class="sxs-lookup"><span data-stu-id="d76f0-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

