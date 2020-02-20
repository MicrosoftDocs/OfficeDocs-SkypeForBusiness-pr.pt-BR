---
title: 'Lync Server 2013: modificar a política de caixa postal hospedada global'
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
ms.openlocfilehash: 12ddff40f3a04ed4bfb0d8205eac732ef3ad7198
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="1c415-102">Modificar a política de caixa postal hospedada global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c415-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c415-103">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="1c415-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="1c415-104">A política de caixa postal hospedada *global* é instalada com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c415-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="1c415-105">É possível modificá-la para corresponder às suas necessidades, mas não é possível renomear ou exclui-la.</span><span class="sxs-lookup"><span data-stu-id="1c415-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="1c415-106">Para modificar a política global, deve usar o cmdlet Set-CsHostedVoicemailPolicy para definir os parâmetros para os valores adequados da sua implantação específica.</span><span class="sxs-lookup"><span data-stu-id="1c415-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="1c415-107">Para obter detalhes sobre o cmdlet [set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c415-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="1c415-108">Para modificar a política de caixa postal hospedada global</span><span class="sxs-lookup"><span data-stu-id="1c415-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="1c415-109">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1c415-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1c415-110">Execute o Set-CsHostedVoicemailPolicy para definir os parâmetros da política global do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="1c415-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="1c415-111">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="1c415-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="1c415-112">Como esse comando não especifica o parâmetro Identity da política, a interface de linha de comando do Windows PowerShell define os seguintes valores na política de caixa postal hospedada global:</span><span class="sxs-lookup"><span data-stu-id="1c415-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="1c415-p103">**Destino** especifica o FQDN do serviço UM do Exchange hospedado. Este parâmetro é opcional, mas se você tentar habilitar um usuário para a caixa postal hospedada e a política atribuída do usuário não possui um valor de Destino, a habilitação falhará.</span><span class="sxs-lookup"><span data-stu-id="1c415-p103">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="1c415-115">**Organization** especifica uma lista separada por vírgulas dos locatários do Exchange que hospedam os usuários do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c415-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="1c415-116">Cada inquilino deve ser especificado como o FQDN daquele inquilino no serviço UM do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="1c415-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1c415-p105">No cmdlet de exemplo anterior, o valor “corp1.litwareinc.com” substitui qualquer valor que pode já estar presente no parâmetro Organização. Por exemplo, se a política já contém uma lista separada por vírgulas da organização, a lista completa seria substituída. Se deseja adicionar uma organização à lista ao invés de substituir toda a lista, execute um comando similar ao seguinte.</span><span class="sxs-lookup"><span data-stu-id="1c415-p105">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter. For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced. If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
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

