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
- chat-teams-channels-revamp
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 502f09891942796a326deba35e29fab234e6548a
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198493"
---
# <a name="cortana-voice-assistance-in-teams"></a>Assistência de voz da Cortana no Teams

> [!NOTE]
> Há suporte para assistência de voz da Cortana em aplicativos móveis Microsoft Teams para iOS e Android, Microsoft Teams Displays e Salas do Microsoft Teams no Windows para usuários no Estados Unidos, Reino Unido, Canadá, Índia e Austrália. A assistência de voz da Cortana no aplicativo móvel do Teams agora está disponível para clientes EDU no en-US. A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras. Atualmente, a assistência de voz da Cortana não está disponível para locatários GCC, GCC-High, DoD e não-US EDU.

A assistência de voz da Cortana no aplicativo móvel do Teams, no Salas do Microsoft Teams no Windows e em dispositivos de exibição do Teams Microsoft permite que Microsoft 365 Enterprise usuários agilizem as tarefas relacionadas à comunicação, colaboração e reunião usando linguagem natural falada. Os usuários podem falar com a Cortana selecionando o botão de microfone localizado no canto superior direito do aplicativo móvel do Teams ou dizendo "Cortana" na sala do Microsoft Teams ou ao usar um Microsoft exibição do Teams. Para se conectar rapidamente com sua equipe de mãos livres e em movimento, os usuários podem dizer consultas como "chamar Megan" ou "enviar uma mensagem para minha próxima reunião". Os usuários também podem participar de reuniões dizendo "ingressar na minha próxima reunião" e usar a assistência de voz para compartilhar arquivos, verificar seu calendário e muito mais. Essas experiências de assistência de voz são entregues usando [serviços de nível empresarial da Cortana](/microsoft-365/admin/misc/cortana-integration) que cumprem totalmente as promessas de privacidade, segurança e conformidade do Office 365, conforme refletido nos [Termos de Serviços Online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true).

## <a name="admin-control-and-limitations"></a>Administração controle e limitações

A assistência de voz da Cortana no Teams é entregue usando serviços que cumprem totalmente o Office 365 promessas de privacidade, segurança e conformidade no nível da empresa, conforme refletido nos Termos de Serviços Online (OST). O recurso será habilitado por padrão para locatários.

Os administradores de locatários podem controlar quem em seu locatário pode usar a assistência de voz da Cortana no Teams usando uma política (TeamsCortanaPolicy). Essa política é definida em um nível de conta de usuário ou locatário. Os administradores podem usar o campo CortanaVoiceInvocationMode dentro desse controle de política para determinar se a Cortana está desabilitada, habilitada apenas com invocação por botão ou com invocação de palavra de velório também (aplicável a dispositivos com suporte, como a exibição Microsoft Teams).

Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (a política atualmente não está disponível no centro de administração do Microsoft Teams).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por exemplo, o comando abaixo cria uma nova política com o nome "EmployeeCortanaPolicy" em que a assistência de voz da Cortana no Microsoft Teams está desabilitada.

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Este exemplo mostra atualizar uma política existente com o nome "EmployeeCortanaPolicy" e habilitar a assistência de voz da Cortana no Microsoft Teams apenas com invocação por botão. Os usuários poderão invocar a Cortana selecionando o botão microfone cortana no Teams. A invocação de palavra de despertar ("Hey Cortana" ou "Cortana") será desabilitada.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Este exemplo mostra a atualização da política e a habilitação da assistência de voz da Cortana com o botão push e a invocação de palavras de despertar.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

No momento, da versão inicial para usuários Microsoft 365 Enterprise nos EUA em inglês, as seguintes funções estão disponíveis:

- O aplicativo móvel do Teams não oferecerá suporte à ativação do wake word, mas terá suporte no futuro.

- Salas do Microsoft Teams em dispositivos de exibição windows e Microsoft Teams darão suporte à ativação do wake word.

## <a name="user-control"></a>Controle de usuário

Usuários individuais podem tentar a assistência de voz da Cortana em diferentes dispositivos:

- Selecione o botão microfone no aplicativo móvel do Teams.

- Selecione o botão microfone ou diga "Cortana" no Salas do Microsoft Teams.

- Diga "Cortana" no Microsoft o Teams exibe dispositivos.

Você pode controlar se a Cortana no Teams está habilitada para seu dispositivo usando uma configuração no dispositivo.

![mostra a progressão das janelas móveis quando você habilita a Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salas do Microsoft Teams no Windows

Fazer alterações no nível do dispositivo só estará disponível se a Cortana estiver habilitada no nível do locatário.

No nível do dispositivo, você pode configurar a Cortana para ser usada de duas maneiras diferentes. Você pode habilitar uma opção ou ambos ao mesmo tempo:

- Tocando em um microfone, que é chamado _cortana push para falar_
- Ao dizer "Ei, Cortana", que se chama _Ativação de Voz da Cortana_

A Cortana _Push para conversar_ será habilitada por padrão se seu quarto estiver configurado com qualquer um dos seguintes idiomas: en-au (Austrália), en-ca (Canadá), en-gb (Reino Unido), en-in (Índia), en-us (Estados Unidos). [Saiba Mais.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) O ícone cortana deslocará o botão _Presente_ no menu _Mais..._ no console do Teams Room. Para desabilitar _o Cortana Push para falar_ , use o PowerShell. [Saiba Mais.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1&preserve-view=true)

Para habilitar _a Ativação de Voz_ da Cortana, essas condições devem ser atendidas:

- um dispositivo certificado pela Cortana deve estar conectado à sala do Teams. Você pode encontrar uma lista de dispositivos certificados no final deste artigo.
- a Sala do Teams deve ser configurada com qualquer um dos seguintes idiomas: en-au (Austrália), en-ca (Canadá), en-gb (Reino Unido), en-in (Índia), en-us (Estados Unidos). Mais idiomas estarão disponíveis em uma data posterior.
- uma das seguintes alterações de configuração deve ser feita:
  - ativar o recurso no centro de administração do Teams [Saiba mais.](/microsoftteams/rooms/rooms-manage)
  - adicione o seguinte atributo XML ao arquivo XML do SkypeSettings:

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

No nível da reunião, as alterações só estarão disponíveis se a _Ativação de Voz_ da Cortana estiver habilitada no nível do dispositivo.  Para habilitar a _Ativação de Voz_ da Cortana durante uma reunião, mova o alternância **Ativado** ou **Desativado** para desabilitar. Quando a reunião terminar, a Cortana retornará ao conjunto de configurações de nível do dispositivo.

Fazer alterações no nível da reunião estará disponível se a Cortana estiver habilitada no nível do dispositivo.

Para habilitar a _ativação de voz_ da Cortana durante uma reunião, mova o alternância **Ativar** ou **Desativar**. Quando a reunião terminar, a Cortana retornará ao conjunto de configurações de nível do dispositivo.

## <a name="cortana-certified-devices-for-teams-rooms"></a>Dispositivos certificados pela Cortana para Salas do Teams

A _Ativação de Voz_ da Cortana pode ser habilitada se você estiver usando um Hub Lenovo 500 ou se tiver algum desses dispositivos conectados ao seu quarto:

- Jabra Panacast 50
- Sistema de conferência Logi Rally Plus
- Bose Video Bar VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech
