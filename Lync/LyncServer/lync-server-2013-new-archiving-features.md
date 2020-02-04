---
title: 'Lync Server 2013: Novos recursos de Arquivamento'
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
ms.openlocfilehash: 1509a0857b54673ab20783f69b34b59c6d2afde8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="fc60b-102">Novos recursos de Arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc60b-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc60b-103">_**Tópico da última modificação:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="fc60b-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="fc60b-104">O arquivamento no Lync Server 2013 pode arquivar os seguintes tipos de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="fc60b-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="fc60b-105">Mensagens instantâneas de ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="fc60b-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="fc60b-106">Conferências (reuniões) que são mensagens instantâneas com vários participantes</span><span class="sxs-lookup"><span data-stu-id="fc60b-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="fc60b-107">Conteúdo de conferências, incluindo conteúdo carregado (por exemplo, folhetos) e conteúdo relacionado ao evento (por exemplo, entradas, saídas, compartilhamento de cargas e alterações de visibilidade)</span><span class="sxs-lookup"><span data-stu-id="fc60b-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="fc60b-108">Além disso, o arquivamento no Lync Server 2013 oferece novos recursos que melhoram a implantação e a eficiência das operações.</span><span class="sxs-lookup"><span data-stu-id="fc60b-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="fc60b-109">Esses novos recursos consistem em:</span><span class="sxs-lookup"><span data-stu-id="fc60b-109">These new features consist of:</span></span>

  - <span data-ttu-id="fc60b-110">**Colocação do arquivamento em servidores front-end.**    O Lync Server 2013 não tem uma função de servidor de arquivamento separada.</span><span class="sxs-lookup"><span data-stu-id="fc60b-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="fc60b-111">O arquivamento é um recurso opcional disponível em todos os servidores front-end em uma implantação do Enterprise Edition e em servidores de edição padrão, que pode ser implementado configurado para um pool ou um site.</span><span class="sxs-lookup"><span data-stu-id="fc60b-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="fc60b-112">**Integração com o Microsoft Exchange.**    Ao implantar o arquivamento, você pode integrar o armazenamento de dados para arquivamento com o armazenamento existente do Exchange 2013 para todos os usuários que estão hospedados no Exchange 2013 e ter suas caixas de correio no bloqueio in-loco, para que você não precise implantar bancos de dados do SQL Server separados para arquivar dados do Lync.</span><span class="sxs-lookup"><span data-stu-id="fc60b-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="fc60b-113">Se você não tiver uma implantação do Exchange 2013 ou se preferir não integrá-la, ou se tiver usuários do Lync 2013 que não são hospedados no Exchange 2013 com suas caixas de correio no bloqueio in-loco, você pode implantar bancos de dados de arquivamento separados usando o SQL Server para stor arquivar dados de comunicações do Lync.</span><span class="sxs-lookup"><span data-stu-id="fc60b-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="fc60b-114">Você pode usar os bancos de dados de armazenamento do Microsoft Exchange Integration e Lync Server 2013 se quiser usar a integração do Microsoft Exchange para alguns, mas não para todos os usuários da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="fc60b-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="fc60b-115">Para obter detalhes sobre o bloqueio in-loco, consulte "bloqueio in-loco [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)" em.</span><span class="sxs-lookup"><span data-stu-id="fc60b-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="fc60b-116">**Espelhamento da SQL Store.**    Ao implantar o arquivamento, você pode habilitar o espelhamento de banco de dados do SQL Server para o banco de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="fc60b-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="fc60b-117">**Arquivamento de quadros de comunicações e sondagens.**    Agora, o conteúdo arquivado da conferência inclui quadros de comunicações e sondagens que são compartilhados durante a reunião.</span><span class="sxs-lookup"><span data-stu-id="fc60b-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="fc60b-118">Os seguintes tipos de conteúdo não são arquivados:</span><span class="sxs-lookup"><span data-stu-id="fc60b-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="fc60b-119">Transferências de arquivo de ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="fc60b-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="fc60b-120">Áudio e vídeo de mensagens instantâneas e conferências de ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="fc60b-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="fc60b-121">Compartilhamento de aplicativos para mensagens instantâneas e conferências ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="fc60b-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fc60b-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="fc60b-122">See Also</span></span>


[<span data-ttu-id="fc60b-123">Planejando Arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc60b-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

