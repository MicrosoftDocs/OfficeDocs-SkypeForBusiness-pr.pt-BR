---
title: Requisitos de conferência discada do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="65589-102">Requisitos de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65589-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65589-103">_**Tópico da última modificação:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="65589-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="65589-104">Antes de iniciar o processo de implantação do Lync Server 2013, você precisa planejar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="65589-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="65589-105">A configuração a ser usada para se conectar à rede telefônica pública comutada (PSTN)</span><span class="sxs-lookup"><span data-stu-id="65589-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="65589-106">Sua estratégia para atribuir regiões de conferência discada para números de acesso discado</span><span class="sxs-lookup"><span data-stu-id="65589-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="65589-107">Sua estratégia para a criação de diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="65589-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="65589-108">Planejando a conectividade de PSTN discada</span><span class="sxs-lookup"><span data-stu-id="65589-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="65589-109">A conferência discada requer pelo menos um servidor de mediação e pelo menos um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="65589-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="65589-110">Você pode implantar um Servidor de Mediação em um site central ou em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="65589-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="65589-111">No site central, você pode colocar um Servidor de Mediação em um Pool de Front-Ends ou servidor Standard Edition, ou pode implantá-lo em um servidor ou pool autônomo.</span><span class="sxs-lookup"><span data-stu-id="65589-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="65589-112">Em um site de filial, você pode implantar um Servidor de Mediação em um servidor autônomo ou como um componente do Aparelho de Filial Persistente.</span><span class="sxs-lookup"><span data-stu-id="65589-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="65589-p102">Você pode implantar um gateway PSTN em um site central ou em um site de filial. Em um site de filial, o gateway PSTN pode ser autônomo ou um componente do Aparelho de Filial Persistente.</span><span class="sxs-lookup"><span data-stu-id="65589-p102">You can deploy a PSTN gateway in a central site or in a branch site. In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65589-115">A conferência discada não usa o bypass de mídia porque o/V Conferência Server não é compatível com o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="65589-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="65589-116">Para obter detalhes sobre como planejar a configuração do servidor de mediação e dos gateways PSTN para conferência discada, consulte [componentes e topologias do servidor de mediação no Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="65589-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="65589-117">Planejando regiões de conferência discada</span><span class="sxs-lookup"><span data-stu-id="65589-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="65589-118">Durante a configuração de discagem, crie planos de discagem e números de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="65589-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="65589-119">Os planos de discagem são conjuntos de regras de normalização que especificam o número e o padrão de dígitos em um número de telefone e convertem o número de telefone no formato padrão E. 164 para roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="65589-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="65589-120">Números de acesso de conferência discada são os números para os quais os participantes ligam para entrar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="65589-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="65589-121">Todo número de acesso de conferência discada deve ser associado a no mínimo um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="65589-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="65589-122">Regiões de conferência discada associe um número de acesso à conferência discada com seus planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="65589-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="65589-123">Ao configurar um plano de discagem, especifique a região de conferência discada que se aplica ao plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="65589-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="65589-124">Ao criar o número de acesso de discagem, selecione as regiões que associam o número de acesso aos planos de discagem apropriados.</span><span class="sxs-lookup"><span data-stu-id="65589-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="65589-125">Quando você cria um plano de discagem, especifica o escopo do plano de discagem: escopo do usuário, escopo do pool ou escopo do site.</span><span class="sxs-lookup"><span data-stu-id="65589-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="65589-126">Todo usuário é atribuído ao plano de discagem do escopo mais estreito que se aplicar a ele.</span><span class="sxs-lookup"><span data-stu-id="65589-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="65589-127">Por exemplo, um usuário é atribuído a um plano de discagem de nível de usuário, caso um se aplique.</span><span class="sxs-lookup"><span data-stu-id="65589-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="65589-128">Se um plano de discagem de nível de usuário não se aplicar, o usuário é atribuído a um plano de discagem de nível de pool.</span><span class="sxs-lookup"><span data-stu-id="65589-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="65589-129">Se um plano de discagem de nível de pool não se aplicar, o usuário é atribuído a um plano de discagem de nível de site.</span><span class="sxs-lookup"><span data-stu-id="65589-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="65589-130">Se um plano de discagem de nível de site não se aplicar, o usuário é atribuído ao plano de discagem global.</span><span class="sxs-lookup"><span data-stu-id="65589-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="65589-p106">Antes de configurar os planos de discagem, é importante planejar como você deseja nomear e usar regiões. As considerações a seguir aplicam-se a regiões de conferência discada:</span><span class="sxs-lookup"><span data-stu-id="65589-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="65589-133">Uma região normalmente é uma área geográfica associada a um escritório ou grupo de escritórios.</span><span class="sxs-lookup"><span data-stu-id="65589-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="65589-p107">Idiomas são associados a números de acesso de discagem. Se você oferecer suporte a áreas geográficas que possuam vários idiomas, deve decidir como deseja definir regiões para oferecer suporte a vários idiomas. Por exemplo, você pode definir várias regiões com base em uma combinação de geografia e idioma ou pode definir uma única região com base em geografia e ter diferentes números de acesso de discagem para cada idioma.</span><span class="sxs-lookup"><span data-stu-id="65589-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="65589-137">Quando um usuário agenda uma reunião, por padrão a reunião usa a região especificada pelo plano de discagem do usuário.</span><span class="sxs-lookup"><span data-stu-id="65589-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="65589-138">Por padrão, todos os números de acesso discada da região estão incluídos no convite da reunião.</span><span class="sxs-lookup"><span data-stu-id="65589-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="65589-139">É importante nomear regiões para que sejam claramente reconhecíveis.</span><span class="sxs-lookup"><span data-stu-id="65589-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="65589-140">O usuário pode usar estes nomes das regiões para alterar a região de uma reunião, para que diferentes números de acesso sejam incluídos no convite.</span><span class="sxs-lookup"><span data-stu-id="65589-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="65589-141">(Quando os usuários usam o Outlook para agendar uma reunião, o usuário usa o suplemento de reunião online para o Lync 2013 para alterar a região).</span><span class="sxs-lookup"><span data-stu-id="65589-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="65589-142">Regiões devem ser criadas para que qualquer convidado que deseje discar para uma conferência possa ver um número de acesso local no convite da conferência.</span><span class="sxs-lookup"><span data-stu-id="65589-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="65589-143">Você pode configurar a ordem em que os números de acesso dentro de uma região aparecem na página de configurações da conferência discada (e, portanto, a ordem em que aparecem no convite de conferência) usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65589-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="65589-144">Qualquer usuário de qualquer localização pode ligar para qualquer número de acesso de discagem para entrar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="65589-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="65589-145">Planejando pastas de conferência</span><span class="sxs-lookup"><span data-stu-id="65589-145">Planning for Conference Directories</span></span>

<span data-ttu-id="65589-146">As pastas de conferência mantêm um mapeamento entre a ID de reunião alfanumérica que um participante usa para ingressar em uma conferência ao usar o Lync 2013 e a ID de conferência somente numérico que um participante de conferência discada usa para participar da conferência.</span><span class="sxs-lookup"><span data-stu-id="65589-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="65589-147">O formato do ID de conferência é como segue:</span><span class="sxs-lookup"><span data-stu-id="65589-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="65589-148">Criar vários diretórios de conferência garantirá que os IDs de conferência sejam curtos até que uma quantidade significativa de conferências seja criada.</span><span class="sxs-lookup"><span data-stu-id="65589-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="65589-149">Em uma organização com um número comum de conferências por usuário, recomendamos criar um diretório de conferência para cada 999 usuários no pool.</span><span class="sxs-lookup"><span data-stu-id="65589-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="65589-150">Usando esta diretriz, as IDs de conferência geralmente podem ser mantidas pequenas.</span><span class="sxs-lookup"><span data-stu-id="65589-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="65589-151">No entanto, assim que o número de diretórios de conferência (em todos os pools) ultrapassar 9, o número do ID de conferência aumentará para suportar conferências adicionais.</span><span class="sxs-lookup"><span data-stu-id="65589-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65589-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="65589-152">See Also</span></span>


[<span data-ttu-id="65589-153">Componente servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65589-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="65589-154">Planos de discagem e regras de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65589-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

