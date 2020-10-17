---
title: 'Lync Server 2013: planejamento para conectividade de mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 540173ea468947786e2ead4927ccc66eb2f3ceda
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526498"
---
# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="09735-102">Planejando a conectividade de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09735-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09735-103">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="09735-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="09735-104">A conectividade de mensagens instantâneas públicas é uma classe de Federação e é configurada para permitir que seus usuários internos e externos do Lync Server 2013 adicionem contatos de qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="09735-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="09735-105">Contatos do Messenger</span><span class="sxs-lookup"><span data-stu-id="09735-105">Messenger contacts</span></span>

  - <span data-ttu-id="09735-106">Instant\!</span><span class="sxs-lookup"><span data-stu-id="09735-106">Yahoo\!</span></span> <span data-ttu-id="09735-107">contacts</span><span class="sxs-lookup"><span data-stu-id="09735-107">contacts</span></span>

  - <span data-ttu-id="09735-108">Contatos do America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="09735-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="09735-109">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="09735-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="09735-110">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="09735-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="09735-111">Messenger até a data de desligamento do serviço.</span><span class="sxs-lookup"><span data-stu-id="09735-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="09735-112">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="09735-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="09735-113">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="09735-113">has been announced.</span></span> <span data-ttu-id="09735-114">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="09735-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="09735-115">O PIC USL é uma licença de assinatura por usuário, por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="09735-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="09735-116">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="09735-116">Messenger.</span></span> <span data-ttu-id="09735-117">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual não será renovado.</span><span class="sxs-lookup"><span data-stu-id="09735-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="09735-118">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="09735-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="09735-119">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="09735-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="09735-120">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de IM e voz.</span><span class="sxs-lookup"><span data-stu-id="09735-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="09735-121">Essa classe de Federação requer as seguintes considerações de planejamento:</span><span class="sxs-lookup"><span data-stu-id="09735-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="09735-122">Os usuários do Windows Live Messenger podem ter a comunicação de áudio/vídeo ponto a ponto com os usuários do Lync Server 2013, além de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="09735-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="09735-123">Os servidores de borda devem atender a requisitos específicos de porta e protocolo.</span><span class="sxs-lookup"><span data-stu-id="09735-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="09735-124">Para obter detalhes, consulte [determine external A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09735-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="09735-125">O Yahoo mensagens instantâneas não tem requisitos exclusivos, além daqueles normalmente usados no planejamento e implantação do servidor de borda típico que está fornecendo Federação.</span><span class="sxs-lookup"><span data-stu-id="09735-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="09735-126">O America Online requer que o certificado do servidor de borda atribuído ao serviço de borda de acesso tenha um cliente de uso avançado de chave (EKU).</span><span class="sxs-lookup"><span data-stu-id="09735-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09735-127">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="09735-127">In This Section</span></span>

  - [<span data-ttu-id="09735-128">Resumo de certificado-conectividade de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09735-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="09735-129">Resumo de porta-conectividade de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09735-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="09735-130">[Resumo de DNS-conectividade de mensagens instantâneas públicas no Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="09735-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

