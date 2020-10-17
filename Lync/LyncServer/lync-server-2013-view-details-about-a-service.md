---
title: 'Lync Server 2013: Exibir detalhes sobre um serviço'
description: 'Lync Server 2013: Exibir detalhes sobre um serviço.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09cc5a86748f18a9a032fbf7e90682f46b324902
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572437"
---
# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="9d06f-103">Exibir detalhes sobre um serviço no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d06f-103">View details about a service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d06f-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9d06f-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9d06f-105">Você pode usar o painel de controle do Lync Server para exibir detalhes sobre cada serviço que está sendo executado em um computador específico em sua topologia.</span><span class="sxs-lookup"><span data-stu-id="9d06f-105">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="9d06f-106">É possível exibir o status e os detalhes de cada serviço, como bancos de dados, portas e serviços dependentes associados.</span><span class="sxs-lookup"><span data-stu-id="9d06f-106">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="9d06f-107">Para exibir detalhes de um serviço</span><span class="sxs-lookup"><span data-stu-id="9d06f-107">To view details for a service</span></span>

1.  <span data-ttu-id="9d06f-108">A partir de uma conta de usuário atribuída a qualquer uma das funções administrativas predefinidas para o Lync Server 2013, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9d06f-108">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="9d06f-109">Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Lync Server 2013, consulte [Planning for Role-Based Access Control in Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="9d06f-109">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="9d06f-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d06f-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9d06f-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9d06f-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9d06f-112">Na barra de navegação esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="9d06f-112">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="9d06f-113">Na página **Status**, classifique ou pesquisa na lista e clique no computador que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="9d06f-113">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="9d06f-114">Clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9d06f-114">Click **Properties**.</span></span>

6.  <span data-ttu-id="9d06f-115">Na janela **Exibir Detalhes do Computador**, classifique a lista de serviços, se for necessário, e clique no serviço que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="9d06f-115">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="9d06f-116">Siga um destes procedimentos, conforme o necessário:</span><span class="sxs-lookup"><span data-stu-id="9d06f-116">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="9d06f-117">Para ver o status mais recente desse serviço específico, clique em **Obter o status do serviço**.</span><span class="sxs-lookup"><span data-stu-id="9d06f-117">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="9d06f-118">Para ver detalhes desse serviço específico, clique em **Propriedades** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="9d06f-118">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="9d06f-119">Para retornar à lista com todos os computadores em sua topologia, clique **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="9d06f-119">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9d06f-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="9d06f-120">See Also</span></span>


[<span data-ttu-id="9d06f-121">Gerenciando a topologia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d06f-121">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

