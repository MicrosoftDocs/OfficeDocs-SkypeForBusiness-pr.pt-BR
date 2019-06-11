---
title: Remover o banco de dados do Servidor SQL para um pool Front-End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6dcbe9bcab20438d02fe489666f9b4c0c0f6d0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="ee93c-102">Remover o banco de dados do Servidor SQL para um pool Front-End</span><span class="sxs-lookup"><span data-stu-id="ee93c-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee93c-103">_**Tópico da última modificação:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ee93c-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ee93c-104">Depois de remover um pool de front-end do Microsoft Lync Server 2010 ou reconfigurar o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedavam os dados do pool.</span><span class="sxs-lookup"><span data-stu-id="ee93c-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="ee93c-105">Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ee93c-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="ee93c-106">Para remover o banco de dados do SQL Server usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="ee93c-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="ee93c-107">No servidor front-end do Lync Server 2013, abra o construtor de topologias e baixe a topologia existente.</span><span class="sxs-lookup"><span data-stu-id="ee93c-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="ee93c-108">No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, repositórios do **SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao pool de front-end removido ou reconfigurado e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="ee93c-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="ee93c-109">Publique a topologia e verifique o status de replicação.</span><span class="sxs-lookup"><span data-stu-id="ee93c-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="ee93c-110">Para Remover bancos de dados de usuários e aplicativos do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ee93c-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="ee93c-111">Para remover os bancos de dados no SQL Server, você deve ser membro do grupo Administradores do SQL Server do SQL Server no qual está removendo os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ee93c-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="ee93c-112">Abrir o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ee93c-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="ee93c-113">Para remover o banco de dados do armazenamento de usuários do pool, digite:</span><span class="sxs-lookup"><span data-stu-id="ee93c-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="ee93c-114">Onde \<FQDN\> é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de \<dados\> e a instância é a instância do banco de dados nomeado (ou seja, se foi definida uma).</span><span class="sxs-lookup"><span data-stu-id="ee93c-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="ee93c-115">Para remover o banco de dados do repositório de aplicativos do pool, digite:</span><span class="sxs-lookup"><span data-stu-id="ee93c-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="ee93c-116">Onde \<FQDN\> é o FQDN do servidor de banco de dados \<,\> e instância é a instância do banco de dados nomeado (ou seja, se foi definida uma).</span><span class="sxs-lookup"><span data-stu-id="ee93c-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="ee93c-117">Quando o cmdlet **Uninstall-CsDataBase** solicita que você confirme ações, leia as informações e, em seguida, pressione **Y** (ou pressione Enter) para continuar, ou pressione **N** e, em seguida, insira se você deseja parar o cmdlet (ou seja, em caso de erros).</span><span class="sxs-lookup"><span data-stu-id="ee93c-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

