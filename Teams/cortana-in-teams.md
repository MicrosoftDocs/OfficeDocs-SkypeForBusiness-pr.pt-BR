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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522308"
---
# <a name="cortana-voice-assistance-in-teams"></a>Assistência de voz da Cortana no Teams

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> A assistência de voz da Cortana tem suporte somente em aplicativos móveis do Microsoft Teams iOS e Android para usuários nos Estados Unidos. No momento, ele não está disponível para locatários GCC, GCC-High, DoD e EDU. A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras.

A assistência de voz da Cortana no aplicativo móvel do Microsoft Teams permite que os usuários do Microsoft 365 Enterprise simplifiquem a comunicação, a colaboração e as tarefas relacionadas à reunião usando linguagem natural falada. Os usuários podem falar com a Cortana clicando no botão microfone localizado no canto superior direito do aplicativo móvel do teams. Para conectar-se rapidamente à equipe enquanto estiver em trânsito, os usuários podem dizer consultas como "ligar Megan" ou "Enviar uma mensagem para a próxima reunião". Os usuários também podem participar de reuniões dizendo "ingressar na minha próxima reunião" e usar a assistência de voz para compartilhar arquivos, verificar o calendário e muito mais. Essas experiências de assistência de voz são fornecidas usando os [serviços de nível corporativo da Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que estão totalmente em conformidade com a privacidade, a segurança e a conformidade do Office 365, conforme refletido nos [termos dos serviços online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

A imagem mostra o envio de um chat na Cortana em um dispositivo móvel.

![Image mostra uma sequência de telas móveis mostrando uma sessão de chat da Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Controle e limitações de administração

O recurso de assistência de voz da Cortana no Teams é oferecido usando serviços que são totalmente compatíveis com o Office 365 a privacidade, a segurança e a conformidade da empresa são prometedos como refletidos nos termos dos serviços online (OST). O recurso será habilitado por padrão para locatários.

Os administradores de locatários podem controlar quem em seus locatários podem usar a assistência de voz da Cortana no Teams usando uma política (TeamsCortanaPolicy). Essa política pode ser definida em um nível de conta de usuário ou locatário. Os administradores podem usar o campo CortanaVoiceInvocationMode dentro desse controle de política para determinar se a Cortana está desabilitada, habilitada somente com a invocação de botão de ação ou com a chamada de ativação do Word (aplicável a dispositivos que dão suporte a ele).

Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (a política não está disponível no centro de administração do Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por exemplo, o comando abaixo cria uma nova política com o nome "EmployeeCortanaPolicy", em que o assistente de voz da Cortana do Microsoft Teams está desabilitado.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Este exemplo mostra a atualização de uma política existente com o nome "EmployeeCortanaPolicy" e a habilitação do assistente de voz da Cortana no Microsoft Teams com o botão de ação somente chamada. Os usuários poderão chamar a Cortana tocando no botão do MIC da Cortana no Teams. A invocação de ativação do Word ("Ei Cortana") será desabilitada.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Este exemplo mostra como atualizar a política e habilitar o assistente de voz da Cortana com o botão de ação e a chamada de ativação de palavras.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> No momento da versão inicial para usuários do Microsoft 365 Enterprise nos EUA em inglês, o aplicativo móvel do Teams não será compatível com a ativação do Word, mas será compatível no futuro.

## <a name="user-control"></a>Controle de usuário

Usuários individuais podem experimentar a assistência de voz da Cortana no aplicativo móvel do teams clicando no botão microfone. Eles também podem controlar se a Cortana no Teams está habilitada para o dispositivo usando uma configuração no aplicativo móvel do teams.

1. Abra o aplicativo móvel Teams.

2. Vá para **configurações**.

3. Selecione **Cortana**.

4. Mova o botão de alternância para **ativado** ou **desativado**, dependendo se você deseja assistência de voz da Cortana no dispositivo.
