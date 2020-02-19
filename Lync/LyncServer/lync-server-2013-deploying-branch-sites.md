---
title: 'Lync Server 2013: Implantando sites de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c167dc4f81053d5b9dde547f2f1e6e3d9d1a0fe7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="97471-102">Implantando sites de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97471-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97471-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="97471-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="97471-104">Os usuários do site de filial obtêm a maior parte da funcionalidade do Lync Server 2013 do servidor no site central ao qual o site de filial está associado.</span><span class="sxs-lookup"><span data-stu-id="97471-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="97471-105">Cada filial está associada a exatamente um local central.</span><span class="sxs-lookup"><span data-stu-id="97471-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="97471-106">Para fazer chamadas de/para a PSTN (Rede Telefônica Pública Comutada), uma filial deve incluir qualquer um dos itens a seguir:</span><span class="sxs-lookup"><span data-stu-id="97471-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="97471-107">Um gateway PSTN e, possivelmente, um Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="97471-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="97471-108">Um tronco SIP</span><span class="sxs-lookup"><span data-stu-id="97471-108">A SIP trunk</span></span>

  - <span data-ttu-id="97471-109">Uma infraestrutura existente de voz com uma central privada de comutação telefônica (PBX)</span><span class="sxs-lookup"><span data-stu-id="97471-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="97471-110">Um aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="97471-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="97471-111">Um servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="97471-111">A Survivable Branch Server</span></span>

<span data-ttu-id="97471-112">Os sites de filial com um aparelho de filial persistente ou servidor de filial persistente são mais resistentes em horários de falhas de rede de longa distância ou de site central do que os sites de filiais sem uma dessas soluções.</span><span class="sxs-lookup"><span data-stu-id="97471-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="97471-113">Por exemplo, em um site com um aparelho de filial persistente ou um servidor de filial persistente implantado, os usuários ainda poderão fazer e receber chamadas PSTN se a rede que conecta o site de filial ao site central estiver desativada.</span><span class="sxs-lookup"><span data-stu-id="97471-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="97471-114">Outra maneira de obter resiliência de site de filial é usar um gateway PSTN ou um tronco SIP com uma implantação do Lync Server em escala total no site de filial.</span><span class="sxs-lookup"><span data-stu-id="97471-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="97471-115">Para obter detalhes sobre qual implantação de site de filial é ideal para sua organização, incluindo pré-requisitos e outras considerações de planejamento, consulte [Planning for PSTN Connectivity in Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) e [Planning for Branch-site Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="97471-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="97471-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="97471-116">In This Section</span></span>

  - [<span data-ttu-id="97471-117">Fornecendo conectividade PSTN em um site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97471-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="97471-118">Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97471-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

