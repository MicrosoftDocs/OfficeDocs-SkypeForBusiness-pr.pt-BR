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
ms.openlocfilehash: 112a2ac98ee22c46cb78c579ead947f70a1d6d447ac81ace3aef224304a281dd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342965"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Configuração de políticas de caixa postal em sua organização

> [!WARNING]
> Para Skype for Business clientes, desabilitar a caixa postal por meio de uma política de chamada Microsoft Teams também pode desabilitar o serviço de caixa postal para seus Skype for Business usuários.

## <a name="voicemail-organization-defaults-for-all-users"></a>Padrão da organização de caixa postal para todos os usuários
- A transcrição da caixa postal está habilitada.
- O mascaramento de profanidade de transcrição de caixa postal está desabilitado.
- A duração máxima da gravação é definida como cinco minutos.

Você pode controlar esses padrões usando os cmdlets [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) e [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)

As mensagens de caixa postal recebidas pelos usuários em sua organização são transcritas na região onde sua organização Microsoft 365 ou Office 365 está hospedada. A região onde seu locatário está hospedado pode não ser a mesma onde o usuário que recebe a mensagem de caixa postal está localizado. Para exibir a região onde seu locatário [](https://go.microsoft.com/fwlink/p/?linkid=2067339) está hospedado, vá para a página Perfil da Organização e clique em Exibir **detalhes** ao lado de **Data location**.

> [!IMPORTANT]
> Não é possível criar uma nova instância de política para mascaramento de profanidade de transcrição e transcrição usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy.**

Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal. Para ver todas as instâncias de política de caixa postal disponíveis, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)

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
  
## <a name="turning-off-transcription-for-your-organization"></a>Desativação da transcrição para sua organização

Como a configuração padrão para transcrição está em sua organização, talvez você queira desabilitá-la usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Para fazer isso, execute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Ativação do mascaramento de obscenidades para sua organização

Mascaramento de obscenidades está desativado por padrão para sua organização. Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Para fazer isso, execute:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a>Alterar a duração da gravação para sua organização

O comprimento máximo de gravação é definido como cinco minutos por padrão para sua organização. Se houver um requisito comercial para aumentar ou diminuir o comprimento máximo de gravação, isso pode ser feito usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Por exemplo, para definir o tempo máximo de gravação como 60 segundos, execute:

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a>Prompts do sistema de idiomas duplos para sua organização

Por padrão, os prompts do sistema de caixa postal são apresentados aos chamadores no idioma selecionado pelo usuário ao configurar sua caixa postal. Se houver um requisito comercial para que os prompts do sistema de caixa postal sejam apresentados em dois idiomas, isso poderá ser feito usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Um idioma principal e secundário deve ser definido e pode não ser o mesmo. Para fazer isso, execute:

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a>Desativação da transcrição para usuário

As políticas de usuário são avaliadas antes das configurações organizacionais padrão. Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os seus usuários, você poderá atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)

Para desabilitar a transcrição para um único usuário, execute:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Ativação do mascaramento de obscenidades para um usuário

Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).

Para habilitar o mascaramento de obscenidades para um único usuário, execute:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a>Alterar a duração da gravação para um usuário

Primeiro, você deve criar uma política de caixa postal personalizada usando o cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy) O comando mostrado abaixo cria uma política de caixa postal online por usuário OneMinuteVoicemailPolicy com MaximumRecordingLength definida como 60 segundos e outros campos definidos como valor global de nível de locatário.

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

Para atribuir essa política personalizada a um usuário, execute: 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a>Prompts do sistema de idiomas duplos para um usuário

Primeiro, você deve criar uma política de caixa postal personalizada usando o cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy) O comando mostrado abaixo cria uma política de caixa postal online por usuário enUS-esSP-VoicemailPolicy com o PrimarySystemPromptLanguage definido como en-US (inglês - Estados Unidos) e SecondarySystemPromptLanguage definido como es-SP (Espanhol - Espanha).

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

Para atribuir essa política personalizada a um usuário, execute: 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> O Get-CsOnlineVoicemailPolicy cmdlet não está retornando atualmente os valores para PrimarySystemPromptLanguage e SecondarySystemPromptLanguage. Para ver esses valores modificarem o comando da seguinte forma:
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> Substitua **PolicyName** pelo nome da política.


> [!IMPORTANT]
> O serviço de caixa postal em Microsoft 365 e Office 365 armazena em cache políticas de caixa postal e atualiza o cache a cada 6 horas. Portanto, as alterações de política feitas podem levar até 6 horas para serem aplicadas.
