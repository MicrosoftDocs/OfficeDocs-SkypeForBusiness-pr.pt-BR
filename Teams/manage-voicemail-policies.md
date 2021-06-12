---
title: Gerenciar políticas de caixa postal
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Gerenciar Políticas de Caixa Postal para seus usuários.
ms.openlocfilehash: aa6b08cba7118a5e43f7f2bd3baea7fb3bc7f158
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910053"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="c12db-103">Configuração de políticas de caixa postal em sua organização</span><span class="sxs-lookup"><span data-stu-id="c12db-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="c12db-104">Para Skype for Business clientes, desabilitar a caixa postal por meio de uma política de chamada Microsoft Teams também pode desabilitar o serviço de caixa postal para seus Skype for Business usuários.</span><span class="sxs-lookup"><span data-stu-id="c12db-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

## <a name="voicemail-organization-defaults-for-all-users"></a><span data-ttu-id="c12db-105">Padrão da organização de caixa postal para todos os usuários</span><span class="sxs-lookup"><span data-stu-id="c12db-105">Voicemail organization defaults for all users</span></span>
- <span data-ttu-id="c12db-106">A transcrição da caixa postal está habilitada.</span><span class="sxs-lookup"><span data-stu-id="c12db-106">Voicemail transcription is enabled.</span></span>
- <span data-ttu-id="c12db-107">O mascaramento de profanidade de transcrição de caixa postal está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="c12db-107">Voicemail transcription profanity masking is disabled.</span></span>
- <span data-ttu-id="c12db-108">A duração máxima da gravação é definida como cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="c12db-108">The maximum recording duration is set to five minutes.</span></span>

<span data-ttu-id="c12db-109">Você pode controlar esses padrões usando os cmdlets [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) e [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="c12db-109">You can control these defaults by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="c12db-110">As mensagens de caixa postal recebidas pelos usuários em sua organização são transcritas na região onde sua organização Microsoft 365 ou Office 365 está hospedada.</span><span class="sxs-lookup"><span data-stu-id="c12db-110">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="c12db-111">A região onde seu locatário está hospedado pode não ser a mesma onde o usuário que recebe a mensagem de caixa postal está localizado.</span><span class="sxs-lookup"><span data-stu-id="c12db-111">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="c12db-112">Para exibir a região onde seu locatário [](https://go.microsoft.com/fwlink/p/?linkid=2067339) está hospedado, vá para a página Perfil da Organização e clique em Exibir **detalhes** ao lado de **Data location**.</span><span class="sxs-lookup"><span data-stu-id="c12db-112">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c12db-113">Não é possível criar uma nova instância de política para mascaramento de profanidade de transcrição e transcrição usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy.**</span><span class="sxs-lookup"><span data-stu-id="c12db-113">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="c12db-114">Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="c12db-114">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="c12db-115">Para ver todas as instâncias de política de caixa postal disponíveis, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="c12db-115">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="c12db-116">Desativação da transcrição para sua organização</span><span class="sxs-lookup"><span data-stu-id="c12db-116">Turning off transcription for your organization</span></span>

<span data-ttu-id="c12db-117">Como a configuração padrão para transcrição está em sua organização, talvez você queira desabilitá-la usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="c12db-117">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="c12db-118">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="c12db-118">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="c12db-119">Ativação do mascaramento de obscenidades para sua organização</span><span class="sxs-lookup"><span data-stu-id="c12db-119">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="c12db-120">Mascaramento de obscenidades está desativado por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c12db-120">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="c12db-121">Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="c12db-121">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="c12db-122">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="c12db-122">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a><span data-ttu-id="c12db-123">Alterar a duração da gravação para sua organização</span><span class="sxs-lookup"><span data-stu-id="c12db-123">Changing the recording duration for your organization</span></span>

<span data-ttu-id="c12db-124">O comprimento máximo de gravação é definido como cinco minutos por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c12db-124">The maximum recording length is set to five minutes by default for your organization.</span></span> <span data-ttu-id="c12db-125">Se houver um requisito comercial para aumentar ou diminuir o comprimento máximo de gravação, isso pode ser feito usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="c12db-125">If there is a business requirement to increase or decrease the maximum recording length, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="c12db-126">Por exemplo, para definir o tempo máximo de gravação como 60 segundos, execute:</span><span class="sxs-lookup"><span data-stu-id="c12db-126">For example, to set the maximum recording time to 60 seconds,  run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a><span data-ttu-id="c12db-127">Prompts do sistema de idiomas duplos para sua organização</span><span class="sxs-lookup"><span data-stu-id="c12db-127">Dual language system prompts for your organization</span></span>

<span data-ttu-id="c12db-128">Por padrão, os prompts do sistema de caixa postal são apresentados aos chamadores no idioma selecionado pelo usuário ao configurar sua caixa postal.</span><span class="sxs-lookup"><span data-stu-id="c12db-128">By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail.</span></span> <span data-ttu-id="c12db-129">Se houver um requisito comercial para que os prompts do sistema de caixa postal sejam apresentados em dois idiomas, isso poderá ser feito usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="c12db-129">If there is a business requirement to have the voicemail system prompts presented in two languages, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="c12db-130">Um idioma principal e secundário deve ser definido e pode não ser o mesmo.</span><span class="sxs-lookup"><span data-stu-id="c12db-130">A primary and secondary language must be set and may not be the same.</span></span> <span data-ttu-id="c12db-131">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="c12db-131">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="c12db-132">Desativação da transcrição para usuário</span><span class="sxs-lookup"><span data-stu-id="c12db-132">Turning off transcription for a user</span></span>

<span data-ttu-id="c12db-133">As políticas de usuário são avaliadas antes das configurações organizacionais padrão.</span><span class="sxs-lookup"><span data-stu-id="c12db-133">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="c12db-134">Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os seus usuários, você poderá atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="c12db-134">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="c12db-135">Para desabilitar a transcrição para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="c12db-135">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="c12db-136">Ativação do mascaramento de obscenidades para um usuário</span><span class="sxs-lookup"><span data-stu-id="c12db-136">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="c12db-137">Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="c12db-137">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="c12db-138">Para habilitar o mascaramento de obscenidades para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="c12db-138">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a><span data-ttu-id="c12db-139">Alterar a duração da gravação para um usuário</span><span class="sxs-lookup"><span data-stu-id="c12db-139">Changing the recording duration for a user</span></span>

<span data-ttu-id="c12db-140">Primeiro, você deve criar uma política de caixa postal personalizada usando o cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="c12db-140">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="c12db-141">O comando mostrado abaixo cria uma política de caixa postal online por usuário OneMinuteVoicemailPolicy com MaximumRecordingLength definida como 60 segundos e outros campos definidos como valor global de nível de locatário.</span><span class="sxs-lookup"><span data-stu-id="c12db-141">The command shown below creates a per-user online voicemail policy OneMinuteVoicemailPolicy with MaximumRecordingLength set to 60 seconds and other fields set to tenant level global value.</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

<span data-ttu-id="c12db-142">Para atribuir essa política personalizada a um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="c12db-142">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a><span data-ttu-id="c12db-143">Prompts do sistema de idiomas duplos para um usuário</span><span class="sxs-lookup"><span data-stu-id="c12db-143">Dual language system prompts for a user</span></span>

<span data-ttu-id="c12db-144">Primeiro, você deve criar uma política de caixa postal personalizada usando o cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="c12db-144">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="c12db-145">O comando mostrado abaixo cria uma política de caixa postal online por usuário enUS-esSP-VoicemailPolicy com o PrimarySystemPromptLanguage definido como en-US (inglês - Estados Unidos) e SecondarySystemPromptLanguage definido como es-SP (Espanhol - Espanha).</span><span class="sxs-lookup"><span data-stu-id="c12db-145">The command shown below creates a per-user online voicemail policy enUS-esSP-VoicemailPolicy with the PrimarySystemPromptLanguage set to en-US (English - United States) and the SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

<span data-ttu-id="c12db-146">Para atribuir essa política personalizada a um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="c12db-146">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> <span data-ttu-id="c12db-147">O Get-CsOnlineVoicemailPolicy cmdlet não está retornando atualmente os valores para PrimarySystemPromptLanguage e SecondarySystemPromptLanguage.</span><span class="sxs-lookup"><span data-stu-id="c12db-147">The Get-CsOnlineVoicemailPolicy cmdlet is not currently returning the values for PrimarySystemPromptLanguage and SecondarySystemPromptLanguage.</span></span> <span data-ttu-id="c12db-148">Para ver esses valores modificarem o comando da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c12db-148">To see these values modify the command as follows:</span></span>
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> <span data-ttu-id="c12db-149">Substitua **PolicyName** pelo nome da política.</span><span class="sxs-lookup"><span data-stu-id="c12db-149">Replace **PolicyName** with the name of the policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c12db-150">O serviço de caixa postal em Microsoft 365 e Office 365 armazena em cache políticas de caixa postal e atualiza o cache a cada 6 horas.</span><span class="sxs-lookup"><span data-stu-id="c12db-150">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="c12db-151">Portanto, as alterações de política feitas podem levar até 6 horas para serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="c12db-151">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
