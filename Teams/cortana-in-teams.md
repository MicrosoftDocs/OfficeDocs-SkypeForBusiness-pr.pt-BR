---
title: Assistente de voz da Cortana no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Saiba como usar o assistente de voz da Cortana com o Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f820bf6c44eae2cfbdb13a683d017be2f93d6756
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255545"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="5f14e-103">Assistência de voz da Cortana no Teams</span><span class="sxs-lookup"><span data-stu-id="5f14e-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="5f14e-104">A assistência de voz da Cortana tem suporte somente em aplicativos móveis do Microsoft Teams iOS e Android para usuários nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5f14e-104">Cortana voice assistance is supported on Microsoft Teams iOS and Android mobile apps only for users in the United States.</span></span> <span data-ttu-id="5f14e-105">No momento, ele não está disponível para locatários GCC, GCC-High, DoD e EDU.</span><span class="sxs-lookup"><span data-stu-id="5f14e-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="5f14e-106">A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras.</span><span class="sxs-lookup"><span data-stu-id="5f14e-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="5f14e-107">A assistência de voz da Cortana no aplicativo móvel do Microsoft Teams permite que os usuários do Microsoft 365 Enterprise simplifiquem a comunicação, a colaboração e as tarefas relacionadas à reunião usando linguagem natural falada.</span><span class="sxs-lookup"><span data-stu-id="5f14e-107">Cortana voice assistance in the Teams mobile app enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="5f14e-108">Os usuários podem falar com a Cortana clicando no botão microfone localizado no canto superior direito do aplicativo móvel do teams.</span><span class="sxs-lookup"><span data-stu-id="5f14e-108">Users can speak to Cortana by clicking on the microphone button located in the upper right of the Teams mobile app.</span></span> <span data-ttu-id="5f14e-109">Para conectar-se rapidamente à equipe enquanto estiver em trânsito, os usuários podem dizer consultas como chamadas de &#8220;Megan&#8221; ou &#8220;enviar uma mensagem para a minha próxima reunião&#8221;.</span><span class="sxs-lookup"><span data-stu-id="5f14e-109">To quickly connect with their team while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="5f14e-110">Os usuários também podem participar de reuniões dizendo &#8220;ingressar na minha próxima reunião&#8221; e usar a assistência de voz para compartilhar arquivos, verificar o calendário e muito mais.</span><span class="sxs-lookup"><span data-stu-id="5f14e-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="5f14e-111">Essas experiências de assistência de voz são fornecidas usando os [serviços de nível corporativo da Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que estão totalmente em conformidade com a privacidade, a segurança e a conformidade do Office 365, conforme refletido nos [termos dos serviços online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="5f14e-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365’s privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="5f14e-112">A imagem mostra o envio de um chat na Cortana em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="5f14e-112">The image shows sending a chat in Cortana on a mobile device.</span></span>

![Image mostra uma sequência de telas móveis mostrando uma sessão de chat da Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="5f14e-114">Controle e limitações de administração</span><span class="sxs-lookup"><span data-stu-id="5f14e-114">Admin control and Limitations</span></span>

<span data-ttu-id="5f14e-115">O recurso de assistência de voz da Cortana no Teams é oferecido usando serviços que são totalmente compatíveis com o Office 365 a privacidade, a segurança e a conformidade da empresa são prometedos como refletidos nos termos dos serviços online (OST).</span><span class="sxs-lookup"><span data-stu-id="5f14e-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="5f14e-116">O recurso será habilitado por padrão para locatários.</span><span class="sxs-lookup"><span data-stu-id="5f14e-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="5f14e-117">Os administradores de locatários podem controlar quem em seus locatários podem usar a assistência de voz da Cortana no Teams usando uma política (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="5f14e-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="5f14e-118">Essa política pode ser definida em um nível de conta de usuário ou locatário.</span><span class="sxs-lookup"><span data-stu-id="5f14e-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="5f14e-119">Os administradores podem usar o campo CortanaVoiceInvocationMode dentro desse controle de política para determinar se a Cortana está desabilitada, habilitada somente com a invocação de botão de ação ou com a chamada de ativação do Word (aplicável a dispositivos que dão suporte a ele).</span><span class="sxs-lookup"><span data-stu-id="5f14e-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it).</span></span>

<span data-ttu-id="5f14e-120">Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (a política não está disponível no centro de administração do Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="5f14e-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="5f14e-121">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="5f14e-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="5f14e-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="5f14e-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="5f14e-123">Grant CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="5f14e-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="5f14e-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="5f14e-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="5f14e-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="5f14e-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="5f14e-126">Por exemplo, o comando abaixo cria uma nova política com o nome &#8220;EmployeeCortanaPolicy&#8221; em que o assistente de voz da Cortana do Microsoft Teams está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="5f14e-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistant in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="5f14e-127">Este exemplo mostra a atualização de uma política existente com o nome &#8220;EmployeeCortanaPolicy&#8221; e a habilitação do assistente de voz da Cortana no Microsoft Teams com o botão de ação somente chamada.</span><span class="sxs-lookup"><span data-stu-id="5f14e-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistant in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="5f14e-128">Os usuários poderão chamar a Cortana tocando no botão do MIC da Cortana no Teams.</span><span class="sxs-lookup"><span data-stu-id="5f14e-128">Users will be able to invoke Cortana by tapping on the Cortana mic button in Teams.</span></span> <span data-ttu-id="5f14e-129">A invocação de ativação do Word (&#8220;Oi Cortana&#8221;) será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="5f14e-129">Wake word (&#8220;Hey Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="5f14e-130">Este exemplo mostra como atualizar a política e habilitar o assistente de voz da Cortana com o botão de ação e a chamada de ativação de palavras.</span><span class="sxs-lookup"><span data-stu-id="5f14e-130">This example shows updating the policy and enabling Cortana voice assistant with both push button and wake-word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="5f14e-131">No momento da versão inicial para usuários do Microsoft 365 Enterprise nos EUA em inglês, o aplicativo móvel do Teams não será compatível com a ativação do Word, mas será compatível no futuro.</span><span class="sxs-lookup"><span data-stu-id="5f14e-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span>

## <a name="user-control"></a><span data-ttu-id="5f14e-132">Controle de usuário</span><span class="sxs-lookup"><span data-stu-id="5f14e-132">User control</span></span>

<span data-ttu-id="5f14e-133">Usuários individuais podem experimentar a assistência de voz da Cortana no aplicativo móvel do teams clicando no botão microfone.</span><span class="sxs-lookup"><span data-stu-id="5f14e-133">Individual users can try out Cortana voice assistance in the Teams mobile app by clicking the microphone button.</span></span> <span data-ttu-id="5f14e-134">Eles também podem controlar se a Cortana no Teams está habilitada para o dispositivo usando uma configuração no aplicativo móvel do teams.</span><span class="sxs-lookup"><span data-stu-id="5f14e-134">They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app.</span></span>

1. <span data-ttu-id="5f14e-135">Abra o aplicativo móvel Teams.</span><span class="sxs-lookup"><span data-stu-id="5f14e-135">Open the Teams mobile app.</span></span>

2. <span data-ttu-id="5f14e-136">Vá para **configurações**.</span><span class="sxs-lookup"><span data-stu-id="5f14e-136">Go to **Settings**.</span></span>

3. <span data-ttu-id="5f14e-137">Selecione **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="5f14e-137">Select **Cortana**.</span></span>

4. <span data-ttu-id="5f14e-138">Mova o botão de alternância para **ativado** ou **desativado**, dependendo se você deseja assistência de voz da Cortana no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5f14e-138">Move the toggle to **On** or **Off**, depending on whether you want Cortana voice assistance on the device.</span></span>
