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
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="70ac6-103">Configurar vários números de emergência no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="70ac6-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="70ac6-104">Leia este tópico para saber como configurar vários números de emergência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="70ac6-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="70ac6-105">O Skype for Business Server agora oferece suporte a vários números de emergência para um cliente.</span><span class="sxs-lookup"><span data-stu-id="70ac6-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="70ac6-106">Vários números de emergência são um novo recurso introduzido na Atualização Cumulativa de junho de 2016.</span><span class="sxs-lookup"><span data-stu-id="70ac6-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="70ac6-107">Antes de configurar seu ambiente para dar suporte a vários números de emergência, certifique-se de ler Plano para vários números de [emergência no Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="70ac6-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="70ac6-108">Se você ainda não tiver atualizado para a Atualização Cumulativa de novembro de 2016, consulte Atualizações para [o Skype for Business Server 2015.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="70ac6-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="70ac6-109">Com a Atualização Cumulativa de novembro de 2016, o número de números de emergência de suporte aumenta de 5 para 100.</span><span class="sxs-lookup"><span data-stu-id="70ac6-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="70ac6-110">Configurar vários números de emergência</span><span class="sxs-lookup"><span data-stu-id="70ac6-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="70ac6-111">Para configurar vários números de emergência, use o cmdlet New-CsEmergencyNumber e especifique o parâmetro EmergencyNumbers com os cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="70ac6-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="70ac6-112">Para uma descrição completa de todos os parâmetros de política de local, como o uso de PSTN e o local necessários, consulte [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="70ac6-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="70ac6-113">O comando a seguir cria um novo número de emergência com a cadeia de caracteres de discagem 911 usando New-CsEmergency cmdlet:</span><span class="sxs-lookup"><span data-stu-id="70ac6-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="70ac6-114">O próximo comando associa o número à política de local especificada especificando o parâmetro EmergencyNumbers no Set-CsLocationPolicy cmdlet:</span><span class="sxs-lookup"><span data-stu-id="70ac6-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="70ac6-115">No próximo exemplo, um número de emergência é criado com uma única máscara de discagem, 112:</span><span class="sxs-lookup"><span data-stu-id="70ac6-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="70ac6-116">O próximo comando cria um número de emergência com várias máscaras de discagem:</span><span class="sxs-lookup"><span data-stu-id="70ac6-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="70ac6-117">O próximo exemplo adiciona vários números de emergência com várias máscaras de discagem e, em seguida, associa os números de emergência à política de local especificada:</span><span class="sxs-lookup"><span data-stu-id="70ac6-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="70ac6-118">O próximo exemplo configura vários números de emergência para provedores de serviços de saúde que usam 911 e 450:</span><span class="sxs-lookup"><span data-stu-id="70ac6-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="70ac6-119">O próximo exemplo configura vários números de emergência para a cidade de Londres:</span><span class="sxs-lookup"><span data-stu-id="70ac6-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="70ac6-120">O próximo exemplo configura vários números de emergência para a Índia:</span><span class="sxs-lookup"><span data-stu-id="70ac6-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="70ac6-121">O próximo exemplo remove uma entrada existente com a cadeia de caracteres de discagem 911 e as máscaras de discagem 112 e 999:</span><span class="sxs-lookup"><span data-stu-id="70ac6-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
