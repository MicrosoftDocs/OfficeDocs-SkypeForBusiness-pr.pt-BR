---
title: Modelo de usuário da conferência do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d4e8f55a9538c9cb70847bc090680662047b6ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="ccf3f-102">O modelo de usuário de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccf3f-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccf3f-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ccf3f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ccf3f-104">Uma parte crítica do modelo de usuário do Lync Server Conferencing é o tamanho da reunião.</span><span class="sxs-lookup"><span data-stu-id="ccf3f-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="ccf3f-105">Após coletar dados de vários pontos de dados (conforme descrito na seção anterior), determinamos o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ccf3f-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="ccf3f-106">A maioria das reuniões é realmente pequena reunião colaborativa com uma média de quatro a seis participantes</span><span class="sxs-lookup"><span data-stu-id="ccf3f-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="ccf3f-107">Aproximadamente 20 a 80% das reuniões têm menos de 20 participantes.</span><span class="sxs-lookup"><span data-stu-id="ccf3f-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="ccf3f-108">99,98% das reuniões têm menos de 100 participantes.</span><span class="sxs-lookup"><span data-stu-id="ccf3f-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="ccf3f-109">Além do tamanho da reunião, o modelo de usuário da conferência também leva em conta uma variedade de fatores, como:</span><span class="sxs-lookup"><span data-stu-id="ccf3f-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="ccf3f-110">**Reuniões simultâneas**   quantos usuários devem estar em reuniões ao mesmo tempo?</span><span class="sxs-lookup"><span data-stu-id="ccf3f-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="ccf3f-111">**Media Mix**   quais tipos de mídia estão disponíveis e que devem ser usadas pelos usuários em reuniões?</span><span class="sxs-lookup"><span data-stu-id="ccf3f-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="ccf3f-112">**Os tipos**   de usuário são usuários internos, usuários remotos, usuários federados ou usuários anônimos?</span><span class="sxs-lookup"><span data-stu-id="ccf3f-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="ccf3f-113">**Tempo de aumento da reunião o tempo**   necessário para que todos os usuários de uma reunião ingressem em uma reunião?</span><span class="sxs-lookup"><span data-stu-id="ccf3f-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="ccf3f-114">Para obter detalhes sobre o modelo de usuário, consulte [modelos de usuário no Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="ccf3f-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="ccf3f-115">Para determinar o número de reuniões e usuários a serem usados para testes, fizemos o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ccf3f-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="ccf3f-116">Retomou o número total de usuários em uma organização (por exemplo, 80.000 usuários) e multiplicado pela taxa de simultaneidade da reunião (por exemplo, 5% de todos os usuários) para determinar o número total de usuários que devem estar em reuniões ao mesmo tempo (neste exemplo , usuários do 4000).</span><span class="sxs-lookup"><span data-stu-id="ccf3f-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="ccf3f-117">Dividiu o número total de usuários pelo número de servidores do Lync Server 2013, front-end na implantação (por exemplo, 8 servidores) para determinar o número estimado de participantes da reunião por servidor front-end (neste exemplo, 500 usuários por servidor front-end).</span><span class="sxs-lookup"><span data-stu-id="ccf3f-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="ccf3f-118">Divida o número de usuários por servidor front-end pelo tamanho médio da reunião (por exemplo, 4 usuários) para determinar o número médio estimado de reuniões por servidor front-end (neste exemplo, reuniões do 125 por servidor front-end).</span><span class="sxs-lookup"><span data-stu-id="ccf3f-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="ccf3f-119">Para obter a carga por mídia em cada servidor front-end, estimamos o mix de mídia.</span><span class="sxs-lookup"><span data-stu-id="ccf3f-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="ccf3f-120">Por exemplo, pressupondo que 75% das reuniões exijam mais do que apenas o suporte a áudio e 50% dessas reuniões exigem compartilhamento de aplicativos, uma média de reuniões do 47 e os usuários da 188 se conectam simultaneamente a cada servidor front-end para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ccf3f-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="ccf3f-121">Testou uma variedade de tamanhos de reunião (com base em nosso modelo de usuário de até 250 usuários em um pool compartilhado) para garantir a escalabilidade do servidor.</span><span class="sxs-lookup"><span data-stu-id="ccf3f-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

