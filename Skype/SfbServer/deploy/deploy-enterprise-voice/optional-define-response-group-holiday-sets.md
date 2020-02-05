---
title: Adicionais Definir conjuntos de feriados do grupo de resposta no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Criar ou modificar conjuntos de feriados do grupo de resposta no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 5d38814a8e4e9e50634b6d63b1db4c8230c496ea
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767314"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="4d9c7-103">Adicionais Definir conjuntos de feriados do grupo de resposta no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4d9c7-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="4d9c7-104">Criar ou modificar conjuntos de feriados do grupo de resposta no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4d9c7-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="4d9c7-p101">As configurações de feriados definem os dias nos quais um grupo de respostas estará fechado para negócios e especificam a ação a ser tomada nesses dias. Um conjunto de feriados é a coleção de feriados que se aplicam a um grupo de respostas.</span><span class="sxs-lookup"><span data-stu-id="4d9c7-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4d9c7-107">Se um fluxo de trabalho for definido como um fluxo de trabalho gerenciado, então qualquer usuário que estiver atribuído à função CsResponseGroupManager poderá definir e modificar feriados para fluxos de trabalho que eles gerenciam.</span><span class="sxs-lookup"><span data-stu-id="4d9c7-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="4d9c7-108">Para criar um conjunto de feriados</span><span class="sxs-lookup"><span data-stu-id="4d9c7-108">To create a holiday set</span></span>

1. <span data-ttu-id="4d9c7-109">Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="4d9c7-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="4d9c7-110">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="4d9c7-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4d9c7-111">Para cada feriado que você deseja definir, execute:</span><span class="sxs-lookup"><span data-stu-id="4d9c7-111">For each holiday you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="4d9c7-112">Para criar o conjunto de feriados que contém os feriados que você definiu, execute:</span><span class="sxs-lookup"><span data-stu-id="4d9c7-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="4d9c7-113">O exemplo a seguir mostra um conjunto de feriados que inclui dois feriados:</span><span class="sxs-lookup"><span data-stu-id="4d9c7-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="4d9c7-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="4d9c7-114">See also</span></span>

[<span data-ttu-id="4d9c7-115">Projetando e criando fluxos de trabalho de grupo de resposta no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4d9c7-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="4d9c7-116">New-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="4d9c7-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="4d9c7-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="4d9c7-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
