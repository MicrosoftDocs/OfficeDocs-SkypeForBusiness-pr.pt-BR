---
title: 'Lync Server 2013: exibir uma lista de aplicativos confiáveis'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d44b6c4fd29109608691914784b02e2ad362b591
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506648"
---
# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="2681c-102">Exibir uma lista de aplicativos confiáveis no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2681c-102">View a list of trusted applications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2681c-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2681c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2681c-104">Você pode usar o painel de controle do Lync Server 2013 para exibir uma lista dos aplicativos confiáveis que você implantou no seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2681c-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="2681c-105">Um aplicativo confiável é um aplicativo baseado no SDK principal do Microsoft Unified Communications Managed API (UCMA) 3,0 Core que é confiável para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2681c-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="2681c-106">Essa relação de confiança é resumida na seguinte lista:</span><span class="sxs-lookup"><span data-stu-id="2681c-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="2681c-107">Os aplicativos confiáveis não são desafiados para autenticação pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2681c-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="2681c-108">Os aplicativos confiáveis não são restringidos pelo Lync Server para transações SIP, conexões ou chamadas VoIP (Voice over Internet Protocol) de saída.</span><span class="sxs-lookup"><span data-stu-id="2681c-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="2681c-109">Aplicativos confiáveis podem representar qualquer usuário e podem participar de conferências sem que apareçam nas listas.</span><span class="sxs-lookup"><span data-stu-id="2681c-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="2681c-110">Os aplicativos confiáveis estão altamente disponíveis e resistentes.</span><span class="sxs-lookup"><span data-stu-id="2681c-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="2681c-111">No painel de controle do Lync Server, você pode ver o nome dos aplicativos, o pool em que eles são executados e a porta que eles utilizam.</span><span class="sxs-lookup"><span data-stu-id="2681c-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="2681c-112">Para exibir uma lista de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="2681c-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="2681c-113">A partir de uma conta de usuário atribuída à função CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2681c-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="2681c-114">Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Lync Server 2013, consulte [Planning for Role-Based Access Control in Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="2681c-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="2681c-115">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2681c-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2681c-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2681c-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2681c-117">Na barra de navegação à esquerda, clique em **topologia** e em **aplicativo confiável**.</span><span class="sxs-lookup"><span data-stu-id="2681c-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="2681c-118">Na página **aplicativo confiável** , clique em um cabeçalho de coluna para classificar os aplicativos, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2681c-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2681c-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="2681c-119">See Also</span></span>


[<span data-ttu-id="2681c-120">Gerenciando a topologia do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2681c-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

