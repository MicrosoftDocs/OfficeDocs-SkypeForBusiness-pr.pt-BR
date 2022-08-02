---
title: Assistência de voz da Cortana no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Saiba como usar a assistência de voz da Cortana com o Teams
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78aaad6506a7130d336d3847c55e0c0ec08c4450
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156780"
---
# <a name="cortana-voice-assistance-in-teams"></a>Assistência de voz da Cortana no Teams

> [!NOTE]
> A assistência de voz da Cortana tem suporte em aplicativos móveis do Microsoft Teams para iOS e Android, Exibições do Microsoft Teams e Salas do Microsoft Teams no Windows para usuários no Estados Unidos, Reino Unido, Canadá, Índia e Austrália. A assistência de voz da Cortana no aplicativo móvel do Teams agora está disponível para clientes EDU no en-US. A expansão para idiomas e regiões adicionais ocorrerá como parte de versões futuras. No momento, a assistência de voz da Cortana não está disponível para locatários GCC, GCC-High, DoD e EDU que não são dos EUA.

A assistência por voz da Cortana no aplicativo móvel do Teams, no Salas do Microsoft Teams no Windows e nos dispositivos de exibição do Microsoft Teams permite que os usuários do Microsoft 365 Enterprise simplifiquem a comunicação, a colaboração e as tarefas relacionadas à reunião usando o idioma natural falado. Os usuários podem falar com a Cortana selecionando o botão de microfone localizado no canto superior direito do aplicativo móvel do Teams ou dizendo "Cortana" na Sala do Microsoft Teams ou ao usar uma exibição do Microsoft Teams. Para se conectar rapidamente com sua equipe de mãos livres e em qualquer lugar, os usuários podem dizer consultas como "chamar Megan" ou "enviar uma mensagem para minha próxima reunião". Os usuários também podem ingressar em reuniões dizendo "ingressar na minha próxima reunião" e usar assistência de voz para compartilhar arquivos, verificar seu calendário e muito mais. Essas experiências de assistência de voz são fornecidas usando serviços de nível empresarial da [Cortana](/microsoft-365/admin/misc/cortana-integration) que estão em conformidade total com as promessas de privacidade, segurança e conformidade da Office 365, conforme refletido nos Termos de Serviços [Online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true).

## <a name="admin-control-and-limitations"></a>Administração e limitações

A assistência de voz da Cortana no Office 365 Teams é fornecida usando serviços que estão em conformidade total com as promessas de privacidade, segurança e conformidade de nível empresarial, conforme refletido nos Termos de Serviços Online (OST). O recurso será habilitado por padrão para locatários.

Os administradores de locatários podem controlar quem em seu locatário pode usar a assistência de voz da Cortana no Teams usando uma política (TeamsCortanaPolicy). Essa política é definida no nível da conta de usuário ou do locatário. Os administradores podem usar o campo CortanaVoiceInvocationMode dentro desse controle de política para determinar se a Cortana está desabilitada, habilitada somente com invocação de botão de ativação ou com invocação de palavra de ativação também (aplicável a dispositivos que dão suporte a ela, como a exibição do Microsoft Teams).

Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (no momento, a política não está disponível no centro de administração do Microsoft Teams).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por exemplo, o comando a seguir cria uma nova política com o nome "EmployeeCortanaPolicy" em que a assistência de voz da Cortana no Microsoft Teams está desabilitada.

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Este exemplo mostra como atualizar uma política existente com o nome "EmployeeCortanaPolicy" e habilitar a assistência de voz da Cortana no Microsoft Teams apenas com invocação de botão de push. Os usuários poderão invocar a Cortana selecionando o botão de microfone da Cortana no Teams. A invocação de palavra de ativação ("Ei Cortana" ou "Cortana") será desabilitada.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Este exemplo mostra como atualizar a política e habilitar a assistência de voz da Cortana com o botão de push e a invocação de palavra de ativação.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

No momento, da versão inicial para Microsoft 365 Enterprise usuários nos EUA em inglês, as seguintes funções estão disponíveis:

- O aplicativo móvel do Teams não dá suporte à ativação de palavra de ativação, mas terá suporte no futuro.

- Salas do Microsoft Teams dispositivos de exibição do Windows e do Microsoft Teams darão suporte à ativação de palavra de ativação.

## <a name="user-control"></a>Controle de usuário

Os usuários individuais podem experimentar a assistência de voz da Cortana em dispositivos diferentes:

- Selecione o botão de microfone no aplicativo móvel do Teams.

- Selecione o botão de microfone ou diga "Cortana" Salas do Microsoft Teams.

- Diga "Cortana" no Microsoft Teams exibe dispositivos.

Você pode controlar se a Cortana no Teams está habilitada para seu dispositivo usando uma configuração no dispositivo.

![mostra a progressão das janelas móveis quando você habilita a Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salas do Microsoft Teams no Windows

Fazer alterações no nível do dispositivo só estará disponível se a Cortana estiver habilitada no nível do locatário.

No nível do dispositivo, você pode configurar a Cortana para ser usada de duas maneiras diferentes. Você pode habilitar uma das opções ou ambas ao mesmo tempo:

- Tocando em um microfone, que é chamado de Cortana _Push to talk_
- Dizendo "Ei, Cortana", que é chamado de _Ativação de Voz da Cortana_

O _Push to talk_ da Cortana está habilitado por padrão se sua sala estiver configurada com qualquer um dos seguintes idiomas: en-au (Austrália), en-ca (Canadá), en-gb (Reino Unido), en-in (Índia), en-us (Estados Unidos). [Saiba Mais.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) O ícone da Cortana deslocará o _botão Apresentar_ no menu _Mais..._ no console da Sala do Teams. Para desabilitar o Push da Cortana _para falar_ , use o PowerShell. [Saiba Mais.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Para habilitar a Ativação de _Voz_ da Cortana, essas condições devem ser atendidas:

- um dispositivo certificado pela Cortana deve estar conectado à sua Sala do Teams. Você pode encontrar uma lista de dispositivos certificados no final deste artigo.
- a Sala do Teams deve ser configurada com qualquer um dos seguintes idiomas: en-au (Austrália), en-ca (Canadá), en-gb (Reino Unido), en-in (Índia), en-us (Estados Unidos). Mais idiomas estarão disponíveis em uma data posterior.
- uma das seguintes alterações de configuração deve ser feita:
  - ative o recurso no Centro de administração [do Teams Para saber mais.](/microsoftteams/rooms/rooms-manage)
  - adicione o seguinte atributo XML ao arquivo XML SkypeSettings:

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

No nível da reunião, fazer alterações estará disponível somente se a Ativação do Cortana _Voice_ estiver habilitada no nível do dispositivo.  Para habilitar a Ativação do Cortana _Voice_ durante uma reunião, mova a opção **Ativar** ou **Desativar** para desabilitar. Depois que a reunião terminar, a Cortana retornará para as configurações de nível de dispositivo definidas.

Fazer alterações no nível da reunião estará disponível se a Cortana estiver habilitada no nível do dispositivo.

Para habilitar _a_ ativação de voz da Cortana durante uma reunião, mova a opção **Ativar** ou **Desativar**. Depois que a reunião terminar, a Cortana retornará para as configurações de nível de dispositivo definidas.

## <a name="cortana-certified-devices-for-teams-rooms"></a>Dispositivos certificados pela Cortana para Salas do Teams

A _Ativação de_ Voz da Cortana poderá ser habilitada se você estiver usando um Lenovo Hub 500 ou se tiver algum desses dispositivos conectados à sua sala:

- Jabra Panacast 50
- Logi Rally Plus Conferencing System
- Bose Video Bar VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech
