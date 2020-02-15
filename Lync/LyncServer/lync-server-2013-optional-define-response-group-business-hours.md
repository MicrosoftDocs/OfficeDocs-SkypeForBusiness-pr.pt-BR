---
title: 'Lync Server 2013: (opcional) definir horário comercial do grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62fe312c08c639293dbd35623d10b58f3e51fe14
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a><span data-ttu-id="8a955-102">Opcion Definir o horário comercial do grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a955-102">(Optional) Define Response Group business hours in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a955-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8a955-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<div>

## <a name="defining-business-hours"></a><span data-ttu-id="8a955-104">Definir o horário comercial</span><span class="sxs-lookup"><span data-stu-id="8a955-104">Defining Business Hours</span></span>

<span data-ttu-id="8a955-105">As configurações de horário comercial definem quando o fluxo de trabalho está disponível para atender a chamadas e especificar as ações a serem executadas para chamadas fora do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="8a955-105">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="8a955-106">Os administradores do Grupo de Resposta podem usar o cmdlet **New-CsRgsHoursOfBusiness** para criar programações predefinidas que você pode usar para vários grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="8a955-106">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="8a955-107">Ao criar ou modificar um fluxo de trabalho, é possível especificar uma programação personalizada aplicada apenas a este fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8a955-107">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="8a955-108">Para obter detalhes, consulte <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">criar ou modificar um fluxo de trabalho de grupo de busca no Lync server 2013</A> ou <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">criar ou modificar um fluxo de trabalho interativo no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8a955-108">For details, see <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Create or modify a hunt group workflow in Lync Server 2013</A> or <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Create or modify an interactive workflow in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8a955-109">Se um fluxo de trabalho é definido como o Fluxo de trabalho gerenciado, qualquer usuário com a função CsResponseGroupManager atribuída pode definir e modificar o horário comercial personalizado para fluxos de trabalho que gerenciam.</span><span class="sxs-lookup"><span data-stu-id="8a955-109">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8a955-110">Use a notação 24 horas para os parâmetros nos seguintes cmdlets (por exemplo, 20:00=20:00 horas).</span><span class="sxs-lookup"><span data-stu-id="8a955-110">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span>



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="8a955-111">Para criar um conjunto de horário comercial predefinido</span><span class="sxs-lookup"><span data-stu-id="8a955-111">To create a predefined business hours collection</span></span>

1.  <span data-ttu-id="8a955-112">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="8a955-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="8a955-113">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8a955-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8a955-114">Para cada intervalo de horas exclusivo que você deseja definir, execute:</span><span class="sxs-lookup"><span data-stu-id="8a955-114">For each unique range of hours you want to define, run:</span></span>
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    <span data-ttu-id="8a955-115">Para criar o conjunto de horário comercial que usa os intervalos definidos, execute:</span><span class="sxs-lookup"><span data-stu-id="8a955-115">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    <span data-ttu-id="8a955-p103">O exemplo a seguir especifica o horário comercial de 9:00: 00 às 17:00 para dias úteis, de 8: 00 a 10:00: 00 e novamente a partir de 14: 00. às 18:00 nos sábados e horário não comercial nos domingos:</span><span class="sxs-lookup"><span data-stu-id="8a955-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a955-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="8a955-123">See Also</span></span>


[<span data-ttu-id="8a955-124">Criar ou modificar um fluxo de trabalho de grupo de busca no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a955-124">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="8a955-125">Criar ou modificar um fluxo de trabalho interativo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a955-125">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="8a955-126">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="8a955-126">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[<span data-ttu-id="8a955-127">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="8a955-127">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

