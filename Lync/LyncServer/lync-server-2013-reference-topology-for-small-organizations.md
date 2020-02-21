---
title: Lync Server 2013 referência topologia para pequenas organizações
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726056b63dfa37864171a77913b5126c23b27045
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="535d8-102">Topologia de referência para Lync Server 2013 em pequenas organizações</span><span class="sxs-lookup"><span data-stu-id="535d8-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="535d8-103">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="535d8-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="535d8-104">A topologia de referência para pequenas organizações mostra como você pode implantar uma solução robusta e altamente disponível implantando apenas três servidores que executam o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="535d8-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="535d8-105">**Topologia de referência para pequenas organizações**</span><span class="sxs-lookup"><span data-stu-id="535d8-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="535d8-106">![Diagrama da topologia de referência de implantação de três servidores](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Diagrama da topologia de referência de implantação de três servidores")</span><span class="sxs-lookup"><span data-stu-id="535d8-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="535d8-107">**Par de servidores Standard Edition implantado**     esta organização tem 4.000 usuários no site central.</span><span class="sxs-lookup"><span data-stu-id="535d8-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="535d8-108">A organização implantou dois servidores Standard Edition e os combinaram para permitir alta disponibilidade e recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="535d8-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="535d8-109">Cada servidor casa 2.000 usuários, mas as informações sobre todos os usuários são sincronizadas entre os dois servidores.</span><span class="sxs-lookup"><span data-stu-id="535d8-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="535d8-110">Se um for desativado, um administrador pode fazer o failover desses usuários para ser servido pelo outro servidor, com o mínimo de interrupção para os usuários.</span><span class="sxs-lookup"><span data-stu-id="535d8-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="535d8-111">Para obter mais informações sobre recursos de alta disponibilidade e recuperação de desastre no Lync Server 2013, consulte [Planning for High Availability and Disaster Recovery in Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="535d8-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="535d8-112">**A implantação do servidor de borda é recomendada.**    Embora a implantação de um servidor de borda não seja necessária para im, presença e conferência internas, recomendamos que ele seja mesmo para pequenas implantações.</span><span class="sxs-lookup"><span data-stu-id="535d8-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="535d8-113">Você pode maximizar seu investimento no Lync Server implantando um servidor de borda para fornecer serviço aos usuários fora dos firewalls da sua organização.</span><span class="sxs-lookup"><span data-stu-id="535d8-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="535d8-114">Os benefícios são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="535d8-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="535d8-115">Os usuários da sua organização podem usar a funcionalidade do Lync Server, se estiverem trabalhando de casa ou estão em trânsito.</span><span class="sxs-lookup"><span data-stu-id="535d8-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="535d8-116">Seus usuários podem convidar usuários de fora para participar de reuniões.</span><span class="sxs-lookup"><span data-stu-id="535d8-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="535d8-117">Se você tiver uma organização de parceiro, fornecedor ou cliente que também usa o Lync Server, você pode formar uma *relação federada* com essa organização.</span><span class="sxs-lookup"><span data-stu-id="535d8-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="535d8-118">A implantação do Lync Server reconhecerá os usuários dessa organização federada, levando à melhor colaboração.</span><span class="sxs-lookup"><span data-stu-id="535d8-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="535d8-119">Seus usuários podem trocar mensagens instantâneas com usuários de serviços públicos de IM, incluindo qualquer uma das seguintes opções: Windows Live, AOL,\!Yahoo e Google Talk.</span><span class="sxs-lookup"><span data-stu-id="535d8-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="535d8-120">Uma licença separada pode ser necessária para conectividade de IM pública com esses serviços.</span><span class="sxs-lookup"><span data-stu-id="535d8-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="535d8-121">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="535d8-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="535d8-122">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="535d8-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="535d8-123">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="535d8-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="535d8-124">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="535d8-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="535d8-125">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="535d8-125">has been announced.</span></span> <span data-ttu-id="535d8-126">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="535d8-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="535d8-127">O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="535d8-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="535d8-128">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="535d8-128">Messenger.</span></span> <span data-ttu-id="535d8-129">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</span><span class="sxs-lookup"><span data-stu-id="535d8-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="535d8-130">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="535d8-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="535d8-131">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="535d8-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="535d8-132">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="535d8-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="535d8-133">**Sustentabilidade do site de filial.**    Esta organização está executando um programa piloto do recurso Enterprise Voice do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="535d8-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="535d8-134">Alguns usuários estão usando o Lync Server como sua única solução de voz.</span><span class="sxs-lookup"><span data-stu-id="535d8-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="535d8-135">Alguns desses usuários do piloto de voz estão localizados no site de filial.</span><span class="sxs-lookup"><span data-stu-id="535d8-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="535d8-136">O site de filial não tem um link de rede de longa distância (WAN) confiável para o site central, portanto, um aparelho de filial persistente é implantado.</span><span class="sxs-lookup"><span data-stu-id="535d8-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="535d8-137">Com isso implantado, se o link de WAN ficar inativo, os usuários no site de filial ainda poderão fazer e receber chamadas (ambas as chamadas dentro da organização e chamadas PSTN), ter funcionalidade de caixa postal e se comunicar com mensagens instantâneas de dois participantes.</span><span class="sxs-lookup"><span data-stu-id="535d8-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="535d8-138">Os usuários ainda podem ser autenticados quando um link WAN estiver indisponível.</span><span class="sxs-lookup"><span data-stu-id="535d8-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="535d8-139">**Implantação do Exchange do UM.**</span><span class="sxs-lookup"><span data-stu-id="535d8-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="535d8-140">Essa topologia de referência inclui um servidor de UM (Unificação de mensagens) do Exchange, que executa o Microsoft Exchange Server, e não o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="535d8-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="535d8-141">Para obter detalhes sobre a UM do Exchange, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [Hosted Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="535d8-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="535d8-142">**Servidor do Office Web Apps.**</span><span class="sxs-lookup"><span data-stu-id="535d8-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="535d8-143">Recomendamos a implantação de um servidor do Office Web Apps ou do farm do servidor do Office Web Apps em todas as organizações que usam a conferência da Web.</span><span class="sxs-lookup"><span data-stu-id="535d8-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="535d8-144">O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências.</span><span class="sxs-lookup"><span data-stu-id="535d8-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="535d8-145">Para obter mais informações, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="535d8-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

