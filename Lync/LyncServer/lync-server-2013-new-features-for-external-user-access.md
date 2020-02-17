---
title: 'Lync Server 2013: novos recursos para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e85c9e83a6dde06c7c091241bea903a3ddd1d813
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="dc5f1-102">Novos recursos para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc5f1-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc5f1-103">_**Última modificação do tópico:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="dc5f1-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="dc5f1-104">O Lync Server 2013 introduz novos recursos que estendem os recursos e os métodos de comunicação para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="dc5f1-105">Além disso, o Lync Server 2013 introduz alterações nos serviços existentes para integrar e estender melhor os serviços que estão disponíveis para sua organização.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="dc5f1-106">Veja a seguir um resumo das alterações que podem afetar o planejamento e a implantação dos serviços do servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="dc5f1-107">**O suporte para IPv6 Addressing**   Lync Server 2013 oferece suporte ao endereçamento IPv6 para todos os serviços do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="dc5f1-108">Se você tiver fornecido endereços IPv6 para as interfaces por meio da configuração no Windows Server, poderá usar endereços IPv6 na configuração do servidor de borda através da configuração de endereço IP no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dc5f1-109">O uso de endereços IPv6 no Lync Server 2013 depende do suporte do IPv6 em roteadores e firewalls que sua organização implanta, bem como suporte por meio de seu provedor de serviços de Internet.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="dc5f1-110">**O XMPP (Extensible Messaging and Presence Protocol)**   Lync Server 2013 introduz um proxy XMPP totalmente integrado (implantado nos servidores de borda) e um Gateway XMPP implantado em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="dc5f1-111">Você pode implantar a Federação do XMPP como um componente opcional.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="dc5f1-112">Adicionar e configurar o XMPP proxy e o Gateway XMPP permitirão que seus usuários do Microsoft Lync 2013 adicionem contatos de parceiros baseados em XMPP para mensagens instantâneas (IM) e presença.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dc5f1-113">Atualmente, os serviços do XMPP no Lync Server 2013 só fornecem mensagens instantâneas e presença entre os clientes do Lync e os contatos baseados no XMPP.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="dc5f1-114">**Serviços de mobilidade para clientes móveis**   introduzidos em uma atualização de cliente para o Lync Server 2010, os serviços de mobilidade no Lync Server 2013 permitem que clientes móveis do Microsoft Lync em telefones celulares e dispositivos tablets usando dispositivos móveis Apple Ios, Android, Windows Phone ou Nokia com suporte para executar tais atividades, como enviar e receber mensagens instantâneas, exibir contatos e ver a presença.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="dc5f1-115">Além disso, os dispositivos móveis são compatíveis com alguns recursos do Enterprise Voice, como clique para ingressar em uma conferência, ligar via trabalho, alcance de um único número, caixa postal e notificação de chamada perdida.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dc5f1-116">Os serviços de mobilidade usam o proxy reverso e os serviços publicados que são implantados em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="dc5f1-117">Nenhuma alteração é necessária para os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="dc5f1-118">**Os diretores são uma função**   opcional a função do servidor Diretor na topologia do Lync Server 2013 não foi alterada.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="dc5f1-119">Ele ainda hospeda serviços Web, autentica previamente as solicitações do usuário e direciona os usuários externos para o pool inicial.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="dc5f1-120">Alterar o diretor de uma função recomendada para uma função opcional não diminui o valor do diretor, mas enfatiza a redução da contagem de servidores e outros requisitos de hardware (por exemplo, balanceadores de carga de hardware para os requisitos de diretor) sem recursos de comprometimento e funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="dc5f1-121">Como os servidores de front-end podem fazer o mesmo trabalho que o diretor sem impacto nos serviços fornecidos, você pode, opcionalmente, implantar diretores, se você escolher.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="dc5f1-122">Você pode excluir com segurança o diretor com confiança de que os servidores front-end fornecerão os mesmos serviços em seu lugar.</span><span class="sxs-lookup"><span data-stu-id="dc5f1-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dc5f1-123">Confira Também</span><span class="sxs-lookup"><span data-stu-id="dc5f1-123">See Also</span></span>


[<span data-ttu-id="dc5f1-124">Planejando e Configurando o IPv6 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc5f1-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="dc5f1-125">Planejamento para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc5f1-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="dc5f1-126">Planejando a Federação do protocolo XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc5f1-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

