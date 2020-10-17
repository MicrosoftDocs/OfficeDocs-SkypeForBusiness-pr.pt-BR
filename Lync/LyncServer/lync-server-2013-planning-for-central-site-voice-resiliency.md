---
title: 'Lync Server 2013: planejamento para resiliência de voz do site central'
description: 'Lync Server 2013: planejamento da resiliência de voz do site central.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd41943212459311abdb64b3ed77c918539d082d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567377"
---
# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="68771-103">Planejamento da resiliência de voz do site central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68771-103">Planning for central site voice resiliency in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68771-104">_**Última modificação do tópico:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="68771-104">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="68771-105">Cada vez mais, as empresas têm vários locais espalhados em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="68771-105">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="68771-106">Manter os serviços de emergência, o acesso ao suporte técnico e a capacidade de conduzir tarefas de negócios críticos quando um site central está fora do serviço é essencial para qualquer solução de resiliência do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="68771-106">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="68771-107">Quando um site central fica indisponível, as seguintes condições devem ser atendidas:</span><span class="sxs-lookup"><span data-stu-id="68771-107">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="68771-108">O failover de voz deve ser fornecido.</span><span class="sxs-lookup"><span data-stu-id="68771-108">Voice failover must be provided.</span></span>

  - <span data-ttu-id="68771-109">Os usuários que normalmente se registram com o pool de front-ends no site central devem ser capazes de se registrar em um pool de front-ends alternativo.</span><span class="sxs-lookup"><span data-stu-id="68771-109">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="68771-110">Isso pode ser feito criando vários registros SRV DNS, cada um deles resolve para um pool de diretores ou pool de front-ends em cada um dos seus sites centrais.</span><span class="sxs-lookup"><span data-stu-id="68771-110">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="68771-111">Você pode ajustar a prioridade e os pesos dos registros SRV para que os usuários que são atendidos por esse site central obtenham o diretor e o pool de front-ends correspondentes em frente dos outros Registros SRV.</span><span class="sxs-lookup"><span data-stu-id="68771-111">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="68771-112">Chamadas para e de usuários localizados em outros sites devem ser redirecionadas para o PSTN.</span><span class="sxs-lookup"><span data-stu-id="68771-112">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="68771-113">Este tópico descreve a solução recomendada para proteger a resiliência de voz do site central.</span><span class="sxs-lookup"><span data-stu-id="68771-113">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="68771-114">Arquitetura e topologia</span><span class="sxs-lookup"><span data-stu-id="68771-114">Architecture and Topology</span></span>

<span data-ttu-id="68771-115">O planejamento da resiliência de voz em um site central requer uma compreensão básica da função central desempenhada pelo registrador do Lync Server 2013 para habilitar o failover de voz.</span><span class="sxs-lookup"><span data-stu-id="68771-115">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="68771-116">O registrador do Lync Server é uma função de servidor que permite o registro e a autenticação de clientes e fornece serviços de roteamento.</span><span class="sxs-lookup"><span data-stu-id="68771-116">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="68771-117">Ele reside junto com outros componentes em um servidor Standard Edition, servidor front-end, diretor ou aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="68771-117">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="68771-118">Um pool de registrador consiste em serviços de registrador em execução no pool de front-ends e residir no mesmo site.</span><span class="sxs-lookup"><span data-stu-id="68771-118">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="68771-119">O pool de front-ends deve ter o balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="68771-119">The Front End pool must be load balanced.</span></span> <span data-ttu-id="68771-120">O balanceamento de carga de DNS é recomendado, mas o balanceamento de carga de hardware é aceitável.</span><span class="sxs-lookup"><span data-stu-id="68771-120">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="68771-121">Um cliente Lync descobre o pool de front-ends através do seguinte mecanismo de descoberta:</span><span class="sxs-lookup"><span data-stu-id="68771-121">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="68771-122">Registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="68771-122">DNS SRV record</span></span>

2.  <span data-ttu-id="68771-123">Serviço Web de descoberta automática (novo no Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="68771-123">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="68771-124">Opção de DHCP 120</span><span class="sxs-lookup"><span data-stu-id="68771-124">DHCP option 120</span></span>

<span data-ttu-id="68771-125">Depois que o cliente do Lync se conecta ao pool de front-ends, ele é direcionado pelo balanceador de carga para um dos servidores front-end no pool.</span><span class="sxs-lookup"><span data-stu-id="68771-125">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="68771-126">Esse servidor front-end, por sua vez, redireciona o cliente para um registrador preferencial no pool.</span><span class="sxs-lookup"><span data-stu-id="68771-126">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="68771-127">Cada usuário habilitado para o Enterprise Voice é atribuído a um determinado pool de registradores, que se torna o pool principal de registradores do usuário.</span><span class="sxs-lookup"><span data-stu-id="68771-127">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="68771-128">Em um determinado site, centenas ou milhares de usuários normalmente compartilham um único pool de registradores primários.</span><span class="sxs-lookup"><span data-stu-id="68771-128">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="68771-129">Para considerar o consumo de recursos do site central por qualquer usuário de site de filial que confie no site central para presença, conferência ou failover, recomendamos que você considere cada usuário de site de filial como se o usuário fosse um usuário registrado no site central.</span><span class="sxs-lookup"><span data-stu-id="68771-129">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="68771-130">No momento, não há limites para o número de usuários do site de filial, incluindo usuários registrados em um aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="68771-130">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="68771-131">Para garantir a resiliência de voz no caso de uma falha de local central, o pool de registradores primário deve ter um único pool de registradores de backup designado, localizado em outro site.</span><span class="sxs-lookup"><span data-stu-id="68771-131">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="68771-132">O backup pode ser configurado usando as configurações de resiliência do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="68771-132">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="68771-133">Supondo que um link de WAN resiliente entre os dois sites, os usuários cujo pool de registradores primários não está mais disponível são direcionados automaticamente para o pool de registradores de backup.</span><span class="sxs-lookup"><span data-stu-id="68771-133">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="68771-134">As etapas a seguir descrevem o processo de descoberta e registro do cliente:</span><span class="sxs-lookup"><span data-stu-id="68771-134">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="68771-135">Um cliente descobre o Lync Server por meio de registros DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="68771-135">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="68771-136">No Lync Server 2013, os registros SRV DNS podem ser configurados para retornar mais de um FQDN para a consulta SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="68771-136">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="68771-137">Por exemplo, se a contoso da empresa tiver três sites centrais (América do Norte, Europa e Ásia-Pacífico) e um pool de diretores em cada site central, os registros SRV DNS poderão apontar para os FQDNs do pool de diretores em cada um dos três locais.</span><span class="sxs-lookup"><span data-stu-id="68771-137">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="68771-138">Contanto que o pool de diretor de um dos locais esteja disponível, o cliente pode se conectar ao primeiro servidor Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68771-138">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68771-139">O uso de um pool de diretor é opcional.</span><span class="sxs-lookup"><span data-stu-id="68771-139">Using a Director pool is optional.</span></span> <span data-ttu-id="68771-140">Um pool de front-ends pode ser usado em seu lugar.</span><span class="sxs-lookup"><span data-stu-id="68771-140">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="68771-141">O pool de diretores informa o cliente do Lync sobre o pool de registradores primário e o pool de registradores de backup do usuário.</span><span class="sxs-lookup"><span data-stu-id="68771-141">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="68771-142">O cliente Lync tenta se conectar primeiro ao pool de registradores primários do usuário.</span><span class="sxs-lookup"><span data-stu-id="68771-142">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="68771-143">Se o pool de registradores primário estiver disponível, o registrador aceitará o registro.</span><span class="sxs-lookup"><span data-stu-id="68771-143">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="68771-144">Se o pool de registradores primários não estiver disponível, o cliente do Lync tentará se conectar ao pool de registradores de backup.</span><span class="sxs-lookup"><span data-stu-id="68771-144">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="68771-145">Se o pool de registradores de backup estiver disponível e tiver determinado que o pool de registradores primários do usuário não está disponível (detectando a falta de pulsação para um intervalo de failover especificado), o pool de registradores de backup aceita o registro do usuário.</span><span class="sxs-lookup"><span data-stu-id="68771-145">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="68771-146">Depois que o registrador de backup detectar que o registrador principal está disponível novamente, o pool de registradores de backup redirecionará os clientes do Lync de failover para o pool principal.</span><span class="sxs-lookup"><span data-stu-id="68771-146">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="68771-147">A figura a seguir mostra a topologia recomendada para garantir a resiliência do site central.</span><span class="sxs-lookup"><span data-stu-id="68771-147">The following figure shows the recommended topology for assuring central site resiliency.</span></span> <span data-ttu-id="68771-148">Os dois sites estão conectados por um link WAN resiliente.</span><span class="sxs-lookup"><span data-stu-id="68771-148">The two sites are connected by a resilient WAN link.</span></span> <span data-ttu-id="68771-149">Se o site central ficar indisponível, os usuários atribuídos a esse pool serão direcionados para o site de backup para registro.</span><span class="sxs-lookup"><span data-stu-id="68771-149">If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="68771-150">**Topologia recomendada para a resiliência de voz do site central**</span><span class="sxs-lookup"><span data-stu-id="68771-150">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="68771-151">![Topologia para resiliência de voz do site central](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologia para resiliência de voz do site central")</span><span class="sxs-lookup"><span data-stu-id="68771-151">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="68771-152">Requisitos e recomendações</span><span class="sxs-lookup"><span data-stu-id="68771-152">Requirements and Recommendations</span></span>

<span data-ttu-id="68771-153">Os seguintes requisitos e recomendações para implementar a resiliência de voz do site central são apropriados para a maioria das organizações:</span><span class="sxs-lookup"><span data-stu-id="68771-153">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="68771-154">Os sites nos quais residem os pools de registradores primário e de backup devem estar conectados por um link WAN resiliente.</span><span class="sxs-lookup"><span data-stu-id="68771-154">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="68771-155">Cada site central deve conter um pool de registradores que consiste em um ou mais registradores.</span><span class="sxs-lookup"><span data-stu-id="68771-155">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="68771-156">Cada pool de registradores deve ter balanceamento de carga usando o balanceamento de carga DNS, balanceamento de carga de hardware ou ambos.</span><span class="sxs-lookup"><span data-stu-id="68771-156">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="68771-157">Para obter informações detalhadas sobre como planejar a configuração de balanceamento de carga, consulte [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68771-157">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="68771-158">Cada usuário deve ser atribuído a um pool de registradores primário usando o cmdlet **set-CsUser** do Lync Server Management Shell ou o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68771-158">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="68771-159">O pool de registradores primário deve ter um único pool de registradores de backup localizado em um site central diferente.</span><span class="sxs-lookup"><span data-stu-id="68771-159">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="68771-160">O pool de registradores primário deve ser configurado para fazer failover para o pool de registradores de backup.</span><span class="sxs-lookup"><span data-stu-id="68771-160">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="68771-161">Por padrão, o registrador principal é definido para failover para o pool de registradores de backup após um intervalo de 300 segundos.</span><span class="sxs-lookup"><span data-stu-id="68771-161">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="68771-162">Você pode alterar esse intervalo usando o construtor de topologias do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68771-162">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="68771-163">Configure uma rota de failover, conforme descrito no tópico "[Configurando uma rota de failover no Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)", na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="68771-163">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="68771-164">Ao configurar a rota, especifique um gateway que esteja localizado em um site diferente do gateway especificado na rota principal.</span><span class="sxs-lookup"><span data-stu-id="68771-164">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="68771-165">Se o site central contiver o servidor de gerenciamento principal e se o site for provavelmente inoperante por um período estendido, será necessário reinstalar as ferramentas de gerenciamento no local de backup; caso contrário, você não poderá alterar as configurações de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="68771-165">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="68771-166">Dependências</span><span class="sxs-lookup"><span data-stu-id="68771-166">Dependencies</span></span>

<span data-ttu-id="68771-167">O Lync Server depende dos seguintes componentes de infraestrutura e software para garantir a resiliência de voz:</span><span class="sxs-lookup"><span data-stu-id="68771-167">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68771-168"><strong>Componente</strong></span><span class="sxs-lookup"><span data-stu-id="68771-168"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="68771-169"><strong>Funcionamento</strong></span><span class="sxs-lookup"><span data-stu-id="68771-169"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68771-170">DNS</span><span class="sxs-lookup"><span data-stu-id="68771-170">DNS</span></span></p></td>
<td><p><span data-ttu-id="68771-171">Resolvendo Registros SRV e registros de servidor-servidor e servidor-cliente</span><span class="sxs-lookup"><span data-stu-id="68771-171">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68771-172">Exchange e serviços Web do Exchange (EWS)</span><span class="sxs-lookup"><span data-stu-id="68771-172">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="68771-173">Armazenamento de contatos; dados de calendário</span><span class="sxs-lookup"><span data-stu-id="68771-173">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68771-174">Unificação de mensagens do Exchange e serviços Web do Exchange</span><span class="sxs-lookup"><span data-stu-id="68771-174">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="68771-175">Logs de chamada, lista de caixa postal, caixa postal</span><span class="sxs-lookup"><span data-stu-id="68771-175">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68771-176">Opções de DHCP 120</span><span class="sxs-lookup"><span data-stu-id="68771-176">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="68771-177">Se o DNS SRV não estiver disponível, o cliente tentará usar a opção 120 de DHCP para descobrir o registrador.</span><span class="sxs-lookup"><span data-stu-id="68771-177">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="68771-178">Para que isso funcione, é necessário configurar um servidor DHCP ou o Lync Server 2013 DHCP deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="68771-178">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="68771-179">Para obter detalhes, consulte Hardware and Software Requirements for Branch-Site resiliência na seção <a href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resiliência de site de filial para Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="68771-179">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="68771-180">Recursos de voz persistente</span><span class="sxs-lookup"><span data-stu-id="68771-180">Survivable Voice Features</span></span>

<span data-ttu-id="68771-181">Se os requisitos e as recomendações anteriores tiverem sido implementados, os seguintes recursos de voz serão fornecidos pelo pool de registradores de backup:</span><span class="sxs-lookup"><span data-stu-id="68771-181">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="68771-182">Chamadas PSTN de saída</span><span class="sxs-lookup"><span data-stu-id="68771-182">Outbound PSTN calls</span></span>

  - <span data-ttu-id="68771-183">Chamadas PSTN de entrada, se o provedor de serviços de telefonia oferecer suporte à capacidade de failover para um site de backup</span><span class="sxs-lookup"><span data-stu-id="68771-183">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="68771-184">Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes</span><span class="sxs-lookup"><span data-stu-id="68771-184">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="68771-185">Manipulação de chamada básica, incluindo chamada em espera, recuperação e transferência</span><span class="sxs-lookup"><span data-stu-id="68771-185">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="68771-186">Mensagens instantâneas de dois participantes e compartilhamento de áudio e vídeo entre usuários no mesmo site</span><span class="sxs-lookup"><span data-stu-id="68771-186">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="68771-187">Encaminhamento de chamadas, toque simultâneo de pontos de extremidade, delegação de chamada e serviços de chamada de equipe, mas somente se as duas partes da delegação de chamada ou todos os membros da equipe estiverem configuradas no mesmo site.</span><span class="sxs-lookup"><span data-stu-id="68771-187">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="68771-188">Os clientes e telefones existentes continuam funcionando.</span><span class="sxs-lookup"><span data-stu-id="68771-188">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="68771-189">CDR (registro de detalhes das chamadas)</span><span class="sxs-lookup"><span data-stu-id="68771-189">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="68771-190">Autenticação e autorização</span><span class="sxs-lookup"><span data-stu-id="68771-190">Authentication and authorization</span></span>

<span data-ttu-id="68771-191">Dependendo de como estão configurados, os seguintes recursos de voz podem ou não funcionar quando um site central primário está fora de serviço:</span><span class="sxs-lookup"><span data-stu-id="68771-191">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="68771-192">Depósito e recuperação de caixa postal</span><span class="sxs-lookup"><span data-stu-id="68771-192">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="68771-193">Se você quiser tornar o UM do Exchange disponível quando o site central primário estiver fora de serviço, você deve executar um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="68771-193">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="68771-194">Altere os registros SRV DNS para que os servidores UM do Exchange no site central apontem para os servidores de backup do UM do Exchange em outro site.</span><span class="sxs-lookup"><span data-stu-id="68771-194">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="68771-195">Configure o plano de discagem de UM de cada usuário para incluir os servidores de UM do Exchange no site central e no site de backup, mas designe os servidores de backup de UM do Exchange como desabilitado.</span><span class="sxs-lookup"><span data-stu-id="68771-195">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="68771-196">Se o site primário ficar indisponível, o administrador do Exchange precisará marcar os servidores de UM do Exchange no local de backup como habilitados.</span><span class="sxs-lookup"><span data-stu-id="68771-196">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="68771-197">Se nenhuma das soluções anteriores for possível, a UM do Exchange não estará disponível, caso o site central fique indisponível.</span><span class="sxs-lookup"><span data-stu-id="68771-197">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="68771-198">Conferência de todos os tipos</span><span class="sxs-lookup"><span data-stu-id="68771-198">Conferencing of all types</span></span>
    
    <span data-ttu-id="68771-199">Um usuário com failover em um site de backup pode ingressar em uma conferência que é criada ou hospedada por um organizador cujo pool está disponível, mas não pode criar ou hospedar uma conferência em seu próprio pool principal, o que não está mais disponível.</span><span class="sxs-lookup"><span data-stu-id="68771-199">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available.</span></span> <span data-ttu-id="68771-200">Da mesma forma, outros usuários não podem participar de conferências hospedadas no pool principal do usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="68771-200">Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="68771-201">Os seguintes recursos de voz não funcionam quando um site central primário está fora de serviço:</span><span class="sxs-lookup"><span data-stu-id="68771-201">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="68771-202">Atendedor automático de conferência</span><span class="sxs-lookup"><span data-stu-id="68771-202">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="68771-203">Presença e roteamento baseado em DND</span><span class="sxs-lookup"><span data-stu-id="68771-203">Presence and DND-based routing</span></span>

  - <span data-ttu-id="68771-204">Atualização de configurações de encaminhamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="68771-204">Updating call forwarding settings</span></span>

  - <span data-ttu-id="68771-205">Serviço de grupo de resposta e estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="68771-205">Response Group service and Call Park</span></span>

  - <span data-ttu-id="68771-206">Provisionamento de novos telefones e clientes</span><span class="sxs-lookup"><span data-stu-id="68771-206">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="68771-207">Pesquisa na Web do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="68771-207">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68771-208">Confira também</span><span class="sxs-lookup"><span data-stu-id="68771-208">See Also</span></span>


[<span data-ttu-id="68771-209">Planejamento de resiliência de voz no site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68771-209">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

