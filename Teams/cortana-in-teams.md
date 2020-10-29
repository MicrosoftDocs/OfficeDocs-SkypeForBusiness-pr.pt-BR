---
title: Assistência de voz da Cortana no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Saiba como usar a assistência de voz da Cortana com o Teams
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
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785385"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="d4f7f-103">Assistência de voz da Cortana no Teams</span><span class="sxs-lookup"><span data-stu-id="d4f7f-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="d4f7f-104">A assistência de voz da Cortana tem suporte nos aplicativos móveis do Microsoft Teams iOS e Android, e no Microsoft Teams é exibido apenas para usuários nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="d4f7f-105">No momento, ele não está disponível para locatários GCC, GCC-High, DoD e EDU.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="d4f7f-106">A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="d4f7f-107">A assistência de voz da Cortana no aplicativo móvel do Teams e nos dispositivos de vídeo do Microsoft Teams permite que os usuários do Microsoft 365 Enterprise simplifiquem a comunicação, a colaboração e as tarefas relacionadas à reunião usando linguagem natural falada.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-107">Cortana voice assistance in the Teams mobile app and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="d4f7f-108">Os usuários podem falar com a Cortana selecionando o botão do microfone localizado no canto superior direito do aplicativo móvel do teams ou dizendo &#8220;Cortana&#8221; na tela do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-108">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams display.</span></span> <span data-ttu-id="d4f7f-109">Para conectar-se rapidamente à equipe de mão e enquanto estiver em trânsito, os usuários podem dizer consultas como chamadas de &#8220;Megan&#8221; ou &#8220;enviar uma mensagem para a minha próxima reunião&#8221;.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-109">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="d4f7f-110">Os usuários também podem participar de reuniões dizendo &#8220;ingressar na minha próxima reunião&#8221; e usar a assistência de voz para compartilhar arquivos, verificar o calendário e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="d4f7f-111">Essas experiências de assistência de voz são fornecidas usando os [serviços de nível corporativo da Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que estão totalmente em conformidade com a privacidade, a segurança e a conformidade do Office 365, conforme refletido nos [termos dos serviços online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="d4f7f-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="d4f7f-112">A imagem mostra o envio de um chat usando a Cortana em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-112">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Image mostra uma sequência de telas móveis mostrando uma sessão de chat da Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="d4f7f-114">Controle e limitações de administração</span><span class="sxs-lookup"><span data-stu-id="d4f7f-114">Admin control and limitations</span></span>

<span data-ttu-id="d4f7f-115">O recurso de assistência de voz da Cortana no Teams é oferecido usando serviços que são totalmente compatíveis com o Office 365 a privacidade, a segurança e a conformidade da empresa são prometedos como refletidos nos termos dos serviços online (OST).</span><span class="sxs-lookup"><span data-stu-id="d4f7f-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="d4f7f-116">O recurso será habilitado por padrão para locatários.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="d4f7f-117">Os administradores de locatários podem controlar quem em seus locatários podem usar a assistência de voz da Cortana no Teams usando uma política (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="d4f7f-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="d4f7f-118">Essa política pode ser definida em um nível de conta de usuário ou locatário.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="d4f7f-119">Os administradores podem usar o campo CortanaVoiceInvocationMode dentro desse controle de política para determinar se a Cortana está desabilitada, habilitada somente com a invocação do botão de ação ou com a chamada do Wake Word (aplicável a dispositivos que dão suporte a ele, como a exibição do Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="d4f7f-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="d4f7f-120">Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (a política não está disponível no centro de administração do Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="d4f7f-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="d4f7f-121">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="d4f7f-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="d4f7f-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="d4f7f-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="d4f7f-123">Grant CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="d4f7f-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="d4f7f-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="d4f7f-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="d4f7f-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="d4f7f-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="d4f7f-126">Por exemplo, o comando abaixo cria uma nova política com o nome &#8220;EmployeeCortanaPolicy&#8221; onde a assistência de voz da Cortana no Microsoft Teams está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="d4f7f-127">Este exemplo mostra a atualização de uma política existente com o nome &#8220;EmployeeCortanaPolicy&#8221; e a habilitação da assistência de voz da Cortana no Microsoft Teams com o botão de ação somente chamada.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="d4f7f-128">Os usuários poderão chamar a Cortana selecionando o botão do MIC da Cortana no Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-128">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="d4f7f-129">Ativar o Word (&#8220;Oi Cortana&#8221; ou &#8220;&#8221; da Cortana) será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-129">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="d4f7f-130">Este exemplo mostra a atualização da política e a habilitação da assistência de voz da Cortana com o botão de ação e a chamada de ativação do Word.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-130">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="d4f7f-131">No momento da versão inicial para usuários do Microsoft 365 Enterprise nos EUA em inglês, o aplicativo móvel do Teams não será compatível com a ativação do Word, mas será compatível no futuro.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span> <span data-ttu-id="d4f7f-132">Ativar a ativação do Word funcionará em dispositivos de exibição do Microsoft Teams na versão inicial.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-132">Wake word activation will work on Microsoft Teams display devices at initial release.</span></span>

## <a name="user-control"></a><span data-ttu-id="d4f7f-133">Controle de usuário</span><span class="sxs-lookup"><span data-stu-id="d4f7f-133">User control</span></span>

<span data-ttu-id="d4f7f-134">Usuários individuais podem experimentar a assistência de voz da Cortana no aplicativo móvel do teams selecionando o botão do microfone.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-134">Individual users can try out Cortana voice assistance in the Teams mobile app by selecting the microphone button.</span></span> <span data-ttu-id="d4f7f-135">Eles podem experimentar a assistência de voz da Cortana em dispositivos de exibição do Microsoft Teams simplesmente dizendo &#8220;Cortana. &#8221; eles também podem controlar se a Cortana no Teams está habilitada para seu dispositivo usando uma configuração no aplicativo móvel do Microsoft Teams ou na exibição do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-135">They can try out Cortana voice assistance on Microsoft Teams display devices by simply saying &#8220;Cortana.&#8221; They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app or on the Microsoft Teams display.</span></span>

1. <span data-ttu-id="d4f7f-136">Abra o aplicativo móvel do teams ou vá para a tela ambiente (residencial) da tela do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-136">Open the Teams mobile app, or go to the ambient (home) screen of the Microsoft Teams display.</span></span>

2. <span data-ttu-id="d4f7f-137">No aplicativo móvel do Microsoft Teams, vá para **configurações** .</span><span class="sxs-lookup"><span data-stu-id="d4f7f-137">In the Teams mobile app, go to **Settings** .</span></span> <span data-ttu-id="d4f7f-138">Na tela do Microsoft Teams, selecione o avatar do usuário e, em seguida, selecione configurações.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-138">On the Microsoft Teams display, select the user avatar, and then select Settings.</span></span> <span data-ttu-id="d4f7f-139">Se a Cortana estiver habilitada, digamos, &#8220;Cortana, vá para configurações. &#8221;</span><span class="sxs-lookup"><span data-stu-id="d4f7f-139">If Cortana is enabled, say, &#8220;Cortana, go to Settings.&#8221;</span></span>

3. <span data-ttu-id="d4f7f-140">Selecione **Cortana** .</span><span class="sxs-lookup"><span data-stu-id="d4f7f-140">Select **Cortana** .</span></span>

4. <span data-ttu-id="d4f7f-141">Mova o botão de alternância para **ativado** ou **desativado** , dependendo se você deseja assistência de voz da Cortana no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4f7f-141">Move the toggle to **On** or **Off** , depending on whether you want Cortana voice assistance on the device.</span></span>
