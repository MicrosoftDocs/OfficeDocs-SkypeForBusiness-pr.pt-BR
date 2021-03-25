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
ms.openlocfilehash: dc05e94e88b371bb9ee22568eff567e758311233
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111887"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="aadba-103">Configurar vários números de emergência no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="aadba-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="aadba-104">Leia este tópico para saber como configurar vários números de emergência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="aadba-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="aadba-105">O Skype for Business Server agora dá suporte a vários números de emergência para um cliente.</span><span class="sxs-lookup"><span data-stu-id="aadba-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="aadba-106">Vários números de emergência é um novo recurso introduzido na Atualização Cumulativa de junho de 2016.</span><span class="sxs-lookup"><span data-stu-id="aadba-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="aadba-107">Antes de configurar seu ambiente para dar suporte a vários números de emergência, leia [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="aadba-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aadba-108">Se você ainda não tiver atualizado para a Atualização Cumulativa de novembro de 2016, consulte Atualizações para [o Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="aadba-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="aadba-109">Com a Atualização Cumulativa de novembro de 2016, o número de números de emergência de suporte aumenta de 5 para 100.</span><span class="sxs-lookup"><span data-stu-id="aadba-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="aadba-110">Configurar vários números de emergência</span><span class="sxs-lookup"><span data-stu-id="aadba-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="aadba-111">Para configurar vários números de emergência, use o cmdlet New-CsEmergencyNumber e especifique o parâmetro EmergencyNumbers com os cmdlets [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="aadba-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="aadba-112">Para uma descrição completa de todos os parâmetros de política de local, como uso PSTN e Local necessários, consulte [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="aadba-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="aadba-113">O comando a seguir cria um novo número de emergência com a cadeia de caracteres de discagem 911 usando o cmdlet New-CsEmergency de discagem:</span><span class="sxs-lookup"><span data-stu-id="aadba-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="aadba-114">O próximo comando associa o número à política de local especificada especificando o parâmetro EmergencyNumbers no cmdlet Set-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="aadba-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="aadba-115">No próximo exemplo, um número de emergência é criado com uma única máscara de discagem, 112:</span><span class="sxs-lookup"><span data-stu-id="aadba-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="aadba-116">O próximo comando cria um número de emergência com várias máscaras de discagem:</span><span class="sxs-lookup"><span data-stu-id="aadba-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="aadba-117">O próximo exemplo adiciona vários números de emergência com várias máscaras de discagem e associa os números de emergência à política de local especificada:</span><span class="sxs-lookup"><span data-stu-id="aadba-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="aadba-118">O próximo exemplo configura vários números de emergência para provedores de saúde que usam 911 e 450:</span><span class="sxs-lookup"><span data-stu-id="aadba-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="aadba-119">O próximo exemplo configura vários números de emergência para a cidade de Londres:</span><span class="sxs-lookup"><span data-stu-id="aadba-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="aadba-120">O próximo exemplo configura vários números de emergência para a Índia:</span><span class="sxs-lookup"><span data-stu-id="aadba-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="aadba-121">O próximo exemplo remove uma entrada existente com a cadeia de caracteres de discagem 911 e as máscaras de discagem 112 e 999:</span><span class="sxs-lookup"><span data-stu-id="aadba-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```