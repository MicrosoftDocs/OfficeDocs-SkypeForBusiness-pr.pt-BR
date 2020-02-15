---
title: 'Lync Server 2013: híbrido e dividido-Domain-descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e4adc6c0f8a3ffda53821c412e0efbda74bbebc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="22cd6-102">Descoberta automática de domínio e híbrido no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22cd6-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22cd6-103">_**Última modificação do tópico:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="22cd6-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="22cd6-104">Um espaço de endereçamento SIP compartilhado, também conhecido como implantação de *domínio dividido* , ou uma implantação *híbrida* , é uma configuração em que os usuários são implantados em uma implantação local e em um ambiente online.</span><span class="sxs-lookup"><span data-stu-id="22cd6-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="22cd6-105">O resultado desejado é ter um usuário, independentemente de onde o servidor local está localizado (local ou online), fazer logon na implantação e ser redirecionado para o local do servidor de origem.</span><span class="sxs-lookup"><span data-stu-id="22cd6-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="22cd6-106">Para fazer isso, o recurso de descoberta automática do Lync Server 2013 é usado para redirecionar o usuário online para a topologia online.</span><span class="sxs-lookup"><span data-stu-id="22cd6-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="22cd6-107">Você pode fazer isso Configurando o localizador de recursos uniforme (URL) de descoberta automática usando o Shell de gerenciamento do Lync Server, o cmdlet **Get-CsHostingProvider** e o cmdlet **set-CsHostingProvider** .</span><span class="sxs-lookup"><span data-stu-id="22cd6-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="22cd6-108">Mobilidade para a Implantação de domínio dividido</span><span class="sxs-lookup"><span data-stu-id="22cd6-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="22cd6-109">Será necessário coletar e registrar os seguintes atributos implantados:</span><span class="sxs-lookup"><span data-stu-id="22cd6-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="22cd6-110">No Shell de gerenciamento do Lync Server, digite</span><span class="sxs-lookup"><span data-stu-id="22cd6-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="22cd6-111">Nos resultados, encontre o provedor online com o atributo **ProxyFQDN**.</span><span class="sxs-lookup"><span data-stu-id="22cd6-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="22cd6-112">Por exemplo, sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="22cd6-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="22cd6-113">Registre o valor de ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="22cd6-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="22cd6-114">Habilite a Federação no painel de controle do Lync Server local, permitindo Federação com o provedor online.</span><span class="sxs-lookup"><span data-stu-id="22cd6-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="22cd6-115">Habilite a federação para o provedor online.</span><span class="sxs-lookup"><span data-stu-id="22cd6-115">Enable federation for the online provider.</span></span> <span data-ttu-id="22cd6-116">Por padrão, todos os usuários online estão habilitados para Federação de domínio e podem se comunicar com todos os domínios.</span><span class="sxs-lookup"><span data-stu-id="22cd6-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="22cd6-117">Se você definir domínios bloqueados e permitidos, determine os domínios que você irá explicitamente permitir ou bloquear explicitamente.</span><span class="sxs-lookup"><span data-stu-id="22cd6-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="22cd6-118">Para Federação online, você deve planejar exceções de firewall, certificados e host DNS (A ou AAAA, se estiver usando IPv6).</span><span class="sxs-lookup"><span data-stu-id="22cd6-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="22cd6-119">Além disso, é necessário configurar as políticas de federação.</span><span class="sxs-lookup"><span data-stu-id="22cd6-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="22cd6-120">Para obter detalhes, consulte [Planning for Lync server 2013 and Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span><span class="sxs-lookup"><span data-stu-id="22cd6-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

