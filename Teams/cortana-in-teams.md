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
# <a name="cortana-voice-assistance-in-teams"></a>Assistência de voz da Cortana no Teams

> [!Note]
> A assistência de voz da Cortana tem suporte nos aplicativos móveis do Microsoft Teams iOS e Android, e no Microsoft Teams é exibido apenas para usuários nos Estados Unidos. No momento, ele não está disponível para locatários GCC, GCC-High, DoD e EDU. A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras.

A assistência de voz da Cortana no aplicativo móvel do Teams e nos dispositivos de vídeo do Microsoft Teams permite que os usuários do Microsoft 365 Enterprise simplifiquem a comunicação, a colaboração e as tarefas relacionadas à reunião usando linguagem natural falada. Os usuários podem falar com a Cortana selecionando o botão do microfone localizado no canto superior direito do aplicativo móvel do teams ou dizendo &#8220;Cortana&#8221; na tela do Microsoft Teams. Para conectar-se rapidamente à equipe de mão e enquanto estiver em trânsito, os usuários podem dizer consultas como chamadas de &#8220;Megan&#8221; ou &#8220;enviar uma mensagem para a minha próxima reunião&#8221;. Os usuários também podem participar de reuniões dizendo &#8220;ingressar na minha próxima reunião&#8221; e usar a assistência de voz para compartilhar arquivos, verificar o calendário e muito mais. Essas experiências de assistência de voz são fornecidas usando os [serviços de nível corporativo da Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que estão totalmente em conformidade com a privacidade, a segurança e a conformidade do Office 365, conforme refletido nos [termos dos serviços online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

A imagem mostra o envio de um chat usando a Cortana em um dispositivo móvel.

![Image mostra uma sequência de telas móveis mostrando uma sessão de chat da Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Controle e limitações de administração

O recurso de assistência de voz da Cortana no Teams é oferecido usando serviços que são totalmente compatíveis com o Office 365 a privacidade, a segurança e a conformidade da empresa são prometedos como refletidos nos termos dos serviços online (OST). O recurso será habilitado por padrão para locatários.

Os administradores de locatários podem controlar quem em seus locatários podem usar a assistência de voz da Cortana no Teams usando uma política (TeamsCortanaPolicy). Essa política pode ser definida em um nível de conta de usuário ou locatário. Os administradores podem usar o campo CortanaVoiceInvocationMode dentro desse controle de política para determinar se a Cortana está desabilitada, habilitada somente com a invocação do botão de ação ou com a chamada do Wake Word (aplicável a dispositivos que dão suporte a ele, como a exibição do Microsoft Teams).

Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (a política não está disponível no centro de administração do Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por exemplo, o comando abaixo cria uma nova política com o nome &#8220;EmployeeCortanaPolicy&#8221; onde a assistência de voz da Cortana no Microsoft Teams está desabilitada.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Este exemplo mostra a atualização de uma política existente com o nome &#8220;EmployeeCortanaPolicy&#8221; e a habilitação da assistência de voz da Cortana no Microsoft Teams com o botão de ação somente chamada. Os usuários poderão chamar a Cortana selecionando o botão do MIC da Cortana no Teams. Ativar o Word (&#8220;Oi Cortana&#8221; ou &#8220;&#8221; da Cortana) será desabilitada.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Este exemplo mostra a atualização da política e a habilitação da assistência de voz da Cortana com o botão de ação e a chamada de ativação do Word.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> No momento da versão inicial para usuários do Microsoft 365 Enterprise nos EUA em inglês, o aplicativo móvel do Teams não será compatível com a ativação do Word, mas será compatível no futuro. Ativar a ativação do Word funcionará em dispositivos de exibição do Microsoft Teams na versão inicial.

## <a name="user-control"></a>Controle de usuário

Usuários individuais podem experimentar a assistência de voz da Cortana no aplicativo móvel do teams selecionando o botão do microfone. Eles podem experimentar a assistência de voz da Cortana em dispositivos de exibição do Microsoft Teams simplesmente dizendo &#8220;Cortana. &#8221; eles também podem controlar se a Cortana no Teams está habilitada para seu dispositivo usando uma configuração no aplicativo móvel do Microsoft Teams ou na exibição do Microsoft Teams.

1. Abra o aplicativo móvel do teams ou vá para a tela ambiente (residencial) da tela do Microsoft Teams.

2. No aplicativo móvel do Microsoft Teams, vá para **configurações** . Na tela do Microsoft Teams, selecione o avatar do usuário e, em seguida, selecione configurações. Se a Cortana estiver habilitada, digamos, &#8220;Cortana, vá para configurações. &#8221;

3. Selecione **Cortana** .

4. Mova o botão de alternância para **ativado** ou **desativado** , dependendo se você deseja assistência de voz da Cortana no dispositivo.
