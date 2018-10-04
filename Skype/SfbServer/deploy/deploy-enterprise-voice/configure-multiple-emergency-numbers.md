---
title: Configurar vários números de emergências no Skype para negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Leia este tópico para saber como configurar vários números de emergências no Skype para Business Server.
ms.openlocfilehash: 64f9368b5d6eaac1c2f872ebf48152514cc99b34
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372682"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="135e2-103">Configurar vários números de emergências no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="135e2-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="135e2-104">Leia este tópico para saber como configurar vários números de emergências no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="135e2-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="135e2-105">Skype para Business Server agora oferece suporte a vários números de emergências para um cliente.</span><span class="sxs-lookup"><span data-stu-id="135e2-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="135e2-106">Vários números de emergência são um novo recurso introduzido no de 2016 junho atualizações cumulativas.</span><span class="sxs-lookup"><span data-stu-id="135e2-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="135e2-107">Antes de configurar seu ambiente para suportar vários números de emergências, certifique-se de ler [Planejar vários números de emergências Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="135e2-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="135e2-108">Se você ainda não atualizadas para o de 2016 novembro atualização cumulativa, consulte [atualizações para Skype para Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="135e2-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="135e2-109">Com o de 2016 novembro atualização cumulativa, o número de números de emergência suporte aumenta de 5 até 100.</span><span class="sxs-lookup"><span data-stu-id="135e2-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="135e2-110">Configurar vários números de emergência</span><span class="sxs-lookup"><span data-stu-id="135e2-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="135e2-111">Para configurar vários números de emergências, você usa o cmdlet New-CsEmergencyNumber e, em seguida, especifique o parâmetro EmergencyNumbers com os cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="135e2-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="135e2-112">Para obter uma descrição completa de todos os parâmetros de política local, como o uso de PSTN e o local necessário, consulte [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="135e2-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="135e2-113">O comando a seguir cria um novo número de emergência com a cadeia de caracteres de discagem 911 usando o cmdlet New-CsEmergency:</span><span class="sxs-lookup"><span data-stu-id="135e2-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 
```

<span data-ttu-id="135e2-114">O próximo comando associa o número à política de local especificada, especificando o parâmetro EmergencyNumbers no cmdlet Set-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="135e2-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

<span data-ttu-id="135e2-115">No próximo exemplo, um número de emergência é criado com uma única máscara de discagem, 112:</span><span class="sxs-lookup"><span data-stu-id="135e2-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

<span data-ttu-id="135e2-116">O próximo comando cria um número de emergência com múltiplas máscaras de discagem:</span><span class="sxs-lookup"><span data-stu-id="135e2-116">The next command creates an emergency number with multiple dial masks:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

<span data-ttu-id="135e2-117">O próximo exemplo adiciona vários números de emergência com várias máscaras de discagem e associa os números de emergência à política de local especificada:</span><span class="sxs-lookup"><span data-stu-id="135e2-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

<span data-ttu-id="135e2-118">O próximo exemplo configura vários números de emergência para os prestadores de serviços de saúde que usam 911 e 450: </span><span class="sxs-lookup"><span data-stu-id="135e2-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 

```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="135e2-119">O próximo exemplo configura vários números de emergência para a cidade de Londres:</span><span class="sxs-lookup"><span data-stu-id="135e2-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="135e2-120">O próximo exemplo configura vários números de emergência para a Índia:</span><span class="sxs-lookup"><span data-stu-id="135e2-120">The next example configures multiple emergency numbers for India:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="135e2-121">O próximo exemplo remove uma entrada existente com a cadeia de caracteres de discagem 911 e as máscaras de discagem 112 e 999:</span><span class="sxs-lookup"><span data-stu-id="135e2-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


