---
title: Remover o banco de dados do SQL Server de um servidor de Monitoramento
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
description: Depois de remover um Monitoring Server, você pode remover os bancos de dados do SQL Server que hospedaram os dados do servidor. Use os procedimentos a seguir para remover as definições do Construtor de Topologias e, em seguida, remova o banco de dados e os arquivos de log do servidor de banco de dados.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753323"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="1b7df-104">Remover o banco de dados do SQL Server de um servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="1b7df-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="1b7df-105">Depois de remover um Monitoring Server, você pode remover os bancos de dados do SQL Server que hospedaram os dados do servidor.</span><span class="sxs-lookup"><span data-stu-id="1b7df-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="1b7df-106">Use os procedimentos a seguir para remover as definições do Construtor de Topologias e, em seguida, remova o banco de dados e os arquivos de log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1b7df-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="1b7df-107">Para remover o banco de dados do SQL Server usando o Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="1b7df-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="1b7df-108">No Servidor front-end do Skype for Business Server 2019, abra o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="1b7df-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="1b7df-109">No Construtor de Topologias, navegue até **Componentes Compartilhados** e, em seguida, Armazenamentos do SQL Server, clique com o botão direito do mouse na instância do SQL Server associada ao Monitoring Server removido ou reconfigurado e clique em  **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="1b7df-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="1b7df-110">Publique a topologia e verifique o status da replicação.</span><span class="sxs-lookup"><span data-stu-id="1b7df-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="1b7df-111">Para remover os arquivos do banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b7df-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="1b7df-112">Para remover os bancos de dados no servidor baseado em SQL Server, você deve ser membro do grupo sysadmins do SQL Server para o servidor do SQL Server em que você está removendo os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1b7df-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="1b7df-113">Abra o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1b7df-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="1b7df-114">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1b7df-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="1b7df-115">Onde está o FQDN (nome de domínio totalmente qualificado) do servidor de banco de dados e é a instância opcional nomeada do banco  _\<FQDN\>_ de  _\<instance\>_ dados.</span><span class="sxs-lookup"><span data-stu-id="1b7df-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="1b7df-116">Quando o cmdlet **Uninstall-CsDataBase** solicitar que você confirme as ações, leia as informações e pressione Y (ou Enter) para continuar ou pressione N e Enter se quiser interromper o cmdlet (se houver erros).</span><span class="sxs-lookup"><span data-stu-id="1b7df-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

