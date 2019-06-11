---
title: 'Lync Server 2013: Movendo usuários para o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1127bd0c767da7f02df8aefb30fda41a64bd353a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="85adc-102">Movendo usuários para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85adc-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85adc-103">_**Tópico da última modificação:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="85adc-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="85adc-104">Se você estiver movendo usuários de uma infraestrutura de telefonia PBX existente para o Enterprise Voice, o processo de implantação incluirá algumas etapas que não fazem parte do processo de planejamento já descrito no [Planning for Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="85adc-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="85adc-105">Para obter informações sobre a migração de usuários de uma implantação de voz empresarial anterior, consulte os documentos de migração que foram incluídos na mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="85adc-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="85adc-106">O processo de mover os usuários de uma infraestrutura de telefonia existente para o Enterprise Voice consiste nas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="85adc-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="85adc-107">Designar números de telefone primários.</span><span class="sxs-lookup"><span data-stu-id="85adc-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="85adc-108">Habilite usuários para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="85adc-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="85adc-109">Preparar planos de discagem para usuários.</span><span class="sxs-lookup"><span data-stu-id="85adc-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="85adc-110">Planejar políticas de voz de usuários.</span><span class="sxs-lookup"><span data-stu-id="85adc-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="85adc-111">Planejar roteiros de chamadas.</span><span class="sxs-lookup"><span data-stu-id="85adc-111">Plan call routes.</span></span>

6.  <span data-ttu-id="85adc-112">Configure o tronco PBX ou SIP para redirecionar chamadas para usuários habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="85adc-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="85adc-113">Mover usuários para a UM (recomendado) Exchange Unified Messaging (recomendado).</span><span class="sxs-lookup"><span data-stu-id="85adc-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="85adc-114">Este tópico descreve o planejamento necessário para cada uma dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="85adc-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="85adc-115">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="85adc-115">Step 1.</span></span> <span data-ttu-id="85adc-116">Designar números de telefone principais</span><span class="sxs-lookup"><span data-stu-id="85adc-116">Designate primary phone numbers</span></span>

<span data-ttu-id="85adc-117">O Enterprise Voice integra voz com outras mídias de mensagens, de forma que, quando uma chamada de entrada chega ao servidor, o servidor mapeia o número para o SIP-URI do usuário e, em seguida, bifurca a chamada para todos os pontos de extremidade do cliente associados ao SIP-URI.</span><span class="sxs-lookup"><span data-stu-id="85adc-117">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="85adc-118">Esse processo requer que cada usuário seja associado a um número de telefone principal.</span><span class="sxs-lookup"><span data-stu-id="85adc-118">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="85adc-119">Um número de telefone principal deve ser:</span><span class="sxs-lookup"><span data-stu-id="85adc-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="85adc-120">Globalmente exclusivo ou, no caso de extensões internas, exclusivas da empresa.</span><span class="sxs-lookup"><span data-stu-id="85adc-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="85adc-121">Pertencente à empresa e roteável na empresa.</span><span class="sxs-lookup"><span data-stu-id="85adc-121">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="85adc-122">Números pessoais não devem ser usados.</span><span class="sxs-lookup"><span data-stu-id="85adc-122">Personal numbers should not be used.</span></span>

<span data-ttu-id="85adc-123">Os usuários da empresa podem ter dois ou mais números de telefone listados para eles nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85adc-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="85adc-124">Todos os números de telefone associados a um usuário específico podem ser exibidos ou alterados na folha de propriedades desse usuário no snap-in usuários e computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85adc-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="85adc-125">A caixa **número de telefone** na guia **geral** da caixa de diálogo Propriedades do **usuário** deve conter o número do trabalho principal do usuário.</span><span class="sxs-lookup"><span data-stu-id="85adc-125">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="85adc-126">Esse número normalmente será designado como o número de telefone principal do usuário.</span><span class="sxs-lookup"><span data-stu-id="85adc-126">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="85adc-127">Alguns usuários podem ter requisitos especiais (por exemplo, um executivo que deseja todas as chamadas de entrada roteadas por meio de um assistente administrativo), mas essas exceções devem ser limitadas apenas àqueles em que a necessidade é clara e crítica.</span><span class="sxs-lookup"><span data-stu-id="85adc-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="85adc-128">Depois que um número principal é escolhido, ele deve ser:</span><span class="sxs-lookup"><span data-stu-id="85adc-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="85adc-129">Normal para o formato E. 164, sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="85adc-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="85adc-130">Copiado para o atributo de **linha msRTCSIP** do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85adc-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85adc-131"><STRONG>Coexistente com controle de chamada remota (RCC)</STRONG></span><span class="sxs-lookup"><span data-stu-id="85adc-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="85adc-132">O RCC é a capacidade de usar o Lync Server para monitorar e controlar um telefone PBX de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="85adc-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="85adc-133">O controle é roteado pelo servidor, que atua como um gateway para o PBX.</span><span class="sxs-lookup"><span data-stu-id="85adc-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="85adc-134">Embora você não possa configurar um usuário para RCC e Enterprise Voice, a configuração de URI de linha designa o número de telefone principal de um usuário em ambos os casos.</span><span class="sxs-lookup"><span data-stu-id="85adc-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="85adc-135">Se você tiver uma infraestrutura de PBX existente que deseja que os usuários selecionados continuem a usar, você pode introduzir o Enterprise Voice em incrementos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="85adc-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="85adc-136">Para obter detalhes sobre esse cenário de implantação, consulte <A href="lync-server-2013-direct-sip-deployment-options.md">Opções de implantação de SIP direto no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="85adc-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="85adc-137">Em versões anteriores, você pode habilitar o RCC e o Enterprise Voice para um usuário, mas somente se você também configurou o usuário para a bifurcação dupla, um recurso no qual uma chamada de entrada tocará o telefone PBX e o Communicator de um usuário simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="85adc-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="85adc-138">No Lync Server 2010, não há suporte para a bifurcação dupla.</span><span class="sxs-lookup"><span data-stu-id="85adc-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="85adc-139">Há três métodos para preencher o atributo **msRTCSIP-line** :</span><span class="sxs-lookup"><span data-stu-id="85adc-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="85adc-140">Servidor de integração de identidades da Microsoft (recomendado)</span><span class="sxs-lookup"><span data-stu-id="85adc-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="85adc-141">A página **usuários** no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="85adc-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="85adc-142">Onde vários números de telefone devem ser processados, um script personalizado desenvolvido pela sua organização é a melhor opção.</span><span class="sxs-lookup"><span data-stu-id="85adc-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="85adc-143">Dependendo de como sua organização representa números de telefone nos serviços de domínio Active Directory, o script pode ter que normalizar números de telefone primários para o formato E. 164 antes de copiá-los para o atributo de **linha de msRTCSIP** .</span><span class="sxs-lookup"><span data-stu-id="85adc-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="85adc-144">Se a sua organização mantém todos os números de telefone nos serviços de domínio Active Directory em um único formato e se esse formato for E. 164, o seu script só precisará gravar cada número de telefone principal para o atributo de **linha de msRTCSIP** .</span><span class="sxs-lookup"><span data-stu-id="85adc-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="85adc-145">Se a sua organização mantém todos os números de telefone nos serviços de domínio Active Directory em um único formato, mas esse formato não é E. 164, o script deve definir uma regra de normalização apropriada para converter os números de telefone principais do formato existente para E. 164 antes de escrevê-los no atributo da **linha de msRTCSIP** .</span><span class="sxs-lookup"><span data-stu-id="85adc-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="85adc-146">Se a sua organização não impõe um formato padrão para números de telefone nos serviços de domínio Active Directory, o script deve definir regras de normalização adequadas para converter os números de telefone principais de seus vários formatos para o E. 164 conformidade antes Escreva os números de telefone principais para o atributo de **linha de msRTCSIP** .</span><span class="sxs-lookup"><span data-stu-id="85adc-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="85adc-147">O script também terá que inserir o prefixo **Tel:** antes de cada número principal antes de escrevê-lo no atributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="85adc-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="85adc-148">O formato esperado do número especificado nesse atributo é:</span><span class="sxs-lookup"><span data-stu-id="85adc-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="85adc-149">Tel: + 14255550100; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="85adc-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="85adc-150">Tel: 5550100 (para ramais de toda a empresa)</span><span class="sxs-lookup"><span data-stu-id="85adc-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="85adc-151">A normalização realizada pelo serviço de catálogo de endereços (ABS) não substitui ou, de outra forma, elimina a necessidade de normalizar o número de telefone principal de cada usuário nos serviços de domínio Active Directory porque o ABS não tem acesso aos serviços de domínio do Active Directory e Portanto, não é possível copiar números primários para o atributo de <STRONG>linha de msRTCSIP</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="85adc-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="85adc-152">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="85adc-152">Step 2.</span></span> <span data-ttu-id="85adc-153">Habilitar usuários para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="85adc-153">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="85adc-154">Além de identificar quais usuários devem ser habilitados, não é necessário um planejamento especial para concluir esta etapa.</span><span class="sxs-lookup"><span data-stu-id="85adc-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="85adc-155">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="85adc-155">Step 3.</span></span> <span data-ttu-id="85adc-156">Preparar planos de discagem para usuários.</span><span class="sxs-lookup"><span data-stu-id="85adc-156">Prepare dial plans for users.</span></span>

<span data-ttu-id="85adc-157">Os usuários habilitados para o Enterprise Voice não poderão fazer chamadas para a PSTN sem planos de discagem no lugar.</span><span class="sxs-lookup"><span data-stu-id="85adc-157">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="85adc-158">Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um único formato padrão (E.164) para fins de roteamento de chamadas e autorização de telefones.</span><span class="sxs-lookup"><span data-stu-id="85adc-158">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="85adc-159">As regras de normalização definem como os números de telefone expressos em vários formatos devem ser roteados para cada local, usuário ou objeto de contato especificado.</span><span class="sxs-lookup"><span data-stu-id="85adc-159">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="85adc-160">Para obter informações sobre como preparar planos de discagem, consulte [planos de discagem e regras de normalização no Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="85adc-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="85adc-161">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="85adc-161">Step 4.</span></span> <span data-ttu-id="85adc-162">Planejar políticas de voz do usuário</span><span class="sxs-lookup"><span data-stu-id="85adc-162">Plan user voice policies</span></span>

<span data-ttu-id="85adc-163">As configurações de classe de serviço de usuário em um PBX herdado, como o direito de fazer chamadas interurbanas ou internacionais de telefones da empresa, devem ser reconfiguradas como políticas de VoIP para usuários migrados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="85adc-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="85adc-164">Para obter detalhes sobre como planejar e criar políticas para o Enterprise Voice, consulte [políticas de voz no Lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="85adc-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="85adc-165">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="85adc-165">Step 5.</span></span> <span data-ttu-id="85adc-166">Planejar roteiros de chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="85adc-166">Plan outbound call routes</span></span>

<span data-ttu-id="85adc-167">As rotas de chamadas especificam como o Lync Server manipula chamadas feitas por usuários do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="85adc-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="85adc-168">Quando um usuário disca um número, o servidor, se necessário, normaliza a cadeia de caracteres de discagem para o formato e. 164 e tenta-lo com um URI SIP.</span><span class="sxs-lookup"><span data-stu-id="85adc-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="85adc-169">Se o servidor não puder fazer a correspondência, ele aplicará uma lógica de roteamento de chamadas de saída com base no número.</span><span class="sxs-lookup"><span data-stu-id="85adc-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="85adc-170">A etapa final em definir essa lógica é criar uma rota de chamada nomeada separada para cada conjunto de números de telefone de destino listados em cada plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="85adc-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="85adc-171">Para obter detalhes sobre o planejamento de rotas de chamadas, consulte [rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="85adc-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="85adc-172">Etapa 6.</span><span class="sxs-lookup"><span data-stu-id="85adc-172">Step 6.</span></span> <span data-ttu-id="85adc-173">Configurar o tronco PBX ou SIP para redirecionar chamadas para usuários do Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="85adc-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="85adc-174">Os usuários que anteriormente eram hospedados em um PBX tradicional ou em uma conexão de tronco SIP com um provedor de serviços de telefonia pela Internet (ITSP) mantêm seus números de telefone após a mudança.</span><span class="sxs-lookup"><span data-stu-id="85adc-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="85adc-175">O único requisito é que, após a movimentação, o PBX ou o tronco SIP devem ser reconfigurados para direcionar as chamadas de entrada para usuários do Enterprise Voice para o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="85adc-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="85adc-176">Etapa 7.</span><span class="sxs-lookup"><span data-stu-id="85adc-176">Step 7.</span></span> <span data-ttu-id="85adc-177">Mover usuários para a Unificação de mensagens do Exchange (recomendado)</span><span class="sxs-lookup"><span data-stu-id="85adc-177">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="85adc-178">Mover usuários para a Unificação de mensagens do Exchange consiste nas seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="85adc-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="85adc-179">Configure a Unificação de mensagens do Exchange e o Lync Server para trabalhar em conjunto.</span><span class="sxs-lookup"><span data-stu-id="85adc-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="85adc-180">Habilite os usuários para atendimento de chamada de Unificação de mensagens do Exchange e Outlook Voice Access.</span><span class="sxs-lookup"><span data-stu-id="85adc-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="85adc-181">Esta tarefa é executada no servidor de Unificação de mensagens do Exchange.</span><span class="sxs-lookup"><span data-stu-id="85adc-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="85adc-182">Para obter detalhes, consulte a biblioteca do TechNet do Exchange [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)Server 2010 em.</span><span class="sxs-lookup"><span data-stu-id="85adc-182">For details, see the Exchange Server 2010 TechNet Library at [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

