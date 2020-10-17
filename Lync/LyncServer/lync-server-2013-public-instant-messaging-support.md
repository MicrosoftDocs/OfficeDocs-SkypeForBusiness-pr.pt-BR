---
title: 'Lync Server 2013: suporte a mensagens instantâneas públicas'
description: 'Lync Server 2013: suporte a mensagens instantâneas públicas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e071e8b79be82d865a85a9488e48dd0a4264c7f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565567"
---
# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="49e42-103">Suporte a mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49e42-103">Public instant messaging support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49e42-104">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="49e42-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="49e42-105">O Lync Server 2013 suporta o uso de provedores de conectividade de mensagens instantâneas públicas licenciados, bem como o uso de protocolo XMPP (eXtensible Messaging and Presence Protocol) para implementar um tipo especial de Federação que permite a um Lync Server acessar parceiros de domínio do XMPP configurados usando o cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="49e42-105">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="49e42-106">Suporte do provedor de conectividade de IM público</span><span class="sxs-lookup"><span data-stu-id="49e42-106">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="49e42-107">Os parceiros de conectividade de mensagem instantânea pública suportados atualmente são:</span><span class="sxs-lookup"><span data-stu-id="49e42-107">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="49e42-108">America Online</span><span class="sxs-lookup"><span data-stu-id="49e42-108">America Online</span></span>

  - <span data-ttu-id="49e42-109">Windows Live</span><span class="sxs-lookup"><span data-stu-id="49e42-109">Windows Live</span></span>

  - <span data-ttu-id="49e42-110">Instant\!</span><span class="sxs-lookup"><span data-stu-id="49e42-110">Yahoo\!</span></span>

<span data-ttu-id="49e42-111">Para comunicações com usuários do Windows Live, o Lync Server 2013 suporta mensagens instantâneas ponto a ponto e chamadas de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="49e42-111">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="49e42-112">Para comunicações com AOL e Yahoo \! , o Lync Server 2013 oferece suporte a mensagens instantâneas ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="49e42-112">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="49e42-113">Uma licença separada pode ser necessária.</span><span class="sxs-lookup"><span data-stu-id="49e42-113">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="49e42-114">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="49e42-114">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="49e42-115">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="49e42-115">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="49e42-116">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="49e42-116">Messenger until the service shut down date.</span></span> <span data-ttu-id="49e42-117">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="49e42-117">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="49e42-118">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="49e42-118">has been announced.</span></span> <span data-ttu-id="49e42-119">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="49e42-119">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="49e42-120">O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="49e42-120">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="49e42-121">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="49e42-121">Messenger.</span></span> <span data-ttu-id="49e42-122">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</span><span class="sxs-lookup"><span data-stu-id="49e42-122">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="49e42-123">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="49e42-123">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="49e42-124">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="49e42-124">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="49e42-125">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="49e42-125">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="49e42-126">Suporte de Federação XMPP</span><span class="sxs-lookup"><span data-stu-id="49e42-126">XMPP Federation Support</span></span>

<span data-ttu-id="49e42-p105">A federação XMPP suporta a comunicação de usuários do Lync com usuários de domínio XMPP configurado que usam um provedor público, como GTalk. As comunicações com estes usuários podem incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="49e42-p105">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk. Communications with these users can include the following:</span></span>

  - <span data-ttu-id="49e42-129">IM ponto a ponto e presença</span><span class="sxs-lookup"><span data-stu-id="49e42-129">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="49e42-130">Criação de contatos federados XMPP no cliente Lync</span><span class="sxs-lookup"><span data-stu-id="49e42-130">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

