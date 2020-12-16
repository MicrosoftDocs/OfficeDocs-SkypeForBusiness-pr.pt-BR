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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686437"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="07dde-103">Assistência de voz da Cortana no Teams</span><span class="sxs-lookup"><span data-stu-id="07dde-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="07dde-104">A assistência de voz da Cortana tem suporte em aplicativos móveis do Microsoft Teams iOS e Android, as salas do Microsoft Teams no Windows e no Microsoft Teams são exibidas somente para usuários nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="07dde-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="07dde-105">No momento, ele não está disponível para locatários GCC, GCC-High, DoD e EDU.</span><span class="sxs-lookup"><span data-stu-id="07dde-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="07dde-106">A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras.</span><span class="sxs-lookup"><span data-stu-id="07dde-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="07dde-107">A assistência de voz da Cortana em salas do Microsoft Teams é liberada na visualização.</span><span class="sxs-lookup"><span data-stu-id="07dde-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="07dde-108">No lançamento da versão prévia, a Cortana tem suporte somente nos EUA com o idioma EN-US nos dispositivos que conectavam microfones Rally.</span><span class="sxs-lookup"><span data-stu-id="07dde-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="07dde-109">A assistência de voz da Cortana no aplicativo móvel do Microsoft Teams em salas do Microsoft Teams no Windows e em dispositivos de exibição do Microsoft Teams permite que os usuários do Microsoft 365 Enterprise simplifiquem a comunicação, a colaboração e as tarefas relacionadas à reunião usando linguagem natural falada.</span><span class="sxs-lookup"><span data-stu-id="07dde-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="07dde-110">Os usuários podem falar com a Cortana selecionando o botão do microfone localizado no canto superior direito do aplicativo móvel do teams ou dizendo &#8220;Cortana&#8221; na sala do Microsoft Teams ou ao usar uma exibição do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="07dde-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="07dde-111">Para conectar-se rapidamente à equipe de mão e enquanto estiver em trânsito, os usuários podem dizer consultas como chamadas de &#8220;Megan&#8221; ou &#8220;enviar uma mensagem para a minha próxima reunião&#8221;.</span><span class="sxs-lookup"><span data-stu-id="07dde-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="07dde-112">Os usuários também podem participar de reuniões dizendo &#8220;ingressar na minha próxima reunião&#8221; e usar a assistência de voz para compartilhar arquivos, verificar o calendário e muito mais.</span><span class="sxs-lookup"><span data-stu-id="07dde-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="07dde-113">Essas experiências de assistência de voz são fornecidas usando os [serviços de nível corporativo da Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que estão totalmente em conformidade com a privacidade, a segurança e a conformidade do Office 365, conforme refletido nos [termos dos serviços online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="07dde-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="07dde-114">A imagem mostra o envio de um chat usando a Cortana em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="07dde-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![uma sequência de telas móveis mostrando uma sessão de chat da Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="07dde-116">Controle e limitações de administração</span><span class="sxs-lookup"><span data-stu-id="07dde-116">Admin control and limitations</span></span>

<span data-ttu-id="07dde-117">O recurso de assistência de voz da Cortana no Teams é oferecido usando serviços que são totalmente compatíveis com o Office 365 a privacidade, a segurança e a conformidade da empresa são prometedos como refletidos nos termos dos serviços online (OST).</span><span class="sxs-lookup"><span data-stu-id="07dde-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="07dde-118">O recurso será habilitado por padrão para locatários.</span><span class="sxs-lookup"><span data-stu-id="07dde-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="07dde-119">Os administradores de locatários podem controlar quem em seus locatários podem usar a assistência de voz da Cortana no Teams usando uma política (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="07dde-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="07dde-120">Essa política pode ser definida em um nível de conta de usuário ou locatário.</span><span class="sxs-lookup"><span data-stu-id="07dde-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="07dde-121">Os administradores podem usar o campo CortanaVoiceInvocationMode dentro desse controle de política para determinar se a Cortana está desabilitada, habilitada somente com o recurso de invocação de botão ou com a chamada do Wake Word (aplicável a dispositivos que dão suporte a ele, como a exibição do Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="07dde-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="07dde-122">Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (a política não está disponível no centro de administração do Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="07dde-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="07dde-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="07dde-123">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="07dde-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="07dde-124">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="07dde-125">Grant CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="07dde-125">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="07dde-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="07dde-126">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="07dde-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="07dde-127">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="07dde-128">Por exemplo, o comando abaixo cria uma nova política com o nome &#8220;EmployeeCortanaPolicy&#8221; onde a assistência de voz da Cortana no Microsoft Teams está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="07dde-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="07dde-129">Este exemplo mostra a atualização de uma política existente com o nome &#8220;EmployeeCortanaPolicy&#8221; e a habilitação da assistência de voz da Cortana no Microsoft Teams com o botão de ação somente chamada.</span><span class="sxs-lookup"><span data-stu-id="07dde-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="07dde-130">Os usuários poderão chamar a Cortana selecionando o botão do MIC da Cortana no Teams.</span><span class="sxs-lookup"><span data-stu-id="07dde-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="07dde-131">Ativar o Word (&#8220;Oi Cortana&#8221; ou &#8220;&#8221; da Cortana) será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="07dde-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="07dde-132">Este exemplo mostra a atualização da política e a habilitação da assistência de voz da Cortana com o botão de ação e a chamada de ativação do Word.</span><span class="sxs-lookup"><span data-stu-id="07dde-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="07dde-133">No momento, do lançamento inicial para usuários do Microsoft 365 Enterprise nos EUA em inglês, as seguintes funções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="07dde-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="07dde-134">O aplicativo móvel do Teams não oferecerá suporte à ativação do Word de ativação, mas será compatível no futuro.</span><span class="sxs-lookup"><span data-stu-id="07dde-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="07dde-135">As salas do Microsoft Teams no Windows e os dispositivos de exibição do Microsoft Teams dão suporte à ativação do Word de ativação.</span><span class="sxs-lookup"><span data-stu-id="07dde-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="07dde-136">Controle de usuário</span><span class="sxs-lookup"><span data-stu-id="07dde-136">User control</span></span>

<span data-ttu-id="07dde-137">Usuários individuais podem experimentar a assistência de voz da Cortana em diferentes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="07dde-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="07dde-138">Selecione o botão de microfone no aplicativo móvel do teams.</span><span class="sxs-lookup"><span data-stu-id="07dde-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="07dde-139">Selecione o botão de microfone ou diga "Cortana" nas salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="07dde-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="07dde-140">Diga "Cortana" em dispositivos de vídeo do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="07dde-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="07dde-141">Você pode controlar se a Cortana no Microsoft Teams está habilitada para seu dispositivo usando uma configuração no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07dde-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="07dde-142">Aplicativo móvel do teams ou a exibição do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07dde-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="07dde-143">Abra o aplicativo móvel Teams.</span><span class="sxs-lookup"><span data-stu-id="07dde-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="07dde-144">Selecione **configurações**  >  **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="07dde-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="07dde-145">Mover ou **desativar** o **botão de alternância** .</span><span class="sxs-lookup"><span data-stu-id="07dde-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="07dde-146">Exibição do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07dde-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="07dde-147">Vá para a tela ambiente (início) da tela do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="07dde-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="07dde-148">Selecione o avatar do usuário e, em seguida, selecione **configurações**.</span><span class="sxs-lookup"><span data-stu-id="07dde-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="07dde-149">Se a Cortana estiver habilitada, por exemplo, "Cortana, vá para configurações".</span><span class="sxs-lookup"><span data-stu-id="07dde-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="07dde-150">Mover ou **desativar** o **botão de alternância** .</span><span class="sxs-lookup"><span data-stu-id="07dde-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="07dde-151">Salas do Microsoft Teams no Windows</span><span class="sxs-lookup"><span data-stu-id="07dde-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="07dde-152">A realização de alterações no nível do dispositivo estará disponível se a Cortana estiver habilitada no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="07dde-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="07dde-153">A Cortana será liberada por padrão.</span><span class="sxs-lookup"><span data-stu-id="07dde-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="07dde-154">Para habilitar a Cortana no nível do dispositivo, esses atributos XML devem ser adicionados ao arquivo XML do SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="07dde-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="07dde-155">A realização de alterações no nível da reunião estará disponível se a Cortana estiver habilitada no nível do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07dde-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="07dde-156">Para habilitar a assistência de voz da Cortana durante uma reunião, mova o botão **de** **alternância.**</span><span class="sxs-lookup"><span data-stu-id="07dde-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="07dde-157">Depois que a reunião termina, a Cortana retorna ao conjunto de configurações do nível do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07dde-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
