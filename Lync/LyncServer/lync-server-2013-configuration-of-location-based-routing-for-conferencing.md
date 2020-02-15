---
title: 'Lync Server 2013: configuração do roteamento baseado em local para conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a959addbcd98e04d336ba380676399dbff2f586b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f35dc-102">Configuração do roteamento baseado em local para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f35dc-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f35dc-103">_**Última modificação do tópico:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="f35dc-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="f35dc-104">O aplicativo de conferência de roteamento baseado em local depende da configuração do roteamento baseado em local do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f35dc-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="f35dc-105">As principais configurações são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="f35dc-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="f35dc-106">O local dos participantes que ingressam em uma reunião é determinado com base no seu site de rede.</span><span class="sxs-lookup"><span data-stu-id="f35dc-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="f35dc-107">Um site de rede e suas sub-redes de rede associadas devem ser definidos no Lync Server para impor o roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="f35dc-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="f35dc-108">Para impor o roteamento baseado em local de reuniões, os participantes do Lync devem estar habilitados para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="f35dc-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f35dc-109">Para impor o roteamento baseado em local de pontos de extremidade PSTN que participam de reuniões, o tronco SIP usado para conectar os pontos de extremidade PSTN deve ser configurado para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="f35dc-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="f35dc-110">Para obter informações adicionais sobre como implantar e configurar o roteamento baseado em local do Lync Server 2013, consulte Configurando o [roteamento baseado em local](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f35dc-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="f35dc-111">Habilitando o aplicativo de conferência de roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="f35dc-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="f35dc-112">O aplicativo de conferência de roteamento baseado em local está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="f35dc-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="f35dc-113">Antes de habilitar esse aplicativo, você precisa determinar a prioridade correta a ser atribuída ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f35dc-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="f35dc-114">Para determinar essa prioridade, execute o seguinte cmdlet no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="f35dc-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="f35dc-115">Get-CsServerApplication-Identity Service: registrar:\<FQDN do pool\></span><span class="sxs-lookup"><span data-stu-id="f35dc-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="f35dc-116">Neste cmdlet, \<o FQDN\> do pool é o pool no qual o aplicativo de conferência de roteamento baseado em local deve ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="f35dc-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="f35dc-117">Este cmdlet retornará a lista de aplicativos hospedados pelo Lync Server e o valor de prioridade para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="f35dc-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="f35dc-118">O aplicativo de conferência de roteamento baseado em local precisa ser atribuído a um valor de prioridade maior do que o aplicativo "UdcAgent" e menor do que os aplicativos "defaultrouting", "ExumRouting" e "OutboundRouting".</span><span class="sxs-lookup"><span data-stu-id="f35dc-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="f35dc-119">Recomendamos que você atribua o aplicativo de conferência de roteamento baseado em local um valor de prioridade que seja um ponto maior do que o valor de prioridade do aplicativo "UdcAgent".</span><span class="sxs-lookup"><span data-stu-id="f35dc-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="f35dc-120">Por exemplo, se o aplicativo "UdcAgent" tiver um valor de prioridade "2", o aplicativo "defaultrouting" tem um valor de prioridade "8", o aplicativo "ExumRouting" tem um valor de prioridade "9" e o aplicativo "OutboundRouting" tem um valor de prioridade "10" e, em seguida, Você deve atribuir o aplicativo de conferência de roteamento baseado em local com um valor de prioridade "3".</span><span class="sxs-lookup"><span data-stu-id="f35dc-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="f35dc-121">Isso colocaria a prioridade dos aplicativos na seguinte ordem: outros aplicativos (prioridades: 0 a 1), "UdcAgent" (prioridade: 2), aplicativo de conferência de roteamento baseado em local (prioridade: 3), outros aplicativos (prioridades: 4 a 8), " Defaultrouting "(prioridade: 9)," ExumRouting "(prioridade: 10) e" OutboundRouting "(prioridade: 11).</span><span class="sxs-lookup"><span data-stu-id="f35dc-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="f35dc-122">Depois de encontrar o valor de prioridade correto para o aplicativo de conferência de roteamento baseado em local, digite o cmdlet a seguir para cada pool de front-end ou servidor Standard Edition que hospeda os usuários habilitados para roteamento baseado em local:</span><span class="sxs-lookup"><span data-stu-id="f35dc-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="f35dc-123">New-CsServerApplication-Identity Service: registrar:\<pool FQDN\>/LBRouting-priority \<Application Priority\> Enabled $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="f35dc-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="f35dc-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f35dc-124">For example:</span></span>

<span data-ttu-id="f35dc-125">New-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3 Enabled $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="f35dc-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="f35dc-126">Após usar esse cmdlet, reinicie todos os servidores front-end no pool ou os servidores Standard Edition onde o aplicativo de conferência de roteamento baseado na localização tenha sido habilitado.</span><span class="sxs-lookup"><span data-stu-id="f35dc-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f35dc-127">Os enforces de roteamento baseado em local para conferências ou transferências de consultoria não serão impostos até que todos os servidores front-end nos pools aplicáveis ou servidores Standard Edition sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="f35dc-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="f35dc-128">Depois que o aplicativo de conferência de roteamento baseado no local tiver sido habilitado com êxito e todos os servidores do Lync aplicáveis forem reiniciados, todas as conferências organizadas por usuários do Lync habilitados para roteamento baseado em local serão monitoradas para evitar o bypass de PSTN</span><span class="sxs-lookup"><span data-stu-id="f35dc-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

