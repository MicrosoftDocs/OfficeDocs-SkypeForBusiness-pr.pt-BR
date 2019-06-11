---
title: Remover instâncias SQL Server e bancos de dados no Servidor Back-End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03a318e81b839d5f92dbaa4ddcc70bbbc8e2e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="a43ee-102">Remover instâncias SQL Server e bancos de dados no Servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="a43ee-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a43ee-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a43ee-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a43ee-104">Você remove os bancos de dados e instâncias do Microsoft SQL Server após remover os servidores que executam o Lync Server 2010 que sejam dependentes deles ou após a reconfiguração dos servidores que executam o Lync Server 2010 para usar outro banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a43ee-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="a43ee-105">Você precisa executar o procedimento neste tópico quando desativar o SQL Server atual ou reconfigurar o servidor atual que executa o Lync Server 2010 de forma que ele processe os bancos de dados obsoletos ou indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="a43ee-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="a43ee-106">Para remover os bancos de dados ou instâncias do servidor de arquivamento ou Monitoring Server, primeiro você deve remover a função de servidor.</span><span class="sxs-lookup"><span data-stu-id="a43ee-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="a43ee-107">Da mesma forma, para remover as instâncias ou os bancos de dados do pool de front-end, você deve primeiro remover ou reconfigurar a função de servidor dependente.</span><span class="sxs-lookup"><span data-stu-id="a43ee-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="a43ee-108">Esses procedimentos não fazem distinção entre bancos de dados posicionados ou instâncias separadas para servidores.</span><span class="sxs-lookup"><span data-stu-id="a43ee-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="a43ee-109">Os procedimentos não são afetados pela colocação de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="a43ee-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a43ee-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a43ee-110">In This Section</span></span>

  - [<span data-ttu-id="a43ee-111">Remover o banco de dados do Servidor SQL para um pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a43ee-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="a43ee-112">Remover banco de dados do SQL Server de um servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="a43ee-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="a43ee-113">Remover o banco de dados do Servidor SQL de um servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="a43ee-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

