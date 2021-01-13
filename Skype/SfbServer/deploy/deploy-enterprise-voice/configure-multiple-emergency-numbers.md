---
title: Configurar vários números de emergência no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Leia este tópico para saber como configurar vários números de emergência no Skype for Business Server.
ms.openlocfilehash: fe53e914eb0c406a4f7013df2f6ec106fa781f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804101"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configurar vários números de emergência no Skype for Business

Leia este tópico para saber como configurar vários números de emergência no Skype for Business Server.

O Skype for Business Server agora oferece suporte a vários números de emergência para um cliente. Vários números de emergência são um novo recurso introduzido na Atualização Cumulativa de junho de 2016. Antes de configurar seu ambiente para dar suporte a vários números de emergência, certifique-se de ler Plano para vários números de [emergência no Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)

> [!NOTE]
> Se você ainda não tiver atualizado para a Atualização Cumulativa de novembro de 2016, consulte Atualizações para [o Skype for Business Server 2015.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) Com a Atualização Cumulativa de novembro de 2016, o número de números de emergência de suporte aumenta de 5 para 100.

## <a name="configure-multiple-emergency-numbers"></a>Configurar vários números de emergência

Para configurar vários números de emergência, use o cmdlet New-CsEmergencyNumber e especifique o parâmetro EmergencyNumbers com os cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Para uma descrição completa de todos os parâmetros de política de local, como o uso de PSTN e o local necessários, consulte [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

O comando a seguir cria um novo número de emergência com a cadeia de caracteres de discagem 911 usando New-CsEmergency cmdlet:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

O próximo comando associa o número à política de local especificada especificando o parâmetro EmergencyNumbers no Set-CsLocationPolicy cmdlet:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

No próximo exemplo, um número de emergência é criado com uma única máscara de discagem, 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

O próximo comando cria um número de emergência com várias máscaras de discagem:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

O próximo exemplo adiciona vários números de emergência com várias máscaras de discagem e, em seguida, associa os números de emergência à política de local especificada:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

O próximo exemplo configura vários números de emergência para provedores de serviços de saúde que usam 911 e 450:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

O próximo exemplo configura vários números de emergência para a cidade de Londres:

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

O próximo exemplo configura vários números de emergência para a Índia:

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

O próximo exemplo remove uma entrada existente com a cadeia de caracteres de discagem 911 e as máscaras de discagem 112 e 999:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
