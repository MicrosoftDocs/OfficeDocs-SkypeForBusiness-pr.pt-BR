---
title: Remover o banco de dados do SQL Server para um pool de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de remover um pool de Front-End ou reconfigure o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedava os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologia e, em seguida, remover os arquivos de banco de dados e log do servidor de banco de dados.
ms.openlocfilehash: 35c9429fc16aef886945f8b0adcd5894ce40b834
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373123"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="edb1d-104">Remover o banco de dados do SQL Server para um pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="edb1d-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="edb1d-105">Depois de remover um pool de Front-End ou reconfigure o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedava os dados do pool.</span><span class="sxs-lookup"><span data-stu-id="edb1d-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="edb1d-106">Use os procedimentos a seguir para remover as definições do construtor de topologia e, em seguida, remover os arquivos de banco de dados e log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="edb1d-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="edb1d-107">Para remover o banco de dados do SQL Server usando o construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="edb1d-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="edb1d-108">Do Skype para Business Server 2019 servidor Front-End, abra o construtor de topologia e baixe a topologia existente.</span><span class="sxs-lookup"><span data-stu-id="edb1d-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="edb1d-109">No construtor de topologias, navegue até **Componentes compartilhados** e depois **Repositórios do SQL Server**, clique com o botão a instância do SQL Server associada ao pool de Front-End removido ou reconfigurado e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="edb1d-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="edb1d-110">Publique a topologia e verifique o status de replicação.</span><span class="sxs-lookup"><span data-stu-id="edb1d-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="edb1d-111">Para remover os bancos de dados de aplicativo e de usuário do SQL server</span><span class="sxs-lookup"><span data-stu-id="edb1d-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="edb1d-112">Para remover os bancos de dados no SQL server, você deve ser membro do grupo de sysadmins do SQL Server para o qual você está removendo os arquivos de banco de dados do SQL server.</span><span class="sxs-lookup"><span data-stu-id="edb1d-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="edb1d-113">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="edb1d-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="edb1d-114">Para remover o banco de dados para o repositório de usuário do pool, digite:</span><span class="sxs-lookup"><span data-stu-id="edb1d-114">To remove the database for the pool user store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="edb1d-115">Onde _ \<FQDN\> _ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de dados, e _ \<instância\> _ é a instância do banco de dados nomeado (isto é, se houver uma definida).</span><span class="sxs-lookup"><span data-stu-id="edb1d-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="edb1d-116">Para remover o banco de dados para o repositório de aplicativos do pool, digite:</span><span class="sxs-lookup"><span data-stu-id="edb1d-116">To remove the database for the pool application store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="edb1d-117">Onde _ \<FQDN\> _ é o FQDN do servidor de banco de dados, e _ \<instância\> _ é a instância do banco de dados nomeado (isto é, se houver uma definida).</span><span class="sxs-lookup"><span data-stu-id="edb1d-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="edb1d-118">Quando o cmdlet **Uninstall-CsDataBase** solicita a confirmação de ações, leia as informações e pressione Y (ou Enter) para continuar ou pressione N e Enter se você deseja parar o cmdlet (se houver erros).</span><span class="sxs-lookup"><span data-stu-id="edb1d-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

