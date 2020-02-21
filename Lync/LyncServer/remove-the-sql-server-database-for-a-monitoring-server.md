---
title: Remover o banco de dados do SQL Server de um servidor de monitoramento
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
ms.openlocfilehash: f175f17b41a72c63aba77e6eb59aadce985ced82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="ee133-102">Remover o banco de dados do SQL Server de um servidor de monitoramento</span><span class="sxs-lookup"><span data-stu-id="ee133-102">Remove the SQL Server database for a Monitoring server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee133-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ee133-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ee133-104">Após remover um servidor de monitoramento do Microsoft Lync Server 2010, você pode remover os bancos de dados do SQL Server que hospedam os dados do servidor.</span><span class="sxs-lookup"><span data-stu-id="ee133-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="ee133-105">Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ee133-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="ee133-106">Para remover o banco de dados do SQL Server usando o construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="ee133-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="ee133-107">No servidor front-end do Lync Server 2013, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="ee133-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="ee133-108">No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, **repositórios do SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao servidor de monitoramento removido ou reconfigurado e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="ee133-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="ee133-109">Publique a topologia e verifique o status da replicação.</span><span class="sxs-lookup"><span data-stu-id="ee133-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="ee133-110">Para remover os arquivos do banco de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="ee133-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="ee133-111">Para remover os bancos de dados no servidor baseado em SQL Server, você deve ser membro do grupo sysadmins do SQL Server para o servidor do SQL Server no qual você está removendo os arquivos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ee133-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="ee133-112">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ee133-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="ee133-113">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ee133-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="ee133-114">Onde \<FQDN\> é o FQDN (nome de domínio totalmente qualificado) do servidor de banco de \<dados\> e a instância é a instância de banco de dados nomeada opcional.</span><span class="sxs-lookup"><span data-stu-id="ee133-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="ee133-115">Quando o cmdlet **Uninstall-CsDataBase** solicitar que você confirme as ações, leia as informações e pressione **Y** (ou Enter) para continuar ou pressione **N** e em seguida Enter se desejar interromper o cmdlet (em caso de erros).</span><span class="sxs-lookup"><span data-stu-id="ee133-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

