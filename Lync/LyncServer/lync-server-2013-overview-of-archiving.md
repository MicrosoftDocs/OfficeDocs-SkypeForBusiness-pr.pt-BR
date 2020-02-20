---
title: 'Lync Server 2013: visão geral do arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a31ef3492ff4c6d0ced3dcf08dd385b7a6801ef6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="7a032-102">Visão geral do arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a032-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a032-103">_**Última modificação do tópico:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="7a032-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="7a032-104">O arquivamento no Lync Server 2013 oferece uma maneira de arquivar comunicações enviadas por meio do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a032-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="7a032-105">Você pode implementar o arquivamento como parte da implantação do Lync Server 2013 inicial ou pode adicioná-lo a uma implantação existente.</span><span class="sxs-lookup"><span data-stu-id="7a032-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="7a032-106">Para usar os bancos de dados de arquivamento do Lync Server 2013 (bancos de dados do SQL Server) para armazenamento de dados de arquivamento, use o construtor de topologias para adicionar os bancos de dados à sua topologia e, em seguida, publique a topologia novamente.</span><span class="sxs-lookup"><span data-stu-id="7a032-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="7a032-107">Se todos os seus usuários estiverem hospedados no Exchange 2013 e tiverem suas caixas de correio colocadas em bloqueio in-loco, não será necessário atualizar sua topologia, mas só precisará habilitar a integração do Microsoft Exchange para armazenar dados arquivados no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="7a032-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="7a032-108">Ao implementar o Arquivamento, você o configura para especificar o que é arquivado.</span><span class="sxs-lookup"><span data-stu-id="7a032-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="7a032-109">Por padrão, nada é arquivado.</span><span class="sxs-lookup"><span data-stu-id="7a032-109">By default, nothing is archived.</span></span> <span data-ttu-id="7a032-110">Você configura e gerencia o arquivamento usando o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a032-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="7a032-111">É possível implementar o Arquivamento para comunicações internas, comunicações externas ou ambos.</span><span class="sxs-lookup"><span data-stu-id="7a032-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="7a032-112">É possível definir as configurações de arquivamento de toda sua organização e, opcionalmente, para sites específicos, pools de sites e usuários e grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="7a032-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="7a032-113">Para obter detalhes sobre como determinar as opções apropriadas para sua organização, consulte [definindo seus requisitos para arquivamento no Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7a032-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="7a032-114">Para obter detalhes sobre como as políticas e as configurações de arquivamento são implementadas e detalhes sobre as informações que podem ou não ser arquivadas, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="7a032-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

