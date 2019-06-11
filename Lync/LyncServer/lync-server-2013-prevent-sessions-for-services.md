---
title: 'Lync Server 2013: impedir sessões para serviços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8d22b74168c784d6a5e19c3ffc32b9e275040b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="e4aff-102">Evitar sessões para serviços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4aff-102">Prevent sessions for services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4aff-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e4aff-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e4aff-104">Você pode usar o painel de controle do Lync Server para impedir novas sessões para todos os serviços do Lync Server 2013 em execução em um computador específico ou para impedir novas sessões para um serviço específico do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4aff-104">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="e4aff-105">Para impedir novas sessões para todos os serviços do Lync Server em um computador</span><span class="sxs-lookup"><span data-stu-id="e4aff-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="e4aff-106">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4aff-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e4aff-107">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4aff-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e4aff-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e4aff-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e4aff-109">Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.</span><span class="sxs-lookup"><span data-stu-id="e4aff-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="e4aff-110">Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando os serviços para os quais você deseja impedir novas sessões e, em seguida, clique nela.</span><span class="sxs-lookup"><span data-stu-id="e4aff-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="e4aff-111">Clique em **ação**.</span><span class="sxs-lookup"><span data-stu-id="e4aff-111">Click **Action**.</span></span>

6.  <span data-ttu-id="e4aff-112">Clique em **impedir novas sessões para todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="e4aff-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="e4aff-113">Para impedir novas sessões para um serviço específico</span><span class="sxs-lookup"><span data-stu-id="e4aff-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="e4aff-114">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4aff-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e4aff-115">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4aff-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e4aff-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e4aff-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e4aff-117">Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.</span><span class="sxs-lookup"><span data-stu-id="e4aff-117">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="e4aff-118">Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele.</span><span class="sxs-lookup"><span data-stu-id="e4aff-118">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="e4aff-119">Clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e4aff-119">Click **Properties**.</span></span>

6.  <span data-ttu-id="e4aff-120">Classifique a lista de serviços, se necessário, e clique no serviço para o qual você deseja impedir novas sessões.</span><span class="sxs-lookup"><span data-stu-id="e4aff-120">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="e4aff-121">Clique em **ação**.</span><span class="sxs-lookup"><span data-stu-id="e4aff-121">Click **Action**.</span></span>

8.  <span data-ttu-id="e4aff-122">Clique em **impedir novas sessões para o serviço**.</span><span class="sxs-lookup"><span data-stu-id="e4aff-122">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="e4aff-123">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e4aff-123">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4aff-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="e4aff-124">See Also</span></span>


[<span data-ttu-id="e4aff-125">Gerenciando a topologia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4aff-125">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

