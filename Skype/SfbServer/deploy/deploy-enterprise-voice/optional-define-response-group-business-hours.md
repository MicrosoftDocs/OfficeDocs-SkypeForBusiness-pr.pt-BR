---
title: (Opcional) Definir o horário comercial do Grupo de Resposta em Skype for Business
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
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 'Crie ou modifique o horário comercial do Grupo de Resposta, Skype for Business Server Enterprise Voice.'
---

# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>(Opcional) Definir o horário comercial do Grupo de Resposta em Skype for Business 
 
Crie ou modifique o horário comercial do Grupo de Resposta, Skype for Business Server Enterprise Voice.
  
## <a name="defining-business-hours"></a>Definir o horário comercial

As configurações de horário comercial definem quando o fluxo de trabalho está disponível para atender a chamadas e especificar as ações a serem executadas para chamadas fora do horário comercial. Os administradores do Grupo de Resposta podem usar o cmdlet **New-CsRgsHoursOfBusiness** para criar programações predefinidas que você pode usar para vários grupos de resposta.
  
> [!TIP]
> Ao criar ou modificar um fluxo de trabalho, é possível especificar uma programação personalizada aplicada apenas a este fluxo de trabalho. Para obter detalhes, [consulte Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md). 
  
> [!NOTE]
> Se um fluxo de trabalho é definido como o Fluxo de trabalho gerenciado, qualquer usuário com a função CsResponseGroupManager atribuída pode definir e modificar o horário comercial personalizado para fluxos de trabalho que gerenciam. 
  
> [!IMPORTANT]
> Use a notação 24 horas para os parâmetros nos seguintes cmdlets (por exemplo, 20:00=20:00 horas). 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>Para criar um conjunto de horário comercial predefinido

1. Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinida que suportam o Grupo de Resposta.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
3. Para cada intervalo de horas exclusivo que você deseja definir, execute:
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    Para criar o conjunto de horário comercial que usa os intervalos definidos, execute:
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    O exemplo a seguir especifica o horário comercial de 9:00: 00 às 17:00 para dias úteis, de 8: 00 a 10:00: 00 e novamente a partir de 14: 00. às 18:00 nos sábados e horário não comercial nos domingos:
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>Confira também

[New-CsRgsTimeRange](/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[New-CsRgsHoursOfBusiness](/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)