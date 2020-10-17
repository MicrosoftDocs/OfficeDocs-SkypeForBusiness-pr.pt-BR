---
title: 'Lync Server 2013: Configurando troncos'
description: 'Lync Server 2013: Configurando troncos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07d9503cd38419a7145796a6edf8484a14cdeb53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544147"
---
# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="3294a-103">Configurando troncos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-103">Configuring trunks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3294a-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3294a-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3294a-105">Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais dos seguintes pontos para fornecer conectividade de rede telefônica pública comutada (PSTN) para clientes e dispositivos Enterprise Voice em sua organização:</span><span class="sxs-lookup"><span data-stu-id="3294a-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="3294a-106">Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="3294a-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="3294a-107">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="3294a-107">PSTN gateway</span></span>

  - <span data-ttu-id="3294a-108">Central privada de comutação telefônica (PBX)</span><span class="sxs-lookup"><span data-stu-id="3294a-108">Private branch exchange (PBX)</span></span>

<span data-ttu-id="3294a-109">Para obter detalhes, consulte [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="3294a-109">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3294a-110">Antes de começar a configuração de tronco, verifique se a topologia foi criada e se o servidor de mediação e seu par foram configurados e associados uns aos outros.</span><span class="sxs-lookup"><span data-stu-id="3294a-110">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="3294a-111">Para obter detalhes, consulte <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir um gateway no construtor de topologias no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="3294a-111">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3294a-112">Como parte da configuração de tronco, você pode habilitar o recurso de bypass de mídia do Lync Server 2013, que permite que a mídia ignore o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="3294a-112">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="3294a-113">Os troncos podem ser configurados com ou sem o desvio de mídia habilitado, mas recomendamos fortemente que você o habilite.</span><span class="sxs-lookup"><span data-stu-id="3294a-113">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="3294a-114">Para obter detalhes, consulte <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media bypass in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="3294a-114">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3294a-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3294a-115">In This Section</span></span>

  - [<span data-ttu-id="3294a-116">Suporte a vários troncos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-116">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="3294a-117">Roteamento entre troncos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-117">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="3294a-118">Exibir informações de configuração de tronco no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-118">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="3294a-119">Configurar um tronco com bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-119">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="3294a-120">Configurar um tronco sem bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-120">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="3294a-121">Criar um novo conjunto de definições de configuração de tronco no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-121">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="3294a-122">Excluir um conjunto existente de definições de configuração do tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-122">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="3294a-123">Modificar as definições de configuração do tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-123">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="3294a-124">Testar as definições de configuração do tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-124">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="3294a-125">Exibir informações sobre troncos SIP individuais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-125">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3294a-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="3294a-126">See Also</span></span>


[<span data-ttu-id="3294a-127">Definir um gateway no construtor de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-127">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="3294a-128">Planejamento da conectividade PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-128">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="3294a-129">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3294a-129">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

