---
title: 'Lync Server 2013: requisitos de resiliência de site de filial'
description: 'Lync Server 2013: requisitos de resiliência do site de filial.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef05917fb53d1333895236e849cb54596cc41947
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555077"
---
# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="283fe-103">Requisitos de resiliência de site de filial para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="283fe-103">Branch-site resiliency requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="283fe-104">_**Última modificação do tópico:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="283fe-104">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="283fe-105">Este tópico ajudará a você preparar usuários para resiliência de site de filial e persistência da caixa postal, e também especifica os requisitos de hardware e software importantes.
</span><span class="sxs-lookup"><span data-stu-id="283fe-105">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="283fe-106">Preparação de usuários da filial para resiliência de site de filial</span><span class="sxs-lookup"><span data-stu-id="283fe-106">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="283fe-107">Prepare os usuários para resiliência de site de filial definindo seu pool de registradores como o aparelho de filial persistente (SBA) ou servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="283fe-107">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="283fe-108">Atribuições do registrador avançado para usuários da filial</span><span class="sxs-lookup"><span data-stu-id="283fe-108">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="283fe-109">Independentemente da solução de resiliência de site de filial que você escolher, será necessário atribuir um registrador principal a cada usuário.</span><span class="sxs-lookup"><span data-stu-id="283fe-109">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="283fe-110">Os usuários do site de filial devem sempre se registrar no site de filial, independentemente de o registrador residir no aparelho de filial persistente, no servidor de filial persistente ou no servidor autônomo do Lync Server 2013 Standard ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="283fe-110">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="283fe-111">Um registro de recurso de serviço (SRV) de sistema de nome de domínio (DNS) é necessário para que o cliente possa descobrir seu pool de Registrador.</span><span class="sxs-lookup"><span data-stu-id="283fe-111">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="283fe-112">Se o aparelho de filial persistente ficar indisponível, é assim que os clientes do site de filial descobrirão automaticamente o registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="283fe-112">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="283fe-113">Se um site de filial não tiver um servidor DNS, há duas maneiras alternativas para configurar a descoberta do aparelho de filial persistente ou servidor de filial persistente:</span><span class="sxs-lookup"><span data-stu-id="283fe-113">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="283fe-114">Configure a opção de DHCP 120 no servidor de protocolo DHCP para apontar para o nome de domínio totalmente qualificado (FQDN) do aparelho de filial persistente ou servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="283fe-114">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="283fe-115">Configure o aparelho de filial persistente ou servidor de filial persistente para responder às consultas do DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="283fe-115">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="283fe-116">Roteamento de voz para usuários de filial</span><span class="sxs-lookup"><span data-stu-id="283fe-116">Voice Routing for Branch Users</span></span>

<span data-ttu-id="283fe-117">É recomendável criar uma política separada de VoIP (Voice over Internet Protocol ) no nível do usuário para usuários em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="283fe-117">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="283fe-118">Essa política deve incluir uma rota primária que usa o aparelho de filial persistente ou o gateway de servidor de filial e uma ou mais rotas de backup que usam um tronco com um gateway PSTN (rede telefônica pública comutada) no site central.</span><span class="sxs-lookup"><span data-stu-id="283fe-118">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="283fe-119">Se a rota principal estiver indisponível, a rota de backup que usa um ou mais gateways do site central será utilizada.</span><span class="sxs-lookup"><span data-stu-id="283fe-119">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="283fe-120">Desta forma, independentemente de onde o usuário estiver registrado, seja no Registrador Avançado do site de filial ou no pool de registradores de backup no site central, a política de VoIP do usuário sempre estará em vigor.</span><span class="sxs-lookup"><span data-stu-id="283fe-120">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="283fe-121">Esta é uma consideração importante para cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="283fe-121">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="283fe-122">Por exemplo, se for necessário renomear o aparelho de filial persistente ou reconfigurar o aparelho de filial persistente para se conectar a um pool de registradores de backup no site central, você deverá mover os usuários do site da filial para o site central para a duração.</span><span class="sxs-lookup"><span data-stu-id="283fe-122">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="283fe-123">(Para obter detalhes sobre como renomear ou reconfigurar um aparelho de filial persistente, consulte o [Apêndice B: gerenciando um aparelho de filial persistente no Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) na documentação de implantação.) Se esses usuários não tiverem políticas de VoIP em nível de usuário ou planos de discagem em nível de usuário, quando os usuários forem movidos para outro site, as políticas de VoIP no nível do site e os planos de discagem no nível do site central se aplicarão aos usuários por padrão, em vez das políticas e planos de discagem no nível de site do site de filial,.</span><span class="sxs-lookup"><span data-stu-id="283fe-123">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="283fe-124">Neste cenário, a menos que as políticas de VoIP e planos de discagem de nível de site usados pelo pool de registradores de backup também possam ser aplicadas aos usuários do site de filial, suas chamadas falharão.</span><span class="sxs-lookup"><span data-stu-id="283fe-124">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="283fe-125">Por exemplo, se os usuários de um site de filial localizado no Japão forem movidos para um site central em Redmund, um plano de discagem com regras de normalização que precedam +1425 a todas as chamadas de 7 dígitos provavelmente não traduzirá chamadas de forma apropriada para estes usuários.</span><span class="sxs-lookup"><span data-stu-id="283fe-125">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="283fe-126">Ao criar uma rota de backup do escritório da filial, é recomendável adicionar dois registros de utilização de telefone do PSTN à política do usuário do escritório da filial e atribuir rotas separadas para cada uma.</span><span class="sxs-lookup"><span data-stu-id="283fe-126">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="283fe-127">A rota inicial, ou primária, direcionaria as chamadas para o gateway associado ao aparelho de filial persistente (SBA) ou ao servidor de filial; o segundo, ou backup, rota direcionaria chamadas para o gateway no site central.</span><span class="sxs-lookup"><span data-stu-id="283fe-127">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="283fe-128">Ao direcionar chamadas, o SBA ou servidor da filial tentará todas as rotas atribuídas ao primeiro registro de uso do PSTN antes de tentar o segundo registro de uso.</span><span class="sxs-lookup"><span data-stu-id="283fe-128">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="283fe-129">Para ajudar a garantir que as chamadas de entrada para os usuários do site de filial chegarão aos usuários quando o gateway de filial ou o componente do Windows do site do aparelho de filial persistente não estiver disponível (o que aconteceria, por exemplo, se o aparelho de filial persistente ou o gateway de ramificação estivessem inativos para manutenção), crie uma rota de failover no gateway (ou trabalhe com seu provedor de discagem direta (DID)) para redirecionar as chamadas de entrada para o pool de registradores de backup no site central.</span><span class="sxs-lookup"><span data-stu-id="283fe-129">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="283fe-130">Daí, as chamadas serão roteadas sobre o link WAN para os usuários da filial.</span><span class="sxs-lookup"><span data-stu-id="283fe-130">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="283fe-131">Garanta que a rota traduza os números para estar de acordo com o gateway PSTN ou outros formatos de número de telefone aceitos pelo ponto do tronco.</span><span class="sxs-lookup"><span data-stu-id="283fe-131">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="283fe-132">Para obter detalhes sobre como criar uma rota de failover, consulte [Configurando uma rota de failover no Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span><span class="sxs-lookup"><span data-stu-id="283fe-132">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="283fe-133">Crie também planos de discagem de nível de serviço para o tronco associado ao gateway no site de filial para normalizar chamadas de entrada.</span><span class="sxs-lookup"><span data-stu-id="283fe-133">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="283fe-134">Se você tiver dois aparelhos de filial persistentes em um site de filial, você pode criar um plano de discagem no nível do site para ambos, a menos que seja necessário um plano de nível de serviço separado para cada um.</span><span class="sxs-lookup"><span data-stu-id="283fe-134">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="283fe-135">Para suportar o consumo dos recursos do site central pelos usuários de qualquer site de filial que se apoiem no site central para presença, conferência ou failover, é recomendável considerar cada usuário de site de filial como se estivesse registrado no site central.</span><span class="sxs-lookup"><span data-stu-id="283fe-135">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="283fe-136">No momento, não há limites para o número de usuários do site de filial, incluindo usuários registrados em um aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="283fe-136">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="283fe-137">Também é recomendável criar um plano de discagem de nível de usuário e uma política de voz e atribuí-los a usuários do site de filial.</span><span class="sxs-lookup"><span data-stu-id="283fe-137">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="283fe-138">Para obter detalhes, consulte [criar um plano de discagem no Lync server 2013](lync-server-2013-create-a-dial-plan.md) e [criar a política de roteamento VoIP para usuários de filial no Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="283fe-138">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="283fe-139">Números de extensão de roteamento</span><span class="sxs-lookup"><span data-stu-id="283fe-139">Routing Extension Numbers</span></span>

<span data-ttu-id="283fe-140">Ao preparar planos de discagem e políticas de voz para usuários de site de filial, certifique-se de incluir regras de normalização e regras de conversão que correspondam às cadeias de caracteres e o formato de número usados no atributo msRTCSIP-line (ou line URI), de modo que as chamadas do Lync 2013 habilitadas entre os usuários do site da filial e os usuários do site central serão roteadas corretamente, particularmente quando as chamadas devem ser reencaminhadas por meio da PSTN</span><span class="sxs-lookup"><span data-stu-id="283fe-140">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="283fe-141">Existem considerações especiais adicionais para números discados que contêm números de extensão, em vez de apenas números de telefone.</span><span class="sxs-lookup"><span data-stu-id="283fe-141">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="283fe-p108">Regras de normalização e de tradução que correspondam a URIs de Linha que contêm um número de extensão, seja de forma exclusiva ou além de um número de telefone totalmente E.164, possuem requisitos adicionais. Esta seção descreve vários cenários de exemplo para rotear chamadas para URIs de Linha com um número de extensão.</span><span class="sxs-lookup"><span data-stu-id="283fe-p108">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements. This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="283fe-p109">Se sua organização não possui Números Fixos Virtuais (DID) configurados para usuários individuais e a URI de Linha de cada usuário está configurada *apenas* com um número de extensão, usuários internos podem ligar uns para os outros discando apenas um número de extensão. No entanto, é necessário configurar regras de normalização que possam se aplicar a chamadas a partir de um site de filial para um usuário do site central que correspondam a números de extensão.</span><span class="sxs-lookup"><span data-stu-id="283fe-p109">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number. However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="283fe-p110">Em um cenário onde o link WAN entre um site de filial e um site central esteja disponível, chamadas de usuários do site de filial para usuários do site central não exigem que a regra de normalização correspondente traduza o número porque a chamada não é roteada sobre o PSTN. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="283fe-p110">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN. For example:</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="283fe-148">Nome da regra</span><span class="sxs-lookup"><span data-stu-id="283fe-148">Rule name</span></span></th>
<th><span data-ttu-id="283fe-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="283fe-149">Description</span></span></th>
<th><span data-ttu-id="283fe-150">Padrão de número</span><span class="sxs-lookup"><span data-stu-id="283fe-150">Number pattern</span></span></th>
<th><span data-ttu-id="283fe-151">Tradução</span><span class="sxs-lookup"><span data-stu-id="283fe-151">Translation</span></span></th>
<th><span data-ttu-id="283fe-152">Exemplo</span><span class="sxs-lookup"><span data-stu-id="283fe-152">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="283fe-153">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="283fe-153">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="283fe-154">Não traduz números de 5 dígitos</span><span class="sxs-lookup"><span data-stu-id="283fe-154">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="283fe-155">^ (\d {5} ) $</span><span class="sxs-lookup"><span data-stu-id="283fe-155">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="283fe-156">$1</span><span class="sxs-lookup"><span data-stu-id="283fe-156">$1</span></span></p></td>
<td><p><span data-ttu-id="283fe-157">10001 não é traduzido</span><span class="sxs-lookup"><span data-stu-id="283fe-157">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="283fe-p111">Você também deve acomodar números de extensão para cenários específicos, como quando o link WAN entre um site de filial e o site central está indisponível e um chamada de um site de filial deve ser roteada através do PSTN. Durante uma interrupção da WAN, se um usuário do site de filial ligar para um usuário do site central discando apenas sua extensão, você deverá ter uma regra de conversão de saída que adicione o número de telefone completo do usuário do site central. Se a URI de Linha contiver o número de telefone completo da sua empresa e o número de extensão único do usuário em vez de um número de telefone completo que seja único para o usuário, você deverá ter uma regra de conversão de saída que adicione o número de telefone completo da empresa no lugar. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="283fe-p111">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN. During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number. If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="283fe-162">Descrição</span><span class="sxs-lookup"><span data-stu-id="283fe-162">Description</span></span></th>
<th><span data-ttu-id="283fe-163">Padrão de correspondência</span><span class="sxs-lookup"><span data-stu-id="283fe-163">Matching pattern</span></span></th>
<th><span data-ttu-id="283fe-164">Tradução</span><span class="sxs-lookup"><span data-stu-id="283fe-164">Translation</span></span></th>
<th><span data-ttu-id="283fe-165">Exemplo</span><span class="sxs-lookup"><span data-stu-id="283fe-165">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="283fe-166">Traduz números de 5 dígitos para o número de telefone e extensão de um usuário</span><span class="sxs-lookup"><span data-stu-id="283fe-166">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="283fe-167">^ (\d {5} ) $</span><span class="sxs-lookup"><span data-stu-id="283fe-167">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="283fe-168">+ 14255550123; Ext = $1</span><span class="sxs-lookup"><span data-stu-id="283fe-168">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="283fe-169">10001 é traduzido como +14255550123;ext=10001</span><span class="sxs-lookup"><span data-stu-id="283fe-169">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="283fe-170">Traduz números de 5 dígitos para o número de telefone da sua empresa e a extensão de um usuário</span><span class="sxs-lookup"><span data-stu-id="283fe-170">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="283fe-171">^ (\d {5} ) $</span><span class="sxs-lookup"><span data-stu-id="283fe-171">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="283fe-172">+ 14255550100; Ext = $1</span><span class="sxs-lookup"><span data-stu-id="283fe-172">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="283fe-173">10001 é traduzido como +14255550100;ext=10001</span><span class="sxs-lookup"><span data-stu-id="283fe-173">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="283fe-p112">Neste cenário, se o ponto do tronco que trata o re-roteamento para o PSTN não suportar os números de extensão, a regra de tradução de saída também deve remover o número de extensão. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="283fe-p112">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="283fe-176">Descrição</span><span class="sxs-lookup"><span data-stu-id="283fe-176">Description</span></span></th>
<th><span data-ttu-id="283fe-177">Padrão de correspondência</span><span class="sxs-lookup"><span data-stu-id="283fe-177">Matching pattern</span></span></th>
<th><span data-ttu-id="283fe-178">Tradução</span><span class="sxs-lookup"><span data-stu-id="283fe-178">Translation</span></span></th>
<th><span data-ttu-id="283fe-179">Exemplo</span><span class="sxs-lookup"><span data-stu-id="283fe-179">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="283fe-180">Remove a extensão dos números de telefone com extensões</span><span class="sxs-lookup"><span data-stu-id="283fe-180">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="283fe-181">^\+(\d *); ext = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="283fe-181">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="283fe-182">+ $1</span><span class="sxs-lookup"><span data-stu-id="283fe-182">+$1</span></span></p></td>
<td><p><span data-ttu-id="283fe-183">+14255550123;ext=10001 é traduzido como +14255550123</span><span class="sxs-lookup"><span data-stu-id="283fe-183">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="283fe-p113">Independente da disponibilidade de um link WAN, se sua organização não possuir números DID configurados para usuários individuais e a URI de Linha para um usuário contiver o número de telefone da sua empresa e o número de extensão único do usuário, você deve configurar a URI de Linha do número de telefone da sua empresa com um número que seja alcançável pelo ponto do tronco ou gateway PSTN no site da filial. Você também deve configurar a URI de Linha do número de telefone da sua empresa para incluir sua própria extensão única para chamadas a serem roteadas para este número.</span><span class="sxs-lookup"><span data-stu-id="283fe-p113">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site. You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="283fe-186">Para obter detalhes sobre chamadas de um usuário do site central para um usuário do site de filial quando o link WAN entre os sites está indisponível, consulte Preparação para Persistência de Caixa Postal, posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="283fe-186">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="283fe-187">Para obter detalhes sobre planos de discagem e regras de normalização, incluindo outras regras de amostra, consulte [Dial Plans and Normalization Rules in Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) na documentação de planejamento e [configurar planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="283fe-187">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="283fe-188">Para obter detalhes sobre as regras de conversão de saída, consulte [regras de conversão no Lync server 2013](lync-server-2013-translation-rules.md) na documentação de planejamento e [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="283fe-188">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="283fe-189">Preparação para persistência de caixa postal</span><span class="sxs-lookup"><span data-stu-id="283fe-189">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="283fe-190">A Unificação de mensagens (UM) do Exchange geralmente é instalada em um site central e não em sites de filial.</span><span class="sxs-lookup"><span data-stu-id="283fe-190">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="283fe-191">Um chamador deve ser capaz de deixar uma mensagem de caixa postal, mesmo se o link WAN entre o site da filial e o site central estiver indisponível.</span><span class="sxs-lookup"><span data-stu-id="283fe-191">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="283fe-192">Como resultado, a configuração do URI de linha para o número de telefone do atendedor automático do UM do Exchange que fornece caixa postal para usuários do site de filial requer considerações especiais, além das regras de política de voz, plano de discagem e normalização aplicáveis a esse número de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="283fe-192">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="283fe-193">Os aparelhos de ramificação persistente (SBAs) e os servidores de filial persistente fornecem sustentabilidade da caixa postal para usuários de filial durante uma interrupção da WAN.</span><span class="sxs-lookup"><span data-stu-id="283fe-193">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="283fe-194">Especificamente, se você estiver usando um aparelho de filial persistente ou servidor de filial persistente e a WAN ficar indisponível, o servidor de filial SBA ou persistente redireciona novamente as chamadas não atendidas pela PSTN para UM do Exchange no site central.</span><span class="sxs-lookup"><span data-stu-id="283fe-194">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="283fe-195">Com um servidor de filial SBA ou persistente, os usuários também podem recuperar mensagens de caixa postal através da PSTN durante uma interrupção da WAN.</span><span class="sxs-lookup"><span data-stu-id="283fe-195">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="283fe-196">Por fim, durante uma interrupção da WAN, o aparelho de filial persistente ou o servidor de filial persistente enfileira as notificações de chamadas perdidas e, em seguida, carrega-as para o servidor de UM do Exchange quando a WAN é restaurada.</span><span class="sxs-lookup"><span data-stu-id="283fe-196">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="283fe-197">Para ajudar a garantir que o encaminhamento de caixa postal é resistente, certifique-se de adicionar uma entrada para o FQDN do pool de sites central e uma entrada para o FQDN do servidor de borda ao arquivo hosts no servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="283fe-197">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="283fe-198">Do contrário, a resolução do DNS pode ultrapassar o tempo se não houver um servidor DNS no site da filial.</span><span class="sxs-lookup"><span data-stu-id="283fe-198">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="283fe-199">Recomendamos seguir as configurações a seguir para a persistência de caixa postal para usuários de filiais:</span><span class="sxs-lookup"><span data-stu-id="283fe-199">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="283fe-200">Um administrador do Microsoft Exchange deve configurar o atendedor automático da UM do Exchange para aceitar apenas mensagens.</span><span class="sxs-lookup"><span data-stu-id="283fe-200">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="283fe-201">Esta configuração desabilita todas as outras funcionalidades genéricas, como transferência para um usuário ou transferência para um operador e limita o AA a aceitar apenas mensagens.</span><span class="sxs-lookup"><span data-stu-id="283fe-201">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="283fe-202">Como alternativa, o administrador do Exchange pode usar um AA genérico ou um AA personalizado para rotear a chamada para um operador.</span><span class="sxs-lookup"><span data-stu-id="283fe-202">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="283fe-203">O administrador do Lync Server deve obter o número de telefone AA e usar esse número de telefone como o número de **atendedor automático do um do Exchange** nas configurações de reencaminhamento de caixa postal para o aparelho de filial persistente ou servidor de filial.</span><span class="sxs-lookup"><span data-stu-id="283fe-203">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="283fe-204">O administrador do Lync Server deve obter o número de telefone de acesso do assinante da UM do Exchange e usar esse número como o número de **acesso do assinante** nas configurações de reencaminhamento de caixa postal para o aparelho de filial persistente ou servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="283fe-204">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="283fe-205">O administrador do Lync Server deve configurar UM do Exchange para que apenas um plano de discagem seja associado a todos os usuários da filial que precisam acessar a caixa postal durante uma interrupção da WAN.</span><span class="sxs-lookup"><span data-stu-id="283fe-205">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="283fe-206">Quando o link WAN está indisponível, as chamadas para usuários do site da filial podem ser roteadas para a caixa postal da UM (Unified Messaging) do Exchange, mas somente se a política de Voz aplicada à chamada especificar um número de telefone de caixa postal que seja único e não inclua um número de extensão.</span><span class="sxs-lookup"><span data-stu-id="283fe-206">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="283fe-207">Requisitos de hardware e software para resiliência de site de filial</span><span class="sxs-lookup"><span data-stu-id="283fe-207">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="283fe-208">Os requisitos de hardware e software variam, dependendo da sua solução de resiliência.</span><span class="sxs-lookup"><span data-stu-id="283fe-208">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="283fe-209">Requisitos para Aparelhos de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="283fe-209">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="283fe-210">O hardware e o software necessários estão integrados ao aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="283fe-210">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="283fe-211">No entanto, também recomendamos que cada site de filial implante um servidor DHCP para obter endereços IP clientes; do contrário, quando a concessão do DHCP expirar, os clientes não terão conectividade IP.</span><span class="sxs-lookup"><span data-stu-id="283fe-211">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="283fe-212">Se os servidores DNS corporativos estiverem localizados somente nos sites centrais, os usuários do site de filial não poderão se conectar a eles durante uma interrupção da WAN e, portanto, a descoberta do Lync Server que usa o registro de recurso DNS SRV (serviço (SRV) falhará.</span><span class="sxs-lookup"><span data-stu-id="283fe-212">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="283fe-213">Para garantir o re-roteamento imediato durante uma interrupção da WAN, registros DNS devem ser armazenados em cache no site da filial.</span><span class="sxs-lookup"><span data-stu-id="283fe-213">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="283fe-214">Se o roteador da filial for compatível, ative o cache do DNS.</span><span class="sxs-lookup"><span data-stu-id="283fe-214">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="283fe-215">Ou você pode implantar um servidor DNS na filial.</span><span class="sxs-lookup"><span data-stu-id="283fe-215">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="283fe-216">Pode ser um servidor autônomo ou uma versão do aparelho de filial persistente que ofereça suporte a recursos DNS.</span><span class="sxs-lookup"><span data-stu-id="283fe-216">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="283fe-217">Para obter detalhes, entre em contato com seu provedor de aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="283fe-217">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="283fe-218">Não é necessário ter um controlador de domínio no site da filial.</span><span class="sxs-lookup"><span data-stu-id="283fe-218">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="283fe-219">O aparelho de filial persistente autentica clientes usando um certificado especial que envia o cliente em resposta à solicitação de certificado do cliente quando ele entra.</span><span class="sxs-lookup"><span data-stu-id="283fe-219">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="283fe-220">Os clientes do Lync podem descobrir o Lync Server usando a opção de DHCP 120 (opção de registrador SIP).</span><span class="sxs-lookup"><span data-stu-id="283fe-220">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="283fe-221">Ela pode ser configurada em uma de duas formas:</span><span class="sxs-lookup"><span data-stu-id="283fe-221">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="283fe-222">Configure o servidor DHCP no site de filial para responder às consultas do DHCP 120, que retornam o FQDN do registrador no aparelho de filial persistente ou servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="283fe-222">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="283fe-223">Ative o Lync Server DHCP.</span><span class="sxs-lookup"><span data-stu-id="283fe-223">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="283fe-224">Quando estiver ativado, o registrador do Lync Server responderá às consultas de opção 120 de DHCP.</span><span class="sxs-lookup"><span data-stu-id="283fe-224">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="283fe-225">Observe que o Registrador Avançado não responde a nenhuma consulta do DHCP diferente da Opção 120 do DHCP.</span><span class="sxs-lookup"><span data-stu-id="283fe-225">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="283fe-226">Além disso, para sites de filial maiores, que possuem várias sub-redes, agentes de retransmissão DHCP devem estar habilitados para encaminhar consultas da Opção 120 do DHCP para o Servidor DHCP (configuração 1) ou para o Registrador Avançado (configuração 2).</span><span class="sxs-lookup"><span data-stu-id="283fe-226">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="283fe-227">Por fim, os usuários do site de filial devem ser configurados para o Enterprise Voice e provisionados com um ponto de extremidade de comunicação unificada apropriado.</span><span class="sxs-lookup"><span data-stu-id="283fe-227">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="283fe-228">Requisitos para Servidores de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="283fe-228">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="283fe-229">Os requisitos para servidores de filial persistentes são os mesmos dos requisitos para um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="283fe-229">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="283fe-230">Para obter detalhes, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="283fe-230">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="283fe-231">Requisitos para implantações de site de filial do Lync Server em larga escala</span><span class="sxs-lookup"><span data-stu-id="283fe-231">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="283fe-232">Para obter detalhes, consulte [determinando seus requisitos de infraestrutura para o Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="283fe-232">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

