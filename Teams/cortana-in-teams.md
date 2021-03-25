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
ms.openlocfilehash: 820689e2bcfa190afefda9d161c787c6be9a7da0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118470"
---
# <a name="cortana-voice-assistance-in-teams"></a>Assistência de voz da Cortana no Teams

> [!Note]
> A assistência de voz da Cortana é suportada em aplicativos móveis do Microsoft Teams iOS e Android, salas do Microsoft Teams no Windows e no Microsoft Teams é exibido, somente para usuários nos Estados Unidos. No momento, ele não está disponível para locatários GCC, GCC-High, DoD, EDU. A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras.

> [!Note]
> A assistência de voz da Cortana nas Salas do Microsoft Teams é lançada em Visualização. Em sua versão de visualização, a Cortana tem suporte apenas nos EUA com o idioma EN-US em dispositivos que conectaram microfones de Comício.

A assistência de voz da Cortana no aplicativo móvel do Teams, nas Salas do Microsoft Teams no Windows e nos dispositivos de exibição do Microsoft Teams permite que os usuários do Microsoft 365 Enterprise agilizem a comunicação, a colaboração e as tarefas relacionadas à reunião usando a linguagem natural falada. Os usuários podem falar com a Cortana selecionando o botão de microfone localizado na parte superior direita do aplicativo móvel do Teams ou dizendo &#8220;Cortana&#8221; na Sala do Microsoft Teams ou ao usar uma exibição do Microsoft Teams. Para se conectar rapidamente com sua equipe de mãos livres e enquanto estão em tempo livre, os usuários podem dizer consultas como &#8220;chamar Megan&#8221; ou &#8220;enviar uma mensagem para minha próxima reunião&#8221;. Os usuários também podem participar de reuniões dizendo &#8220;minha próxima reunião&#8221; e usar assistência de voz para compartilhar arquivos, verificar seu calendário e muito mais. Essas experiências de assistência de voz são entregues usando serviços de nível empresarial [da Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que estão em conformidade com as promessas de privacidade, segurança e conformidade do Office 365, conforme refletido nos Termos de Serviços [Online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

A imagem mostra o envio de um chat usando a Cortana em um dispositivo móvel.

![uma sequência de telas móveis mostrando uma sessão de chat da Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Controle de administrador e limitações

A assistência de voz da Cortana no Teams é entregue usando serviços que estão em conformidade com as promessas de privacidade, segurança e conformidade no nível empresarial do Office 365, conforme refletido nos Termos de Serviços Online (OST). O recurso será habilitado por padrão para locatários.

Os administradores de locatários podem controlar quem em seu locatário pode usar a assistência de voz da Cortana no Teams usando uma política (TeamsCortanaPolicy). Essa política pode ser definida em um nível de conta de usuário ou de locatário. Os administradores podem usar o campo CortanaVoiceInvocationMode neste controle de política para determinar se a Cortana está desabilitada, habilitada somente com invocação por botão ou com invocação de palavra de alerta também (aplicável a dispositivos que a suportam, como a exibição do Microsoft Teams).

Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (a política não está disponível no centro de administração do Microsoft Teams).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por exemplo, o comando abaixo cria uma nova política com o nome &#8220;EmployeeCortanaPolicy&#8221; onde a assistência de voz da Cortana no Microsoft Teams está desabilitada.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Este exemplo mostra a atualização de uma política existente com o nome &#8220;employeeCortanaPolicy&#8221; e habilitando a assistência de voz da Cortana no Microsoft Teams somente com invocação por botão de botão. Os usuários poderão invocar a Cortana selecionando o botão de microfone cortana no Teams. Palavra de &#8220;chamada hey Cortana&#8221; ou &#8220;cortana&#8221;) será desabilitada.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Este exemplo mostra a atualização da política e a habilitação da assistência de voz da Cortana com o botão push e a invocação de palavra de alerta.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

No momento, da versão inicial para usuários do Microsoft 365 Enterprise nos EUA em inglês, as seguintes funções estão disponíveis:

- O aplicativo móvel do Teams não dará suporte à ativação de palavra de alerta, mas terá suporte no futuro.  

- As Salas do Microsoft Teams nos dispositivos de exibição do Windows e do Microsoft Teams darão suporte à ativação de palavra de alerta.

## <a name="user-control"></a>Controle do usuário

Usuários individuais podem experimentar a assistência de voz da Cortana em diferentes dispositivos:

- Selecione o botão microfone no aplicativo móvel do Teams.

- Selecione o botão de microfone ou diga "Cortana" em Salas do Microsoft Teams.

- Diga "Cortana" em dispositivos de exibição do Microsoft Teams.

Você pode controlar se a Cortana no Teams está habilitada para seu dispositivo usando uma configuração no dispositivo.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Aplicativo móvel do Teams ou exibição do Microsoft Teams

  1. Abra o aplicativo móvel do Teams.

  2. Selecione **Configurações**  >  **Cortana**.

  3. Mova a **alternância Para ou** **para fora.**

### <a name="microsoft-teams-display"></a>Exibição do Microsoft Teams

  1. Vá para a tela ambiente (home) da exibição do Microsoft Teams.

  2. Selecione o avatar do usuário e selecione **Configurações**. Se a Cortana estiver habilitada, diga: "Cortana, vá para Configurações".

  3. Mova a **alternância Para ou** **para fora.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Salas do Microsoft Teams no Windows

Fazer alterações no nível do dispositivo estará disponível se a Cortana estiver habilitada no nível do locatário. A Cortana será liberada OFF por padrão.

Para habilitar a Cortana no nível do dispositivo, esses atributos XML devem ser adicionados no arquivo XML do SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Fazer alterações no nível da reunião estará disponível se a Cortana estiver habilitada no nível do dispositivo.

Para habilitar a assistência de voz da Cortana durante uma reunião, mova a **alternância Ativado** ou **Desligado.** Quando a reunião terminar, a Cortana retornará às configurações de nível do dispositivo definidas.