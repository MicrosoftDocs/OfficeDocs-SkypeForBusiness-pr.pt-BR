---
title: 'Lync Server 2013: Gerenciando a infraestrutura de rede do Lync Server 2013'
description: 'Lync Server 2013: Gerenciando a infraestrutura de rede do Lync Server 2013.'
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
ms.openlocfilehash: ab1b5c6fe52374b012063ac26640e9bb25496ad7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564097"
---
# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="c2f66-103">Gerenciando a infraestrutura de rede do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2f66-103">Managing the Lync Server 2013 network infrastructure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2f66-104">_**Última modificação do tópico:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="c2f66-104">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="c2f66-105">O Microsoft Lync Server 2013 inclui suporte para o CAC (controle de admissão de chamadas) e bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="c2f66-105">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="c2f66-106">Para implementar estes recursos, você deve configurar uma rede de regiões, sites, subredes e assim por diante, que permitirão gerenciar a largura de banda em situações onde as transmissões de áudio e vídeo precisam ser restritas.</span><span class="sxs-lookup"><span data-stu-id="c2f66-106">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="c2f66-107">Também é possível usar a tecnologia de rede QoS para oferecer uma melhor experiência ao usuário final para comunicações de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="c2f66-107">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="c2f66-108">Você pode usar o painel de controle do Lync Server para configurar e gerenciar o CAC, o bypass de mídia e a QoS.</span><span class="sxs-lookup"><span data-stu-id="c2f66-108">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="c2f66-109">Os seguintes tópicos oferecem as etapas sobre como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="c2f66-109">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c2f66-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c2f66-110">In This Section</span></span>

  - [<span data-ttu-id="c2f66-111">Gerenciando a qualidade de serviço (QoS) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2f66-111">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="c2f66-112">Gerenciando o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2f66-112">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="c2f66-113">Interfaces de rede do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2f66-113">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="c2f66-114">Impedir novas conexões com o Lync Server 2013 para manutenção do servidor</span><span class="sxs-lookup"><span data-stu-id="c2f66-114">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="c2f66-115">Metodologia de qualidade de chamada do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2f66-115">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="c2f66-116">Principais indicadores de integridade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2f66-116">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

