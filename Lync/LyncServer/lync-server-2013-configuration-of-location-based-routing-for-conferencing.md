---
title: 'Lync Server 2013: configuração do roteamento de Location-Based para conferência'
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
ms.openlocfilehash: bd5ada5e4af1ed4ed43434ddf4d82abc25f4cd5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507798"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="dd789-102">Configuração do roteamento de Location-Based para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd789-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd789-103">_**Última modificação do tópico:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="dd789-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="dd789-104">O aplicativo de conferência de roteamento de Location-Based depende da configuração do Lync Server 2013 Location-Based Routing.</span><span class="sxs-lookup"><span data-stu-id="dd789-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="dd789-105">As principais configurações são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="dd789-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="dd789-106">O local dos participantes que ingressam em uma reunião é determinado com base no seu site de rede.</span><span class="sxs-lookup"><span data-stu-id="dd789-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="dd789-107">Um site de rede e suas sub-redes de rede associadas devem ser definidos no Lync Server para impor o roteamento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="dd789-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="dd789-108">Para impor Location-Based roteamento de reuniões, os participantes do Lync devem estar habilitados para roteamento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="dd789-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="dd789-109">Para impor Location-Based roteamento de pontos de extremidade PSTN que participam de reuniões, o tronco SIP usado para conectar os pontos de extremidade PSTN deve ser configurado para roteamento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="dd789-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="dd789-110">Para obter informações adicionais sobre como implantar e configurar o roteamento de Location-Based do Lync Server 2013, consulte Configurando o [roteamento baseado em local](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="dd789-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="dd789-111">Habilitando o aplicativo de conferência de roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="dd789-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="dd789-112">O aplicativo de conferência de roteamento Location-Based está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="dd789-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="dd789-113">Antes de habilitar esse aplicativo, você precisa determinar a prioridade correta a ser atribuída ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dd789-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="dd789-114">Para determinar essa prioridade, execute o seguinte cmdlet no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="dd789-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

<span data-ttu-id="dd789-115">Neste cmdlet, \<Pool FQDN\> é o pool no qual o aplicativo de conferência de roteamento do Location-Based deve ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="dd789-115">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="dd789-116">Este cmdlet retornará a lista de aplicativos hospedados pelo Lync Server e o valor de prioridade para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="dd789-116">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="dd789-117">O aplicativo de conferência de roteamento Location-Based precisa ter um valor de prioridade maior do que o aplicativo "UdcAgent" e menor do que os aplicativos "defaultrouting", "ExumRouting" e "OutboundRouting".</span><span class="sxs-lookup"><span data-stu-id="dd789-117">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="dd789-118">Recomendamos que você atribua o Location-Based aplicativo de conferência de roteamento um valor de prioridade que seja um ponto maior do que o valor de prioridade do aplicativo "UdcAgent".</span><span class="sxs-lookup"><span data-stu-id="dd789-118">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="dd789-119">Por exemplo, se o aplicativo "UdcAgent" tiver um valor de prioridade de "2", o aplicativo "defaultrouting" tem um valor de prioridade "8", o aplicativo "ExumRouting" tem um valor de prioridade "9" e o aplicativo "OutboundRouting" tem um valor de prioridade "10", então você deve atribuir Location-Based o aplicativo de conferência de roteamento a um valor "3".</span><span class="sxs-lookup"><span data-stu-id="dd789-119">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="dd789-120">Isso colocaria a prioridade dos aplicativos na seguinte ordem: outros aplicativos (prioridades: 0 a 1), "UdcAgent" (prioridade: 2), Location-Based aplicativo de conferência de roteamento (prioridade: 3), outros aplicativos (prioridades: 4 a 8), "roteamento default" (prioridade: 9), "ExumRouting" (prioridade: 10) e "OutboundRouting" (prioridade: 11).</span><span class="sxs-lookup"><span data-stu-id="dd789-120">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="dd789-121">Depois de encontrar o valor de prioridade correto para o aplicativo de conferência de roteamento Location-Based, digite o seguinte cmdlet para cada pool de Front-End ou servidor Standard Edition que hospeda os usuários habilitados para Location-Based roteamento:</span><span class="sxs-lookup"><span data-stu-id="dd789-121">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

<span data-ttu-id="dd789-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="dd789-122">For example:</span></span>

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

<span data-ttu-id="dd789-123">Após usar esse cmdlet, reinicie todos os servidores front-end no pool ou os servidores Standard Edition nos quais o aplicativo de conferência de roteamento Location-Based foi habilitado.</span><span class="sxs-lookup"><span data-stu-id="dd789-123">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dd789-124">Location-Based os enforcementos de roteamento para conferências ou transferências de consultoria não serão impostos até que todos os servidores front-end nos pools aplicáveis ou servidores Standard Edition sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="dd789-124">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="dd789-125">Depois que o aplicativo de conferência de roteamento Location-Based tiver sido habilitado com êxito e todos os servidores do Lync aplicáveis forem reiniciados, todas as conferências organizadas por usuários do Lync habilitados para Location-Based roteamento serão monitoradas para evitar o bypass de chamadas PSTN</span><span class="sxs-lookup"><span data-stu-id="dd789-125">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

