---
title: (Opcional) Definir conjuntos de feriados do Grupo de Resposta Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: 'Crie ou modifique conjuntos de feriados do Grupo de Resposta, Skype for Business Server Enterprise Voice.'
---

# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a>(Opcional) Definir conjuntos de feriados do Grupo de Resposta Skype for Business
 
Crie ou modifique conjuntos de feriados do Grupo de Resposta, Skype for Business Server Enterprise Voice.
  
As configurações de feriados definem os dias nos quais um grupo de respostas estará fechado para negócios e especificam a ação a ser tomada nesses dias. Um conjunto de feriados é a coleção de feriados que se aplicam a um grupo de respostas.
  
> [!NOTE]
> Se um fluxo de trabalho for definido como um fluxo de trabalho gerenciado, então qualquer usuário que estiver atribuído à função CsResponseGroupManager poderá definir e modificar feriados para fluxos de trabalho que eles gerenciam. 
  
### <a name="to-create-a-holiday-set"></a>Para criar um conjunto de feriados

1. Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinida que suportam o Grupo de Resposta.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
3. Para cada feriado que você deseja definir, execute:
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Para criar o conjunto de feriados que contém os feriados definidos, execute:
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    O seguinte exemplo mostra um conjunto de feriados que inclui dois feriados:
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>Confira também

[Criando e criando fluxos de trabalho de grupo de resposta Skype for Business](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](/powershell/module/skype/new-csrgsholidayset?view=skype-ps)