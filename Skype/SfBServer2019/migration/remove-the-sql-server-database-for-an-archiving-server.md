---
title: Remover o banco de dados do Servidor SQL de um servidor de Arquivamento
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
description: Após remover um servidor de arquivamento, você pode remover os bancos de dados do SQL Server que hospedaram os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753303"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="092ad-104">Remover o banco de dados do Servidor SQL de um servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="092ad-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="092ad-105">Após remover um servidor de arquivamento, você pode remover os bancos de dados do SQL Server que hospedaram os dados do pool.</span><span class="sxs-lookup"><span data-stu-id="092ad-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="092ad-106">Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="092ad-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="092ad-107">Para remover o banco de dados do SQL Server usando o construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="092ad-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="092ad-108">No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="092ad-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="092ad-109">No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, **repositórios do SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao servidor de arquivamento removido ou reconfigurado e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="092ad-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="092ad-110">Publique a topologia e verifique o status da replicação.</span><span class="sxs-lookup"><span data-stu-id="092ad-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="092ad-111">Para remover os arquivos do banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="092ad-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="092ad-112">Para remover os bancos de dados no SQL Server, você deve ser um membro do grupo sysadmins do SQL Server de onde você está removendo os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="092ad-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="092ad-113">Abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="092ad-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="092ad-114">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="092ad-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="092ad-115">Onde _\<FQDN\>_ é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de dados e _\<instance\>_ é a instância de banco de dados nomeada (isto é, se houver uma definida).</span><span class="sxs-lookup"><span data-stu-id="092ad-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="092ad-116">Quando o cmdlet **Uninstall-CsDataBase** solicitar que você confirme as ações, leia as informações e pressione Y (ou Enter) para continuar, ou pressione N e, em seguida, Enter se você deseja interromper o cmdlet (se houver erros).</span><span class="sxs-lookup"><span data-stu-id="092ad-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

