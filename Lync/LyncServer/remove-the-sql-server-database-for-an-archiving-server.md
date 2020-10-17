---
title: Remover o banco de dados do Servidor SQL de um servidor de Arquivamento
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fab9cefc3fff51267426fd26263f9e2ec20a85ee
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518098"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="f3ad9-102">Remover o banco de dados do Servidor SQL de um servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="f3ad9-102">Remove the SQL Server database for an Archiving server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3ad9-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f3ad9-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f3ad9-104">Após remover um servidor de arquivamento do Microsoft Lync Server 2010, você pode remover os bancos de dados do SQL Server que hospedam os dados do pool.</span><span class="sxs-lookup"><span data-stu-id="f3ad9-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="f3ad9-105">Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f3ad9-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="f3ad9-106">Para remover o banco de dados do SQL Server usando o construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="f3ad9-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="f3ad9-107">No servidor front-end do Lync Server 2013, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f3ad9-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="f3ad9-108">No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, **repositórios do SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao servidor de arquivamento removido ou reconfigurado e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="f3ad9-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="f3ad9-109">Publique a topologia e verifique o status da replicação.</span><span class="sxs-lookup"><span data-stu-id="f3ad9-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="f3ad9-110">Para remover os arquivos do banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3ad9-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="f3ad9-111">Para remover os bancos de dados no SQL Server, você deve ser um membro do grupo sysadmins do SQL Server de onde você está removendo os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f3ad9-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="f3ad9-112">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3ad9-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="f3ad9-113">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f3ad9-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="f3ad9-114">Onde \<FQDN\> é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de dados e \<instance\> é a instância de banco de dados nomeada (isto é, se houver uma definida).</span><span class="sxs-lookup"><span data-stu-id="f3ad9-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="f3ad9-115">Quando o cmdlet **Uninstall-CsDataBase** solicitar que você confirme as ações, leia as informações e pressione **Y** (ou Enter) para continuar ou pressione **N** e em seguida Enter se desejar interromper o cmdlet (em caso de erros).</span><span class="sxs-lookup"><span data-stu-id="f3ad9-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

