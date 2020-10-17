---
title: 'Lync Server 2013: suporte a vários troncos'
description: 'Lync Server 2013: suporte a vários troncos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbabb90405b3fdae47a59ba8a0798743943216d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552417"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="4f381-103">Suporte a vários troncos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f381-103">Multiple trunk support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f381-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4f381-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4f381-105">A funcionalidade do Lync Server 2013 oferece suporte a várias associações entre gateways e servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="4f381-105">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="4f381-106">Essas associações são feitas por meio da definição de um tronco, que é uma associação lógica entre um pool de servidor de mediação e um gateway PSTN (controlador de borda de sessão), SBC ou IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="4f381-106">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="4f381-107">Use o construtor de topologia para associar gateways a servidores de mediação (ou seja, troncos).</span><span class="sxs-lookup"><span data-stu-id="4f381-107">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="4f381-108">Para atribuir ou remover um tronco no Lync Server 2013, primeiro você deve definir um tronco no construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="4f381-108">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="4f381-109">Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do servidor de mediação, a porta de escuta do servidor de mediação, o FQDN do gateway e a porta de escuta do gateway.</span><span class="sxs-lookup"><span data-stu-id="4f381-109">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="4f381-110">Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="4f381-110">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="4f381-111">Isso fornece resiliência adicional para a infraestrutura do Enterprise Voice, que é especialmente útil em cenários de interoperabilidade de PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="4f381-111">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="4f381-112">Quando um tronco é definido, ele deve ser associado a uma rota.</span><span class="sxs-lookup"><span data-stu-id="4f381-112">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="4f381-113">Para associar um tronco a uma rota, você define um nome simples para o tronco no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4f381-113">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="4f381-114">Esse nome simples é usado como o nome do tronco no painel de controle do Lync Server, onde os troncos podem ser associados a rotas.</span><span class="sxs-lookup"><span data-stu-id="4f381-114">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="4f381-115">O nome do tronco simples é usado como o nome do gateway no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f381-115">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="4f381-116">O administrador deve selecionar um tronco padrão associado a um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="4f381-116">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="4f381-117">No construtor de topologias, clique com o botão direito do mouse no servidor de mediação associado e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4f381-117">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="4f381-118">Especifique o gateway padrão para o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="4f381-118">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="4f381-119">O diagrama a seguir ilustra os vários troncos definidos para cada servidor de mediação e gateway.</span><span class="sxs-lookup"><span data-stu-id="4f381-119">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="4f381-120">**Roteamento de tronco M-N**</span><span class="sxs-lookup"><span data-stu-id="4f381-120">**M-N Trunk Routing**</span></span>

<span data-ttu-id="4f381-121">![Várias atribuições de tronco.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Várias atribuições de tronco.")</span><span class="sxs-lookup"><span data-stu-id="4f381-121">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

