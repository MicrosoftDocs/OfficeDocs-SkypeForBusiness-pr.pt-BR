---
title: Configurar ingresso em reunião sem PIN no Skype for Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Resumo: Saiba como configurar o PIN sem a opção de ingresso em Skype para Business Server 2015 da reunião.'
ms.openlocfilehash: 6e9e26f856fec85b3f7436684d1b084eb3873ba9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="fccb8-103">Configurar ingresso em reunião sem PIN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fccb8-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="fccb8-104">**Resumo:** Saiba como configurar o PIN sem a opção de ingresso em Skype para Business Server 2015 da reunião.</span><span class="sxs-lookup"><span data-stu-id="fccb8-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fccb8-105">Quando um chamador discada tenta ingressar em uma reunião, o serviço de atendedor automático da conferência (CAA) coloca o chamador em uma caneta fornecerá diferente do Lobby & #x 2014; Se um apresentador não ainda estiver em uma chamada e o chamador discada não tiver inserido um líder de PIN.</span><span class="sxs-lookup"><span data-stu-id="fccb8-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="fccb8-106">A opção de ingresso na reunião sem o PIN permite a participação na reunião discada dos chamadores sem inserir PIN de líder, mesmo se eles forem a primeira pessoa que da chamada.</span><span class="sxs-lookup"><span data-stu-id="fccb8-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="fccb8-107">Lembre-se do seguinte ao configurar esse recurso:</span><span class="sxs-lookup"><span data-stu-id="fccb8-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="fccb8-108">Aplica-se somente a reuniões particulares.</span><span class="sxs-lookup"><span data-stu-id="fccb8-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="fccb8-109">Permite que os chamadores PSTN permaneçam na reuniões particulares sem a presença de usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="fccb8-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="fccb8-110">Depois que a configuração for alterada, aplica-se a todas as reuniões privadas existentes e novas.</span><span class="sxs-lookup"><span data-stu-id="fccb8-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="fccb8-111">Pode ser ativada no site do organizador ou em nível global.</span><span class="sxs-lookup"><span data-stu-id="fccb8-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="fccb8-112">Opções para quem pode ignorar o lobby podem ser definidas para qualquer um dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="fccb8-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="fccb8-113">**Qualquer pessoa de minha empresa com Chamadores entram diretamente**</span><span class="sxs-lookup"><span data-stu-id="fccb8-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="fccb8-114">**Qualquer pessoa (sem restrições) com Chamadores entram diretamente** (Esta é a configuração padrão).</span><span class="sxs-lookup"><span data-stu-id="fccb8-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="fccb8-115">Quando configurado para habilitar o ingresso sem PIN, o serviço CAA ainda avisa o PIN do líder.</span><span class="sxs-lookup"><span data-stu-id="fccb8-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="fccb8-116">Os usuários podem participar da reunião se um PIN for ou não inserido.</span><span class="sxs-lookup"><span data-stu-id="fccb8-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="fccb8-117">No entanto, preservar a capacidade de inserir um líder PIN permite que um chamador dial-in autenticar como um líder e gerenciar a reunião, se necessário.</span><span class="sxs-lookup"><span data-stu-id="fccb8-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="fccb8-118">Configurar o ingresso à reunião sem PIN</span><span class="sxs-lookup"><span data-stu-id="fccb8-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="fccb8-119">Para habilitar a participação de reunião sem PIN para seus usuários, use o cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) com o parâmetro AllowAnonymousPstnActivation conforme segue:</span><span class="sxs-lookup"><span data-stu-id="fccb8-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="fccb8-120">Por exemplo, o seguinte comando habilita o ingresso à reunião sem PIN para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="fccb8-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True

```

<span data-ttu-id="fccb8-121">Para fins de segurança, quando o ingresso à reunião sem PIN estiver ativado, você pode querer restringir usuários anônimos de discagem externa, assegurando que ConferencingPolicy seja definida da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fccb8-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False

```

<span data-ttu-id="fccb8-122">Para obter mais informações, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fccb8-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

