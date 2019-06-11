---
title: 'Lync Server 2013: criar uma política de correio de voz hospedada por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d09638c28c1cbd2b068972aff169376508325885
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="50454-102">Criar uma política de correio de voz hospedada por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50454-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50454-103">_**Tópico da última modificação:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="50454-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="50454-104">Uma política *por usuário* pode impactar apenas usuários individuais, grupos e objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="50454-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="50454-105">Para implantar uma política por usuário, você deve explicitamente atribuir a política a um ou mais usuários, grupos ou objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="50454-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="50454-106">Para obter detalhes, consulte [atribuir uma política de correio de voz hospedada por usuário no Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="50454-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="50454-107">Para obter detalhes sobre como trabalhar com políticas de correio de voz hospedadas por usuário, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="50454-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="50454-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="50454-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="50454-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="50454-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="50454-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="50454-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="50454-111">Para criar uma política de correio de voz hospedada por usuário</span><span class="sxs-lookup"><span data-stu-id="50454-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="50454-112">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="50454-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="50454-113">Execute o cmdlet New-CsHostedVoicemailPolicy para criar a política.</span><span class="sxs-lookup"><span data-stu-id="50454-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="50454-114">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="50454-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="50454-115">O exemplo anterior cria uma política de caixa postal hospedada com o escopo por usuário e define os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="50454-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="50454-116">**Identity** especifica um identificador exclusivo para a política, que inclui o escopo.</span><span class="sxs-lookup"><span data-stu-id="50454-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="50454-117">Para uma política com escopo por usuário, esse valor de parâmetro é especificado como uma cadeia de caracteres simples, por exemplo, exrio.</span><span class="sxs-lookup"><span data-stu-id="50454-117">For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="50454-118">**Destino** especifica o nome de domínio totalmente qualificado (FQDN) do serviço do Exchange um hospedado.</span><span class="sxs-lookup"><span data-stu-id="50454-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="50454-119">Esse parâmetro é opcional, mas se você tentar habilitar um usuário para a caixa postal hospedada e a política atribuída do usuário não tiver um valor de destino, o habilitar falhará.</span><span class="sxs-lookup"><span data-stu-id="50454-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="50454-120">**Descrição** fornece informações descritivas opcionais sobre a política.</span><span class="sxs-lookup"><span data-stu-id="50454-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="50454-121">**Organização** especifica uma lista separada por vírgulas dos locatários do Exchange que os usuários do Lync Server 2013 em casa.</span><span class="sxs-lookup"><span data-stu-id="50454-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="50454-122">Cada locatário deve ser especificado como FQDN do locatário no serviço do Exchange UM hospedado.</span><span class="sxs-lookup"><span data-stu-id="50454-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50454-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="50454-123">See Also</span></span>


[<span data-ttu-id="50454-124">Atribuir uma política de correio de voz hospedada por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50454-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

