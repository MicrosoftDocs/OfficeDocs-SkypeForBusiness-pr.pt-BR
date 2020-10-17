---
title: 'Lync Server 2013: iniciar ou parar serviços do Lync Server'
description: 'Lync Server 2013: iniciar ou parar serviços do Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d6e6520cbf6fda38676beab984c2d006061b019
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541857"
---
# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="54e46-103">Iniciar ou interromper os serviços do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54e46-103">Start or stop Lync Server 2013 services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54e46-104">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="54e46-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="54e46-105">Você pode usar o painel de controle do Lync Server para iniciar ou parar todos os serviços do Lync Server 2013 em execução em um computador específico ou para iniciar ou parar um serviço específico.</span><span class="sxs-lookup"><span data-stu-id="54e46-105">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="54e46-106">Para iniciar ou parar todos os serviços do Lync Server em um computador</span><span class="sxs-lookup"><span data-stu-id="54e46-106">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="54e46-107">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54e46-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="54e46-108">Você pode determinar se foi atribuído o CsServerAdministrator ou a função RBAC do CsAdministrator executando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="54e46-108">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="54e46-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54e46-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="54e46-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54e46-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="54e46-111">Na barra de navegação esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="54e46-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="54e46-112">Na página **Status**, classifique ou procure pela lista para encontrar o computador executando os serviços que você deseja iniciar ou parar e clique neles.</span><span class="sxs-lookup"><span data-stu-id="54e46-112">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="54e46-113">Clique em **Ação**.</span><span class="sxs-lookup"><span data-stu-id="54e46-113">Click **Action**.</span></span>

6.  <span data-ttu-id="54e46-114">Clique em **Iniciar todos os serviços** ou **Parar todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="54e46-114">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="54e46-115">Para iniciar ou parar um serviço específico</span><span class="sxs-lookup"><span data-stu-id="54e46-115">To start or stop a specific service</span></span>

1.  <span data-ttu-id="54e46-116">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="54e46-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54e46-117">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54e46-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="54e46-118">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54e46-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="54e46-119">Na barra de navegação esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="54e46-119">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="54e46-120">Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando o serviço que você deseja iniciar ou interromper e clique nele.</span><span class="sxs-lookup"><span data-stu-id="54e46-120">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="54e46-121">Clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="54e46-121">Click **Properties**.</span></span>

6.  <span data-ttu-id="54e46-122">Classifique a lista de serviços, se necessário e clique no serviço que você deseja iniciar ou parar.</span><span class="sxs-lookup"><span data-stu-id="54e46-122">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="54e46-123">Clique em **Ação**.</span><span class="sxs-lookup"><span data-stu-id="54e46-123">Click **Action**.</span></span>

8.  <span data-ttu-id="54e46-124">Clique em **Iniciar serviço** ou **Parar serviço**.</span><span class="sxs-lookup"><span data-stu-id="54e46-124">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="54e46-125">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="54e46-125">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54e46-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="54e46-126">See Also</span></span>


[<span data-ttu-id="54e46-127">Impedir sessões para serviços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54e46-127">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="54e46-128">Gerenciando a topologia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54e46-128">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

