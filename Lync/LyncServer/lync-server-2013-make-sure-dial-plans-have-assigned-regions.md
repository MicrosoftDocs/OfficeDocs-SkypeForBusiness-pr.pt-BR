---
title: 'Lync Server 2013: Certifique-se de que os planos de discagem tenham regiões atribuídas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a1982a3625fce40eee9b46036fa4e294ed75edd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="57853-102">Verifique se os planos de discagem Lync Server 2013 possuem regiões atribuídas</span><span class="sxs-lookup"><span data-stu-id="57853-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57853-103">_**Última modificação do tópico:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="57853-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="57853-p101">Os planos de discagem que serão usados em conferências discadas precisam ter uma **Região de conferência discada** especificada para associar os números de acesso de conferência discada ao plano de discagem apropriado. Ao configurar um plano de discagem, especifique a região de conferência discada que se aplica ao plano de discagem. Em seguida, ao criar o número de acesso discado, selecione as regiões que associam esse número de acesso aos planos de discagem apropriados.</span><span class="sxs-lookup"><span data-stu-id="57853-p101">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan. When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="57853-p102">Como é importante especificar uma região para todos os planos de discagem, recomendamos usar este procedimento para verificar se todos os planos de discagem têm regiões. Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="57853-p102">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions. This step is optional.</span></span>

<span data-ttu-id="57853-109">Use o cmdlet **Get-CsDialPlan** para verificar se a região está definida para todos os planos de discagem da conferência discada.</span><span class="sxs-lookup"><span data-stu-id="57853-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="57853-110">Se a região não existir nos planos de discagem, você poderá usar o cmdlet **Set-CsDialPlan** para defini-la.</span><span class="sxs-lookup"><span data-stu-id="57853-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="57853-111">Você também pode usar o painel de controle do Lync Server para atualizar a região em planos de discagem existentes.</span><span class="sxs-lookup"><span data-stu-id="57853-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="57853-112">Para obter detalhes sobre como usar o painel de controle do Lync Server, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="57853-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="57853-113">Para verificar se os planos de discagem têm a propriedade de região definida</span><span class="sxs-lookup"><span data-stu-id="57853-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="57853-114">Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="57853-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="57853-115">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="57853-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="57853-116">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="57853-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="57853-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="57853-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="57853-118">Neste exemplo, todos os planos de discagem configurados para sua organização são retornados.</span><span class="sxs-lookup"><span data-stu-id="57853-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="57853-119">Revise os planos de discagem retornados para identificar todos que estão faltando na região da conferência discada.</span><span class="sxs-lookup"><span data-stu-id="57853-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="57853-120">Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57853-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="57853-121">Para definir a propriedade de região de um plano de discagem</span><span class="sxs-lookup"><span data-stu-id="57853-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="57853-122">Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="57853-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="57853-123">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="57853-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="57853-124">Para todos os planos de discagem que não têm a região de conferência discada, execute:</span><span class="sxs-lookup"><span data-stu-id="57853-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="57853-125">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="57853-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="57853-126">Neste exemplo, o plano de discagem com Identidade de Redmond é modificado para definir a propriedade DialinConferencingRegion como "Costa Leste dos EUA".</span><span class="sxs-lookup"><span data-stu-id="57853-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="57853-127">Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57853-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

