---
title: 'Lync Server 2013: definindo seus requisitos para servidores front-end, mensagens instantâneas e presença'
description: 'Lync Server 2013: definindo seus requisitos para servidores front-end, sistema de mensagens instantâneas e presença.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923132b32d5aef80191b19a7b85c3f17276e5946
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545367"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="30d20-103">Definindo seus requisitos para servidores front-end, mensagens instantâneas e presença no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30d20-103">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30d20-104">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="30d20-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="30d20-105">A principal tarefa de planejamento de mensagens instantâneas (IM) e presença é garantir que você tenha servidores front-end suficientes para os usuários.</span><span class="sxs-lookup"><span data-stu-id="30d20-105">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="30d20-106">Habilitando a comunicação com usuários externos</span><span class="sxs-lookup"><span data-stu-id="30d20-106">Enabling Communication with External Users</span></span>

<span data-ttu-id="30d20-107">Você pode aumentar significativamente os benefícios de seu investimento no Lync Server, permitindo que os usuários se comuniquem com usuários externos.</span><span class="sxs-lookup"><span data-stu-id="30d20-107">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="30d20-108">Os usuários externos podem incluir:</span><span class="sxs-lookup"><span data-stu-id="30d20-108">External users can include:</span></span>

  - <span data-ttu-id="30d20-109">**Usuários**     remotos Os próprios usuários da sua organização, quando estão trabalhando fora de seus firewalls e estão usando seus laptops ou outros dispositivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30d20-109">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="30d20-110">**Usuários federados**     Usuários de empresas com as quais você trabalha e que também executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30d20-110">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="30d20-111">Para permitir que os usuários contatem facilmente esses usuários, você pode criar relacionamentos federados com essas empresas.</span><span class="sxs-lookup"><span data-stu-id="30d20-111">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="30d20-112">**Usuários públicos**     Usuários de serviços públicos de IM, como serviços de IM fornecidos pela rede do Windows Live de serviços de Internet, Yahoo e \! AOL, e usuários de provedores e servidores que usam o protocolo XMPP (Extensible Messaging and Presence Protocol), como o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="30d20-112">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30d20-113">Observe que uma licença separada pode ser necessária para a conectividade de mensagens instantâneas públicas com Windows Live, AOL e Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="30d20-113">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="30d20-114">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="30d20-114">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="30d20-115">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="30d20-115">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="30d20-116">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="30d20-116">Messenger until the service shut down date.</span></span> <span data-ttu-id="30d20-117">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="30d20-117">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="30d20-118">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="30d20-118">has been announced.</span></span> <span data-ttu-id="30d20-119">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="30d20-119">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="30d20-120">O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="30d20-120">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="30d20-121">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="30d20-121">Messenger.</span></span> <span data-ttu-id="30d20-122">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</span><span class="sxs-lookup"><span data-stu-id="30d20-122">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="30d20-123">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="30d20-123">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="30d20-124">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="30d20-124">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="30d20-125">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="30d20-125">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="30d20-126">Para habilitar qualquer um ou todos esses cenários, você precisa implantar um servidor de borda para ajudar a habilitar comunicações seguras entre sua implantação do Lync Server e usuários externos.</span><span class="sxs-lookup"><span data-stu-id="30d20-126">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="30d20-127">Os usuários e usuários remotos da sua organização em organizações federadas poderão ver a presença de cada um e se comunicar usando mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="30d20-127">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="30d20-128">Para obter detalhes sobre como habilitar a comunicação com usuários externos, consulte [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="30d20-128">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="30d20-129">Arquivamento de conteúdo de IM</span><span class="sxs-lookup"><span data-stu-id="30d20-129">Archiving IM Content</span></span>

<span data-ttu-id="30d20-130">O Lync Server fornece recursos que você pode usar se sua organização deve seguir as regulamentações de conformidade.</span><span class="sxs-lookup"><span data-stu-id="30d20-130">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="30d20-131">Você pode usar o arquivamento para arquivar o conteúdo de mensagens INSTANTÂNEAs para todos os usuários em sua organização ou apenas para determinados usuários que você especificar.</span><span class="sxs-lookup"><span data-stu-id="30d20-131">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="30d20-132">Para obter detalhes, consulte [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="30d20-132">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="30d20-133">Se você também tiver o Microsoft Exchange Server 2013 implantado, você pode integrar o arquivamento de dados do Exchange com o arquivamento de dados do Lync Server e usar uma única ferramenta para pesquisar ambos os tipos de dados arquivados.</span><span class="sxs-lookup"><span data-stu-id="30d20-133">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="30d20-134">Para obter mais informações, consulte [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange server 2013 Archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="30d20-134">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

