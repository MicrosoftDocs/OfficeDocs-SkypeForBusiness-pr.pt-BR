---
title: 'Lync Server 2013: criar uma política de caixa postal hospedada no nível do site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd227787ae790b280c98c73e9ca0bb516d7dc092
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="6cd4d-102">Criar uma política de caixa postal hospedada no nível do site no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cd4d-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cd4d-103">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="6cd4d-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="6cd4d-p101">Uma política de *local* pode afetar todos os usuários hospedados no local em que a política foi definida. Se um usuário for configurado para acesso hospedado ao serviço de UM do Exchange e não tiver recebido uma política Por usuário, a política de local será aplicada. Caso não tenha implantado uma política de local, será aplicada a política global.</span><span class="sxs-lookup"><span data-stu-id="6cd4d-p101">A *site* policy can impact all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies. If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="6cd4d-107">Para obter detalhes sobre como configurar políticas de site, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6cd4d-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="6cd4d-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6cd4d-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="6cd4d-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6cd4d-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="6cd4d-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6cd4d-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="6cd4d-111">Para criar uma política de caixa postal hospedada em um site</span><span class="sxs-lookup"><span data-stu-id="6cd4d-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="6cd4d-112">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6cd4d-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6cd4d-p102">Execute o cmdlet New-CsHostedVoicemailPolicy para criar a política. Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="6cd4d-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="6cd4d-115">Esse exemplo cria uma política de caixa postal com escopo do site e define os parâmetros a seguir:</span><span class="sxs-lookup"><span data-stu-id="6cd4d-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="6cd4d-116">A **Identidade** especifica um identificador único para a política, o que inclui o escopo.</span><span class="sxs-lookup"><span data-stu-id="6cd4d-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="6cd4d-117">Para uma política com escopo de site, o valor do parâmetro Identity deve ser especificado no `site:` \* \<nome\>\* do formato, por `site:Redmond`exemplo,.</span><span class="sxs-lookup"><span data-stu-id="6cd4d-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="6cd4d-p104">**Destino** especifica o nome de domínio completamente qualificado (FQDN) do serviço Exchange UM hospedado. Esse parâmetro é opcional, mas se você tentar ativar um usuário para o correio de voz hospedado e a política atribuída ao usuário não possui um valor de Destino, a ativação irá falhar.</span><span class="sxs-lookup"><span data-stu-id="6cd4d-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="6cd4d-120">**Descrição** fornece informações descritivas opcionais sobre a política.</span><span class="sxs-lookup"><span data-stu-id="6cd4d-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="6cd4d-121">**Organization** especifica uma lista separada por vírgulas dos locatários do Exchange que hospedam os usuários do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6cd4d-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="6cd4d-122">Cada inquilino deve ser especificado como FQDN daquele inquilino no serviço hospedado de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cd4d-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

