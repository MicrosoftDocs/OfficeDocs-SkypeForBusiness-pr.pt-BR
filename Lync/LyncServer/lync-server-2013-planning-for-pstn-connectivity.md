---
title: 'Lync Server 2013: planejamento da conectividade PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811f69e8286e341b7769a58d03c42d0a43e63075
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="7f42d-102">Planejamento da conectividade PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f42d-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f42d-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7f42d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7f42d-104">Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para a PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço).</span><span class="sxs-lookup"><span data-stu-id="7f42d-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="7f42d-105">Os usuários que colocam e recebem chamadas não devem estar cientes da tecnologia subjacente: da perspectiva do usuário, uma chamada entre a infraestrutura do Enterprise Voice e a PSTN deve parecer com apenas outra chamada telefônica.</span><span class="sxs-lookup"><span data-stu-id="7f42d-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="7f42d-106">O Lync Server 2013 fornece conectividade PSTN confiável e escalonável usando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7f42d-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="7f42d-107">**Troncos SIP** para um provedor de serviço de telefonia da Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="7f42d-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="7f42d-108">**Conexões SIP diretas** com um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="7f42d-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="7f42d-109">**Conexões SIP diretas** com um PBX</span><span class="sxs-lookup"><span data-stu-id="7f42d-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="7f42d-110">Dependendo de seu tamanho, cobertura geográfica e infraestrutura de voz existente, uma determinada empresa pode usar uma, duas ou até mesmo três opções em vários locais.</span><span class="sxs-lookup"><span data-stu-id="7f42d-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f42d-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7f42d-111">In This Section</span></span>

  - [<span data-ttu-id="7f42d-112">Tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f42d-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="7f42d-113">Conexões SIP diretas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f42d-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="7f42d-114">Tronco M:N no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f42d-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="7f42d-115">Regras de conversão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f42d-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="7f42d-116">Planejamento de roteamento de voz de saída no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f42d-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

