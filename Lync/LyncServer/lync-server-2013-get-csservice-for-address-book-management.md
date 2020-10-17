---
title: 'Lync Server 2013: Get-CsService para gerenciamento de catálogo de endereços'
description: 'Lync Server 2013: Get-CsService para gerenciamento de catálogo de endereços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e46173429988d87022c13fab33e3778279dd0e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554647"
---
# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="e2308-103">Get-CsService para gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2308-103">Get-CsService for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2308-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e2308-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e2308-p101">Quem pode executar este cmdlet: por padrão, os membros dos grupos a seguir estão autorizados a executar o cmdlet Get-CsService localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para retornar uma lista de todas as funções RBAC (controle de acesso baseado em função) que receberam a atribuição desse cmdlet (incluindo qualquer função RBAC personalizada criada por você), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e2308-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="e2308-107">Get-CsService é importante recuperar e exibir a configuração atual de seus serviços Web definidos pela infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="e2308-107">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="e2308-108">Ao definir o FQDN (nome de domínio totalmente qualificado) do pool e o parâmetro WebServer, o cmdlet retorna os serviços baseados na Web oferecidos pelo servidor, incluindo o manipulador de catálogo de endereços e URIs de expansão de lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="e2308-108">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="e2308-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e2308-109">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="e2308-110">Esse cmdlet retorna o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e2308-110">This cmdlet returns the following:</span></span>

<span data-ttu-id="e2308-111">Identity: webserver:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="e2308-111">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="e2308-112">Filestore: filestore:dc01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="e2308-112">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="e2308-113">Userserver: userserver:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="e2308-113">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="e2308-114">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="e2308-114">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="e2308-115">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="e2308-115">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="e2308-116">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="e2308-116">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="e2308-117">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="e2308-117">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="e2308-118">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="e2308-118">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="e2308-119">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="e2308-119">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="e2308-120">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="e2308-120">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="e2308-121">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="e2308-121">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="e2308-122">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="e2308-122">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="e2308-123">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="e2308-123">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="e2308-124">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="e2308-124">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="e2308-125">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="e2308-125">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="e2308-126">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="e2308-126">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="e2308-127">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="e2308-127">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="e2308-128">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="e2308-128">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="e2308-129">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="e2308-129">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="e2308-130">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="e2308-130">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="e2308-131">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="e2308-131">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="e2308-132">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="e2308-132">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="e2308-133">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="e2308-133">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="e2308-134">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="e2308-134">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="e2308-135">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="e2308-135">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="e2308-136">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="e2308-136">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="e2308-137">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="e2308-137">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="e2308-138">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="e2308-138">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="e2308-139">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="e2308-139">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="e2308-140">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="e2308-140">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="e2308-141">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="e2308-141">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="e2308-142">MeetExternalUri : https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="e2308-142">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="e2308-143">DialinExternalUri : https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="e2308-143">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="e2308-144">CscpInternalUri : https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="e2308-144">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="e2308-145">ReachExternalUri : https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="e2308-145">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="e2308-146">ReachInternalUri : https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="e2308-146">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="e2308-147">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="e2308-147">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="e2308-148">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="e2308-148">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="e2308-149">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2308-149">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="e2308-150">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e2308-150">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="e2308-151">DependentServiceList: {registrar:pool01. contoso. net, ConferencingServer:pool01. contoso. net}</span><span class="sxs-lookup"><span data-stu-id="e2308-151">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="e2308-152">ServiceId: 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="e2308-152">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="e2308-153">SiteId: site: Redmond</span><span class="sxs-lookup"><span data-stu-id="e2308-153">SiteId : Site:Redmond</span></span>

<span data-ttu-id="e2308-154">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e2308-154">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="e2308-155">Versão: 5</span><span class="sxs-lookup"><span data-stu-id="e2308-155">Version : 5</span></span>

<span data-ttu-id="e2308-156">Função: WebServer</span><span class="sxs-lookup"><span data-stu-id="e2308-156">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e2308-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="e2308-157">See Also</span></span>


[<span data-ttu-id="e2308-158">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="e2308-158">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

