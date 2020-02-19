---
title: 'Lync Server 2013: visão geral da implantação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33328e124a1b444b4639b85bc6c1941c55f5ed1f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="59af6-102">Visão geral da implantação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59af6-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59af6-103">_**Última modificação do tópico:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="59af6-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="59af6-104">A principal diferença entre o Lync Server 2013 Enterprise Edition e o Lync Server 2013 Standard Edition é que a edição Standard não é compatível com os recursos de alta disponibilidade incluídos na Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="59af6-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="59af6-105">Para alta disponibilidade, você precisa implantar vários servidores front-end em um pool e, em seguida, pode espelhar o servidor que executa o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59af6-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="59af6-106">Com o Enterprise Edition, você pode optar por colocar ou definir um servidor de mediação autônomo.</span><span class="sxs-lookup"><span data-stu-id="59af6-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="59af6-107">O servidor de monitoramento e o servidor de arquivamento podem usar um servidor autônomo executando o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59af6-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="59af6-108">Ou podem ter instâncias do SQL Server em execução no servidor de banco de dados para os pools e servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="59af6-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="59af6-109">Os servidores que executam o Lync Server 2013 Standard Edition são destinados a organizações menores e locais remotos, que são removidos geograficamente da implantação principal da organização.</span><span class="sxs-lookup"><span data-stu-id="59af6-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="59af6-110">Dois servidores de servidor Standard Edition emparelhados para failover em caso de desastre podem suportar até 5.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="59af6-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="59af6-111">Não é possível poolr servidores Standard Edition como servidores de front-end na Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="59af6-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="59af6-112">Além disso, o banco de dados do SQL Server que a Standard Edition usa é um servidor colocado executando o SQL Server Express projetado para lidar com cargas de trabalho do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="59af6-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="59af6-113">Isso não significa que todas as funções devem residir em um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="59af6-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="59af6-114">Você pode ter servidores de mediação autônomos e servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="59af6-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="59af6-115">O banco de dados do SQL Server para o repositório de gerenciamento central e para os fins do Lync Server 2013 deve residir no servidor Standard Edition colocado com o servidor que executa o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59af6-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="59af6-116">O servidor de monitoramento e o servidor de arquivamento usam um servidor autônomo com o banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59af6-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

