---
title: 'Lync Server 2013: Políticas de correio de voz hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811f975868dad7bc0fcf6d5a2867ca2f3b81cd59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="993b6-102">Políticas de correio de voz hospedado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="993b6-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="993b6-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="993b6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="993b6-104">Uma *política de correio de voz hospedada* fornece informações para o aplicativo de roteamento ExUM do Lync Server 2013 sobre onde direcionar chamadas para usuários cujas caixas de correio estão localizadas em um serviço hospedado do Exchange.</span><span class="sxs-lookup"><span data-stu-id="993b6-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="993b6-105">As políticas de correio de voz hospedadas são necessárias somente para a integração do Lync Server 2013 com o Exchange UM hospedado.</span><span class="sxs-lookup"><span data-stu-id="993b6-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="993b6-106">Elas não são necessárias para integração com o Exchange UM local.</span><span class="sxs-lookup"><span data-stu-id="993b6-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="993b6-107">Escopo da política de caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="993b6-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="993b6-108">O escopo da política de caixa postal hospedada determina o nível hierárquico no qual a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="993b6-108">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="993b6-109">Você pode configurar políticas de caixa postal hospedadas com os seguintes níveis de escopo:</span><span class="sxs-lookup"><span data-stu-id="993b6-109">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="993b6-110">A política *global* pode potencialmente afetar todos os usuários na implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="993b6-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="993b6-111">Se um usuário estiver habilitado para acesso do Exchange UM hospedado e não tiver sido atribuída uma política por usuário e se uma política do site não foi atribuída ao site do usuário, a política global será aplicada.</span><span class="sxs-lookup"><span data-stu-id="993b6-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="993b6-112">A política global é instalada com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="993b6-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="993b6-113">Você pode modificá-la para atender às suas necessidades, mas não pode renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="993b6-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="993b6-114">Uma política de *site* pode afetar todos os usuários que estão hospedados no site para o qual a política está definida.</span><span class="sxs-lookup"><span data-stu-id="993b6-114">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="993b6-115">Se um usuário estiver configurado para acesso do Exchange UM hospedado e não tiver sido atribuída uma política por usuário, a política do site será aplicada.</span><span class="sxs-lookup"><span data-stu-id="993b6-115">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="993b6-116">Uma política *por usuário* pode afetar apenas usuários individuais ou grupos.</span><span class="sxs-lookup"><span data-stu-id="993b6-116">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="993b6-117">Para impor uma política por usuário, você deve explicitamente atribuir a política a usuários individuais, grupos e objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="993b6-117">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="993b6-118">Na maioria dos casos, apenas uma política de caixa postal hospedada é necessária.</span><span class="sxs-lookup"><span data-stu-id="993b6-118">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="993b6-119">Muitas vezes, você pode modificar a política global para atender a todas as suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="993b6-119">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="993b6-120">Se você implantar várias políticas de caixa postal hospedadas, todas essas políticas terão escopo por usuário.</span><span class="sxs-lookup"><span data-stu-id="993b6-120">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="993b6-121">Atributos hospedados da política de caixa postal</span><span class="sxs-lookup"><span data-stu-id="993b6-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="993b6-122">Uma política de caixa postal define dois atributos que o aplicativo de roteamento ExUM do Lync Server 2013 é inserido na URI de solicitação de uma mensagem de convite enviada para a implementação do Exchange UM hospedada:</span><span class="sxs-lookup"><span data-stu-id="993b6-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="993b6-123">**Destino:** O nome de domínio totalmente qualificado (FQDN) do serviço do Exchange UM hospedado.</span><span class="sxs-lookup"><span data-stu-id="993b6-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="993b6-124">Esse valor é usado pelo servidor de borda do Lync Server local para fins de roteamento.</span><span class="sxs-lookup"><span data-stu-id="993b6-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="993b6-125">O FQDN para Exchange Online é exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="993b6-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="993b6-126">**Organização:** O FQDN do locatário no serviço do Exchange UM hospedado que aloja as caixas de correio dos usuários do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="993b6-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="993b6-127">Uma política de caixa postal pode conter várias organizações.</span><span class="sxs-lookup"><span data-stu-id="993b6-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="993b6-128">Se mais de uma organização estiver incluída na política, esse atributo deve ser uma lista separada por vírgulas dos locatários do Exchange Server que hospedam suas caixas de correio de usuário do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="993b6-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="993b6-129">O administrador de locatário do seu serviço do Exchange UM hospedado fornecerá os valores necessários para as configurações de atributo de destino e organização.</span><span class="sxs-lookup"><span data-stu-id="993b6-129">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="993b6-130">Para configurar sua política, você deve executar o cmdlet New-CsHostedVoicemailPolicy ou usar o cmdlet Set-CsHostedVoicemailPolicy para modificar um que existe (por exemplo, a política global).</span><span class="sxs-lookup"><span data-stu-id="993b6-130">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="993b6-131">Para obter detalhes sobre o gerenciamento de políticas de caixa postal hospedadas, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="993b6-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="993b6-132">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="993b6-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="993b6-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="993b6-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="993b6-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="993b6-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="993b6-135">Atribuição de política de caixa postal por usuário</span><span class="sxs-lookup"><span data-stu-id="993b6-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="993b6-136">Se a sua política de caixa postal hospedada for definida com o escopo por usuário, você deverá atribuí-la explicitamente.</span><span class="sxs-lookup"><span data-stu-id="993b6-136">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="993b6-137">Você pode executar o cmdlet Grant-CsHostedVoicemailPolicy para atribuir a política a usuários individuais ou grupos.</span><span class="sxs-lookup"><span data-stu-id="993b6-137">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="993b6-138">Para obter detalhes sobre como atribuir ou remover uma política de correio de voz hospedada por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="993b6-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="993b6-139">Grant CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="993b6-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="993b6-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="993b6-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

