---
title: Remover instâncias e bancos de dados do SQL Server no servidor back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02aa65c631e62d7ffb699d85d982858164848c2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="d6758-102">Remover instâncias e bancos de dados do SQL Server no servidor back-end</span><span class="sxs-lookup"><span data-stu-id="d6758-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6758-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d6758-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d6758-104">Você remove os bancos de dados e instâncias do Microsoft SQL Server após remover os servidores que executam o Lync Server 2010 que são dependentes deles ou após a reconfiguração dos servidores que executam o Lync Server 2010 para usar outro banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d6758-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="d6758-105">Você precisa executar o procedimento neste tópico quando você desativa o SQL Server atual ou reconfigura o servidor atual executando o Lync Server 2010 de forma que ele processe os bancos de dados obsoletos ou indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="d6758-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="d6758-106">Para remover os bancos de dados ou instâncias do servidor de arquivamento ou do Monitoring Server, primeiro você deve remover a função de servidor.</span><span class="sxs-lookup"><span data-stu-id="d6758-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="d6758-107">Da mesma forma, para remover as instâncias ou os bancos de dados do pool de front-ends, primeiro você deve remover ou reconfigurar a função de servidor dependente.</span><span class="sxs-lookup"><span data-stu-id="d6758-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="d6758-108">Esses procedimentos não fazem distinção entre bancos de dados colocados ou instâncias separadas.</span><span class="sxs-lookup"><span data-stu-id="d6758-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="d6758-109">Os procedimentos não são afetados pela colocação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d6758-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6758-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d6758-110">In This Section</span></span>

  - [<span data-ttu-id="d6758-111">Remover o banco de dados do SQL Server para um pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="d6758-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="d6758-112">Remover o banco de dados do SQL Server de um servidor de monitoramento</span><span class="sxs-lookup"><span data-stu-id="d6758-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="d6758-113">Remover o banco de dados do SQL Server para um servidor de arquivamento</span><span class="sxs-lookup"><span data-stu-id="d6758-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

