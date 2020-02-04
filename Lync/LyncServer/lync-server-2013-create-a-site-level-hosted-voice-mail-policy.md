---
title: 'Lync Server 2013: criar uma política de correio de voz hospedada no nível do site'
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
ms.openlocfilehash: 6aeae2e533bd62cf1f3e24e7ceff69b870ebc7b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="cbfae-102">Criar uma política de caixa postal hospedada no nível do site no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbfae-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbfae-103">_**Tópico da última modificação:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="cbfae-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="cbfae-104">Uma política de *site* pode afetar todos os usuários que estão hospedados no site para o qual a política está definida.</span><span class="sxs-lookup"><span data-stu-id="cbfae-104">A *site* policy can impact all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="cbfae-105">Se um usuário estiver configurado para acesso do Exchange UM hospedado e não tiver sido atribuída uma política por usuário, a política do site será aplicada.</span><span class="sxs-lookup"><span data-stu-id="cbfae-105">If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies.</span></span> <span data-ttu-id="cbfae-106">Se você não implantou uma política de site, a política global se aplica.</span><span class="sxs-lookup"><span data-stu-id="cbfae-106">If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="cbfae-107">Para obter detalhes sobre como configurar políticas de site, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="cbfae-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="cbfae-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cbfae-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="cbfae-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cbfae-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="cbfae-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cbfae-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="cbfae-111">Para criar uma política de caixa postal hospedada no site</span><span class="sxs-lookup"><span data-stu-id="cbfae-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="cbfae-112">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cbfae-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cbfae-113">Execute o cmdlet New-CsHostedVoicemailPolicy para criar a política.</span><span class="sxs-lookup"><span data-stu-id="cbfae-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="cbfae-114">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="cbfae-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="cbfae-115">Este exemplo cria uma política de caixa postal hospedada com escopo de site e define os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="cbfae-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="cbfae-116">**Identity** especifica um identificador exclusivo para a política, que inclui o escopo.</span><span class="sxs-lookup"><span data-stu-id="cbfae-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="cbfae-117">Para uma política com escopo de site, o valor do parâmetro Identity deve ser especificado no `site:` \* \<nome\>\* do formato, por `site:Redmond`exemplo,.</span><span class="sxs-lookup"><span data-stu-id="cbfae-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="cbfae-118">**Destino** especifica o nome de domínio totalmente qualificado (FQDN) do serviço do Exchange um hospedado.</span><span class="sxs-lookup"><span data-stu-id="cbfae-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="cbfae-119">Esse parâmetro é opcional, mas se você tentar habilitar um usuário para a caixa postal hospedada e a política atribuída do usuário não tiver um valor de destino, o habilitar falhará.</span><span class="sxs-lookup"><span data-stu-id="cbfae-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="cbfae-120">**Descrição** fornece informações descritivas opcionais sobre a política.</span><span class="sxs-lookup"><span data-stu-id="cbfae-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="cbfae-121">**Organização** especifica uma lista separada por vírgulas dos locatários do Exchange que os usuários do Lync Server 2013 em casa.</span><span class="sxs-lookup"><span data-stu-id="cbfae-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="cbfae-122">Cada locatário deve ser especificado como FQDN do locatário no serviço do Exchange UM hospedado.</span><span class="sxs-lookup"><span data-stu-id="cbfae-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

