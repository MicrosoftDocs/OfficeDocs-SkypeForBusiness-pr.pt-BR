---
title: Configurando Autodiscover para mobilidade com implantações híbridas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1865cab188bace472996db6207de62ce8498976
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="2fea3-102">Configurando Autodiscover no Lync Server 2013 para mobilidade com implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="2fea3-102">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fea3-103">_**Tópico da última modificação:** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="2fea3-103">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="2fea3-104">Implantações híbridas são configurações que usam o serviço de nuvem do Microsoft Lync Online e a implantação local.</span><span class="sxs-lookup"><span data-stu-id="2fea3-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="2fea3-105">Nesse tipo de configuração, o serviço de descoberta automática deve ser capaz de localizar onde o usuário está realmente localizado.</span><span class="sxs-lookup"><span data-stu-id="2fea3-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="2fea3-106">Isso é dizer, o recurso de descoberta automática ajuda a localizar a conta de usuário e onde o servidor que hospeda a conta do usuário é, independentemente de estar na implantação local ou na implantação do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2fea3-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="2fea3-107">Por exemplo, se a conta de um usuário estiver hospedada em um servidor no Lync Online, a tentativa de localizar o usuário acontecerá da seguinte maneira, em um processo conhecido como *descoberta*:</span><span class="sxs-lookup"><span data-stu-id="2fea3-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="2fea3-108">O usuário inicia uma tentativa de conexão com a implantação local, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="2fea3-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="2fea3-109">A tentativa é enviada para lyncdiscover.contoso.com, o nome DNS associado ao serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="2fea3-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="2fea3-110">A descoberta automática se refere ao pool de registradores presumidos na implantação do contoso.com local e recebe informações sobre o servidor primário real do usuário hospedado no Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2fea3-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="2fea3-111">A descoberta automática envia ao usuário uma referência para o serviço de descoberta automática do **Lync.com** online.</span><span class="sxs-lookup"><span data-stu-id="2fea3-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="2fea3-112">O usuário inicia uma tentativa de conexão com o serviço de descoberta automática do lync.com Online e consegue localizar a conta do usuário e o servidor primário do usuário.</span><span class="sxs-lookup"><span data-stu-id="2fea3-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="2fea3-113">Para permitir que os clientes móveis descubram a implantação em que o servidor primário do usuário está localizado, você deve configurar o serviço de descoberta automática com um novo Uniform Resource Locator (URL).</span><span class="sxs-lookup"><span data-stu-id="2fea3-113">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="2fea3-114">Siga este procedimento para configurar o serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="2fea3-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="2fea3-115">Configurando a descoberta automática para implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="2fea3-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="2fea3-116">Use Get-CsHostingProvider para recuperar o valor da ProxyFQDN de atributo.</span><span class="sxs-lookup"><span data-stu-id="2fea3-116">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="2fea3-117">No Shell de gerenciamento do Lync Server, digite</span><span class="sxs-lookup"><span data-stu-id="2fea3-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="2fea3-118">Onde \[a\] identidade é substituída pelo nome de domínio do espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="2fea3-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2fea3-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="2fea3-119">See Also</span></span>


<span data-ttu-id="2fea3-120">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fea3-120">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="2fea3-121">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2fea3-121">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

