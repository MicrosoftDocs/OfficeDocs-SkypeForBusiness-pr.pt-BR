---
title: 'Lync Server 2013: Get-CsService para gerenciamento de catálogo de endereços'
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
ms.openlocfilehash: c39520a54ae664a1eddf241cbf1d8d27fe858510
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="72827-102">Get-CsService para gerenciamento de catálogo de endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72827-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72827-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="72827-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="72827-p101">Quem pode executar este cmdlet: por padrão, os membros dos grupos a seguir estão autorizados a executar o cmdlet Get-CsService localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para retornar uma lista de todas as funções RBAC (controle de acesso baseado em função) que receberam a atribuição desse cmdlet (incluindo qualquer função RBAC personalizada criada por você), execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="72827-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="72827-106">Get-CsService é útil para recuperar e exibir a configuração atual de seus serviços Web definidos pela infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="72827-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="72827-107">Ao definir o FQDN (nome de domínio totalmente qualificado) do pool e o parâmetro WebServer, o cmdlet retorna os serviços baseados na Web oferecidos pelo servidor, incluindo o manipulador de catálogo de endereços e URIs de expansão de lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="72827-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="72827-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="72827-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="72827-109">Esse cmdlet retorna o seguinte:</span><span class="sxs-lookup"><span data-stu-id="72827-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="72827-110">Identity: webserver:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="72827-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="72827-111">Filestore: filestore:dc01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="72827-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="72827-112">Userserver: userserver:pool01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="72827-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="72827-113">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="72827-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="72827-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="72827-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="72827-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="72827-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="72827-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="72827-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="72827-117">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="72827-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="72827-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="72827-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="72827-119">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="72827-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="72827-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="72827-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="72827-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="72827-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="72827-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="72827-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="72827-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="72827-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="72827-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="72827-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="72827-125">LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="72827-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="72827-126">ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="72827-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="72827-127">ABHandlerExternalUri :https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="72827-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="72827-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="72827-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="72827-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="72827-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="72827-130">CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="72827-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="72827-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="72827-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="72827-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="72827-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="72827-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="72827-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="72827-134">CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="72827-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="72827-135">DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="72827-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="72827-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="72827-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="72827-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="72827-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="72827-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="72827-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="72827-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="72827-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="72827-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="72827-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="72827-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="72827-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="72827-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="72827-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="72827-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="72827-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="72827-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="72827-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="72827-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="72827-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="72827-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="72827-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="72827-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="72827-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="72827-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="72827-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="72827-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="72827-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="72827-150">DependentServiceList: {registrar:pool01. contoso. net, ConferencingServer:pool01. contoso. net}</span><span class="sxs-lookup"><span data-stu-id="72827-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="72827-151">ServiceId: 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="72827-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="72827-152">SiteId: site: Redmond</span><span class="sxs-lookup"><span data-stu-id="72827-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="72827-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="72827-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="72827-154">Versão: 5</span><span class="sxs-lookup"><span data-stu-id="72827-154">Version : 5</span></span>

<span data-ttu-id="72827-155">Função: WebServer</span><span class="sxs-lookup"><span data-stu-id="72827-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="72827-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="72827-156">See Also</span></span>


[<span data-ttu-id="72827-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="72827-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

