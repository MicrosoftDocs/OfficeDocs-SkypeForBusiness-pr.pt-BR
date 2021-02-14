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
> A assistência de voz da Cortana é suportada nos aplicativos móveis do Microsoft Teams para iOS e Android, salas do Microsoft Teams no Windows e em exibições do Microsoft Teams, somente para usuários nos Estados Unidos. No momento, ele não está disponível para locatários GCC, GCC-High, DoD, EDU. A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras.

> [!Note]
> A assistência de voz da Cortana nas Salas do Microsoft Teams é lançada em Visualização. Em sua versão de visualização, a Cortana tem suporte somente nos EUA com o idioma EN-US em dispositivos que tenham microfones Desconectados.

A assistência de voz da Cortana no aplicativo móvel do Teams, nas Salas do Microsoft Teams no Windows e em dispositivos de exibição do Microsoft Teams permite que os usuários do Microsoft 365 Enterprise simplifiquem a comunicação, a colaboração e as tarefas relacionadas a reuniões usando o idioma natural falado. Os usuários podem falar com a Cortana selecionando o botão de microfone localizado no canto superior direito do aplicativo móvel do Teams ou dizendo &#8220;Cortana&#8221; na Sala do Microsoft Teams ou ao usar uma exibição do Microsoft Teams. Para se conectar rapidamente com a equipe com as mãos livres e em qualquer lugar, os usuários podem dizer consultas, como ligar para a &#8220;Ou &#8220;a Megan&#8221; &#8220;enviar uma mensagem para a minha próxima reunião&#8221;. Os usuários também podem ingressar em reuniões dizendo &#8220;ingressar na minha próxima reunião&#8221; e usar a assistência de voz para compartilhar arquivos, verificar o calendário e muito mais. Essas experiências de assistência de voz são entregues usando serviços de nível empresarial [cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que estão totalmente em conformidade com as promessas de privacidade, segurança e conformidade do Office 365, conforme refletido nos Termos de Serviços [Online (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

A imagem mostra o envio de um chat usando a Cortana em um dispositivo móvel.

![uma sequência de telas móveis mostrando uma sessão de chat da Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Controle e limitações do administrador

A assistência de voz da Cortana no Teams é entregue usando serviços que estão totalmente em conformidade com as promessas de privacidade, segurança e conformidade no nível empresarial do Office 365, como refletido nos Termos de Serviços Online (OST). O recurso será habilitado por padrão para locatários.

Os administradores de locatários podem controlar quem em seu locatário pode usar a assistência de voz da Cortana no Teams usando uma política (TeamsCortanaPolicy). Essa política pode ser definida em um nível de conta de usuário ou de locatário. Os administradores podem usar o campo CortanaVoiceInvocationMode dentro desse controle de política para determinar se a Cortana está desabilitada, habilitada somente com invocação por push ou com a invocação de palavra de alerta também (aplicável a dispositivos que a suportam, como a exibição do Microsoft Teams).

Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (no momento, a política não está disponível no Centro de administração do Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por exemplo, o comando a seguir cria uma nova política com o nome &#8220;EmployeeCortanaPolicy&#8221; onde a assistência de voz da Cortana no Microsoft Teams está desabilitada.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Este exemplo mostra a atualização de uma política existente com o nome &#8220;EmployeeCortanaPolicy&#8221; e habilitando a assistência de voz da Cortana no Microsoft Teams apenas com a invocação do botão de push. Os usuários poderão invocar a Cortana selecionando o botão de microfone cortana no Teams. A palavra de &#8220;chamada Ei Cortana&#8221; ou &#8220;Cortana&#8221;) será desabilitada.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Este exemplo mostra a atualização da política e a habilitação da assistência de voz da Cortana com o botão de pressionar e ativar a invocação de palavras.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

No momento, da versão inicial para usuários do Microsoft 365 Enterprise nos EUA em inglês, as seguintes funções estão disponíveis:

- O aplicativo móvel do Teams não terá suporte para ativar o wake word, mas terá suporte no futuro.  

- As Salas do Microsoft Teams nos dispositivos de exibição do Windows e do Microsoft Teams serão compatíveis com a ativação de palavra despertada.

## <a name="user-control"></a>Controle do usuário

Usuários individuais podem experimentar a assistência de voz da Cortana em diferentes dispositivos:

- Selecione o botão de microfone no aplicativo móvel do Teams.

- Selecione o botão de microfone ou diga "Cortana" nas Salas do Microsoft Teams.

- Diga "Cortana" em dispositivos de exibição do Microsoft Teams.

Você pode controlar se a Cortana no Teams está habilitada para seu dispositivo usando uma configuração no dispositivo.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Aplicativo móvel do Teams ou exibição do Microsoft Teams

  1. Abra o aplicativo móvel do Teams.

  2. Selecione **Configurações**  >  **da Cortana.**

  3. Mova a **alternância Para a frente** ou **para fora.**

### <a name="microsoft-teams-display"></a>Exibição do Microsoft Teams

  1. Vá para a tela ambiente (página inicial) da exibição do Microsoft Teams.

  2. Selecione o avatar do usuário e, em seguida, selecione **Configurações.** Se a Cortana estiver habilitada, diga, "Cortana, vá para Configurações".

  3. Mova a **alternância Para a frente** ou **para fora.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Salas do Microsoft Teams no Windows

Fazer alterações no nível do dispositivo estará disponível se a Cortana estiver habilitada no nível do locatário. A Cortana será liberada POR padrão.

Para habilitar a Cortana no nível do dispositivo, esses atributos XML devem ser adicionados ao arquivo XML do SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Fazer alterações no nível da reunião estará disponível se a Cortana estiver habilitada no nível do dispositivo.

Para habilitar a assistência de voz da Cortana durante uma reunião, mova a **alternância Ativar** ou **Desligar.** Quando a reunião terminar, a Cortana retornará às configurações de nível do dispositivo definidas.
