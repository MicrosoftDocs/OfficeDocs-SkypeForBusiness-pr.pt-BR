---
title: Cortana de voz no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Saiba como usar a Cortana de voz com Teams
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
ms.openlocfilehash: 0b343a3f69d2b0f97f9d7d3054951719da2e9e43
ms.sourcegitcommit: b7da2655607a17cde9537ed9e00db29b4c1a68df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53219138"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="f1aaf-103">Cortana de voz no Teams</span><span class="sxs-lookup"><span data-stu-id="f1aaf-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="f1aaf-104">Cortana Microsoft Teams assistência de voz é suportada em aplicativos móveis para iOS e Android e Microsoft Teams para usuários nos Estados Unidos, Reino Unido, Canadá, Índia e Austrália.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="f1aaf-105">Salas do Microsoft Teams no Windows é suportado apenas para usuários nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="f1aaf-106">Cortana assistência de voz não está disponível atualmente para locatários de EDU GCC, GCC-High, DoD e não-US.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="f1aaf-107">Cortana de voz no aplicativo móvel Teams agora está disponível para clientes EDU no en-US.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="f1aaf-108">A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="f1aaf-109">Cortana de voz no Salas do Microsoft Teams é lançada em Preview.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="f1aaf-110">Em sua versão de visualização, Cortana é compatível somente nos EUA com o idioma EN-US em dispositivos que conectaram microfones de Comício.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="f1aaf-111">Cortana assistência de voz no aplicativo móvel Teams, no Salas do Microsoft Teams no Windows e em dispositivos de exibição do Microsoft Teams permite que os usuários Microsoft 365 Enterprise agilizem a comunicação, a colaboração e as tarefas relacionadas à reunião usando a linguagem natural falada.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="f1aaf-112">Os usuários podem falar com Cortana selecionando o botão de microfone localizado na parte superior direita do aplicativo móvel do Teams ou dizendo &#8220;Cortana&#8221; na sala Microsoft Teams ou ao usar uma tela Microsoft Teams de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="f1aaf-113">Para se conectar rapidamente com sua equipe de mãos livres e enquanto estão em tempo livre, os usuários podem dizer consultas como &#8220;chamar Megan&#8221; ou &#8220;enviar uma mensagem para minha próxima reunião&#8221;.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="f1aaf-114">Os usuários também podem participar de reuniões dizendo &#8220;minha próxima reunião&#8221; e usar assistência de voz para compartilhar arquivos, verificar seu calendário e muito mais.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="f1aaf-115">Essas experiências de assistência [](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) de voz são entregues usando Cortana de nível empresarial que estão em conformidade com as promessas de privacidade, segurança e conformidade do Office 365 da Office 365, conforme refletido nos Termos de Serviços [Online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="f1aaf-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="f1aaf-116">A imagem mostra o envio de um chat usando Cortana em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-116">The image shows sending a chat using Cortana on a mobile device.</span></span>

![uma sequência de telas móveis mostrando uma sessão Cortana chat](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="f1aaf-118">Controle de administrador e limitações</span><span class="sxs-lookup"><span data-stu-id="f1aaf-118">Admin control and limitations</span></span>

<span data-ttu-id="f1aaf-119">Cortana assistência de voz no Teams Office 365 é entregue usando serviços que estão em conformidade com as promessas de privacidade, segurança e conformidade no nível da empresa, conforme refletido nos Termos de Serviços Online (OST).</span><span class="sxs-lookup"><span data-stu-id="f1aaf-119">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="f1aaf-120">O recurso será habilitado por padrão para locatários.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-120">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="f1aaf-121">Os administradores de locatários podem controlar quem em seu locatário pode usar Cortana de voz Teams usando uma política (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="f1aaf-121">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="f1aaf-122">Essa política é definida em um nível de conta de usuário ou de locatário.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-122">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="f1aaf-123">Os administradores podem usar o campo CortanaVoiceInvocationMode dentro deste controle de política para determinar se o Cortana está desabilitado, habilitado somente com invocação por botão ou com invocação de palavra de alerta também (aplicável a dispositivos que a suportam, como a Microsoft Teams display).</span><span class="sxs-lookup"><span data-stu-id="f1aaf-123">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="f1aaf-124">Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (a política não está disponível no Microsoft Teams de administração).</span><span class="sxs-lookup"><span data-stu-id="f1aaf-124">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="f1aaf-125">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f1aaf-125">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f1aaf-126">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f1aaf-126">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f1aaf-127">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f1aaf-127">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f1aaf-128">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f1aaf-128">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f1aaf-129">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f1aaf-129">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="f1aaf-130">Por exemplo, o comando a seguir cria uma nova política com o nome &#8220;EmployeeCortanaPolicy&#8221; onde Cortana assistência de voz no Microsoft Teams está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-130">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="f1aaf-131">Este exemplo mostra a atualização de uma política existente com o nome &#8220;EmployeeCortanaPolicy&#8221; e habilitando Cortana assistência de voz no Microsoft Teams somente com invocação por botão.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-131">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="f1aaf-132">Os usuários poderão invocar o Cortana selecionando o botão Cortana microfone no Teams.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-132">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="f1aaf-133">Palavra de acordar (&#8220;chamada hey Cortana&#8221; ou &#8220;Cortana&#8221;) será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-133">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="f1aaf-134">Este exemplo mostra a atualização da política e a habilitação Cortana de voz com o botão push e a invocação de palavra de alerta.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-134">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="f1aaf-135">No momento, da versão inicial para Microsoft 365 Enterprise usuários nos EUA em inglês, as seguintes funções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="f1aaf-135">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="f1aaf-136">O Teams aplicativo móvel não dará suporte à ativação de palavra de alerta, mas ele terá suporte no futuro.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-136">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="f1aaf-137">Salas do Microsoft Teams em Windows e Microsoft Teams de exibição darão suporte à ativação de palavra de alerta.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-137">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="f1aaf-138">Controle do usuário</span><span class="sxs-lookup"><span data-stu-id="f1aaf-138">User control</span></span>

<span data-ttu-id="f1aaf-139">Usuários individuais podem tentar Cortana de voz em diferentes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="f1aaf-139">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="f1aaf-140">Selecione o botão microfone no aplicativo Teams celular.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-140">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="f1aaf-141">Selecione o botão de microfone ou diga "Cortana" no Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-141">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="f1aaf-142">Diga "Cortana" em Microsoft Teams exibe dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-142">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="f1aaf-143">Você pode controlar se Cortana no Teams está habilitado para seu dispositivo usando uma configuração no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-143">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="f1aaf-144">Teams aplicativo móvel ou o Microsoft Teams de exibição</span><span class="sxs-lookup"><span data-stu-id="f1aaf-144">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="f1aaf-145">Abra o aplicativo Teams celular.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-145">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="f1aaf-146">Selecione **Configurações**  >  **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-146">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="f1aaf-147">Mova a **alternância Para ou** **para fora.**</span><span class="sxs-lookup"><span data-stu-id="f1aaf-147">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="f1aaf-148">Microsoft Teams exibição</span><span class="sxs-lookup"><span data-stu-id="f1aaf-148">Microsoft Teams display</span></span>

  1. <span data-ttu-id="f1aaf-149">Vá para a tela ambiente (home) do Microsoft Teams display.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-149">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="f1aaf-150">Selecione o avatar do usuário e selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-150">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="f1aaf-151">Se Cortana estiver habilitado, diga, "Cortana, vá para Configurações".</span><span class="sxs-lookup"><span data-stu-id="f1aaf-151">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="f1aaf-152">Mova a **alternância Para ou** **para fora.**</span><span class="sxs-lookup"><span data-stu-id="f1aaf-152">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="f1aaf-153">Salas do Microsoft Teams no Windows</span><span class="sxs-lookup"><span data-stu-id="f1aaf-153">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="f1aaf-154">Fazer alterações no nível do dispositivo estará disponível se Cortana estiver habilitado no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-154">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="f1aaf-155">Cortana será liberado OFF por padrão.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-155">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="f1aaf-156">Para habilitar Cortana no nível do dispositivo, esses atributos XML devem ser adicionados no arquivo XML do SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="f1aaf-156">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="f1aaf-157">Fazer alterações no nível da reunião estará disponível se Cortana estiver habilitado no nível do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-157">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="f1aaf-158">Para habilitar Cortana de voz durante uma reunião, mova a **alternância Ativado** ou **Desligado.**</span><span class="sxs-lookup"><span data-stu-id="f1aaf-158">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="f1aaf-159">Depois que a reunião terminar, Cortana retornará às configurações de nível do dispositivo definidas.</span><span class="sxs-lookup"><span data-stu-id="f1aaf-159">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
