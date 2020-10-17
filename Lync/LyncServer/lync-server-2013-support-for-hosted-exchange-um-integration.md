---
title: Lync Server 2013 suporte para integração de UM do Exchange hospedado
description: Lync Server 2013 suporte para integração de UM do Exchange hospedado.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88920667d703bc634921903e8e3995cb65db6873
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546316"
---
# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="d4397-103">Suporte à integração de UM do Exchange hospedado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4397-103">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4397-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d4397-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d4397-105">O aplicativo de roteamento ExUM do Lync Server 2013 oferece suporte à integração com a Unificação de mensagens (UM) do Exchange em um ambiente local, onde o Lync Server 2013 e o Exchange UM estão instalados localmente em sua empresa ou em com um do Exchange hospedado por um provedor de serviços, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="d4397-105">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="d4397-106">![Implantação de UM do Exchange do Lync Server local](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implantação de UM do Exchange do Lync Server local")</span><span class="sxs-lookup"><span data-stu-id="d4397-106">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="d4397-107">Os modos a seguir são suportados:</span><span class="sxs-lookup"><span data-stu-id="d4397-107">The following modes are supported:</span></span>

  - <span data-ttu-id="d4397-108">**Modo**     no local O Lync Server 2013 e o Exchange UM são implantados em servidores locais dentro de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="d4397-108">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="d4397-109">**Modo**     entre locais O Lync Server 2013 é implantado em servidores locais dentro de sua empresa e o UM do Exchange é hospedado em um recurso do provedor de serviços online, como um data center do Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d4397-109">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="d4397-110">**Modo misto**     Sua implantação do Lync Server 2013 tem algumas caixas de correio de usuário hospedadas em servidores locais que executam o Microsoft Exchange Server em sua empresa e algumas caixas de correio hospedadas em um data center de serviço do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="d4397-110">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4397-111">O modo misto pode ser usado como uma solução de transição durante a avaliação e em etapas a migração de usuários para o UM do Exchange hospedado ou como uma solução permanente se você optar por manter os serviços de UM do Exchange da UM no local após a migração de outros.</span><span class="sxs-lookup"><span data-stu-id="d4397-111">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="d4397-112">Para integrar o Lync Server 2013 à UM do Exchange hospedado, você deve configurar um *espaço de endereçamento SIP compartilhado* (também chamado de *domínio dividido*).</span><span class="sxs-lookup"><span data-stu-id="d4397-112">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="d4397-113">Nessa configuração, o Lync Server 2013 e o provedor de serviços UM do Exchange hospedado por terceiros podem acessar o mesmo espaço de endereço de domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="d4397-113">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="d4397-114">Para obter detalhes, consulte [arquitetura de integração da um do Exchange hospedado no Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="d4397-114">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

