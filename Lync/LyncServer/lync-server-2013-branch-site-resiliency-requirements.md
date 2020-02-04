---
title: 'Lync Server 2013: Requisitos de resiliência do site da filial'
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
ms.openlocfilehash: 4f146f2c358e6eb6718aa60f8a51106430e6a4a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="f2846-102">Requisitos de resiliência do site da filial para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2846-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2846-103">_**Tópico da última modificação:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="f2846-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="f2846-104">Este tópico ajudará você a preparar os usuários para resiliência do site de filial e persistência da caixa postal. Ele também especifica os requisitos importantes de hardware e software.</span><span class="sxs-lookup"><span data-stu-id="f2846-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="f2846-105">Preparação de usuários da filial para resiliência do site de filial</span><span class="sxs-lookup"><span data-stu-id="f2846-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="f2846-106">Prepare os usuários para a resiliência de site de filial definindo o pool registrador como o aparelho de ramificação sobreviventes (SBA) ou o servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="f2846-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="f2846-107">Atribuições do Registrador Avançado para usuários da filial</span><span class="sxs-lookup"><span data-stu-id="f2846-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="f2846-108">Independentemente da solução de resiliência de site de filial escolhida, será necessário atribuir um Registrador Avançado primário a cada usuário.</span><span class="sxs-lookup"><span data-stu-id="f2846-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="f2846-109">Os usuários do site de ramificação sempre devem se registrar no registrador de site, independentemente de o registrador residir na ramificação, servidor de ramificação sobreviventes ou servidor autônomo do Lync Server 2013 Standard ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f2846-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="f2846-110">Um registro DNS (Sistema de Nomes de Domínio) de recurso de serviços (SRV) é necessário para que o cliente possa descobrir o seu pool de Registradores Avançados.</span><span class="sxs-lookup"><span data-stu-id="f2846-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="f2846-111">Se o aparelho de ramificação sobreviventes ficar indisponível, é como os clientes do site de filiais detectam automaticamente o registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="f2846-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="f2846-112">Se um site de filial não tiver um servidor DNS, existem duas maneiras alternativas para configurar a descoberta do aparelho de ramificação sobreviventes ou do servidor de ramificação sobreviventes:</span><span class="sxs-lookup"><span data-stu-id="f2846-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="f2846-113">Configure a opção de DHCP 120 no servidor DHCP (Dynamic Host Configuration Protocol) para apontar para o nome de domínio totalmente qualificado (FQDN) do aparelho de ramificação sobreviventes ou do servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="f2846-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="f2846-114">Configure o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes para responder às consultas de DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="f2846-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="f2846-115">Roteamento de voz para usuários de filial</span><span class="sxs-lookup"><span data-stu-id="f2846-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="f2846-116">É recomendável criar uma política VoIP separada em nível de usuário para os usuários de um site de filial.</span><span class="sxs-lookup"><span data-stu-id="f2846-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="f2846-117">Essa política deve incluir uma rota primária que usa o aplicativo de ramificação ou o gateway de servidor de ramificação sobreviventes e uma ou mais rotas de backup que usam um tronco com um gateway PSTN (rede telefônica pública comutada) no site central.</span><span class="sxs-lookup"><span data-stu-id="f2846-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="f2846-118">Se a rota principal não estiver disponível, a rota de backup que usa um ou mais gateways do site central será utilizada.</span><span class="sxs-lookup"><span data-stu-id="f2846-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="f2846-119">Dessa forma, independentemente de onde o usuário estiver registrado — seja no Registrador Avançado do site de filial ou no pool de Registradores Avançados de backup no site central — a política VoIP do usuário estará sempre em vigor.</span><span class="sxs-lookup"><span data-stu-id="f2846-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="f2846-120">Essa é uma consideração importante para cenários de failover.</span><span class="sxs-lookup"><span data-stu-id="f2846-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="f2846-121">Por exemplo, se precisar renomear o aparelho de ramificação sobreviventes ou reconfigurar o aparelho de ramificação sobreviventes para se conectar a um pool de registradores de backup no site central, você deverá mover os usuários do site para o site central durante a duração.</span><span class="sxs-lookup"><span data-stu-id="f2846-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="f2846-122">(Para obter detalhes sobre como renomear ou reconfigurar um aparelho de ramificação sobreviventes, consulte o [Apêndice B: gerenciando um aparelho de ramificação sobreviventes no Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) na documentação de implantação.) Se esses usuários não tiverem políticas de VoIP em nível de usuário ou planos de discagem em nível de usuário, quando os usuários forem movidos para outro site, as políticas de VoIP no nível do site e os planos de discagem no nível do site central se aplicam aos usuários por padrão, em vez de políticas de VoIP no nível de site e de planos de discagem</span><span class="sxs-lookup"><span data-stu-id="f2846-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="f2846-123">Nesse cenário, a menos que as políticas VoIP e os planos de discagem em nível de site usados pelo pool de Registradores Avançados de backup também possam ser aplicados aos usuários do site de filial, suas chamadas falharão.</span><span class="sxs-lookup"><span data-stu-id="f2846-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="f2846-124">Por exemplo, se os usuários de um site de filial localizado no Japão forem movidos para um site central em Redmond, um plano de discagem com regras de normalização que acrescentem o prefixo +1425 a todas as chamadas de 7 dígitos provavelmente não converterá as chamadas de forma apropriada para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="f2846-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2846-125">Ao criar uma rota de backup do escritório da filial, é recomendável adicionar dois registros de uso do telefone PSTN à política do usuário do escritório da filial e atribuir rotas separadas a cada um deles.</span><span class="sxs-lookup"><span data-stu-id="f2846-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="f2846-126">A rota inicial ou primária faria chamadas para o gateway associado à ferramenta de ramificação (SBA) ou ao servidor de ramificação sobreviventes. a rota de segundo, ou backup, direcionaria chamadas para o gateway no site central.</span><span class="sxs-lookup"><span data-stu-id="f2846-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="f2846-127">Ao direcionar as chamadas, o SBA ou o servidor da filial tentará todas as rotas atribuídas ao primeiro registro de uso PSTN, antes de tentar o segundo registro.</span><span class="sxs-lookup"><span data-stu-id="f2846-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="f2846-128">Para ajudar a garantir que as chamadas recebidas para os usuários do site de ramificação cheguem a esses usuários quando o gateway da ramificação ou o componente do Windows do site do aparelho de ramificação sobreviventes estiver indisponível (o que aconteceria, por exemplo, se a ramificação ou ramificação sobreviventes pode ser retentada o gateway foi desativado para manutenção), crie uma rota de failover no gateway (ou trabalhe com o seu provedor de discagem direta) para redirecionar as chamadas de entrada para o pool de registradores de backup no site central.</span><span class="sxs-lookup"><span data-stu-id="f2846-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="f2846-129">A partir desse local, as chamadas serão encaminhadas através do link WAN para os usuários da filial.</span><span class="sxs-lookup"><span data-stu-id="f2846-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="f2846-130">A rota deverá converter os números para que fiquem em conformidade com o gateway PSTN ou outros formatos de número de telefone aceitos pelo par de tronco.</span><span class="sxs-lookup"><span data-stu-id="f2846-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="f2846-131">Para obter detalhes sobre como criar uma rota de failover, consulte [Configurando uma rota de failover no Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span><span class="sxs-lookup"><span data-stu-id="f2846-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="f2846-132">Além disso, crie planos de discagem de nível de serviço para o tronco associado ao gateway no site de filial a fim de normalizar as chamadas de entrada.</span><span class="sxs-lookup"><span data-stu-id="f2846-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="f2846-133">Se você tiver dois aparelhos de ramificação sobreviventes em um site de filial, poderá criar um plano de discagem em nível de site para ambos, a menos que seja necessário um plano de nível de serviço separado para cada um.</span><span class="sxs-lookup"><span data-stu-id="f2846-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2846-134">Para contabilizar o consumo de recursos do site central pelos usuários de um site de filial que dependam do site central para fins de presença, conferência ou failover, é recomendável considerar cada usuário do site de filial como se estivesse registrado no site central.</span><span class="sxs-lookup"><span data-stu-id="f2846-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="f2846-135">No momento, não há limites quanto ao número de usuários de sites de filiais, incluindo usuários registrados em um aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="f2846-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="f2846-136">Também é recomendável criar um plano de discagem e uma política de voz em nível de usuário, e atribuí-los aos usuários do site de filial.</span><span class="sxs-lookup"><span data-stu-id="f2846-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="f2846-137">Para obter detalhes, consulte [criar um plano de discagem no Lync server 2013](lync-server-2013-create-a-dial-plan.md) e [criar a política de roteamento de VoIP para usuários de ramificação no Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f2846-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="f2846-138">Roteamento de números de ramal</span><span class="sxs-lookup"><span data-stu-id="f2846-138">Routing Extension Numbers</span></span>

<span data-ttu-id="f2846-139">Ao preparar planos de discagem e políticas de voz para usuários de site de ramificação, certifique-se de incluir regras de normalização e regras de tradução que correspondam às cadeias de caracteres e o formato de número usados no atributo msRTCSIP-linha (ou URI de linha) para que as chamadas do Lync 2013 sejam habilitadas entre Branch os usuários do site e os usuários do site central serão roteados corretamente, principalmente quando as chamadas devem ser redirecionadas pelo PSTN porque o link de rede de longa distância não está disponível.</span><span class="sxs-lookup"><span data-stu-id="f2846-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="f2846-140">Além disso, há considerações especiais para números discados que contêm números de ramal, e não apenas números de telefone.</span><span class="sxs-lookup"><span data-stu-id="f2846-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="f2846-p108">As regras de normalização e de conversão que fazem a correspondência das URIs de Linha que contêm um número de ramal, exclusivamente ou além de um número de telefone E.164 completo, têm requisitos adicionais. Esta seção descreve vários cenários de exemplo para encaminhar chamadas para URIs de Linha com um número de ramal.</span><span class="sxs-lookup"><span data-stu-id="f2846-p108">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements. This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="f2846-p109">Se a sua organização não tiver números de telefone de Discagem Direta Interna (DDI) configurados para usuários individuais, e a URI da Linha de cada usuário estiver configurada *apenas* com um número de ramal, os usuários internos poderão ligar uns para os outros discando apenas um número de ramal. No entanto, é necessário configurar regras de normalização aplicáveis às chamadas de um usuário do site de filial para outro do site central, que façam a correspondência dos números de ramal.</span><span class="sxs-lookup"><span data-stu-id="f2846-p109">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number. However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="f2846-p110">Em um cenário em que o link WAN entre um site de filial e um site central esteja disponível, as chamadas de usuários do site de filial para os do site central não exigirão que a regra de normalização de correspondência converta o número porque a chamada não é encaminhada através da PSTN. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f2846-p110">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN. For example:</span></span>


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
<th><span data-ttu-id="f2846-147">Nome da regra</span><span class="sxs-lookup"><span data-stu-id="f2846-147">Rule name</span></span></th>
<th><span data-ttu-id="f2846-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="f2846-148">Description</span></span></th>
<th><span data-ttu-id="f2846-149">Padrão do número</span><span class="sxs-lookup"><span data-stu-id="f2846-149">Number pattern</span></span></th>
<th><span data-ttu-id="f2846-150">Conversão</span><span class="sxs-lookup"><span data-stu-id="f2846-150">Translation</span></span></th>
<th><span data-ttu-id="f2846-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f2846-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2846-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="f2846-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="f2846-153">Não converte números de 5 dígitos</span><span class="sxs-lookup"><span data-stu-id="f2846-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="f2846-154">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="f2846-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="f2846-155">$1</span><span class="sxs-lookup"><span data-stu-id="f2846-155">$1</span></span></p></td>
<td><p><span data-ttu-id="f2846-156">10001 não é convertido</span><span class="sxs-lookup"><span data-stu-id="f2846-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2846-p111">Você também deve acomodar números de ramal para cenários específicos, como, por exemplo, quando o link WAN entre um site de filial e o site central não está disponível, e uma chamada de um site de filial deve ser encaminhada através da PSTN. Durante uma interrupção da WAN, se um usuário do site de filial ligar para outro do site central discando apenas seu ramal, será necessário ter uma regra de conversão de saída que adicione o número de telefone completo do usuário do site central. Se a URI da Linha do usuário contiver o número de telefone completo da sua organização e o número de ramal exclusivo do usuário, em vez de um número de telefone completo que seja exclusivo do usuário, será necessário ter uma regra de conversão de saída que adicione o número de telefone completo da organização. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f2846-p111">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN. During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number. If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2846-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="f2846-161">Description</span></span></th>
<th><span data-ttu-id="f2846-162">Padrão de correspondência</span><span class="sxs-lookup"><span data-stu-id="f2846-162">Matching pattern</span></span></th>
<th><span data-ttu-id="f2846-163">Conversão</span><span class="sxs-lookup"><span data-stu-id="f2846-163">Translation</span></span></th>
<th><span data-ttu-id="f2846-164">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f2846-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2846-165">Converte números de 5 dígitos no número de telefone e no ramal do usuário</span><span class="sxs-lookup"><span data-stu-id="f2846-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="f2846-166">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="f2846-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="f2846-167">+14255550123;ext=$1</span><span class="sxs-lookup"><span data-stu-id="f2846-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="f2846-168">10001 é convertido em +14255550123;ext=10001</span><span class="sxs-lookup"><span data-stu-id="f2846-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2846-169">Converte números de 5 dígitos no número de telefone da organização e no ramal do usuário</span><span class="sxs-lookup"><span data-stu-id="f2846-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="f2846-170">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="f2846-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="f2846-171">+14255550100;ext=$1</span><span class="sxs-lookup"><span data-stu-id="f2846-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="f2846-172">10001 é convertido em +14255550100;ext=10001</span><span class="sxs-lookup"><span data-stu-id="f2846-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2846-p112">Neste cenário, se o par do tronco que trata do reencaminhamento para a PSTN não aceitar números de ramal, a regra de conversão de saída também deverá remover o número do ramal. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f2846-p112">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2846-175">Descrição</span><span class="sxs-lookup"><span data-stu-id="f2846-175">Description</span></span></th>
<th><span data-ttu-id="f2846-176">Padrão de correspondência</span><span class="sxs-lookup"><span data-stu-id="f2846-176">Matching pattern</span></span></th>
<th><span data-ttu-id="f2846-177">Conversão</span><span class="sxs-lookup"><span data-stu-id="f2846-177">Translation</span></span></th>
<th><span data-ttu-id="f2846-178">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f2846-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2846-179">Remove o ramal dos números de telefone com ramais</span><span class="sxs-lookup"><span data-stu-id="f2846-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="f2846-180">^\+(\d *); ext = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="f2846-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="f2846-181">+$1</span><span class="sxs-lookup"><span data-stu-id="f2846-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="f2846-182">+14255550123;ext=10001 é convertido em +14255550123</span><span class="sxs-lookup"><span data-stu-id="f2846-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2846-p113">Independentemente de um link WAN estar ou não disponível, se a sua organização não tiver números DDI configurados para os usuários individuais, e a URI da Linha de um usuário contiver o número de telefone da organização e o número do ramal exclusivo do usuário, você deverá configurar a URI da Linha do número de telefone da organização com um número que possa ser acessado pelo par do tronco ou pelo gateway PSTN no site de filial. Você também deve configurar a URI da Linha do número de telefone da organização para incluir seu próprio ramal exclusivo de modo que as chamadas sejam encaminhadas para esse número.</span><span class="sxs-lookup"><span data-stu-id="f2846-p113">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site. You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="f2846-185">Para obter detalhes sobre chamadas de um usuário do site central para um usuário do site da filial quando o link de WAN entre os sites não estiver disponível, consulte "preparando para a imsustentabilidade da caixa postal" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f2846-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="f2846-186">Para obter detalhes sobre planos de discagem e regras de normalização, incluindo outras regras de amostra, consulte [planos de discagem e regras de normalização no Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) na documentação de planejamento e [Configurando planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f2846-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="f2846-187">Para obter detalhes sobre as regras de conversão de saída, consulte [regras de tradução no Lync server 2013](lync-server-2013-translation-rules.md) na documentação de planejamento e [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f2846-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="f2846-188">Preparação para persistência da caixa postal</span><span class="sxs-lookup"><span data-stu-id="f2846-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="f2846-189">A UM (Unificação de mensagens) do Exchange geralmente é instalada apenas em um site central e não em sites de filiais.</span><span class="sxs-lookup"><span data-stu-id="f2846-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="f2846-190">Um chamador deve ser capaz de deixar uma mensagem de caixa postal, mesmo que o link WAN entre o site de filial e o central não esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="f2846-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="f2846-191">Como resultado, a configuração do URI de linha do número de telefone do atendedor automático do Exchange UM que forneça a caixa postal para os usuários do site de ramificação exige considerações especiais, além da política de voz, do plano de discagem e das regras de normalização aplicáveis a essa caixa postal tempo.</span><span class="sxs-lookup"><span data-stu-id="f2846-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="f2846-192">Os appliances de ramificação sobreviventes (SBAs) e os servidores de filiais sobreviventes fornecem sustentabilidade da caixa postal para usuários de filiais durante uma falha de WAN.</span><span class="sxs-lookup"><span data-stu-id="f2846-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="f2846-193">Especificamente, se você estiver usando um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes e a WAN ficar indisponível, o servidor de ramificação SBA ou sobreviver redirecionará chamadas não atendidas pela PSTN para o Exchange UM no site central.</span><span class="sxs-lookup"><span data-stu-id="f2846-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="f2846-194">Com um servidor de ramificação SBA ou sobreviventes, os usuários também podem recuperar mensagens de caixa postal por meio da PSTN durante uma falha de WAN.</span><span class="sxs-lookup"><span data-stu-id="f2846-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="f2846-195">Por fim, durante uma falha de WAN, o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes enfileira notificações de chamada perdida e, em seguida, carrega-as para o servidor do Exchange UM quando a WAN é restaurada.</span><span class="sxs-lookup"><span data-stu-id="f2846-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="f2846-196">Para ajudar a garantir que o redirecionamento de caixa postal seja resistente, certifique-se de adicionar uma entrada para o FQDN do pool de site central e uma entrada para o FQDN do servidor de borda ao arquivo hosts no servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="f2846-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="f2846-197">Caso contrário, o tempo limite da resolução DNS poderá expirar se não houver um servidor DNS no site de filial.</span><span class="sxs-lookup"><span data-stu-id="f2846-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="f2846-198">Recomendamos definir as configurações a seguir para a persistência da caixa postal dos usuários do site de filial:</span><span class="sxs-lookup"><span data-stu-id="f2846-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="f2846-199">Um administrador do Microsoft Exchange deve configurar o atendedor automático do Exchange UM para aceitar somente mensagens.</span><span class="sxs-lookup"><span data-stu-id="f2846-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="f2846-200">Essa configuração desabilita todas as outras funcionalidades genéricas, como a transferência para um usuário ou a transferência para um operador, e limita o AA a aceitar apenas mensagens.</span><span class="sxs-lookup"><span data-stu-id="f2846-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="f2846-201">Como alternativa, o administrador do Exchange pode usar um AA genérico ou um AA personalizado a fim de encaminhar a chamada para um operador.</span><span class="sxs-lookup"><span data-stu-id="f2846-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="f2846-202">O administrador do Lync Server deve levar o número de telefone AA e usar esse número de telefone como o número de **atendedor automático de um do Exchange** nas configurações de redirecionamento de caixa postal para o aparelho de ramificação ou servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="f2846-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="f2846-203">O administrador do Lync Server deve obter o número de telefone de acesso do assinante do Exchange UM e usar esse número como o número de **acesso do assinante** nas configurações de redirecionamento de caixa postal para o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="f2846-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="f2846-204">O administrador do Lync Server deve configurar o UM do Exchange para que apenas um plano de discagem esteja associado a todos os usuários da ramificação que precisam acessar a caixa postal durante uma falha de WAN.</span><span class="sxs-lookup"><span data-stu-id="f2846-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="f2846-205">Quando o link WAN não está disponível, as chamadas para os usuários do site de filial poderão ser encaminhadas para a caixa postal de UM (Unificação de Mensagens) do Exchange do usuário, mas somente se a política de voz aplicada à chamada especificar um número de telefone de caixa postal que seja exclusivo e não inclua um número de ramal.</span><span class="sxs-lookup"><span data-stu-id="f2846-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="f2846-206">Requisitos de hardware e software para resiliência de sites de filial</span><span class="sxs-lookup"><span data-stu-id="f2846-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="f2846-207">Os requisitos de hardware e software variam, dependendo da solução de resiliência.</span><span class="sxs-lookup"><span data-stu-id="f2846-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="f2846-208">Requisitos para Aparelhos de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="f2846-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="f2846-209">O hardware e o software necessários estão integrados ao aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="f2846-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="f2846-210">No entanto, também recomendamos que cada site de filial implante um servidor DHCP para obter os endereços IP de clientes; caso contrário, quando a concessão de DHCP expirar, os clientes não terão conectividade IP.</span><span class="sxs-lookup"><span data-stu-id="f2846-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="f2846-211">Se os servidores DNS da empresa estiverem localizados somente em sites centrais, os usuários do site de filial não poderão se conectar a eles durante uma falha de WAN e, portanto, a descoberta do Lync Server que usa o SRV (registro de recurso de serviço) DNS falhará.</span><span class="sxs-lookup"><span data-stu-id="f2846-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="f2846-212">Para garantir o redirecionamento de prompt durante uma falha de WAN, os registros DNS devem ser armazenados em cache no site da filial.</span><span class="sxs-lookup"><span data-stu-id="f2846-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="f2846-213">Se o roteador de ramificação oferecer suporte, ative o cache de DNS.</span><span class="sxs-lookup"><span data-stu-id="f2846-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="f2846-214">Ou você pode implantar um servidor DNS na ramificação.</span><span class="sxs-lookup"><span data-stu-id="f2846-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="f2846-215">Isso pode ser um servidor autônomo ou uma versão do aparelho de ramificação sobreviventes que ofereça suporte a recursos de DNS.</span><span class="sxs-lookup"><span data-stu-id="f2846-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="f2846-216">Para obter detalhes, entre em contato com seu provedor de aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="f2846-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2846-217">Não é necessário ter um controlador de domínio em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="f2846-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="f2846-218">O aparelho de ramificação sobreviventes autentica clientes usando um certificado especial que envia o cliente em resposta à solicitação de certificado do cliente quando ele entra.</span><span class="sxs-lookup"><span data-stu-id="f2846-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="f2846-219">Os clientes do Lync podem descobrir o Lync Server usando a opção de DHCP 120 (opção de registrador de SIP).</span><span class="sxs-lookup"><span data-stu-id="f2846-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="f2846-220">Essa opção pode ser configurada de uma de destas duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="f2846-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="f2846-221">Configure o servidor DHCP no site de filial para responder a consultas DHCP 120, que retornam o FQDN do registrador na ramificação da ramificação sobreviventes ou do servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="f2846-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="f2846-222">Ative o DHCP do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2846-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="f2846-223">Quando essa opção estiver ativada, o registrador do Lync Server responderá às consultas de opção de DHCP 120.</span><span class="sxs-lookup"><span data-stu-id="f2846-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="f2846-224">Observe que o Registrador Avançado não responde a nenhuma consulta do DHCP diferente das Opções 120 do DHCP.</span><span class="sxs-lookup"><span data-stu-id="f2846-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="f2846-225">Além disso, para sites de filial maiores, com várias sub-redes, agentes de retransmissão DHCP devem ser habilitados para encaminhar consultas da Opção 120 do DHCP para o Servidor DHCP (configuração 1) ou para o Registrador Avançado (configuração 2).</span><span class="sxs-lookup"><span data-stu-id="f2846-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="f2846-226">Por fim, os usuários do site de filiais devem ser configurados para Enterprise Voice e provisionados com um ponto de extremidade de comunicação unificado apropriado.</span><span class="sxs-lookup"><span data-stu-id="f2846-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="f2846-227">Requisitos para Servidores de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="f2846-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="f2846-228">Os requisitos para servidores de filiais sobreviventes são os mesmos dos requisitos para um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f2846-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="f2846-229">Para obter detalhes, consulte [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="f2846-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="f2846-230">Requisitos para implantações em filiais do servidor do Lync Server em toda a escala</span><span class="sxs-lookup"><span data-stu-id="f2846-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="f2846-231">Para obter detalhes, consulte [determinando os requisitos de infraestrutura do Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="f2846-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

