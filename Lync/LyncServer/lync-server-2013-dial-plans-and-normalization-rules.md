---
title: 'Lync Server 2013: planos de discagem e regras de normalização'
description: 'Lync Server 2013: planos de discagem e regras de normalização.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0341d0c5267a2272ff45bd93408b2bd14f0ceeaa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559737"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="9569c-103">Planos de discagem e regras de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9569c-103">Dial plans and normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9569c-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9569c-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9569c-105">Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um formato padrão único (E.164) para fins de roteamento de chamadas e autorização.</span><span class="sxs-lookup"><span data-stu-id="9569c-105">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="9569c-106">As regras de normalização definem como os números de telefone expressos em vários formatos devem ser roteados para cada local, usuário ou objeto de contato especificado.</span><span class="sxs-lookup"><span data-stu-id="9569c-106">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="9569c-107">A mesma cadeia de caracteres de discagem pode ser interpretada e convertida de forma diferente, dependendo do local de onde é discada e do objeto de contato ou pessoa que está fazendo a chamada.</span><span class="sxs-lookup"><span data-stu-id="9569c-107">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="9569c-108">Escopo do plano de discagem</span><span class="sxs-lookup"><span data-stu-id="9569c-108">Dial Plan Scope</span></span>

<span data-ttu-id="9569c-109">Um \*escopo \* do plano de discagem determina o nível hierárquico no qual o plano de discagem pode ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="9569c-109">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="9569c-110">No Lync Server, um usuário pode ser atribuído a um plano de discagem específico por usuário.</span><span class="sxs-lookup"><span data-stu-id="9569c-110">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="9569c-111">Se um plano de discagem do usuário não for atribuído, o plano de discagem do pool do Registrador é aplicado.</span><span class="sxs-lookup"><span data-stu-id="9569c-111">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="9569c-112">Se não houver nenhum plano de discagem do pool do Registrador, o plano de discagem local é aplicado.</span><span class="sxs-lookup"><span data-stu-id="9569c-112">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="9569c-113">Finalmente, se nenhum plano de discagem é aplicável para o usuário, o plano de discagem global é aplicado.</span><span class="sxs-lookup"><span data-stu-id="9569c-113">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="9569c-114">Os clientes obtêm níveis de escopo do plano de discagem por meio de configurações de provisionamento em banda fornecidas quando os usuários fazem logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9569c-114">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="9569c-115">Como administrador, você pode gerenciar e atribuir níveis de escopo do plano de discagem usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9569c-115">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9569c-116">O plano de discagem de gateway PSTN (rede telefônica pública comutada) de nível de serviço é aplicado às chamadas de entrada de um gateway específico.</span><span class="sxs-lookup"><span data-stu-id="9569c-116">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="9569c-117">Os níveis de escopo do plano de discagem são definidos como a seguir:</span><span class="sxs-lookup"><span data-stu-id="9569c-117">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="9569c-118">**Plano de discagem do usuário:** Podem ser atribuídos a usuários individuais, grupos ou objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="9569c-118">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="9569c-119">Os aplicativos de voz podem pesquisar um plano de discagem por usuário quando uma chamada é recebida com o contexto de telefone definido como user-default.</span><span class="sxs-lookup"><span data-stu-id="9569c-119">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="9569c-120">Para o propósito de atribuir um plano de discagem, um objeto de contato é tratado como um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="9569c-120">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="9569c-121">**Plano de discagem do pool:** Pode ser criado no nível de serviço para qualquer gateway PSTN ou registrador em sua topologia.</span><span class="sxs-lookup"><span data-stu-id="9569c-121">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="9569c-122">Para definir um plano de discagem do pool, você deve especificar o serviço (gateway PSTN ou pool do Registrador) ao qual o plano de discagem se aplica.</span><span class="sxs-lookup"><span data-stu-id="9569c-122">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="9569c-123">**Plano de discagem de site:** Pode ser criado para um site inteiro, exceto para qualquer usuário, grupo ou objeto de contato que receba um plano de discagem do pool ou um plano de discagem do usuário.</span><span class="sxs-lookup"><span data-stu-id="9569c-123">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="9569c-124">Para definir um plano de discagem local, você deve especificar o local ao qual o plano de discagem é aplicado.</span><span class="sxs-lookup"><span data-stu-id="9569c-124">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="9569c-125">**Plano de discagem global:** O plano de discagem padrão instalado com o produto.</span><span class="sxs-lookup"><span data-stu-id="9569c-125">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="9569c-126">É possível editar o plano de discagem global, mas não exclui-lo.</span><span class="sxs-lookup"><span data-stu-id="9569c-126">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="9569c-127">Este plano de discagem se aplica a todos os usuários, grupos e objetos de contato do Enterprise Voice em sua implantação, a menos que você configure e atribua um plano de discagem com um escopo mais específico.</span><span class="sxs-lookup"><span data-stu-id="9569c-127">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="9569c-128">Planejamento de planos de discagem</span><span class="sxs-lookup"><span data-stu-id="9569c-128">Planning for Dial Plans</span></span>

<span data-ttu-id="9569c-129">Para planejar um plano de discagem, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9569c-129">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="9569c-130">Listar todos os locais nos quais sua organização tem um escritório.</span><span class="sxs-lookup"><span data-stu-id="9569c-130">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="9569c-131">A lista deve estar atualizada e concluída.</span><span class="sxs-lookup"><span data-stu-id="9569c-131">The list must be up-to-date and complete.</span></span> <span data-ttu-id="9569c-132">Precisará ser revisada conforme a organização da empresa evolui.</span><span class="sxs-lookup"><span data-stu-id="9569c-132">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="9569c-133">Em uma grande empresa multinacional com numerosas pequenas filiais, essa pode ser uma tarefa demorada.</span><span class="sxs-lookup"><span data-stu-id="9569c-133">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="9569c-134">Identificar padrões de números válidos para cada site.</span><span class="sxs-lookup"><span data-stu-id="9569c-134">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="9569c-p109">A parte mais demorada do planejamento de seus planos de discagem é identificar os padrões de números válidos para cada local. Em alguns casos, será possível copiar as regras de normalização gravadas para um plano de discagem a outros planos de discagem, especialmente se os locais correspondentes estão dentro do mesmo país/região ou continente. Em outros casos, as pequenas alterações em números em um plano de discagem podem ser suficientes para usá-los em outros planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="9569c-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="9569c-138">Desenvolva um esquema em toda a organização para os planos de discagem de nomeação.</span><span class="sxs-lookup"><span data-stu-id="9569c-138">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="9569c-139">Adotar um esquema de nomeação padrão garante a consistência em toda a organização e facilita a manutenção e as atualizações.</span><span class="sxs-lookup"><span data-stu-id="9569c-139">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="9569c-140">Decida se vários planos de discagem são necessários para um único local.</span><span class="sxs-lookup"><span data-stu-id="9569c-140">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="9569c-141">Se sua organização mantém um único plano de discagem entre vários locais, talvez ainda seja necessário criar um plano de discagem separado para usuários do Enterprise Voice que estão migrando de um PBX (central privada de comutação telefônica) e que precisam ter suas extensões existentes retidas.</span><span class="sxs-lookup"><span data-stu-id="9569c-141">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="9569c-142">Decida se são necessários planos de discagem por usuário.</span><span class="sxs-lookup"><span data-stu-id="9569c-142">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="9569c-143">Por exemplo, se você tiver usuários em um site de filial registrados com o site central ou se tiver usuários registrados em um aparelho de filial persistente, você pode considerar cenários de discagem especiais para tais usuários usando planos de discagem por usuário e regras de normalização.</span><span class="sxs-lookup"><span data-stu-id="9569c-143">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="9569c-144">Para obter detalhes, consulte [Branch-site resiliência Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9569c-144">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="9569c-145">Determine o escopo do plano de discagem (como descrito anteriormente neste tópico).</span><span class="sxs-lookup"><span data-stu-id="9569c-145">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="9569c-146">Para criar um plano de discagem, especifique valores nos campos a seguir, conforme necessário, usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9569c-146">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="9569c-147">Nome e o nome simples</span><span class="sxs-lookup"><span data-stu-id="9569c-147">Name and Simple Name</span></span>

<span data-ttu-id="9569c-148">Para planos de discagem do usuário, você deve especificar um nome descritivo que identifique os usuários, grupos ou objetos de contato aos quais o plano de discagem será atribuído.</span><span class="sxs-lookup"><span data-stu-id="9569c-148">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="9569c-149">Para planos de discagem local, o campo Nome é preenchido com o nome do local e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="9569c-149">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="9569c-150">Para planos de discagem do pool, o campo nome é preenchido previamente com o gateway PSTN ou FQDN (nome de domínio totalmente qualificado) do pool de front-end e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="9569c-150">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="9569c-151">O *Nome simples* do plano de discagem é preenchido com uma sequência derivada do nome do plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="9569c-151">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="9569c-152">O campo nome simples é editável, o que permite que você crie uma Convenção de nomenclatura mais descritiva para os planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="9569c-152">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="9569c-153">O valor \*Nome simples \* não pode estar vazio e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="9569c-153">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="9569c-154">Uma prática recomendada é desenvolver uma Convenção de nomenclatura para toda a sua organização e, em seguida, usar essa Convenção de forma consistente em todos os sites e usuários.</span><span class="sxs-lookup"><span data-stu-id="9569c-154">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="9569c-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="9569c-155">Description</span></span>

<span data-ttu-id="9569c-p113">Recomendamos digitar o nome comum reconhecível da localização geográfica à qual se aplica o plano de discagem correspondente. Por exemplo, se o nome do plano de discagem for Londres.Contoso.com, a descrição recomendada seria Londres.</span><span class="sxs-lookup"><span data-stu-id="9569c-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="9569c-158">Região da conferência discada</span><span class="sxs-lookup"><span data-stu-id="9569c-158">Dial-in Conferencing Region</span></span>

<span data-ttu-id="9569c-159">Se você estiver implantando a conferência discada, precisará especificar uma região de conferência de discagem para associar os números de acesso da conferência discada com um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="9569c-159">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="9569c-160">Prefixo de acesso externo</span><span class="sxs-lookup"><span data-stu-id="9569c-160">External Access Prefix</span></span>

<span data-ttu-id="9569c-161">Você pode especificar um prefixo de acesso externo de até quatro caracteres ( \# , \* e 0-9) se os usuários precisarem discar um ou mais dígitos à esquerda adicionais (por exemplo, 9) para obter uma linha externa.</span><span class="sxs-lookup"><span data-stu-id="9569c-161">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9569c-162">Se você especificar um prefixo de acesso externo, não é necessário criar uma regra de normalização adicional para acomodar o prefixo.</span><span class="sxs-lookup"><span data-stu-id="9569c-162">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="9569c-163">Regras de normalização</span><span class="sxs-lookup"><span data-stu-id="9569c-163">Normalization Rules</span></span>

<span data-ttu-id="9569c-164">As regras de normalização definem como os números de telefone expressos em vários formatos devem ser roteados para o local nomeado.</span><span class="sxs-lookup"><span data-stu-id="9569c-164">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="9569c-165">A mesma cadeia de caracteres de número pode ser interpretada e convertida de forma diferente, dependendo da localidade da qual ela é discada.</span><span class="sxs-lookup"><span data-stu-id="9569c-165">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="9569c-166">As regras de normalização são necessárias para o roteamento de chamada porque os usuários podem, e devem, usar vários formatos ao inserir números de telefone em suas listas de contatos.</span><span class="sxs-lookup"><span data-stu-id="9569c-166">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="9569c-167">A normalização de números de telefone fornecidos pelo usuário oferece um formato consistente que facilita as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="9569c-167">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="9569c-168">Corresponde a um número discado para o SIP-URI do destinatário pretendido.</span><span class="sxs-lookup"><span data-stu-id="9569c-168">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="9569c-169">Aplicar regras de autorização de discagem à parte de chamada.</span><span class="sxs-lookup"><span data-stu-id="9569c-169">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="9569c-170">Estes são alguns dos campos numéricos que as regras de normalização talvez precisem considerar:</span><span class="sxs-lookup"><span data-stu-id="9569c-170">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="9569c-171">Plano de discagem</span><span class="sxs-lookup"><span data-stu-id="9569c-171">Dial plan</span></span>

  - <span data-ttu-id="9569c-172">Código do país</span><span class="sxs-lookup"><span data-stu-id="9569c-172">Country code</span></span>

  - <span data-ttu-id="9569c-173">Código de área</span><span class="sxs-lookup"><span data-stu-id="9569c-173">Area code</span></span>

  - <span data-ttu-id="9569c-174">Tamanho da extensão</span><span class="sxs-lookup"><span data-stu-id="9569c-174">Length of extension</span></span>

  - <span data-ttu-id="9569c-175">Prefixo do local</span><span class="sxs-lookup"><span data-stu-id="9569c-175">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="9569c-176">Criando regras de normalização</span><span class="sxs-lookup"><span data-stu-id="9569c-176">Creating Normalization Rules</span></span>

<span data-ttu-id="9569c-177">As regras de normalização usam expressões regulares do .NET Framework para especificar padrões de correspondência numérica que o servidor usa para converter sequências de discagem para o formato E.164 para fins de pesquisa de número inverso.</span><span class="sxs-lookup"><span data-stu-id="9569c-177">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="9569c-178">Você cria regras de normalização no painel de controle do Lync Server inserindo as expressões manualmente ou digitando os dígitos iniciais e o comprimento das cadeias de caracteres de discagem a serem atendidas e permitindo que o painel de controle do Lync Server gere a expressão regular correspondente para você.</span><span class="sxs-lookup"><span data-stu-id="9569c-178">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="9569c-179">De qualquer forma, ao terminar, você pode inserir um número de teste para verificar se a regra de normalização funciona como esperado.</span><span class="sxs-lookup"><span data-stu-id="9569c-179">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="9569c-180">Para obter detalhes sobre o uso de expressões regulares do .NET Framework, consulte "expressões regulares do .NET Framework" em [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="9569c-180">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="9569c-181">Exemplos de regras de normalização</span><span class="sxs-lookup"><span data-stu-id="9569c-181">Sample Normalization Rules</span></span>

<span data-ttu-id="9569c-p116">A tabela a seguir mostra exemplos de regras de normalização que são gravadas como expressões reguladores do .NET Framework. São apenas exemplos e não deve ser uma referência prescritiva para a criação de regras de normalização.</span><span class="sxs-lookup"><span data-stu-id="9569c-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="9569c-184">Tabela 1. Regras de normalização usando expressões regulares do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9569c-184">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

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
<th><span data-ttu-id="9569c-185">Nome da regra</span><span class="sxs-lookup"><span data-stu-id="9569c-185">Rule name</span></span></th>
<th><span data-ttu-id="9569c-186">Descrição</span><span class="sxs-lookup"><span data-stu-id="9569c-186">Description</span></span></th>
<th><span data-ttu-id="9569c-187">Padrão de número</span><span class="sxs-lookup"><span data-stu-id="9569c-187">Number pattern</span></span></th>
<th><span data-ttu-id="9569c-188">Tradução</span><span class="sxs-lookup"><span data-stu-id="9569c-188">Translation</span></span></th>
<th><span data-ttu-id="9569c-189">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9569c-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9569c-190">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="9569c-190">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="9569c-191">Converte extensões de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="9569c-191">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="9569c-192">^ (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="9569c-192">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="9569c-193">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="9569c-193">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="9569c-194">0100 é convertido em +14255550100</span><span class="sxs-lookup"><span data-stu-id="9569c-194">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9569c-195">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="9569c-195">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="9569c-196">Converte extensões de 5 dígitos</span><span class="sxs-lookup"><span data-stu-id="9569c-196">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="9569c-197">^ 5 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="9569c-197">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="9569c-198">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="9569c-198">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="9569c-199">50100 é convertido em +14255550100</span><span class="sxs-lookup"><span data-stu-id="9569c-199">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9569c-200">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="9569c-200">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="9569c-201">Converte números de 7 dígitos para números locais de Redmond</span><span class="sxs-lookup"><span data-stu-id="9569c-201">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="9569c-202">^ (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="9569c-202">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="9569c-203">+ 1425 $1</span><span class="sxs-lookup"><span data-stu-id="9569c-203">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="9569c-204">5550100 é convertido em +14255550100</span><span class="sxs-lookup"><span data-stu-id="9569c-204">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9569c-205">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="9569c-205">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="9569c-206">Converte números de 7 dígitos para números locais de Dallas</span><span class="sxs-lookup"><span data-stu-id="9569c-206">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="9569c-207">^ (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="9569c-207">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="9569c-208">+ 1972 $1</span><span class="sxs-lookup"><span data-stu-id="9569c-208">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="9569c-209">5550100 é convertido em +19725550100</span><span class="sxs-lookup"><span data-stu-id="9569c-209">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9569c-210">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="9569c-210">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="9569c-211">Converte números de 10 dígitos nos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="9569c-211">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="9569c-212">^ (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="9569c-212">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="9569c-213">+ 1 $1</span><span class="sxs-lookup"><span data-stu-id="9569c-213">+1$1</span></span></p></td>
<td><p><span data-ttu-id="9569c-214">2065550100 é convertido em +12065550100</span><span class="sxs-lookup"><span data-stu-id="9569c-214">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9569c-215">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="9569c-215">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="9569c-216">Converte números com prefixos de longa distância nos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="9569c-216">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="9569c-217">^ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="9569c-217">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="9569c-218">+ $1</span><span class="sxs-lookup"><span data-stu-id="9569c-218">+$1</span></span></p></td>
<td><p><span data-ttu-id="9569c-219">12145550100 é convertido em +2145550100</span><span class="sxs-lookup"><span data-stu-id="9569c-219">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9569c-220">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="9569c-220">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="9569c-221">Converte números com prefixos internacionais nos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="9569c-221">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="9569c-222">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="9569c-222">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="9569c-223">+ $1</span><span class="sxs-lookup"><span data-stu-id="9569c-223">+$1</span></span></p></td>
<td><p><span data-ttu-id="9569c-224">01191445550100 é convertido em +91445550100</span><span class="sxs-lookup"><span data-stu-id="9569c-224">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9569c-225">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="9569c-225">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="9569c-226">Converte 0 no operador de Redmond</span><span class="sxs-lookup"><span data-stu-id="9569c-226">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="9569c-227">^ $0</span><span class="sxs-lookup"><span data-stu-id="9569c-227">^0$</span></span></p></td>
<td><p><span data-ttu-id="9569c-228">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="9569c-228">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="9569c-229">0 é convertido em +14255550100</span><span class="sxs-lookup"><span data-stu-id="9569c-229">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9569c-230">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="9569c-230">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="9569c-231">Converte números com o prefixo dentro da rede (6) e o código de área de Redmond (222)</span><span class="sxs-lookup"><span data-stu-id="9569c-231">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="9569c-232">^ 6222 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="9569c-232">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="9569c-233">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="9569c-233">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="9569c-234">62220100 é convertido em +14255550100</span><span class="sxs-lookup"><span data-stu-id="9569c-234">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9569c-235">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="9569c-235">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="9569c-236">Converte números com o prefixo dentro da rede (6) e o código de área de Nova York (333)</span><span class="sxs-lookup"><span data-stu-id="9569c-236">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="9569c-237">^ 6333 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="9569c-237">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="9569c-238">+ 1202555 $1</span><span class="sxs-lookup"><span data-stu-id="9569c-238">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="9569c-239">63330100 é convertido em +12025550100</span><span class="sxs-lookup"><span data-stu-id="9569c-239">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9569c-240">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="9569c-240">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="9569c-241">Converte números com o prefixo dentro da rede (6) e o código de área de Dallas (444)</span><span class="sxs-lookup"><span data-stu-id="9569c-241">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="9569c-242">^ 6444 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="9569c-242">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="9569c-243">+ 1972555 $1</span><span class="sxs-lookup"><span data-stu-id="9569c-243">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="9569c-244">64440100 é convertido em +19725550100</span><span class="sxs-lookup"><span data-stu-id="9569c-244">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9569c-245">A tabela a seguir ilustra um exemplo de plano de discagem para Redmond, Washington, Estados Unidos, baseado nas regras de normalização mostradas na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="9569c-245">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="9569c-p117">Tabela 2. Plano de discagem de Redmond com base em regras de normalização mostradas na Tabela 1</span><span class="sxs-lookup"><span data-stu-id="9569c-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9569c-248">Redmond. forestFQDN</span><span class="sxs-lookup"><span data-stu-id="9569c-248">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9569c-249">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="9569c-249">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9569c-250">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="9569c-250">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9569c-251">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="9569c-251">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9569c-252">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="9569c-252">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9569c-253">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="9569c-253">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9569c-254">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="9569c-254">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9569c-255">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="9569c-255">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9569c-256">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="9569c-256">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="9569c-p118">Os nomes das regras de normalização mostrados na tabela anterior não incluem espaços, mas é uma questão de escolha. O primeiro nome da tabela, por exemplo, poderia ter sido escrito "extensão de 5 dígitos" ou "extensão de 5-dígitos" e ainda ser válido.</span><span class="sxs-lookup"><span data-stu-id="9569c-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

