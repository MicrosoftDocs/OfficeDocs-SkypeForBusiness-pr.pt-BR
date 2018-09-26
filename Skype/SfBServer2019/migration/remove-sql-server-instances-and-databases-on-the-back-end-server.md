---
title: Remover instâncias do SQL Server e os bancos de dados do servidor Back-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Remover os bancos de dados do Microsoft SQL Server e instâncias depois de remover os servidores que executam que são dependentes neles ou após reconfigurar os servidores para usar outro banco de dados. Você precisará executar o procedimento neste tópico quando você desativa o servidor SQL atual ou reconfigurar o servidor atual de forma que ele processa os bancos de dados obsoletas ou indisponível.
ms.openlocfilehash: 648c808ee293c4fa33352d0f68ba337e4a489d27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027876"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="0c7e8-104">Remover instâncias do SQL Server e os bancos de dados do servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="0c7e8-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="0c7e8-105">Remover os bancos de dados do Microsoft SQL Server e instâncias depois de remover os servidores que executam que são dependentes neles ou após reconfigurar os servidores para usar outro banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="0c7e8-106">Você precisará executar o procedimento neste tópico quando você desativa o servidor SQL atual ou reconfigurar o servidor atual de forma que ele processa os bancos de dados obsoletas ou indisponível.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="0c7e8-107">Para remover os bancos de dados ou instâncias do servidor de arquivamento ou o Monitoring Server, você deve remover primeiro a função de servidor.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="0c7e8-108">Da mesma forma, para remover os bancos de dados para o pool de Front-End ou instâncias, você deve primeiro remover ou reconfigurar a função de servidor dependentes.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="0c7e8-109">Estes procedimentos não fazem nenhuma distinção entre bancos de dados colocados ou instâncias separadas para servidores.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="0c7e8-110">Os procedimentos são afetados pela colocação de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0c7e8-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0c7e8-111">In this section</span></span>

- [<span data-ttu-id="0c7e8-112">Remover o banco de dados do SQL Server para um pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="0c7e8-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="0c7e8-113">Remover o banco de dados do SQL Server para um servidor de monitoramento</span><span class="sxs-lookup"><span data-stu-id="0c7e8-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="0c7e8-114">Remover o banco de dados do SQL Server para um servidor de arquivamento</span><span class="sxs-lookup"><span data-stu-id="0c7e8-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

