---
title: Remover banco de dados do SQL Server de um servidor de Monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f877f7d8d1ade4d260ed137f52046c21f29cf11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="627d0-102">Remover banco de dados do SQL Server de um servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="627d0-102">Remove the SQL Server database for a Monitoring server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="627d0-103">_**Tópico da última modificação:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="627d0-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="627d0-104">Depois de remover um Microsoft Lync Server 2010 Monitoring Server, você pode remover os bancos de dados do SQL Server que hospedam os dados do servidor.</span><span class="sxs-lookup"><span data-stu-id="627d0-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="627d0-105">Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="627d0-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="627d0-106">Para remover o banco de dados do SQL Server usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="627d0-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="627d0-107">No servidor front-end do Lync Server 2013, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="627d0-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="627d0-108">No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, **repositórios do SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao servidor de monitoramento removido ou reconfigurado e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="627d0-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="627d0-109">Publique a topologia e, em seguida, verifique o status de replicação.</span><span class="sxs-lookup"><span data-stu-id="627d0-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="627d0-110">Para remover os arquivos de banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="627d0-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="627d0-111">Para remover os bancos de dados no servidor baseado no SQL Server, você deve ser membro do grupo Administradores do SQL Server para o servidor SQL Server no qual está removendo os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="627d0-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="627d0-112">Abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="627d0-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="627d0-113">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="627d0-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="627d0-114">Onde \<FQDN\> é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de \<dados\> e a instância é a instância do banco de dados nomeado opcional.</span><span class="sxs-lookup"><span data-stu-id="627d0-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="627d0-115">Quando o cmdlet **Uninstall-CsDataBase** solicita que você confirme ações, leia as informações e, em seguida, pressione **Y** (ou pressione Enter) para continuar, ou pressione **N** e, em seguida, insira se você deseja parar o cmdlet (ou seja, em caso de erros).</span><span class="sxs-lookup"><span data-stu-id="627d0-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

