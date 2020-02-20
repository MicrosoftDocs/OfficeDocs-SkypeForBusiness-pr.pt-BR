---
title: 'Lync Server 2013: Gerenciando a infraestrutura de rede do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f958e6532738720bb5969199d72e38a79a3bc6ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="ac55e-102">Gerenciando a infraestrutura de rede do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac55e-102">Managing the Lync Server 2013 network infrastructure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac55e-103">_**Última modificação do tópico:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="ac55e-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="ac55e-104">O Microsoft Lync Server 2013 inclui suporte para o CAC (controle de admissão de chamadas) e bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="ac55e-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="ac55e-105">Para implementar estes recursos, você deve configurar uma rede de regiões, sites, subredes e assim por diante, que permitirão gerenciar a largura de banda em situações onde as transmissões de áudio e vídeo precisam ser restritas.</span><span class="sxs-lookup"><span data-stu-id="ac55e-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="ac55e-106">Também é possível usar a tecnologia de rede QoS para oferecer uma melhor experiência ao usuário final para comunicações de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="ac55e-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="ac55e-107">Você pode usar o painel de controle do Lync Server para configurar e gerenciar o CAC, o bypass de mídia e a QoS.</span><span class="sxs-lookup"><span data-stu-id="ac55e-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="ac55e-108">Os seguintes tópicos oferecem as etapas sobre como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="ac55e-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ac55e-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ac55e-109">In This Section</span></span>

  - [<span data-ttu-id="ac55e-110">Gerenciando a qualidade de serviço (QoS) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac55e-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="ac55e-111">Gerenciando o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac55e-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="ac55e-112">Interfaces de rede do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac55e-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="ac55e-113">Impedir novas conexões com o Lync Server 2013 para manutenção do servidor</span><span class="sxs-lookup"><span data-stu-id="ac55e-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="ac55e-114">Metodologia de qualidade de chamada do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac55e-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="ac55e-115">Principais indicadores de integridade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac55e-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

