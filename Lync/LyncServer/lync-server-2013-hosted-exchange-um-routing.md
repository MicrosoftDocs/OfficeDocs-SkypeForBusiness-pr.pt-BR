---
title: 'Lync Server 2013: roteamento do Exchange UM hospedado'
description: 'Lync Server 2013: roteamento do Exchange UM hospedado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72fbdee5550ae53d5ff5e7513ea384cedad62c5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550127"
---
# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="f55cb-103">Roteamento do Exchange UM hospedado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f55cb-103">Hosted Exchange UM routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f55cb-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f55cb-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f55cb-105">O aplicativo de roteamento de UM do Exchange é executado no servidor front-end para encaminhar chamadas para uma implantação local da UM (Unificação de mensagens) do Microsoft Exchange Server ou para o serviço UM do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="f55cb-105">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="f55cb-106">O aplicativo ExUM Routing</span><span class="sxs-lookup"><span data-stu-id="f55cb-106">The ExUM Routing Application</span></span>

<span data-ttu-id="f55cb-107">O aplicativo de roteamento de UM do Lync Server 2013 do Exchange usa informações de configurações de conta de usuário e de parâmetros de política de caixa postal hospedada para determinar como rotear chamadas para mensagens de voz hospedadas, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="f55cb-107">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="f55cb-108">**Exemplo de implantação mista de encaminhamento do UM do Exchange**</span><span class="sxs-lookup"><span data-stu-id="f55cb-108">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="f55cb-109">![Implantação de UM do Exchange do Lync Server local](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Implantação de UM do Exchange do Lync Server local")</span><span class="sxs-lookup"><span data-stu-id="f55cb-109">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="f55cb-110">O roteamento da UM do Exchange pode ser configurado para rotear chamadas para usuários habilitados para um do Exchange local, para usuários habilitados para um do Exchange hospedado ou para uma combinação dos dois.</span><span class="sxs-lookup"><span data-stu-id="f55cb-110">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="f55cb-111">Por exemplo, suponha que a caixa de correio da Roy e o serviço UM do Exchange estejam hospedados em uma implantação local do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f55cb-111">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="f55cb-112">As informações de endereço de proxy da conta de usuário Roy fornecem as informações que o aplicativo de roteamento ExUM usa para rotear chamadas para um servidor de UM do Exchange local.</span><span class="sxs-lookup"><span data-stu-id="f55cb-112">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="f55cb-113">A caixa de correio de Alice e o serviço UM do Exchange estão localizados em um data center do provedor de serviço do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="f55cb-113">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="f55cb-114">O roteamento de suas chamadas de UM do Exchange é configurado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f55cb-114">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="f55cb-115">Os valores definidos no atributo msExchUCVoiceMailSettings de conta de usuário de Alice solicitam que o aplicativo ExUM Routing verifique os detalhes de encaminhamento em uma política de caixa postal hospedada.</span><span class="sxs-lookup"><span data-stu-id="f55cb-115">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f55cb-116">O valor do atributo msExchUCVoiceMailSettings pode ser definido pelo provedor de serviços do Exchange ou pelo administrador do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f55cb-116">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="f55cb-117">No exemplo mostrado no diagrama anterior, o valor (CsHostedVoiceMail = 1) foi definido pelo administrador do Lync Server 2013 para habilitar a caixa postal hospedada para Ana Maria.</span><span class="sxs-lookup"><span data-stu-id="f55cb-117">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="f55cb-118">Para obter detalhes sobre esse atributo, consulte <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange User Management in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f55cb-118">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="f55cb-119">A política de caixa postal hospedada atribuída à conta de usuário de Alice fornece os detalhes de encaminhamento:</span><span class="sxs-lookup"><span data-stu-id="f55cb-119">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="f55cb-120">O destino é o provedor de serviços UM UM do Exchange hospedado (ls. ExUm. \<hostedExchangeServer\> . com neste exemplo).</span><span class="sxs-lookup"><span data-stu-id="f55cb-120">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="f55cb-121">As organizações são identificadas pelas IDs de locatário, que são os FQDNs de roteamento para mensagens SIP para locatários do Exchange Server que estão localizados na ls. ExUm. \<hostedExchangeServer\> . com (corp.contoso.com e corp.litwareinc.com neste exemplo).</span><span class="sxs-lookup"><span data-stu-id="f55cb-121">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f55cb-122">O FQDN para Exchange Online é exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f55cb-122">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="f55cb-123">Para obter detalhes, consulte [Hosted voice mail Policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f55cb-123">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f55cb-124">Se o atributo msExchUCVoiceMailSettings e as configurações de endereço proxy do UM estiverem presentes em uma conta de usuário, o atributo msExchUCVoiceMailSettings prevalecerá.</span><span class="sxs-lookup"><span data-stu-id="f55cb-124">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

