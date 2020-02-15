---
title: 'Lync Server 2013: opções de bypass de mídia global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b6a5f0d7a6a89b30b0ef08f8631b06fb9047616
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="9c383-102">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c383-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c383-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="9c383-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c383-104">Este tópico pressupõe que você já configurou o bypass de mídia para qualquer tronco para um ponto (um gateway PSTN (rede telefônica pública comutada), um IP-PBX ou um SBC (controlador de borda de sessão) em um provedor de serviços de telefonia da Internet) para um site ou serviço específico para que você deseja que a mídia ignore o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="9c383-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="9c383-105">Além de habilitar o bypass de mídia para conexões individuais de tronco associadas a um par, você deve também habilitá-lo globalmente.</span><span class="sxs-lookup"><span data-stu-id="9c383-105">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="9c383-106">As configurações de bypass de mídia global podem especificar que o bypass de mídia sempre é tentado para chamadas para o PSTN, ou que o bypass de mídia seja empregado usando o mapeamento de sub-redes para sites de rede e regiões de rede — semelhante ao que é feito pelo controle de admissão de chamadas, outro recurso de voz avançado.</span><span class="sxs-lookup"><span data-stu-id="9c383-106">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="9c383-107">Quando o bypass de mídia e o controle de admissão de chamada são habilitados, a região de rede, o local de rede e as informações de sub-rede especificadas para o controle de admissão de chamada são usados automaticamente ao determinar se o bypass de mídia deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="9c383-107">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="9c383-108">Isso significa que você não pode especificar que o bypass de mídia sempre seja tentado para chamadas para o PSTN quando o controle de admissão de chamadas estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="9c383-108">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="9c383-109">Este tópico descreve como usar o painel de controle do Lync Server e o Shell de gerenciamento do Lync Server juntos para definir as configurações de bypass de mídia global.</span><span class="sxs-lookup"><span data-stu-id="9c383-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c383-110">Ao usar estas etapas para configurar o bypass de mídia, pressupõe-se que você possui uma boa conectividade entre os clientes e o par do Servidor de Mediação (por exemplo, um gateway PSTN, um IP-PBX, ou um SBC em um provedor de tronco SIP).</span><span class="sxs-lookup"><span data-stu-id="9c383-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="9c383-111">Se houver qualquer limitação de largura de banda no link, o bypass de mídia não poderá ser aplicado na chamada.</span><span class="sxs-lookup"><span data-stu-id="9c383-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="9c383-112">O bypass de mídia não interopera com todos os gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="9c383-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="9c383-113">A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com IP-PBXs da Cisco.</span><span class="sxs-lookup"><span data-stu-id="9c383-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="9c383-114">O bypass de mídia é suportado apenas com produtos e versões listados no programa de interoperabilidade aberta de comunicações <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>unificativas – Lync Server em.</span><span class="sxs-lookup"><span data-stu-id="9c383-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="9c383-115">Próximas etapas: definir as configurações globais do bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="9c383-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="9c383-116">Depois de habilitar o bypass de mídia em quaisquer conexões tronco para um par de sites específicos ou serviços, use o seguinte conteúdo para:</span><span class="sxs-lookup"><span data-stu-id="9c383-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="9c383-117">Habilitar o bypass de mídia sempre, conforme descrito em [Configure Media bypass in Lync Server 2013 para sempre ignorar o servidor de mediação](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="9c383-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="9c383-118">Ou configure o bypass de mídia para usar informações de site e de região, conforme descrito em [Configure Media bypass Global Settings in Lync Server 2013 to use site and Region Information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span><span class="sxs-lookup"><span data-stu-id="9c383-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c383-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="9c383-119">See Also</span></span>


[<span data-ttu-id="9c383-120">Configurar um tronco com bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c383-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="9c383-121">Associar uma sub-rede a um site de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c383-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="9c383-122">Configurar bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c383-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="9c383-123">Bypass de mídia e servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c383-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

