---
title: Configurar vários números de emergência no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Leia este tópico para saber como configurar vários números de emergência no Skype for Business Server.
ms.openlocfilehash: 0a2387576418aa2631095c46e970fdfac234ca4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303373"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configurar vários números de emergência no Skype for Business

Leia este tópico para saber como configurar vários números de emergência no Skype for Business Server.

O Skype for Business Server agora oferece suporte a vários números de emergência para um cliente. Vários números de emergência é um novo recurso apresentado na atualização cumulativa de junho de 2016. Antes de configurar seu ambiente para dar suporte a vários números de emergência, certifique-se de ler [plano para vários números de emergência no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Se você ainda não atualizou a atualização cumulativa de novembro de 2016, consulte [atualizações para o Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). Com a atualização cumulativa de novembro de 2016, o número de números de emergência de suporte aumenta de 5 para 100. 

## <a name="configure-multiple-emergency-numbers"></a>Configurar vários números de emergência

Para configurar vários números de emergência, use o cmdlet New-CsEmergencyNumber e, em seguida, especifique o parâmetro EmergencyNumbers com os cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Para obter uma descrição completa de todos os parâmetros de política de localização, como o uso e o local de PSTN necessários, consulte [set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

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

O próximo comando cria um número de emergência com várias máscaras de discagem:

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


