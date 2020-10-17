---
title: 'Lync Server 2013: novos recursos de arquivamento'
description: 'Lync Server 2013: novos recursos de arquivamento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b69c90e62914284f178ae328375c6e350f5b3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561347"
---
# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="d931c-103">Novos recursos de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d931c-103">New Archiving features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d931c-104">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="d931c-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="d931c-105">O arquivamento no Lync Server 2013 pode arquivar os seguintes tipos de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="d931c-105">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="d931c-106">Mensagens instantâneas ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="d931c-106">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="d931c-107">As conferências (reuniões) que são mensagens instantâneas de várias partes</span><span class="sxs-lookup"><span data-stu-id="d931c-107">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="d931c-108">Conteúdo de conferências, incluindo conteúdo carregado (por exemplo, folhetos) e conteúdo relacionado ao evento (por exemplo, entradas, saídas, cargas, compartilhamento e alterações de visibilidade)</span><span class="sxs-lookup"><span data-stu-id="d931c-108">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="d931c-109">Além disso, o arquivamento no Lync Server 2013 oferece novos recursos que melhoram a implantação e a eficiência das operações.</span><span class="sxs-lookup"><span data-stu-id="d931c-109">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="d931c-110">Esses novos recursos consistem em:</span><span class="sxs-lookup"><span data-stu-id="d931c-110">These new features consist of:</span></span>

  - <span data-ttu-id="d931c-111">**Colocação do arquivamento em servidores front-end.**     O Lync Server 2013 não tem uma função de servidor de arquivamento separada.</span><span class="sxs-lookup"><span data-stu-id="d931c-111">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="d931c-112">O Arquivamento é um recurso opcional disponível em todos os Servidores front-end em uma implantação Enterprise Edition e, nos servidores Standard Edition, que podem ser implementados e configurados para um pool ou site.</span><span class="sxs-lookup"><span data-stu-id="d931c-112">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="d931c-113">**Integração com o Microsoft Exchange.**     Ao implantar o arquivamento, você pode integrar o armazenamento de dados para arquivamento com seu armazenamento existente do Exchange 2013 para todos os usuários hospedados no Exchange 2013 e ter suas caixas de correio colocadas em In-Place isenção, portanto, não é necessário implantar bancos de dados do SQL Server separados para arquivar dados do Lync.</span><span class="sxs-lookup"><span data-stu-id="d931c-113">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="d931c-114">Se você não tiver uma implantação do Exchange 2013, ou se preferir não integrá-la, ou se você tiver usuários do Lync 2013 que não estejam hospedados no Exchange 2013 com suas caixas de correio colocadas em In-Place isenção, poderá implantar bancos de dados de arquivamento separados usando o SQL Server para armazenar dados arquivados de comunicações do Lync.</span><span class="sxs-lookup"><span data-stu-id="d931c-114">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="d931c-115">Você pode usar os bancos de dados de integração do Microsoft Exchange e do Lync Server 2013 se quiser usar a integração do Microsoft Exchange para alguns, mas não todos os usuários em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d931c-115">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="d931c-116">Para obter detalhes sobre In-Place reter, consulte "bloqueio in-loco" em [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500) .</span><span class="sxs-lookup"><span data-stu-id="d931c-116">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="d931c-117">**Espelhamento do repositório SQL.**     Ao implantar o arquivamento, você pode habilitar o espelhamento de banco de dados do SQL Server para o banco de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="d931c-117">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="d931c-118">**Arquivamento de quadros de comunicações e pesquisas.**     O conteúdo de conferência arquivada agora inclui quadros de comunicações e pesquisas que são compartilhadas durante a reunião.</span><span class="sxs-lookup"><span data-stu-id="d931c-118">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="d931c-119">Os seguintes tipos de conteúdo não são arquivados:</span><span class="sxs-lookup"><span data-stu-id="d931c-119">The following types of content are not archived:</span></span>

  - <span data-ttu-id="d931c-120">Transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="d931c-120">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="d931c-121">Áudio/vídeo para mensagens instantâneas ponto a ponto e conferências</span><span class="sxs-lookup"><span data-stu-id="d931c-121">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="d931c-122">Compartilhamento de aplicativos para mensagens instantâneas ponto a ponto e conferências</span><span class="sxs-lookup"><span data-stu-id="d931c-122">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d931c-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="d931c-123">See Also</span></span>


[<span data-ttu-id="d931c-124">Planejamento para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d931c-124">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

