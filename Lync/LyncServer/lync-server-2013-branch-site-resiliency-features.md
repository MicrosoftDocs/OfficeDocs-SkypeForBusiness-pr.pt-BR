---
title: 'Lync Server 2013: Recursos de resiliência do site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e452dc297a79525b587d13aa58ed1e1270d41aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="9cc59-102">Recursos de resiliência do site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cc59-102">Branch-site resiliency features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cc59-103">_**Tópico da última modificação:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="9cc59-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="9cc59-104">Se você fornecer resiliência de site de filial, se a conexão WAN de um site de filial com um site central falhar ou se o site central estiver inacessível, os seguintes recursos de voz deverão continuar disponíveis:</span><span class="sxs-lookup"><span data-stu-id="9cc59-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="9cc59-105">Chamadas de rede de telefonia pública comutada (PSTN) de entrada e saída</span><span class="sxs-lookup"><span data-stu-id="9cc59-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="9cc59-106">Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes</span><span class="sxs-lookup"><span data-stu-id="9cc59-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="9cc59-107">Administração básica de chamadas, incluindo espera, recuperação e transferência de chamadas</span><span class="sxs-lookup"><span data-stu-id="9cc59-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="9cc59-108">Mensagens instantâneas de dois participantes</span><span class="sxs-lookup"><span data-stu-id="9cc59-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="9cc59-109">Encaminhamento de chamadas, toque simultâneo de pontos de extremidade, delegação de chamadas e serviços de chamada de equipe, mas somente se o delegante e o delegado (por exemplo, um gerente e o administrador do gerente) ou todos os membros da equipe estiverem configurados no mesmo site</span><span class="sxs-lookup"><span data-stu-id="9cc59-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="9cc59-110">Registros de detalhes de chamadas (CDRs)</span><span class="sxs-lookup"><span data-stu-id="9cc59-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="9cc59-111">Conferência de discagem PSTN com Atendedor Automático de Conferência</span><span class="sxs-lookup"><span data-stu-id="9cc59-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="9cc59-112">Recursos de caixa postal, se forem configuradas definições de reroteamento de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="9cc59-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="9cc59-113">(Para obter detalhes, consulte [requisitos de resiliência de site de filial para o Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span><span class="sxs-lookup"><span data-stu-id="9cc59-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="9cc59-114">Autenticação e autorização de usuário</span><span class="sxs-lookup"><span data-stu-id="9cc59-114">User authentication and authorization</span></span>

<span data-ttu-id="9cc59-115">Os recursos a seguir estarão disponíveis somente se a sua solução de resiliência for uma implantação do Lync Server em escala total no site da filial:</span><span class="sxs-lookup"><span data-stu-id="9cc59-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="9cc59-116">Conferências de IM, webconferências e conferências de A/V</span><span class="sxs-lookup"><span data-stu-id="9cc59-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="9cc59-117">Presença e roteamento baseado em Não Incomodar (DND), onde as chamadas não tocam em extensões com o DND ativado</span><span class="sxs-lookup"><span data-stu-id="9cc59-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="9cc59-118">Atualização de configurações de encaminhamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="9cc59-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="9cc59-119">Aplicativo grupo de resposta e aplicativo de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="9cc59-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="9cc59-120">Provisionar novos telefones e clientes, mas somente se os serviços de domínio Active Directory estiverem presentes no site de filial.</span><span class="sxs-lookup"><span data-stu-id="9cc59-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="9cc59-121">9-1-1 Avançado (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="9cc59-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="9cc59-122">Se o E9-1-1 estiver implantado e o tronco SIP no site central não estiver disponível porque o link de WAN está indisponível, então o aparelho de ramificação sobreviventes roteará chamadas E9-1-1 para o gateway de filial local.</span><span class="sxs-lookup"><span data-stu-id="9cc59-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="9cc59-123">Para habilitar este recurso, as políticas de voz dos usuários do site de filial devem rotear chamadas para o gateway local, em caso da falha da WAN.</span><span class="sxs-lookup"><span data-stu-id="9cc59-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9cc59-124">O SBA (aparelho de filial persistente) não tem suporte no XMPP.</span><span class="sxs-lookup"><span data-stu-id="9cc59-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="9cc59-125">Os usuários hospedados em uma configuração do SBA não poderão enviar mensagens de chat nem ver a presença com os contatos do XMPP.</span><span class="sxs-lookup"><span data-stu-id="9cc59-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

