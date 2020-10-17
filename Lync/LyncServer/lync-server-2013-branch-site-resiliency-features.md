---
title: 'Lync Server 2013: recursos de resiliência de site de filial'
description: 'Lync Server 2013: recursos de resiliência de site de filial.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a498751ce99d0e8e85d6cbe53915c864e64440bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552197"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="243be-103">Recursos de resiliência de site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="243be-103">Branch-site resiliency features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="243be-104">_**Última modificação do tópico:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="243be-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="243be-105">Se você fornecer resiliência de site de filial, se a conexão WAN de um site de filial com um site central falhar ou se o site central estiver inacessível, os seguintes recursos de voz deverão continuar disponíveis:</span><span class="sxs-lookup"><span data-stu-id="243be-105">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="243be-106">Chamadas de rede telefônica pública comutada (PSTN) de entrada e saída</span><span class="sxs-lookup"><span data-stu-id="243be-106">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="243be-107">Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes</span><span class="sxs-lookup"><span data-stu-id="243be-107">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="243be-108">Manipulação de chamada básica, incluindo chamada em espera, recuperação e transferência</span><span class="sxs-lookup"><span data-stu-id="243be-108">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="243be-109">Mensagens instantâneas de dois participantes</span><span class="sxs-lookup"><span data-stu-id="243be-109">Two-party instant messaging</span></span>

  - <span data-ttu-id="243be-110">Encaminhamento de chamadas, toque simultâneo de pontos de extremidade, delegação de chamada e serviços de chamada de equipe, mas somente se o delegante e o representante (por exemplo, um gerente e o administrador do gerente) ou todos os membros da equipe estiverem configurados no mesmo site</span><span class="sxs-lookup"><span data-stu-id="243be-110">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="243be-111">Registros de detalhes da chamada (CDRs)</span><span class="sxs-lookup"><span data-stu-id="243be-111">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="243be-112">Conferência de discagem PSTN com Atendedor Automático de Conferência</span><span class="sxs-lookup"><span data-stu-id="243be-112">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="243be-113">Recursos de caixa postal, se você definir configurações de reencaminhamento de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="243be-113">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="243be-114">(Para obter detalhes, consulte [Branch-site resiliência Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span><span class="sxs-lookup"><span data-stu-id="243be-114">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="243be-115">Autenticação e autorização de usuário</span><span class="sxs-lookup"><span data-stu-id="243be-115">User authentication and authorization</span></span>

<span data-ttu-id="243be-116">Os recursos a seguir estarão disponíveis somente se sua solução de resiliência for uma implantação do Lync Server em escala total no site de filial:</span><span class="sxs-lookup"><span data-stu-id="243be-116">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="243be-117">Conferência de IM, Web e A/V</span><span class="sxs-lookup"><span data-stu-id="243be-117">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="243be-118">Presence e não incomodar (DND)-roteamento baseado (onde as chamadas são impedidas de tocar em extensões com o DND ativado)</span><span class="sxs-lookup"><span data-stu-id="243be-118">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="243be-119">Atualização de configurações de encaminhamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="243be-119">Updating call forwarding settings</span></span>

  - <span data-ttu-id="243be-120">Aplicativo de grupo de resposta e aplicativo de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="243be-120">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="243be-121">Provisionamento de novos telefones e clientes, mas somente se o serviços de domínio do Active Directory estiver presente no site de filial.</span><span class="sxs-lookup"><span data-stu-id="243be-121">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="243be-122">Enhanced 9-1-1 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="243be-122">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="243be-123">Se o E9-1-1 for implantado e o tronco SIP no site central não estiver disponível porque o link WAN está inoperante, o aparelho de filial persistente encaminhará chamadas E9-1-1 para o gateway de filial local.</span><span class="sxs-lookup"><span data-stu-id="243be-123">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="243be-124">Para habilitar esse recurso, as políticas de voz dos usuários do site de filial devem rotear chamadas para o gateway local em caso de falha de WAN.</span><span class="sxs-lookup"><span data-stu-id="243be-124">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="243be-125">SBA (filial persistente) não tem suporte para o XMPP.</span><span class="sxs-lookup"><span data-stu-id="243be-125">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="243be-126">Os usuários hospedados em uma configuração do SBA não poderão enviar mensagens instantâneas ou ver presença com contatos do XMPP.</span><span class="sxs-lookup"><span data-stu-id="243be-126">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

