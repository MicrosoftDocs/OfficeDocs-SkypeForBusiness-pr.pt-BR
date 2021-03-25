---
title: Configurar a junção de reunião sem PIN no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumo: saiba como configurar a opção de junção de reunião sem PIN no Skype for Business Server.'
ms.openlocfilehash: 76a2fb401c684e0eb685b733cb1b0a63ecbd9907
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119390"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="4aa2c-103">Configurar a junção de reunião sem PIN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4aa2c-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="4aa2c-104">**Resumo:** Saiba como configurar a opção de junção de reunião sem PIN no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4aa2c-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="4aa2c-105">Quando um chamador discado tenta ingressar em uma reunião, o serviço de Conferência Atendedor Automático (CAA) coloca o chamador em uma caneta de espera diferente do Lobby &#x2014; se um apresentador ainda não estiver em uma chamada e o chamador de discagem não tiver inserido um PIN líder.</span><span class="sxs-lookup"><span data-stu-id="4aa2c-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="4aa2c-106">A opção de ingresso de reunião sem PIN permite que os chamadores de discagem participem de uma reunião sem inserir um PIN líder, mesmo que sejam a primeira pessoa em uma chamada.</span><span class="sxs-lookup"><span data-stu-id="4aa2c-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="4aa2c-107">Lembre-se do seguinte ao configurar este recurso:</span><span class="sxs-lookup"><span data-stu-id="4aa2c-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="4aa2c-108">Aplica-se apenas a reuniões privadas.</span><span class="sxs-lookup"><span data-stu-id="4aa2c-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="4aa2c-109">Permite que os chamadores PSTN permaneçam em reuniões privadas sem a presença de usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="4aa2c-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="4aa2c-110">Depois que a configuração for alterada, ela se aplicará a todas as reuniões privadas existentes e novas.</span><span class="sxs-lookup"><span data-stu-id="4aa2c-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="4aa2c-111">Pode ser habilitado no site do organizador ou no nível global.</span><span class="sxs-lookup"><span data-stu-id="4aa2c-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="4aa2c-112">As opções para quem pode ignorar o lobby podem ser definidas para um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="4aa2c-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="4aa2c-113">**Qualquer pessoa da minha organização com chamadores entrar diretamente**</span><span class="sxs-lookup"><span data-stu-id="4aa2c-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="4aa2c-114">**Qualquer pessoa (sem restrições) com chamadores entrar diretamente** (Essa é a configuração padrão).)</span><span class="sxs-lookup"><span data-stu-id="4aa2c-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="4aa2c-115">Quando configurado para habilitar a junção sem PIN, o serviço CAA ainda solicita um PIN líder.</span><span class="sxs-lookup"><span data-stu-id="4aa2c-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="4aa2c-116">Os usuários podem ingressar na reunião se um PIN foi inserido ou não.</span><span class="sxs-lookup"><span data-stu-id="4aa2c-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="4aa2c-117">No entanto, manter a capacidade de inserir um PIN líder permite que um chamador de discagem se autenture como um líder e gerencie a reunião, se necessário.</span><span class="sxs-lookup"><span data-stu-id="4aa2c-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="4aa2c-118">Configurar a junção de reunião sem PIN</span><span class="sxs-lookup"><span data-stu-id="4aa2c-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="4aa2c-119">Para habilitar a junção de reunião sem PIN para seus usuários, use o cmdlet [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) com o parâmetro AllowAnonymousPstnActivation da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4aa2c-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="4aa2c-120">Por exemplo, o comando a seguir habilita a junção de reunião sem PIN para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="4aa2c-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="4aa2c-121">Para fins de segurança, quando a junção de reunião sem PIN estiver ativas, talvez você queira restringir a discagem de usuários anônimos, garantindo que o ConferencingPolicy seja definido da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4aa2c-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="4aa2c-122">Para obter mais informações, [consulte Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4aa2c-122">For more information, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
