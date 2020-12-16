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
# <a name="cortana-voice-assistance-in-teams"></a>Assistência de voz da Cortana no Teams

> [!Note]
> A assistência de voz da Cortana tem suporte em aplicativos móveis do Microsoft Teams iOS e Android, as salas do Microsoft Teams no Windows e no Microsoft Teams são exibidas somente para usuários nos Estados Unidos. No momento, ele não está disponível para locatários GCC, GCC-High, DoD e EDU. A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras.

> [!Note]
> A assistência de voz da Cortana em salas do Microsoft Teams é liberada na visualização. No lançamento da versão prévia, a Cortana tem suporte somente nos EUA com o idioma EN-US nos dispositivos que conectavam microfones Rally.

A assistência de voz da Cortana no aplicativo móvel do Microsoft Teams em salas do Microsoft Teams no Windows e em dispositivos de exibição do Microsoft Teams permite que os usuários do Microsoft 365 Enterprise simplifiquem a comunicação, a colaboração e as tarefas relacionadas à reunião usando linguagem natural falada. Os usuários podem falar com a Cortana selecionando o botão do microfone localizado no canto superior direito do aplicativo móvel do teams ou dizendo &#8220;Cortana&#8221; na sala do Microsoft Teams ou ao usar uma exibição do Microsoft Teams. Para conectar-se rapidamente à equipe de mão e enquanto estiver em trânsito, os usuários podem dizer consultas como chamadas de &#8220;Megan&#8221; ou &#8220;enviar uma mensagem para a minha próxima reunião&#8221;. Os usuários também podem participar de reuniões dizendo &#8220;ingressar na minha próxima reunião&#8221; e usar a assistência de voz para compartilhar arquivos, verificar o calendário e muito mais. Essas experiências de assistência de voz são fornecidas usando os [serviços de nível corporativo da Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que estão totalmente em conformidade com a privacidade, a segurança e a conformidade do Office 365, conforme refletido nos [termos dos serviços online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

A imagem mostra o envio de um chat usando a Cortana em um dispositivo móvel.

![uma sequência de telas móveis mostrando uma sessão de chat da Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Controle e limitações de administração

O recurso de assistência de voz da Cortana no Teams é oferecido usando serviços que são totalmente compatíveis com o Office 365 a privacidade, a segurança e a conformidade da empresa são prometedos como refletidos nos termos dos serviços online (OST). O recurso será habilitado por padrão para locatários.

Os administradores de locatários podem controlar quem em seus locatários podem usar a assistência de voz da Cortana no Teams usando uma política (TeamsCortanaPolicy). Essa política pode ser definida em um nível de conta de usuário ou locatário. Os administradores podem usar o campo CortanaVoiceInvocationMode dentro desse controle de política para determinar se a Cortana está desabilitada, habilitada somente com o recurso de invocação de botão ou com a chamada do Wake Word (aplicável a dispositivos que dão suporte a ele, como a exibição do Microsoft Teams).

Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (a política não está disponível no centro de administração do Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

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

No momento, do lançamento inicial para usuários do Microsoft 365 Enterprise nos EUA em inglês, as seguintes funções estão disponíveis:

- O aplicativo móvel do Teams não oferecerá suporte à ativação do Word de ativação, mas será compatível no futuro.  

- As salas do Microsoft Teams no Windows e os dispositivos de exibição do Microsoft Teams dão suporte à ativação do Word de ativação.

## <a name="user-control"></a>Controle de usuário

Usuários individuais podem experimentar a assistência de voz da Cortana em diferentes dispositivos:

- Selecione o botão de microfone no aplicativo móvel do teams.

- Selecione o botão de microfone ou diga "Cortana" nas salas do Microsoft Teams.

- Diga "Cortana" em dispositivos de vídeo do Microsoft Teams.

Você pode controlar se a Cortana no Microsoft Teams está habilitada para seu dispositivo usando uma configuração no dispositivo.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Aplicativo móvel do teams ou a exibição do Microsoft Teams

  1. Abra o aplicativo móvel Teams.

  2. Selecione **configurações**  >  **Cortana**.

  3. Mover ou **desativar** o **botão de alternância** .

### <a name="microsoft-teams-display"></a>Exibição do Microsoft Teams

  1. Vá para a tela ambiente (início) da tela do Microsoft Teams.

  2. Selecione o avatar do usuário e, em seguida, selecione **configurações**. Se a Cortana estiver habilitada, por exemplo, "Cortana, vá para configurações".

  3. Mover ou **desativar** o **botão de alternância** .
  
### <a name="microsoft-teams-rooms-on-windows"></a>Salas do Microsoft Teams no Windows

A realização de alterações no nível do dispositivo estará disponível se a Cortana estiver habilitada no nível do locatário. A Cortana será liberada por padrão.

Para habilitar a Cortana no nível do dispositivo, esses atributos XML devem ser adicionados ao arquivo XML do SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

A realização de alterações no nível da reunião estará disponível se a Cortana estiver habilitada no nível do dispositivo.

Para habilitar a assistência de voz da Cortana durante uma reunião, mova o botão **de** **alternância.** Depois que a reunião termina, a Cortana retorna ao conjunto de configurações do nível do dispositivo.
