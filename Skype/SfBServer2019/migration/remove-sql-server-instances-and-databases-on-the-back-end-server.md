---
title: Remover instâncias SQL Server e bancos de dados no Servidor Back-End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você remove os bancos de dados e instâncias do Microsoft SQL Server após remover os servidores em execução dependentes deles ou depois de reconfigurar os servidores para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando desativar o SQL Server atual ou reconfigurar o servidor atual de modo que ele processe os bancos de dados obsoletos ou indisponíveis.
ms.openlocfilehash: 01552fcd494514802fffb35de7db7643f8cc26fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812979"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="7492f-104">Remover instâncias SQL Server e bancos de dados no Servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="7492f-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="7492f-105">Você remove os bancos de dados e instâncias do Microsoft SQL Server após remover os servidores em execução dependentes deles ou depois de reconfigurar os servidores para usar outro banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7492f-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="7492f-106">Você precisa executar o procedimento neste tópico quando desativar o SQL Server atual ou reconfigurar o servidor atual de modo que ele processe os bancos de dados obsoletos ou indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="7492f-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="7492f-107">Para remover os bancos de dados ou instâncias do servidor de arquivamento ou Monitoring Server, primeiro você deve remover a função de servidor.</span><span class="sxs-lookup"><span data-stu-id="7492f-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="7492f-108">Da mesma forma, para remover as instâncias ou os bancos de dados do pool de front-end, você deve primeiro remover ou reconfigurar a função de servidor dependente.</span><span class="sxs-lookup"><span data-stu-id="7492f-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="7492f-109">Esses procedimentos não fazem distinção entre bancos de dados posicionados ou instâncias separadas para servidores.</span><span class="sxs-lookup"><span data-stu-id="7492f-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="7492f-110">Os procedimentos não são afetados pela colocação de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="7492f-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7492f-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7492f-111">In this section</span></span>

- [<span data-ttu-id="7492f-112">Remover o banco de dados do Servidor SQL para um pool Front-End</span><span class="sxs-lookup"><span data-stu-id="7492f-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="7492f-113">Remover banco de dados do SQL Server de um servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="7492f-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="7492f-114">Remover o banco de dados do Servidor SQL de um servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="7492f-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

