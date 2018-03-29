---
title: Configurar vários números de emergência no Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 4/21/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Leia este tópico para saber como configurar vários números de emergência no Skype for Business Server 2015.
ms.openlocfilehash: 98d9bbef92f5f3894fb288c01e474288f9f7bb4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business-2015"></a>Configurar vários números de emergência no Skype for Business 2015
 
Leia este tópico para saber como configurar vários números de emergência no Skype for Business Server 2015.
  
Skype para Business Server agora oferece suporte a vários números de emergências para um cliente. Vários números de emergência são um novo recurso introduzido no de 2016 junho atualizações cumulativas. Antes de configurar seu ambiente para suportar vários números de emergências, certifique-se de ler [Planejar vários números de emergências Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).
  
> [!NOTE]
> Se você ainda não atualizadas para o de 2016 novembro atualização cumulativa, consulte [atualizações para Skype para Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). Com o de 2016 novembro atualização cumulativa, o número de números de emergência suporte aumenta de 5 até 100. 
  
## <a name="configure-multiple-emergency-numbers"></a>Configurar vários números de emergência

Para configurar vários números de emergências, você usa o cmdlet New-CsEmergencyNumber e, em seguida, especifique o parâmetro EmergencyNumbers com os cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Para obter uma descrição completa de todos os parâmetros de política local, como o uso de PSTN e o local necessário, consulte [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).
  
O comando a seguir cria um novo número de emergência com a cadeia de caracteres de discagem 911 usando o cmdlet New-CsEmergency:
  
```
> $a = New-CsEmergencyNumber -DialString 911 

```

O próximo comando associa o número à política de local especificada, especificando o parâmetro EmergencyNumbers no cmdlet Set-CsLocationPolicy:
  
```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 

```

No próximo exemplo, um número de emergência é criado com uma única máscara de discagem, 112:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 

```

O próximo comando cria um número de emergência com múltiplas máscaras de discagem:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 

```

O próximo exemplo adiciona vários números de emergência com várias máscaras de discagem e associa os números de emergência à política de local especificada:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 

```

O próximo exemplo configura vários números de emergência para os prestadores de serviços de saúde que usam 911 e 450:  
  
```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

O próximo exemplo configura vários números de emergência para a cidade de Londres:
  
```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}

```

O próximo exemplo configura vários números de emergência para a Índia:
  
```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}

```

O próximo exemplo remove uma entrada existente com a cadeia de caracteres de discagem 911 e as máscaras de discagem 112 e 999:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 

```


