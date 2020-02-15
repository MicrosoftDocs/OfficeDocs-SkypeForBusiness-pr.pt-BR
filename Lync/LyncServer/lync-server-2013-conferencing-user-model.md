---
title: Modelo de usuário de conferência do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcc74259f9a5cb6ee40cb29fbab56e638ba78b79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="23cf6-102">O modelo de usuário de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23cf6-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23cf6-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="23cf6-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="23cf6-104">Uma parte crítica do modelo de usuário de conferência do Lync Server é o tamanho da reunião.</span><span class="sxs-lookup"><span data-stu-id="23cf6-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="23cf6-105">Depois de coletar dados de vários pontos de dados (como descrito na seção anterior), nós determinados o seguinte:</span><span class="sxs-lookup"><span data-stu-id="23cf6-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="23cf6-106">A maioria das reuniões é composta por pequenas reuniões colaborativas com uma média de quatro a seis participantes</span><span class="sxs-lookup"><span data-stu-id="23cf6-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="23cf6-107">Aproximadamente 80 por cento das reuniões tem menos de 20 participantes.</span><span class="sxs-lookup"><span data-stu-id="23cf6-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="23cf6-108">99,98 por cento das reuniões tem menos de 100 participantes.</span><span class="sxs-lookup"><span data-stu-id="23cf6-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="23cf6-109">Além do tamanho da reunião, o modelo de usuário de conferência também considera vários fatores, como:</span><span class="sxs-lookup"><span data-stu-id="23cf6-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="23cf6-110">**Reuniões simultâneas**   quantos usuários devem estar em reuniões ao mesmo tempo?</span><span class="sxs-lookup"><span data-stu-id="23cf6-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="23cf6-111">**Media Mix**   quais tipos de mídia estão disponíveis e que devem ser usados por usuários em reuniões?</span><span class="sxs-lookup"><span data-stu-id="23cf6-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="23cf6-112">**Os tipos**   de usuários são usuários internos, usuários remotos, usuários federados ou usuários anônimos?</span><span class="sxs-lookup"><span data-stu-id="23cf6-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="23cf6-113">**Aumento do tempo de reunião quanto tempo**   leva para todos os usuários de uma reunião ingressar em uma reunião?</span><span class="sxs-lookup"><span data-stu-id="23cf6-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="23cf6-114">Para obter detalhes sobre o modelo de usuário, consulte [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="23cf6-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="23cf6-115">Para determinar o número de reuniões e usuários para usar em testes foi realizado o seguinte:</span><span class="sxs-lookup"><span data-stu-id="23cf6-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="23cf6-116">Pegamos o número total de usuários em uma organização (por exemplo, 80.000 usuários) e multiplicamos pela taxa de simultaneidade da reunião (por exemplo, 5% de todos os usuários) para determinar o número total de usuários esperados em reuniões simultâneas (neste exemplo, 4000 usuários).</span><span class="sxs-lookup"><span data-stu-id="23cf6-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="23cf6-117">Dividido o número total de usuários pelo número de servidores front-end do Lync Server 2013 na implantação (por exemplo, 8 servidores) para determinar o número estimado de participantes da reunião por servidor front-end (neste exemplo, 500 usuários por servidor de front-end).</span><span class="sxs-lookup"><span data-stu-id="23cf6-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="23cf6-118">Dividido o número de usuários por servidor front-end pelo tamanho médio da reunião (por exemplo, 4 usuários) para determinar o número médio estimado de reuniões por servidor de front-end (neste exemplo, 125 reuniões por servidor de front-end).</span><span class="sxs-lookup"><span data-stu-id="23cf6-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="23cf6-119">Para obter a carga por mídia em cada servidor de front-end, estimamos o mix de mídia.</span><span class="sxs-lookup"><span data-stu-id="23cf6-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="23cf6-120">Por exemplo, supondo que 75% das reuniões exijam mais do que apenas suporte a áudio e 50% dessas reuniões exigem o compartilhamento de aplicativos, uma média de 47 reuniões e 188 usuários conectam simultaneamente a cada servidor front-end para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="23cf6-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="23cf6-121">Testado em vários tamanhos de reunião (com base em nosso modelo de usuário de até 250 usuários em um pool compartilhado) para garantir a escalabilidade do servidor.</span><span class="sxs-lookup"><span data-stu-id="23cf6-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

