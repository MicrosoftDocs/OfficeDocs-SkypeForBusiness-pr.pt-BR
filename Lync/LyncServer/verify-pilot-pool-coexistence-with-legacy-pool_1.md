---
title: Verificar a coexistência do pool piloto com o pool herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51709bba3f96f8761b9687387b78954c8840ff41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="25b80-102">Verificar a coexistência do pool piloto com o pool herdado</span><span class="sxs-lookup"><span data-stu-id="25b80-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25b80-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="25b80-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="25b80-104">Verifique o pool na Ferramenta Administrativa do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="25b80-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="25b80-105">Abra a ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="25b80-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="25b80-106">Expanda o nó **Floresta**, expanda o nó **ServidoresStandard Edition** ou **Pools Enterprise** e expanda o pool ou o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="25b80-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="25b80-107">Verifique se os serviços do Office Communications Server 2007 R2 estão em execução no pool.</span><span class="sxs-lookup"><span data-stu-id="25b80-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="25b80-108">![Console de administração do Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console de administração do Office Communications Server 2007 R2")</span><span class="sxs-lookup"><span data-stu-id="25b80-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="25b80-109">Verificar o pool piloto no painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25b80-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="25b80-110">A partir de uma conta de usuário que seja membro da função CsAdministrator, faça logon no servidor front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25b80-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="25b80-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25b80-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="25b80-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="25b80-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="25b80-113">Clique em **Topologia**.</span><span class="sxs-lookup"><span data-stu-id="25b80-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="25b80-114">Verifique se os servidores que você implantou estão presentes em seu pool piloto.</span><span class="sxs-lookup"><span data-stu-id="25b80-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="25b80-115">![Página de topologia do painel de controle do Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Página de topologia do painel de controle do Lync Server")</span><span class="sxs-lookup"><span data-stu-id="25b80-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="25b80-116">Verificar se os serviços do Lync Server 2013 foram iniciados</span><span class="sxs-lookup"><span data-stu-id="25b80-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="25b80-117">No servidor front-end do Lync Server 2013, abra o applet de **Serviços** no grupo **Ferramentas administrativas** .</span><span class="sxs-lookup"><span data-stu-id="25b80-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="25b80-118">Verifique se os serviços listados correspondem à lista na seguinte figura.</span><span class="sxs-lookup"><span data-stu-id="25b80-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="25b80-119">![Página de serviços mostrando os serviços do Lync iniciado](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Página de serviços mostrando os serviços do Lync iniciado")</span><span class="sxs-lookup"><span data-stu-id="25b80-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

