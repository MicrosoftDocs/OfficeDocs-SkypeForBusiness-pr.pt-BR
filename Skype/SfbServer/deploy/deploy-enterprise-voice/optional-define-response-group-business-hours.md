---
title: Adicionais Definir o horário comercial do grupo de resposta no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Criar ou modificar o horário comercial do grupo de resposta no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 602494d014c1a3c7874c91462f88b4bcd84f0abb
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003101"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="f9125-103">Adicionais Definir o horário comercial do grupo de resposta no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f9125-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="f9125-104">Criar ou modificar o horário comercial do grupo de resposta no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f9125-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="f9125-105">Definir o horário comercial</span><span class="sxs-lookup"><span data-stu-id="f9125-105">Defining Business Hours</span></span>

<span data-ttu-id="f9125-106">As configurações de horário comercial definem quando o fluxo de trabalho está disponível para atender a chamadas e especificar as ações a serem executadas para chamadas fora do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="f9125-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="f9125-107">Os administradores do Grupo de Resposta podem usar o cmdlet  **New-CsRgsHoursOfBusiness** para criar programações predefinidas que você pode usar para vários grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="f9125-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="f9125-108">Ao criar ou modificar um fluxo de trabalho, é possível especificar uma programação personalizada aplicada apenas a este fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f9125-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="f9125-109">Para obter detalhes, consulte [projetando e criando fluxos de trabalho de grupo de resposta no Skype for Business](designing-and-creating-response-group-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="f9125-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f9125-110">Se um fluxo de trabalho é definido como o Fluxo de Trabalho Gerenciado, qualquer usuário com a função CsResponseGroupManager atribuída pode definir e modificar o horário comercial personalizado para fluxos de trabalho que gerenciam.</span><span class="sxs-lookup"><span data-stu-id="f9125-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f9125-111">Use a notação 24 horas para os parâmetros nos seguintes cmdlets (por exemplo, 20:00=8:00 P.M.).</span><span class="sxs-lookup"><span data-stu-id="f9125-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="f9125-112">Para criar um conjunto de horário comercial predefinido</span><span class="sxs-lookup"><span data-stu-id="f9125-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="f9125-113">Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="f9125-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="f9125-114">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="f9125-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f9125-115">Para cada intervalo de horas exclusivo que você deseja definir, execute:</span><span class="sxs-lookup"><span data-stu-id="f9125-115">For each unique range of hours you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="f9125-116">Para criar o conjunto de horário comercial que usa os intervalos definidos, execute:</span><span class="sxs-lookup"><span data-stu-id="f9125-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="f9125-p103">O exemplo a seguir especifica o horário comercial de 9:00 às 17:00 para dias úteis, de 8:00 às 10:00 e novamente a partir de 14:00 às 18:00 aos sábados e horário não comercial nos domingos:</span><span class="sxs-lookup"><span data-stu-id="f9125-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="f9125-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="f9125-124">See also</span></span>

[<span data-ttu-id="f9125-125">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="f9125-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="f9125-126">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="f9125-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
