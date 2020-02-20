---
title: 'Lync Server 2013: criar uma política de caixa postal hospedada por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e13002fa83215c5c1aade627cb6e7ea86cf0a04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="04d14-102">Criar uma política de caixa postal hospedada por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04d14-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04d14-103">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="04d14-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="04d14-104">Uma política *por usuário* pode afetar somente usuários individuais, grupos ou objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="04d14-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="04d14-105">Para implantar uma política por usuário, atribua explicitamente a política a um ou mais usuários, grupos ou objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="04d14-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="04d14-106">Para obter detalhes, consulte [atribuir uma política de caixa postal hospedada por usuário no Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="04d14-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="04d14-107">Para obter detalhes sobre como trabalhar com políticas de caixa postal hospedada por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="04d14-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="04d14-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="04d14-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="04d14-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="04d14-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="04d14-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="04d14-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="04d14-111">Para criar uma política de correio de voz hospedada por usuário</span><span class="sxs-lookup"><span data-stu-id="04d14-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="04d14-112">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="04d14-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="04d14-p102">Execute o cmdlet New-CsHostedVoicemailPolicy para criar a política. Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="04d14-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="04d14-115">O exemplo anterior cria uma política de correio de voz hospedada com o escopo por usuário, e define os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="04d14-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="04d14-p103">**Identidade** especifica um identificador exclusivo para a política, que inclui o escopo. Para uma política com escopo por usuário, esse valor de parâmetro é especificado como uma cadeia de caracteres simples, por exemplo, ExRedmond.</span><span class="sxs-lookup"><span data-stu-id="04d14-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="04d14-p104">**Destino** especifica o nome de domínio completamente qualificado (FQDN) do serviço Exchange UM hospedado. Esse parâmetro é opcional, mas se você tentar ativar um usuário para o correio de voz hospedado e a política atribuída ao usuário não possui um valor de Destino, a ativação irá falhar.</span><span class="sxs-lookup"><span data-stu-id="04d14-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="04d14-120">**Descrição** fornece informações descritivas opcionais sobre a política.</span><span class="sxs-lookup"><span data-stu-id="04d14-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="04d14-121">**Organization** especifica uma lista separada por vírgulas dos locatários do Exchange que hospedam os usuários do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="04d14-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="04d14-122">Cada inquilino deve ser especificado como o FQDN daquele inquilino no serviço UM do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="04d14-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="04d14-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="04d14-123">See Also</span></span>


[<span data-ttu-id="04d14-124">Atribuir uma política de caixa postal hospedada por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04d14-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

