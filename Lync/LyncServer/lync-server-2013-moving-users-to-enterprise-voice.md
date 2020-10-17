---
title: 'Lync Server 2013: movendo usuários para o Enterprise Voice'
description: 'Lync Server 2013: movendo usuários para o Enterprise Voice.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41b075f916f4d81d8d3c24c24c7393be58e10a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542007"
---
# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="edd19-103">Movendo usuários para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edd19-103">Moving users to Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edd19-104">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="edd19-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="edd19-105">Se você estiver movendo usuários de uma infraestrutura de telefonia PBX existente para o Enterprise Voice, o processo de implantação incluirá algumas etapas que não fazem parte do processo de planejamento já descrito no [Planning for Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="edd19-105">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="edd19-106">Para informações sobre a migração de usuários de uma implantação anterior do Enterprise Voice, consulte os documentos de migração incluídos na sua mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="edd19-106">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="edd19-107">O processo de migração dos usuários de uma infraestrutura de telefonia existente para o Enterprise Voice consiste nas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="edd19-107">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="edd19-108">Designar números de telefone principais.</span><span class="sxs-lookup"><span data-stu-id="edd19-108">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="edd19-109">Habilitar usuários para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="edd19-109">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="edd19-110">Preparar planos de discagem para os usuários.</span><span class="sxs-lookup"><span data-stu-id="edd19-110">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="edd19-111">Planejar as políticas de voz dos usuários.</span><span class="sxs-lookup"><span data-stu-id="edd19-111">Plan user voice policies.</span></span>

5.  <span data-ttu-id="edd19-112">Planejar rotas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="edd19-112">Plan call routes.</span></span>

6.  <span data-ttu-id="edd19-113">Configurar o PBX ou Tronco SIP para rerotear chamadas para usuários habilitados para o  Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="edd19-113">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="edd19-114">Mover usuários para a Unificação de mensagens (UM) do Exchange (recomendado).</span><span class="sxs-lookup"><span data-stu-id="edd19-114">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="edd19-115">Este tópico descreve o planejamento necessário em cada uma dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="edd19-115">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="edd19-p102">Etapa 1. Designar números de telefone principais</span><span class="sxs-lookup"><span data-stu-id="edd19-p102">Step 1. Designate primary phone numbers</span></span>

<span data-ttu-id="edd19-p103">O Enterprise Voice integra voz a outras mídias de mensagens de forma que, quando uma chamada recebida chega ao servidor, o servidor mapeia o número para o URI do SIP do usuário e, em seguida, bifurca a chamada para todos os pontos de extremidade do cliente associados a esse URI do SIP. Esse processo exige que cada usuário esteja associado a um número de telefone principal.</span><span class="sxs-lookup"><span data-stu-id="edd19-p103">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI. This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="edd19-120">Um número de telefone principal deve ser:</span><span class="sxs-lookup"><span data-stu-id="edd19-120">A primary phone number must be:</span></span>

  - <span data-ttu-id="edd19-121">Globalmente exclusivo ou, no caso de ramais internos, exclusivo na empresa.</span><span class="sxs-lookup"><span data-stu-id="edd19-121">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="edd19-p104">Próprio da empresa e roteável. Números pessoais não devem ser usados.</span><span class="sxs-lookup"><span data-stu-id="edd19-p104">Owned by and routable in the enterprise. Personal numbers should not be used.</span></span>

<span data-ttu-id="edd19-124">Os usuários da empresa podem ter dois ou mais números de telefone listados para eles nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="edd19-124">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="edd19-125">Todos os números de telefone associados a um usuário específico podem ser exibidos ou alterados na respectiva folha de propriedades no snap-in Usuários e Computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="edd19-125">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="edd19-p106">A caixa **Número de telefone** na guia **Geral** da caixa de diálogo **Propriedades do Usuário** deve conter o número de trabalho principal do usuário. Normalmente, esse número é designado como o número de telefone principal do usuário.</span><span class="sxs-lookup"><span data-stu-id="edd19-p106">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number. This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="edd19-128">Alguns usuários podem ter requisitos especiais (como um executivo que deseja que as chamadas recebidas sejam roteadas por um assistente administrativo), mas essas exceções devem ser limitadas somente àquelas nas quais a necessidade seja clara e crítica.</span><span class="sxs-lookup"><span data-stu-id="edd19-128">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="edd19-129">Após a escolha do número principal, ele deverá ser:</span><span class="sxs-lookup"><span data-stu-id="edd19-129">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="edd19-130">Normalizado no formato E.164, sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="edd19-130">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="edd19-131">Copiado para o atributo **msRTCSIP-line** do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="edd19-131">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="edd19-132"><STRONG>Coexistência com o RCC (controle de chamada remota).</STRONG></span><span class="sxs-lookup"><span data-stu-id="edd19-132"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="edd19-133">O RCC é a capacidade de usar o Lync Server para monitorar e controlar um telefone de PBX de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="edd19-133">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="edd19-134">O controle é roteado pelo servidor, que atua como um gateway para o PBX.</span><span class="sxs-lookup"><span data-stu-id="edd19-134">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="edd19-135">Embora você não possa configurar um usuário para ambos, RCC e Enterprise Voice, a configuração do URI de Linha designa o número de telefone principal do usuário em ambos os casos.</span><span class="sxs-lookup"><span data-stu-id="edd19-135">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="edd19-136">Se você tem uma infraestrutura de PBX existente que deseja que usuários selecionados continuem usando, pode introduzir o Enterprise Voice de forma incremental na sua organização.</span><span class="sxs-lookup"><span data-stu-id="edd19-136">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="edd19-137">Para obter detalhes sobre esse cenário de implantação, consulte <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP Deployment Options in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="edd19-137">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="edd19-138">Em versões anteriores, você pode habilitar o RCC e o Enterprise Voice para um usuário, mas apenas se você também configurou o usuário para bifurcação dupla, um recurso no qual uma chamada de entrada tocará o telefone PBX do usuário e o Communicator simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="edd19-138">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="edd19-139">No Lync Server 2010, não há suporte para a bifurcação dupla.</span><span class="sxs-lookup"><span data-stu-id="edd19-139">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="edd19-140">Há três métodos para popular o atributo **msRTCSIP-line**:</span><span class="sxs-lookup"><span data-stu-id="edd19-140">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="edd19-141">Microsoft Identity Integration Server (recomendado)</span><span class="sxs-lookup"><span data-stu-id="edd19-141">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="edd19-142">A página **usuários** no painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="edd19-142">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="edd19-143">Onde muitos números de telefone devem ser processados, um script personalizado desenvolvido pela sua organização é a melhor opção.</span><span class="sxs-lookup"><span data-stu-id="edd19-143">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="edd19-144">Dependendo de como a organização representa os números de telefone nos Serviços de Domínio Active Directory, o script talvez precise normalizar números de telefone principais no formato E.164 antes de copiá-los para o atributo **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="edd19-144">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="edd19-145">Se a sua organização mantém todos os números de telefone dos Serviços de Domínio Active Directory em um único formato, e se esse formato é o E.164, então o script só precisará gravar cada número de telefone principal no atributo **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="edd19-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="edd19-146">Se a sua organização mantém todos os números de telefone dos Serviços de Domínio Active Directory em um único formato, mas esse formato não é o E.164, o script deverá definir uma regra de normalização apropriada para converter os números de telefone principais do formato existente no formato E.164, antes de gravá-los no atributo **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="edd19-146">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="edd19-147">Se a sua organização não impõe um formato padrão aos números de telefone dos Serviços de Domínio Active Directory, o script deverá definir regras de normalização apropriadas para converter os números de telefone principais dos vários formatos existentes no formato E.164, antes de gravá-los no atributo **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="edd19-147">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="edd19-148">Seu script também deverá inserir o prefixo **Tel:** antes de cada número principal antes de gravá-lo no atributo **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="edd19-148">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="edd19-149">O formato esperado do número especificado nesse atributo é:</span><span class="sxs-lookup"><span data-stu-id="edd19-149">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="edd19-150">Tel: + 14255550100; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="edd19-150">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="edd19-151">Tel:5550100 (para ramais exclusivos na empresa toda).</span><span class="sxs-lookup"><span data-stu-id="edd19-151">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="edd19-152">A normalização realizada pelo ABS (Serviço de Catálogo de Endereços) não substitui nem elimina a necessidade de normalizar o número de telefone principal de cada usuário nos Serviços de Domínio Active Directory, pois o ABS não tem acesso aos Serviços de Domínio Active Directory e, portanto, não pode copiar números de telefone principais para o atributo <STRONG>msRTCSIP-line</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="edd19-152">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="edd19-p111">Etapa 2. Habilitar usuários para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="edd19-p111">Step 2. Enable users for Enterprise Voice</span></span>

<span data-ttu-id="edd19-155">Além de identificar os usuários que devem ser habilitados, nenhum outro planejamento especial é necessário para concluir esta etapa.</span><span class="sxs-lookup"><span data-stu-id="edd19-155">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="edd19-p112">Etapa 3. Preparar planos de discagem para os usuários.</span><span class="sxs-lookup"><span data-stu-id="edd19-p112">Step 3. Prepare dial plans for users.</span></span>

<span data-ttu-id="edd19-p113">Usuários que estão habilitados para o Enterprise Voice não conseguirão fazer chamadas para o PSTN sem planos de discagem. Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um formato padrão único (E.164) para fins de roteamento de chamadas e autorização. Regras de normalização definem como números de telefone expressos em vários formatos serão roteados para cada local, usuário ou objeto de contato especificado.</span><span class="sxs-lookup"><span data-stu-id="edd19-p113">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place. A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing. Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="edd19-161">Para obter informações sobre como preparar planos de discagem, consulte [Dial Plans and Normalization Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="edd19-161">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="edd19-162">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="edd19-162">Step 4.</span></span> <span data-ttu-id="edd19-163">Planejar as políticas de voz dos usuários</span><span class="sxs-lookup"><span data-stu-id="edd19-163">Plan user voice policies</span></span>

<span data-ttu-id="edd19-164">Configurações de serviço de classe do usuário em um PBX herdado, como o direito de fazer chamadas de longa distância ou internacionais a partir dos telefones da empresa, devem ser reconfigurados como políticas de VoIP para usuários movidos para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="edd19-164">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="edd19-165">Para obter detalhes sobre como planejar e criar políticas para o Enterprise Voice, consulte [Voice Policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="edd19-165">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="edd19-166">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="edd19-166">Step 5.</span></span> <span data-ttu-id="edd19-167">Planejar rotas de chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="edd19-167">Plan outbound call routes</span></span>

<span data-ttu-id="edd19-168">As rotas de chamada especificam como o Lync Server trata as chamadas de saída feitas por usuários do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="edd19-168">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="edd19-169">Quando um usuário disca para um número, o servidor, se necessário, normaliza a cadeia de caracteres de discagem para o formato E.164 e tenta compará-lo com um URI de SIP.</span><span class="sxs-lookup"><span data-stu-id="edd19-169">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="edd19-170">Se o servidor não conseguir a correspondência, aplica o roteamento de chamada de saída com base no número.</span><span class="sxs-lookup"><span data-stu-id="edd19-170">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="edd19-171">A etapa final em definir a lógica é criar uma rota de chamada nomeada separada para cada conjunto de números de telefone de destino que esteja listado em cada plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="edd19-171">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="edd19-172">Para obter detalhes sobre como planejar rotas de chamada, consulte [rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="edd19-172">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="edd19-173">Etapa 6.</span><span class="sxs-lookup"><span data-stu-id="edd19-173">Step 6.</span></span> <span data-ttu-id="edd19-174">Configurar o PBX ou Tronco SIP para rerotear chamadas para usuários do Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="edd19-174">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="edd19-175">Usuários que anteriormente eram hospedados em uma conexão PBX ou Tronco SIP tradicional com um Provedor de Serviços de Telefonia de Internet (ITSP) mantêm seus números de telefone depois da mudança.</span><span class="sxs-lookup"><span data-stu-id="edd19-175">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="edd19-176">O único requisito é que após a movimentação, o PBX ou tronco SIP deve ser reconfigurado para rotear as chamadas de entrada para usuários do Enterprise Voice para o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="edd19-176">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="edd19-p120">Etapa 7. Mover usuários para a Unificação de Mensagens do Exchange (recomendado)</span><span class="sxs-lookup"><span data-stu-id="edd19-p120">Step 7. Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="edd19-179">Mover usuários para a Unificação de Mensagens do Exchange consiste das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="edd19-179">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="edd19-180">Configure a Unificação de mensagens do Exchange e o Lync Server para trabalhar juntos.</span><span class="sxs-lookup"><span data-stu-id="edd19-180">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="edd19-181">Habilitar os usuários para atender chamadas pela Unificação de Mensagens do Exchange e para o Outlook Voice Access.</span><span class="sxs-lookup"><span data-stu-id="edd19-181">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="edd19-182">Esta tarefa é executada no servidor de Unificação de Mensagens do Exchange.</span><span class="sxs-lookup"><span data-stu-id="edd19-182">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="edd19-183">Para obter detalhes, consulte a Biblioteca TechNet do Exchange Server 2010 em [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372) .</span><span class="sxs-lookup"><span data-stu-id="edd19-183">For details, see the Exchange Server 2010 TechNet Library at [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

