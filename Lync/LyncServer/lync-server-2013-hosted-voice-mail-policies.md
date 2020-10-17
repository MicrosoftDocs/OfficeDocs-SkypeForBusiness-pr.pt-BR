---
title: 'Lync Server 2013: políticas de caixa postal hospedadas'
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
ms.openlocfilehash: e72fd57b05e618f03382a19995beaf9c542dc859
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504168"
---
# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="0b561-102">Políticas de caixa postal hospedada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b561-102">Hosted voice mail policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b561-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0b561-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0b561-104">Uma *política de caixa postal hospedada* fornece informações para o aplicativo de roteamento ExUM do Lync Server 2013 sobre onde rotear chamadas para usuários cujas caixas de correio estão localizadas em um serviço do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="0b561-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b561-105">As políticas de caixa postal hospedadas são necessárias apenas para a integração do Lync Server 2013 com a UM do Exchange hospedada.</span><span class="sxs-lookup"><span data-stu-id="0b561-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="0b561-106">Elas não são necessárias para integração com UM do Exchange local.</span><span class="sxs-lookup"><span data-stu-id="0b561-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="0b561-107">Escopo da política de caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="0b561-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="0b561-p102">O escopo da política de caixa postal hospedada determina o nível hierárquico no qual a política é aplicada. É possível configurar as políticas de caixa postal hospedadas com os seguintes níveis de escopo:</span><span class="sxs-lookup"><span data-stu-id="0b561-p102">Hosted voice mail policy scope determines the hierarchical level at which the policy applies. You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="0b561-110">A política *global* pode potencialmente afetar todos os usuários na implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b561-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="0b561-111">Se um usuário for habilitado para acesso à UM do Exchange hospedada e não tiver recebido uma política por usuário, e se uma política de site não tiver sido atribuída ao site do usuário, a política global será aplicada.</span><span class="sxs-lookup"><span data-stu-id="0b561-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="0b561-112">A política global é instalada com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b561-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="0b561-113">É possível modificá-la para atender a suas necessidades, mas não é possível renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="0b561-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="0b561-p104">Uma política de *site* pode afetar todos os usuários hospedados no site para o qual a política foi definida. Se um usuário for configurado para receber acesso à UM do Exchange hospedada e não tiver recebido uma política por usuário, a política de site será aplicada.</span><span class="sxs-lookup"><span data-stu-id="0b561-p104">A *site* policy can affect all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="0b561-p105">Uma política *por usuário* pode afetar somente usuários ou grupos individuais. Para aplicar uma política por usuário, você precisa atribuir explicitamente a política a usuários individuais, grupos e objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="0b561-p105">A *per-user* policy can affect only individual users or groups. To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b561-p106">Na maioria dos casos, somente a política de caixa postal hospedada é necessário. É possível modificar com frequência a política global a fim de atender a todas as suas necessidades. Se você implantar múltiplas políticas de caixa postal hospedadas, todas essas políticas terão um escopo por usuário.</span><span class="sxs-lookup"><span data-stu-id="0b561-p106">In most cases, only one hosted voice mail policy is required. You can often modify the global policy to meet all your needs. If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="0b561-121">Atributos de política de caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="0b561-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="0b561-122">Uma política de caixa postal define dois atributos que o aplicativo de roteamento ExUM do Lync Server 2013 é inserido no URI de solicitação de uma mensagem de convite que é enviada para a implementação do UM do Exchange hospedado:</span><span class="sxs-lookup"><span data-stu-id="0b561-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="0b561-123">**Destino:** O FQDN (nome de domínio totalmente qualificado) do serviço UM do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="0b561-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="0b561-124">Esse valor é usado pelo servidor de borda do Lync Server local para fins de roteamento.</span><span class="sxs-lookup"><span data-stu-id="0b561-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0b561-125">O FQDN para Exchange Online é exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0b561-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="0b561-126">**Organização:** O FQDN do locatário no serviço de UM do Exchange hospedado que hospeda as caixas de correio dos usuários do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b561-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="0b561-127">Uma política de caixa postal pode conter várias organizações.</span><span class="sxs-lookup"><span data-stu-id="0b561-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="0b561-128">Se mais de uma organização estiver incluída na política, esse atributo deve ser uma lista separada por vírgulas dos locatários do Exchange Server que hospedam suas caixas de correio de usuário do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b561-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b561-p109">O administrador de inquilino de seu serviço de UM do Exchange hospedada fornecerá os valores necessários para suas configurações de Destino e Organização. Para configurar sua política, você precisa executar o cmdlet New-CsHostedVoicemailPolicy ou usar o cmdlet Set-CsHostedVoicemailPolicy para modificar um que exista (por exemplo, a política global).</span><span class="sxs-lookup"><span data-stu-id="0b561-p109">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings. To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="0b561-131">Para obter detalhes sobre o gerenciamento de políticas de caixa postal hospedadas, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0b561-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="0b561-132">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0b561-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="0b561-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0b561-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="0b561-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0b561-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="0b561-135">Atribuição da política de caixa postal por usuário</span><span class="sxs-lookup"><span data-stu-id="0b561-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="0b561-p110">Se sua política de caixa postal hospedada for definida com escopo por usuário, será necessária atribuí-la explicitamente. É possível executar o cmdlet Grant-CsHostedVoicemailPolicy a fim de atribuir a política a usuários ou grupos individuais.</span><span class="sxs-lookup"><span data-stu-id="0b561-p110">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it. You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="0b561-138">Para obter detalhes sobre como atribuir ou remover uma política de caixa postal hospedada por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0b561-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="0b561-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0b561-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="0b561-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0b561-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

