---
title: 'Lync Server 2013: Configurando a descoberta automática para implantações híbridas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6015603d2c8c151cbe9d9b76410e51708f3ba9e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="cf34d-102">Configurando a descoberta automática no Lync Server 2013 para implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="cf34d-102">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf34d-103">_**Última modificação do tópico:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="cf34d-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="cf34d-104">As implantações híbridas são configurações que usam o serviço de nuvem do Microsoft Lync Online e a implantação no local.</span><span class="sxs-lookup"><span data-stu-id="cf34d-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="cf34d-105">Nesse tipo de configuração, o serviço de descoberta automática deve ser capaz de localizar onde o usuário está realmente localizado.</span><span class="sxs-lookup"><span data-stu-id="cf34d-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="cf34d-106">Isso é dizer, a descoberta automática ajuda a localizar a conta de usuário e onde o servidor que hospeda a conta do usuário é, independentemente de se ele estiver na implantação local ou na implantação do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="cf34d-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="cf34d-107">Por exemplo, se a conta de um usuário estiver hospedada em um servidor no Lync Online, a tentativa de localizar o usuário acontecerá da seguinte maneira, em um processo conhecido como *descoberta*:</span><span class="sxs-lookup"><span data-stu-id="cf34d-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="cf34d-108">O usuário inicia uma tentativa de conexão com a implantação local, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="cf34d-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="cf34d-109">A tentativa é enviada a lyncdiscover.contoso.com, o nome de DNS associado ao serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="cf34d-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="cf34d-110">A descoberta automática se refere ao pool de registradores assumido na implantação local do contoso.com e recebe informações sobre o servidor local real do usuário hospedado no Lync Online.</span><span class="sxs-lookup"><span data-stu-id="cf34d-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="cf34d-111">A descoberta automática envia ao usuário uma referência do serviço online de descoberta automática do **lync.com**.</span><span class="sxs-lookup"><span data-stu-id="cf34d-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="cf34d-112">O usuário inicia uma tentativa de conexão com o serviço online de descoberta automática do lync.com e pode localizar a conta do usuário e o servidor que o está hospedando.</span><span class="sxs-lookup"><span data-stu-id="cf34d-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="cf34d-113">Para permitir que os clientes descubram a implantação onde o servidor local do usuário está localizado, você deve configurar o serviço de descoberta automática com um novo Uniform Resource Locator (URL).</span><span class="sxs-lookup"><span data-stu-id="cf34d-113">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="cf34d-114">Para configurar o serviço de descoberta automática, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cf34d-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="cf34d-115">Configurando a descoberta automática em implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="cf34d-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="cf34d-116">No tópico, [requisitos de serviço de descoberta automática para o Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), use Get-CsHostingProvider para recuperar o valor do atributo ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="cf34d-116">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="cf34d-117">No Shell de gerenciamento do Lync Server, digite</span><span class="sxs-lookup"><span data-stu-id="cf34d-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="cf34d-118">Onde \[Identity\] é substituído pelo nome de domínio do espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="cf34d-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cf34d-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="cf34d-119">See Also</span></span>


[<span data-ttu-id="cf34d-120">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="cf34d-120">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="cf34d-121">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="cf34d-121">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

