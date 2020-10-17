---
title: 'Lync Server 2013: configurar o 9-1-1 avançado'
description: 'Lync Server 2013: configurar o 9-1-1 avançado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7a2a9ed10e7f29f53a4dfff6dff926ded18d38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553327"
---
# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="ce0b7-103">Configurar o 9-1-1 avançado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0b7-103">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce0b7-104">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="ce0b7-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="ce0b7-p101">O 9-1-1 Avançado (E9-1-1) é um recurso de notificação de emergência que associa o número de telefone de quem está ligando a um endereço cívico ou de uma rua. Usando essas informações, o PSAP (Ponto de Atendimento de Segurança Pública) consegue expedir imediatamente os serviços de emergência para o chamador com problemas.</span><span class="sxs-lookup"><span data-stu-id="ce0b7-p101">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address. Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="ce0b7-107">Para oferecer suporte ao E9-1-1, o Lync Server 2013 deve ser capaz de associar corretamente um local a um cliente e garantir que essas informações sejam usadas para rotear a chamada de emergência para o PSAP mais próximo.</span><span class="sxs-lookup"><span data-stu-id="ce0b7-107">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="ce0b7-108">Para obter detalhes sobre o planejamento de uma implantação do E9-1-1, consulte [Planning for Emergency Services (E9-1-1) no Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="ce0b7-108">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ce0b7-109">O Lync Server 2013 suporta apenas E9-1-1 nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="ce0b7-109">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="ce0b7-110">Para implantar o E9-1-1, você precisará configurar uma conexão de SIP com um provedor de serviços de E9-1-1 qualificado ou implantar um gateway de ELIN (número de identificação de local de emergência) em um provedor de serviços de E9-1-1 com uma PSTN (Rede Telefônica Pública Comutada).</span><span class="sxs-lookup"><span data-stu-id="ce0b7-110">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="ce0b7-111">Para obter detalhes, consulte <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">enhanced 9-1-1 (E9-1-1) e servidor de mediação no Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ce0b7-111">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="ce0b7-112">Para obter detalhes sobre a configuração de conexões de tronco, consulte <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">configurar um tronco com bypass de mídia no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ce0b7-112">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ce0b7-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ce0b7-113">In This Section</span></span>

  - [<span data-ttu-id="ce0b7-114">Configurar uma rota de voz do E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0b7-114">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="ce0b7-115">Criar políticas de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0b7-115">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="ce0b7-116">Configurar as informações do site para o E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0b7-116">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="ce0b7-117">Configurar o banco de dados de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0b7-117">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="ce0b7-118">Configurar recursos avançados do E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0b7-118">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

