---
title: 'Lync Server 2013: Configurando o suporte para grandes reuniões'
description: 'Lync Server 2013: Configurando o suporte para grandes reuniões.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb04b4192c6daa9e6ea255b52566dacee1bd2dcd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554207"
---
# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="0014a-103">Configurando o suporte para grandes reuniões no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0014a-103">Setting up support for large meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0014a-104">_**Última modificação do tópico:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="0014a-104">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="0014a-105">O suporte a grandes reuniões de até 1000 usuários exige a criação de uma topologia apropriada, os pré-requisitos de software e hardware de reunião e a configuração adequada do ambiente.</span><span class="sxs-lookup"><span data-stu-id="0014a-105">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="0014a-106">Requisitos de topologia</span><span class="sxs-lookup"><span data-stu-id="0014a-106">Topology Requirements</span></span>

<span data-ttu-id="0014a-107">Uma única reunião grande requer pelo menos um servidor front-end e um servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="0014a-107">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="0014a-108">No entanto, para fornecer alta disponibilidade, recomendamos um pool de servidores front-end com servidores back-end espelhados.</span><span class="sxs-lookup"><span data-stu-id="0014a-108">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="0014a-109">O usuário que hospeda as grandes reuniões deve ter sua conta de usuário hospedada neste pool.</span><span class="sxs-lookup"><span data-stu-id="0014a-109">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="0014a-110">No entanto, não recomendamos que você hospede outras contas de usuário nesse pool.</span><span class="sxs-lookup"><span data-stu-id="0014a-110">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="0014a-111">Em vez disso, use-o apenas para grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="0014a-111">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="0014a-112">A prática recomendada é criar uma conta de usuário especial nesse pool para ser usada apenas para hospedar grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="0014a-112">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="0014a-113">Como a grande configuração de reunião é otimizada para desempenho, usá-la como um usuário normal pode ter problemas como a incapacidade de promover uma sessão P2P para uma reunião quando um ponto de extremidade PSTN está envolvido.</span><span class="sxs-lookup"><span data-stu-id="0014a-113">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="0014a-114">O gerenciamento de um pool com exatamente dois servidores front-end requer algumas considerações especiais.</span><span class="sxs-lookup"><span data-stu-id="0014a-114">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="0014a-115">Para obter mais informações, consulte [topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="0014a-115">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="0014a-116">Além disso, se você quiser fornecer opcionalmente o backup de recuperação de desastres e o failover do pool usado para grandes reuniões, é possível emparelhar com uma configuração de pool dedicado de forma semelhante em um Data Center diferente.</span><span class="sxs-lookup"><span data-stu-id="0014a-116">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="0014a-117">Para obter detalhes, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="0014a-117">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="0014a-118">![Configuração do pool de reuniões grandes](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configuração do pool de reuniões grandes")</span><span class="sxs-lookup"><span data-stu-id="0014a-118">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="0014a-119">As observações adicionais sobre a topologia incluem:</span><span class="sxs-lookup"><span data-stu-id="0014a-119">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="0014a-120">Um compartilhamento de arquivos é necessário para armazenar o conteúdo da reunião e, se o servidor de arquivamento estiver implantado e habilitado, para armazenar os arquivos de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0014a-120">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="0014a-121">O compartilhamento de arquivos pode ser dedicado ao pool ou pode ser o mesmo compartilhamento de arquivo usado por outro pool no site no qual o pool é implantado.</span><span class="sxs-lookup"><span data-stu-id="0014a-121">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="0014a-122">Para obter detalhes sobre como configurar o compartilhamento de arquivos, consulte [Configure File Storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="0014a-122">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="0014a-123">Um servidor do Office Web Apps é necessário para habilitar a funcionalidade de apresentação do PowerPoint em grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="0014a-123">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="0014a-124">O servidor do Office Web Apps pode ser dedicado ao grande pool de reuniões ou pode ser o mesmo servidor do Office Web Apps usado por outros pools no site no qual o pool dedicado é implantado.</span><span class="sxs-lookup"><span data-stu-id="0014a-124">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="0014a-125">O balanceamento de carga dos servidores front-end requer o balanceamento de carga de hardware para o tráfego HTTP (como download de conteúdo de reunião).</span><span class="sxs-lookup"><span data-stu-id="0014a-125">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="0014a-126">O balanceamento de carga de DNS é recomendado para tráfego SIP.</span><span class="sxs-lookup"><span data-stu-id="0014a-126">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="0014a-127">Para obter detalhes, consulte [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0014a-127">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="0014a-128">Se você quiser usar o Monitoring Server para o pool dedicado de grandes reuniões, recomendamos o uso do Monitoring Server e do banco de dados compartilhado em todos os pools de servidores front-end na sua implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0014a-128">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="0014a-129">Requisitos de hardware e de software</span><span class="sxs-lookup"><span data-stu-id="0014a-129">Hardware and Software Requirements</span></span>

<span data-ttu-id="0014a-130">Os requisitos de hardware para servidores em um pool de grande reunião dedicado são os mesmos que para seus outros servidores do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0014a-130">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="0014a-131">Para obter detalhes sobre os requisitos de hardware, consulte "[plataformas de hardware de servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="0014a-131">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="0014a-132">Os servidores em um pool de reunião grande dedicado devem atender a todos os requisitos de software do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0014a-132">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="0014a-133">Para obter detalhes sobre os requisitos de software, confira a seguinte documentação:</span><span class="sxs-lookup"><span data-stu-id="0014a-133">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="0014a-134">Suporte a sistemas operacionais de servidor e de ferramentas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0014a-134">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="0014a-135">Suporte a software de banco de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0014a-135">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="0014a-136">Requisitos de software adicionais para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0014a-136">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="0014a-137">Além disso, o Lync Server 2013 e todos os clientes do Lync Server 2013 devem ter as atualizações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="0014a-137">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="0014a-138">Requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="0014a-138">Configuration Requirements</span></span>

<span data-ttu-id="0014a-139">Recomendamos a criação de uma nova política de conferência especificamente para grandes reuniões e, em seguida, a atribuição da política de conferência aos usuários hospedados no pool dedicado de grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="0014a-139">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="0014a-140">Configure a política de conferência usando as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="0014a-140">Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="0014a-141">Defina a opção **MaxMeetingSize** para **1000**.</span><span class="sxs-lookup"><span data-stu-id="0014a-141">Set the **MaxMeetingSize** option to **1000**.</span></span> <span data-ttu-id="0014a-142">(O padrão é **250**).</span><span class="sxs-lookup"><span data-stu-id="0014a-142">(The default is **250**.)</span></span>

  - <span data-ttu-id="0014a-143">Defina a opção **AllowLargeMeetings** como **true**.</span><span class="sxs-lookup"><span data-stu-id="0014a-143">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="0014a-144">Defina a opção **EnableAppDesktopSharing** para **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="0014a-144">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="0014a-145">Defina a opção **AllowUserToScheduleMeetingsWithAppSharing** para **falso**.</span><span class="sxs-lookup"><span data-stu-id="0014a-145">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="0014a-146">Defina a opção **AllowSharedNotes** para **falso**.</span><span class="sxs-lookup"><span data-stu-id="0014a-146">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="0014a-147">Defina a opção **AllowAnnotations** para **falso**.</span><span class="sxs-lookup"><span data-stu-id="0014a-147">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="0014a-148">Defina a opção **DisablePowerPointAnnotations** como **true**.</span><span class="sxs-lookup"><span data-stu-id="0014a-148">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="0014a-149">Defina a opção **AllowMultiview** para **falso**.</span><span class="sxs-lookup"><span data-stu-id="0014a-149">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="0014a-150">Defina a opção **EnableMultiviewJoin** para **falso**.</span><span class="sxs-lookup"><span data-stu-id="0014a-150">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0014a-151">O suporte para o usuário 1000 grandes reuniões no Lync Server 2013 requer que a configuração <STRONG>AllowLargeMeetings</STRONG> na política de conferência do Agendador de reunião seja definida como true.</span><span class="sxs-lookup"><span data-stu-id="0014a-151">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="0014a-152">Quando essa configuração for definida como true, a experiência do Lync será otimizada para reuniões extras grandes quando os usuários ingressarem em reunião.</span><span class="sxs-lookup"><span data-stu-id="0014a-152">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="0014a-153">Especificamente, em uma grande reunião, o Lync não mostrará a inicial ou a atualização da lista de participantes da reunião completa, que é um afunilamento de desempenho para o cliente e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0014a-153">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="0014a-154">Em vez disso, o Lync mostrará apenas informações sobre o usuário e a lista de apresentadores da reunião.</span><span class="sxs-lookup"><span data-stu-id="0014a-154">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="0014a-155">O Lync ainda exibirá corretamente o número total de participantes disponíveis nas grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="0014a-155">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="0014a-156">Com exceção da configuração do **tamanho máximo da reunião** , todas as outras configurações de política de conferência especificadas aqui são necessárias para desabilitar os recursos de conferência que não são necessários em grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="0014a-156">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="0014a-157">Além disso, você precisa configurar o pool de reunião grande dedicado para que cada usuário do Lync Server 2013 hospedado no pool e responsável pelo gerenciamento da agenda da reunião tenha as permissões apropriadas.</span><span class="sxs-lookup"><span data-stu-id="0014a-157">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="0014a-158">Para tanto, siga estes passos:</span><span class="sxs-lookup"><span data-stu-id="0014a-158">To do this, do the following:</span></span>

  - <span data-ttu-id="0014a-159">Defina a opção **designar como apresentador** como **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="0014a-159">Set the **Designate as presenter** option to **None**.</span></span> <span data-ttu-id="0014a-160">Normalmente, um ou apenas alguns usuários de todos os participantes de uma grande reunião são os apresentadores, portanto, os participantes não devem ser admitidos automaticamente em grandes reuniões como apresentadores.</span><span class="sxs-lookup"><span data-stu-id="0014a-160">Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters.</span></span> <span data-ttu-id="0014a-161">Em vez disso, os apresentadores devem ser explicitamente designados no horário do plano de reunião ou ser promovidos explicitamente durante a grande reunião.</span><span class="sxs-lookup"><span data-stu-id="0014a-161">Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="0014a-162">Certifique-se de que a caixa de seleção **tipo de conferência atribuído por padrão** não esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="0014a-162">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="0014a-163">Esta configuração controla se o suplemento de reunião online para o Lync 2013 sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as reuniões agendadas têm a mesma URL de ingresso e informações de áudio.</span><span class="sxs-lookup"><span data-stu-id="0014a-163">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="0014a-164">Em pequenos cenários de colaboração de grupo, ter esse tipo de conferência atribuído funciona bem porque todos têm sua própria conferência atribuída individualmente e a URL de ingresso e as informações de áudio constantes ajudam a facilitar a reunião mais rápida.</span><span class="sxs-lookup"><span data-stu-id="0014a-164">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="0014a-165">No entanto, no cenário de reunião grande, a equipe de suporte de grande reunião agenda as grandes reuniões usando um único conjunto de credenciais de usuário e, em seguida, fornece URLs de ingresso e informações de áudio aos solicitantes da reunião.</span><span class="sxs-lookup"><span data-stu-id="0014a-165">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="0014a-166">Nesse caso, o uso de uma URL diferente para ingressar em cada reunião funciona melhor.</span><span class="sxs-lookup"><span data-stu-id="0014a-166">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="0014a-167">Certifique-se de que a caixa de seleção **admitir usuários anônimos por padrão** não esteja selecionada, a menos que seja necessária.</span><span class="sxs-lookup"><span data-stu-id="0014a-167">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="0014a-168">Essa configuração afeta o tipo de acesso de reunião padrão agendado pelo suplemento reunião online para Lync 2013 quando não estiver usando uma conferência atribuída.</span><span class="sxs-lookup"><span data-stu-id="0014a-168">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="0014a-169">A opção apropriada para essa configuração depende das necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0014a-169">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="0014a-170">Se a maioria das grandes reuniões da sua organização forem reuniões internas, não selecione essa opção.</span><span class="sxs-lookup"><span data-stu-id="0014a-170">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="0014a-171">Se a maioria das reuniões grandes exigir que usuários externos possam participar, selecione essa opção.</span><span class="sxs-lookup"><span data-stu-id="0014a-171">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

