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
ms.openlocfilehash: facfda5d1d7ce67ea08f71cbfb943792eeced7a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="a9f64-102">Implantando sites de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9f64-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9f64-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a9f64-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a9f64-104">Os usuários do site de filiais obtêm a maioria da funcionalidade do Lync Server 2013 do servidor no site central ao qual o site de filial está associado.</span><span class="sxs-lookup"><span data-stu-id="a9f64-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="a9f64-105">Cada site de filial está associado a um site central de exatamente.</span><span class="sxs-lookup"><span data-stu-id="a9f64-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="a9f64-106">Para fornecer chamadas de e para a rede telefônica pública comutada (PSTN), um site de filial pode conter qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a9f64-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="a9f64-107">Um gateway PSTN e, possivelmente, um servidor meditação</span><span class="sxs-lookup"><span data-stu-id="a9f64-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="a9f64-108">Um tronco SIP</span><span class="sxs-lookup"><span data-stu-id="a9f64-108">A SIP trunk</span></span>

  - <span data-ttu-id="a9f64-109">Uma infraestrutura de voz existente com um PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="a9f64-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="a9f64-110">Um aparelho de ramificação sobreviventes</span><span class="sxs-lookup"><span data-stu-id="a9f64-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="a9f64-111">Um servidor de ramificação sobreviventes</span><span class="sxs-lookup"><span data-stu-id="a9f64-111">A Survivable Branch Server</span></span>

<span data-ttu-id="a9f64-112">Os sites de filiais com um aparelho de ramificação sobreviventes ou um servidor de filiais sobreviventes são mais resistentes em tempo de falhas de rede de longa distância ou de locais centrais do que os sites de filiais sem uma dessas soluções.</span><span class="sxs-lookup"><span data-stu-id="a9f64-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="a9f64-113">Por exemplo, em um site com um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes implantado, os usuários ainda poderão fazer e receber chamadas PSTN se a rede que conecta o site de filial ao site central estiver inativa.</span><span class="sxs-lookup"><span data-stu-id="a9f64-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="a9f64-114">Outra maneira de obter resiliência de site de filial é usar um gateway PSTN ou um tronco SIP com uma implantação completa do Lync Server no site da filial.</span><span class="sxs-lookup"><span data-stu-id="a9f64-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="a9f64-115">Para obter detalhes sobre qual implantação de site de filial é ideal para sua organização, incluindo pré-requisitos e outras considerações de planejamento, consulte [planejando a conectividade PSTN no Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) e [planejando a resiliência de voz no site de filial no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a9f64-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a9f64-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a9f64-116">In This Section</span></span>

  - [<span data-ttu-id="a9f64-117">Fornecendo conectividade de PSTN ao site da filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9f64-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="a9f64-118">Implantando Aplicativo ou Servidor de Filial Persistente com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9f64-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

