---
title: Lync Server 2013 suporte para integração de UM do Exchange hospedado
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
ms.openlocfilehash: 714b10cfc10e101439670eda6ff3810be06b8599
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="7635d-102">Suporte à integração de UM do Exchange hospedado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7635d-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7635d-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7635d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7635d-104">O aplicativo de roteamento ExUM do Lync Server 2013 oferece suporte à integração com a Unificação de mensagens (UM) do Exchange em um ambiente local, onde o Lync Server 2013 e o Exchange UM estão instalados localmente em sua empresa ou em com um do Exchange hospedado por um provedor de serviços, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="7635d-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="7635d-105">![Implantação de UM do Exchange do Lync Server local](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implantação de UM do Exchange do Lync Server local")</span><span class="sxs-lookup"><span data-stu-id="7635d-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="7635d-106">Os modos a seguir são suportados:</span><span class="sxs-lookup"><span data-stu-id="7635d-106">The following modes are supported:</span></span>

  - <span data-ttu-id="7635d-107">**O modo**   local do Lync Server 2013 e do Exchange são implantados em servidores locais dentro de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="7635d-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="7635d-108">**O modo**   entre locais do Lync Server 2013 é implantado em servidores locais dentro de sua empresa e o um do Exchange está hospedado no recurso de um provedor de serviços online, como um data center do Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7635d-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="7635d-109">**Modo misto sua**   implantação do Lync Server 2013 tem algumas caixas de correio de usuário hospedadas em servidores locais que executam o Microsoft Exchange Server em sua empresa e algumas caixas de correio hospedadas em um data center de serviço do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="7635d-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7635d-110">O modo misto pode ser usado como uma solução de transição durante a avaliação e em etapas a migração de usuários para o UM do Exchange hospedado ou como uma solução permanente se você optar por manter os serviços de UM do Exchange da UM no local após a migração de outros.</span><span class="sxs-lookup"><span data-stu-id="7635d-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="7635d-111">Para integrar o Lync Server 2013 à UM do Exchange hospedado, você deve configurar um *espaço de endereçamento SIP compartilhado* (também chamado de *domínio dividido*).</span><span class="sxs-lookup"><span data-stu-id="7635d-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="7635d-112">Nessa configuração, o Lync Server 2013 e o provedor de serviços UM do Exchange hospedado por terceiros podem acessar o mesmo espaço de endereço de domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="7635d-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="7635d-113">Para obter detalhes, consulte [arquitetura de integração da um do Exchange hospedado no Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7635d-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

