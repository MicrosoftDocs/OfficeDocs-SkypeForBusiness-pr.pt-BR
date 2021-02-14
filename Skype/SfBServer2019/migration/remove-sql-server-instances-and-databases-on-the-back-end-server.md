---
title: Remover a Instância do SQL Server e os bancos de dados no Servidor Back-End
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
description: Remova os bancos de dados e instâncias do Microsoft SQL Server depois de remover os servidores em execução que dependem deles ou depois de reconfigurar os servidores para usar outro banco de dados. Você precisa executar o procedimento neste tópico ao retirar o SQL Server atual ou reconfigurar o servidor atual de forma que ele renderiza os bancos de dados obsoletos ou indisponíveis.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752153"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="1eba7-104">Remover a Instância do SQL Server e os bancos de dados no Servidor Back-End</span><span class="sxs-lookup"><span data-stu-id="1eba7-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="1eba7-105">Remova os bancos de dados e instâncias do Microsoft SQL Server depois de remover os servidores em execução que dependem deles ou depois de reconfigurar os servidores para usar outro banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1eba7-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="1eba7-106">Você precisa executar o procedimento neste tópico ao retirar o SQL Server atual ou reconfigurar o servidor atual de forma que ele renderiza os bancos de dados obsoletos ou indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="1eba7-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="1eba7-107">Para remover os bancos de dados ou instâncias do Servidor de Arquivamento ou do Monitoring Server, você deve primeiro remover a função de servidor.</span><span class="sxs-lookup"><span data-stu-id="1eba7-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="1eba7-108">Da mesma forma, para remover as instâncias ou os bancos de dados do pool de Front-End, primeiro você deve remover ou reconfigurar a função de servidor dependente.</span><span class="sxs-lookup"><span data-stu-id="1eba7-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="1eba7-109">Esses procedimentos não fazem distinção entre bancos de dados colocados ou instâncias separadas.</span><span class="sxs-lookup"><span data-stu-id="1eba7-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="1eba7-110">Os procedimentos não são afetados pela colocação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1eba7-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="1eba7-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1eba7-111">In this section</span></span>

- [<span data-ttu-id="1eba7-112">Remover o banco de dados do Servidor SQL para um pool Front-End</span><span class="sxs-lookup"><span data-stu-id="1eba7-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="1eba7-113">Remover banco de dados do SQL Server de um servidor de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="1eba7-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="1eba7-114">Remover o banco de dados do Servidor SQL de um servidor de Arquivamento</span><span class="sxs-lookup"><span data-stu-id="1eba7-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

