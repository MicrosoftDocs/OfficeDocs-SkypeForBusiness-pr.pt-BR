---
title: 'Lync Server 2013: cmdlets do servidor de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server cmdlets
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415635(v=OCS.15)
ms:contentKeyID: 48183534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60081dc4d56c65e3cbef29a9231f855578d07054
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="62f8e-102">Cmdlets do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62f8e-102">Edge Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62f8e-103">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="62f8e-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="62f8e-104">Os servidores de borda fornecem uma maneira de estender os recursos do Microsoft Lync Server 2013 para pessoas que não estão conectados à sua rede interna.</span><span class="sxs-lookup"><span data-stu-id="62f8e-104">Edge Servers provide a way for you to extend the capabilities of Microsoft Lync Server 2013 to people who are not logged on to your internal network.</span></span> <span data-ttu-id="62f8e-105">Por exemplo, se você tiver usuários remotos – usuários autenticados que fazem logon no Lync Server 2013 pela Internet, e não através da rede interna, será necessário configurar um servidor de borda que execute o serviço de borda de acesso do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62f8e-105">For example, if you have remote users -- authenticated users who log on to Lync Server 2013 over the Internet rather than through the internal network -- you will need to set up an Edge Server that runs the Lync Server Access Edge service.</span></span> <span data-ttu-id="62f8e-106">Além disso, os servidores de borda são necessários se você quiser estabelecer uma federação com outra organização ou se quiser dar aos usuários o direito de se comunicar com pessoas que têm contas com um serviço de mensagens instantâneas\!públicos, como Yahoo, AOL ou MSN.</span><span class="sxs-lookup"><span data-stu-id="62f8e-106">Additionally, Edge Servers are required if you want to establish federation with another organization or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN.</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="62f8e-107">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="62f8e-107">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="62f8e-108">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="62f8e-108">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="62f8e-109">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="62f8e-109">Messenger until the service shut down date.</span></span> <span data-ttu-id="62f8e-110">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="62f8e-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="62f8e-111">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="62f8e-111">has been announced.</span></span> <span data-ttu-id="62f8e-112">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="62f8e-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="62f8e-113">O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="62f8e-113">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="62f8e-114">Instantânea.</span><span class="sxs-lookup"><span data-stu-id="62f8e-114">Messenger.</span></span> <span data-ttu-id="62f8e-115">A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</span><span class="sxs-lookup"><span data-stu-id="62f8e-115">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="62f8e-116">Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="62f8e-116">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="62f8e-117">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="62f8e-117">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="62f8e-118">A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</span><span class="sxs-lookup"><span data-stu-id="62f8e-118">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a><span data-ttu-id="62f8e-119">Cmdlets do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="62f8e-119">Edge Server Cmdlets</span></span>

<span data-ttu-id="62f8e-120">A lista a seguir contém os cmdlets diretamente relacionados ao gerenciamento dos Servidores de borda:</span><span class="sxs-lookup"><span data-stu-id="62f8e-120">The following is a list of cmdlets that relate directly to managing Edge Servers:</span></span>

<span data-ttu-id="62f8e-121">**Servidor de borda**</span><span class="sxs-lookup"><span data-stu-id="62f8e-121">**Edge Server**</span></span>

  - <span></span>  
    <span data-ttu-id="62f8e-122">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="62f8e-122">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="62f8e-123">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="62f8e-123">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="62f8e-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="62f8e-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="62f8e-125">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="62f8e-125">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="62f8e-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="62f8e-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="62f8e-127">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="62f8e-127">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="62f8e-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="62f8e-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="62f8e-129">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="62f8e-129">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62f8e-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="62f8e-130">See Also</span></span>


[<span data-ttu-id="62f8e-131">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="62f8e-131">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

