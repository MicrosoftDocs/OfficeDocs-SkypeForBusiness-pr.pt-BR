---
title: Configurando a descoberta automática para mobilidade com implantações híbridas
description: Configurando a descoberta automática para mobilidade com implantações híbridas.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a66f0045ec1fce65b8e21b6a6f4494b96c93912
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562457"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="09f44-103">Configurando a descoberta automática no Lync Server 2013 para mobilidade com implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="09f44-103">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09f44-104">_**Última modificação do tópico:** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="09f44-104">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="09f44-105">As implantações híbridas são configurações que usam o serviço de nuvem do Microsoft Lync Online e a implantação no local.</span><span class="sxs-lookup"><span data-stu-id="09f44-105">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="09f44-106">Nesse tipo de configuração, o serviço de descoberta automática deve ser capaz de localizar onde o usuário está realmente localizado.</span><span class="sxs-lookup"><span data-stu-id="09f44-106">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="09f44-107">Isso é dizer, a descoberta automática ajuda a localizar a conta de usuário e onde o servidor que hospeda a conta do usuário é, independentemente de se ele estiver na implantação local ou na implantação do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="09f44-107">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="09f44-108">Por exemplo, se a conta de um usuário estiver hospedada em um servidor no Lync Online, a tentativa de localizar o usuário acontecerá da seguinte maneira, em um processo conhecido como *descoberta*:</span><span class="sxs-lookup"><span data-stu-id="09f44-108">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="09f44-109">O usuário inicia uma tentativa de conexão com a implantação local, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="09f44-109">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="09f44-110">A tentativa é enviada a lyncdiscover.contoso.com, o nome de DNS associado ao serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="09f44-110">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="09f44-111">A descoberta automática se refere ao pool de registradores assumido na implantação local do contoso.com e recebe informações sobre o servidor local real do usuário hospedado no Lync Online.</span><span class="sxs-lookup"><span data-stu-id="09f44-111">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="09f44-112">A descoberta automática envia ao usuário uma referência do serviço online de descoberta automática do **lync.com**.</span><span class="sxs-lookup"><span data-stu-id="09f44-112">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="09f44-113">O usuário inicia uma tentativa de conexão com o serviço online de descoberta automática do lync.com e pode localizar a conta do usuário e o servidor que o está hospedando.</span><span class="sxs-lookup"><span data-stu-id="09f44-113">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="09f44-p103">Para permitir que os clientes móveis descubram a implantação em que o servidor que hospeda o usuário está localizado, é necessário configurar o serviço de descoberta automática com uma nova URL. Para configurar o serviço de descoberta automática, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="09f44-p103">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL). Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="09f44-116">Configurando a descoberta automática em implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="09f44-116">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="09f44-117">Você usa Get-CsHostingProvider para recuperar o valor do atributo ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="09f44-117">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="09f44-118">No Shell de gerenciamento do Lync Server, digite</span><span class="sxs-lookup"><span data-stu-id="09f44-118">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="09f44-119">Onde \[ Identity \] é substituído pelo nome de domínio do espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="09f44-119">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="09f44-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="09f44-120">See Also</span></span>


<span data-ttu-id="09f44-121">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09f44-121">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="09f44-122">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="09f44-122">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

