---
title: 'Lync Server 2013: suporte a vários troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156db04ceb26809c7043f30e9e01ea0071e0a31d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="4401a-102">Suporte a vários troncos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4401a-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4401a-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4401a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4401a-104">A funcionalidade do Lync Server 2013 oferece suporte a várias associações entre gateways e servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="4401a-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="4401a-105">Essas associações são feitas pela definição de um tronco, que é uma associação lógica entre um pool do servidor de mediação e um gateway de rede telefônica pública comutada (SBC), ou PBX IP.</span><span class="sxs-lookup"><span data-stu-id="4401a-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="4401a-106">Use o construtor de topologias para associar gateways a servidores de mediação (ou seja, troncos).</span><span class="sxs-lookup"><span data-stu-id="4401a-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="4401a-107">Para atribuir ou remover um tronco no Lync Server 2013, primeiro você deve definir um tronco no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4401a-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="4401a-108">Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do servidor de mediação, a porta de escuta do servidor de mediação, o FQDN do gateway e a porta de escuta do gateway.</span><span class="sxs-lookup"><span data-stu-id="4401a-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="4401a-109">Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="4401a-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="4401a-110">Isso fornece resiliência adicional à infraestrutura Enterprise Voice, que é especialmente útil em cenários de interoperabilidade de PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="4401a-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="4401a-111">Quando um tronco é definido, ele precisa ser associado à rota.</span><span class="sxs-lookup"><span data-stu-id="4401a-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="4401a-112">Para associar um tronco a uma rota, você define um nome simples para o tronco no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4401a-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="4401a-113">Esse nome simples é usado como o nome do tronco no painel de controle do Lync Server, em que os troncos podem ser associados às rotas.</span><span class="sxs-lookup"><span data-stu-id="4401a-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="4401a-114">O nome do tronco simples é usado como o nome do gateway do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4401a-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="4401a-115">O administrador deve selecionar um tronco padrão associado a um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="4401a-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="4401a-116">No construtor de topologias, clique com o botão direito do mouse no servidor de mediação associado e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4401a-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="4401a-117">Especifique o gateway padrão do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="4401a-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="4401a-118">O diagrama a seguir ilustra os vários troncos que são definidos para cada servidor e gateway de mediação.</span><span class="sxs-lookup"><span data-stu-id="4401a-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="4401a-119">**M-N roteamento de tronco**</span><span class="sxs-lookup"><span data-stu-id="4401a-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="4401a-120">![Várias atribuições de tronco.] (images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Várias atribuições de tronco.")</span><span class="sxs-lookup"><span data-stu-id="4401a-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

