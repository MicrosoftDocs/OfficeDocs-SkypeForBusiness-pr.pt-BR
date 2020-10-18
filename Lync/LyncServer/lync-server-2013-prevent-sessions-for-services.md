---
title: 'Lync Server 2013: impedir sessões para serviços'
description: 'Lync Server 2013: impedir sessões de serviços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 846a9da5330c3e64f61c27dfadd883f0c43a0ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579807"
---
# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="b921e-103">Impedir sessões para serviços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b921e-103">Prevent sessions for services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b921e-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b921e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b921e-105">Você pode usar o painel de controle do Lync Server para impedir novas sessões para todos os serviços do Lync Server 2013 em execução em um computador específico ou para impedir novas sessões para um serviço do Lync Server 2013 específico.</span><span class="sxs-lookup"><span data-stu-id="b921e-105">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="b921e-106">Para impedir novas sessões para todos os serviços do Lync Server em um computador</span><span class="sxs-lookup"><span data-stu-id="b921e-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="b921e-107">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b921e-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b921e-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b921e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b921e-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b921e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b921e-110">Na barra de navegação à esquerda, clique em **Topologia** e, em seguida, clique em **Status**.</span><span class="sxs-lookup"><span data-stu-id="b921e-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="b921e-111">Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando os serviços para os quais você deseja impedir novas sessões e clique nele.</span><span class="sxs-lookup"><span data-stu-id="b921e-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="b921e-112">Clique em **Ação**.</span><span class="sxs-lookup"><span data-stu-id="b921e-112">Click **Action**.</span></span>

6.  <span data-ttu-id="b921e-113">Clique em **Impedir novas sessões para todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="b921e-113">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="b921e-114">Para Impedir novas sessões para um serviço específico</span><span class="sxs-lookup"><span data-stu-id="b921e-114">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="b921e-115">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b921e-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b921e-116">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b921e-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b921e-117">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b921e-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b921e-118">Na barra de navegação esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="b921e-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="b921e-119">Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando o serviço que você deseja iniciar ou interromper e clique nele.</span><span class="sxs-lookup"><span data-stu-id="b921e-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="b921e-120">Clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b921e-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="b921e-121">Classifique a lista de serviços, se necessário e clique no serviço para o qual você deseja impedir novas sessões.</span><span class="sxs-lookup"><span data-stu-id="b921e-121">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="b921e-122">Clique em **Ações**.</span><span class="sxs-lookup"><span data-stu-id="b921e-122">Click **Action**.</span></span>

8.  <span data-ttu-id="b921e-123">Clique em **Impedir novas sessões para o serviço**.</span><span class="sxs-lookup"><span data-stu-id="b921e-123">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="b921e-124">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b921e-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b921e-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="b921e-125">See Also</span></span>


[<span data-ttu-id="b921e-126">Gerenciando a topologia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b921e-126">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

