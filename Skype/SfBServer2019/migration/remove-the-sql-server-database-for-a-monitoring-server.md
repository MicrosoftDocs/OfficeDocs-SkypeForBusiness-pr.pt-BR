---
title: Remover banco de dados do SQL Server de um servidor de Monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Depois de remover um servidor de monitoramento, você pode remover os bancos de dados do SQL Server que hospedam os dados do servidor. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.
ms.openlocfilehash: 1034abac5b257200504c599fe8655a788d638aa0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241546"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="369f5-104">Remover banco de dados do SQL Server de um servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="369f5-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="369f5-105">Depois de remover um servidor de monitoramento, você pode remover os bancos de dados do SQL Server que hospedam os dados do servidor.</span><span class="sxs-lookup"><span data-stu-id="369f5-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="369f5-106">Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="369f5-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="369f5-107">Para remover o banco de dados do SQL Server usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="369f5-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="369f5-108">No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="369f5-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="369f5-109">No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, repositórios do **SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao servidor de monitoramento removido ou reconfigurado e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="369f5-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="369f5-110">Publique a topologia e, em seguida, verifique o status de replicação.</span><span class="sxs-lookup"><span data-stu-id="369f5-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="369f5-111">Para remover os arquivos de banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="369f5-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="369f5-112">Para remover os bancos de dados no servidor baseado no SQL Server, você deve ser membro do grupo Administradores do SQL Server para o servidor SQL Server no qual está removendo os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="369f5-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="369f5-113">Abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="369f5-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="369f5-114">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="369f5-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="369f5-115">Onde _ \<FQDN\> _ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de _ \<dados\> _ e a instância é a instância do banco de dados nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="369f5-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="369f5-116">Quando o cmdlet **Uninstall-CsDataBase** solicita que você confirme as ações, leia as informações e, em seguida, pressione Y (ou Enter) para continuar, ou pressione N e, em seguida, insira se você deseja parar o cmdlet (se houver erros).</span><span class="sxs-lookup"><span data-stu-id="369f5-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

