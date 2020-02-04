---
title: 'Lync Server 2013: modificar a política de caixa de correio de voz hospedada global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="ec0f3-102">Modificar a política de caixa de correio de voz hospedada global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec0f3-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec0f3-103">_**Tópico da última modificação:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="ec0f3-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="ec0f3-104">A política de caixa de correio de voz hospedada *global* é instalada com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="ec0f3-105">Você pode modificá-la para atender às suas necessidades, mas não pode renomeá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="ec0f3-106">Para modificar a política global, use o cmdlet Set-CsHostedVoicemailPolicy para definir os parâmetros para os valores apropriados para a implantação específica.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="ec0f3-107">Para obter detalhes sobre o cmdlet [set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="ec0f3-108">Para modificar a política de caixa de correio de voz hospedada global</span><span class="sxs-lookup"><span data-stu-id="ec0f3-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="ec0f3-109">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ec0f3-110">Execute o cmdlet Set-CsHostedVoicemailPolicy para definir os parâmetros de política global do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="ec0f3-111">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="ec0f3-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="ec0f3-112">Como esse comando não especifica o parâmetro Identity da política, a interface de linha de comando do Windows PowerShell define os seguintes valores na política de caixa postal hospedada global:</span><span class="sxs-lookup"><span data-stu-id="ec0f3-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="ec0f3-113">**Destino** especifica o nome de domínio totalmente qualificado (FQDN) do serviço do Exchange um hospedado.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-113">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="ec0f3-114">Esse parâmetro é opcional, mas se você tentar habilitar um usuário para a caixa postal hospedada e a política atribuída do usuário não tiver um valor de destino, o habilitar falhará.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-114">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="ec0f3-115">**Organização** especifica uma lista separada por vírgulas dos locatários do Exchange que hospedam os usuários do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="ec0f3-116">Cada locatário deve ser especificado como FQDN do locatário no serviço do Exchange UM hospedado.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ec0f3-117">No cmdlet do exemplo anterior, o valor "corp1.litwareinc.com" substitui qualquer valor que já esteja presente no parâmetro da organização.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-117">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter.</span></span> <span data-ttu-id="ec0f3-118">Por exemplo, se a política já contiver uma lista separada por vírgulas de organizações, a lista completa será substituída.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-118">For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced.</span></span> <span data-ttu-id="ec0f3-119">Se você quiser adicionar uma organização à lista em vez de substituir a lista inteira, execute um comando semelhante ao seguinte.</span><span class="sxs-lookup"><span data-stu-id="ec0f3-119">If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

