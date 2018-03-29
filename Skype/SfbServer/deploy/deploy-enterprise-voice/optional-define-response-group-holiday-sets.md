---
title: (Opcional) Definir os conjuntos de feriados do Grupo de Resposta no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Criar ou modificar os conjuntos de feriados do grupo de resposta, em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: b176a90b11957128fe485cd608608798d6ff6365
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business-2015"></a>(Opcional) Definir os conjuntos de feriados do Grupo de Resposta no Skype for Business 2015
 
Criar ou modificar os conjuntos de feriados do grupo de resposta, em Skype para Business Server Enterprise Voice.
  
As configurações de feriados definem os dias nos quais um grupo de respostas estará fechado para negócios e especificam a ação a ser tomada nesses dias. Um conjunto de feriados é a coleção de feriados que se aplicam a um grupo de respostas.
  
> [!NOTE]
> Se um fluxo de trabalho for definido como um fluxo de trabalho gerenciado, então qualquer usuário que estiver atribuído à função CsResponseGroupManager poderá definir e modificar feriados para fluxos de trabalho que eles gerenciam. 
  
### <a name="to-create-a-holiday-set"></a>Para criar um conjunto de feriados

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Para cada feriado que você deseja definir, execute:
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Para criar o conjunto de feriados que contém os feriados que você definiu, execute:
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    O exemplo a seguir mostra um conjunto de feriados que inclui dois feriados:
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>Consulte também

#### 

[Projetando e criando fluxos de trabalho do grupo de resposta no Skype para negócios 2015](designing-and-creating-response-group-workflows.md)
#### 

[New-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)
  
[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)

