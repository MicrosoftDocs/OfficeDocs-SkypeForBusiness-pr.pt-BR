---
title: Cortana de voz no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Saiba como usar a Cortana de voz com Teams
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
ms.openlocfilehash: 5f888e36d9c0cdd19a0fdd8184d72eeee5ad2a45
ms.sourcegitcommit: 9f7372f7568b4275169590510d2b7a0c0ad7577b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "65171697"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana de voz no Teams

> [!Note]
> A Cortana de voz tem suporte em aplicativos móveis do Microsoft Teams para iOS e Android e Microsoft Teams para usuários no Estados Unidos, Reino Unido, Canadá, Índia e Austrália. Salas do Microsoft Teams no Windows há suporte apenas para dispositivos com localidade definida como en-us. Cortana assistência por voz não está disponível atualmente para locatários GCC, GCC-High, DoD e EDU que não são dos EUA. Cortana de voz no aplicativo Teams móvel agora está disponível para clientes EDU no en-US. A expansão para idiomas e regiões adicionais ocorrerá como parte de versões futuras.


Cortana de voz no aplicativo móvel Teams, no Salas do Microsoft Teams no Windows e em dispositivos Microsoft Teams de exibição Microsoft Teams habilita Microsoft 365 Enterprise  para simplificar a comunicação, a colaboração e as tarefas relacionadas à reunião usando o idioma natural falado. Os usuários podem falar com Cortana selecionando o botão de microfone localizado no canto superior direito do aplicativo móvel do Teams ou dizendo "Cortana" na Sala Microsoft Teams ou ao usar uma Microsoft Teams de vídeo. Para se conectar rapidamente com sua equipe de mãos livres e em qualquer lugar, os usuários podem dizer consultas como "chamar Megan" ou "enviar uma mensagem para minha próxima reunião". Os usuários também podem ingressar em reuniões dizendo "ingressar na minha próxima reunião" e usar assistência de voz para compartilhar arquivos, verificar seu calendário e muito mais. Essas experiências de assistência de voz são fornecidas usando [Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) serviços de nível empresarial que estão em conformidade total com as promessas de privacidade, segurança e conformidade do Office 365, conforme refletido nos Termos de Serviços [Online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

## <a name="admin-control-and-limitations"></a>Controle e limitações do administrador

Cortana assistência por voz no Teams é fornecida usando serviços que estão em conformidade total com as promessas de privacidade, segurança e conformidade de nível empresarial do Office 365, conforme refletido nos Termos de Serviços Online (OST). O recurso será habilitado por padrão para locatários.

Os administradores de locatários podem controlar quem em seu locatário pode usar Cortana de voz no Teams usando uma política (TeamsCortanaPolicy). Essa política é definida no nível da conta de usuário ou do locatário. Os administradores podem usar o campo CortanaVoiceInvocationMode dentro desse controle de política para determinar se o Cortana está desabilitado, habilitado somente com invocação de botão de push ou com invocação de palavra de ativação também (aplicável a dispositivos que dão suporte a ele, como a exibição Microsoft Teams).

Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (no momento, a política não está disponível no Microsoft Teams de administração).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por exemplo, o comando a seguir cria uma nova política com o nome "EmployeeCortanaPolicy", em que Cortana de voz no Microsoft Teams está desabilitado.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Este exemplo mostra a atualização de uma política existente com o nome "EmployeeCortanaPolicy" e Cortana assistência de voz no Microsoft Teams somente com invocação de botão de push. Os usuários poderão invocar Cortana selecionando o botão Cortana microfone no Teams. A invocação de palavra de Cortana" ou "Cortana") será desabilitada.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Este exemplo mostra como atualizar a política e habilitar a Cortana de voz com o botão de push e a invocação de palavra de ativação.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

No momento, da versão inicial para Microsoft 365 Enterprise usuários nos EUA em inglês, as seguintes funções estão disponíveis:

- O Teams aplicativo móvel não será compatível com a ativação de palavra de ativação, mas ele terá suporte no futuro.  

- Salas do Microsoft Teams em dispositivos Windows e Microsoft Teams de vídeo darão suporte à ativação de palavra de ativação.

## <a name="user-control"></a>Controle de usuário

Usuários individuais podem tentar Cortana de voz em dispositivos diferentes:

- Selecione o botão de microfone no Teams aplicativo móvel.

- Selecione o botão de microfone ou diga "Cortana" no Salas do Microsoft Teams.

- Diga "Cortana" em Microsoft Teams exibe dispositivos.

Você pode controlar se Cortana no Teams está habilitado para seu dispositivo usando uma configuração no dispositivo.

![mostra a progressão das janelas móveis quando você habilita Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salas do Microsoft Teams no Windows

Fazer alterações no nível do dispositivo só estará disponível se Cortana estiver habilitado no nível do locatário. 

No nível do dispositivo, você pode configurar Cortana para ser usado de duas maneiras diferentes. Você pode habilitar uma das opções ou ambas ao mesmo tempo: 
- Tocando em um microfone, que é chamado Cortana _Push to Talk_
- Dizendo "Ei, Cortana", que é chamado _Cortana ativação de voz_

Cortana push _to talk_ é habilitado por padrão se sua sala estiver configurada com qualquer um dos seguintes idiomas: en-au (Austrália), en-ca (Canadá), en-gb (Reino Unido), en-in (Índia), en-us (Estados Unidos). [Saiba Mais.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana ícone deslocará o _botão Apresentar_ sob _o botão Mais..._ menu no console Teams Room. Para desabilitar Cortana _push para falar,_ use o PowerShell.[ Saiba Mais.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Para habilitar Cortana _ativação de_ voz, essas condições devem ser atendidas:
- um Cortana certificado deve estar conectado à sua Teams Room. Você pode encontrar uma lista de dispositivos certificados no final deste artigo.
- o Teams Room deve ser configurado com qualquer um dos seguintes idiomas: en-au (Austrália), en-ca (Canadá), en-gb (Reino Unido), en-in (Índia), en-us (Estados Unidos). Mais idiomas estarão disponíveis em uma data posterior.
- uma das seguintes alterações de configuração deve ser feita:
  - ative o recurso no Teams admin Center [Saiba mais.](/microsoftteams/rooms/rooms-manage)
  - adicione o seguinte atributo XML ao arquivo XML SkypeSettings:

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
No nível da reunião, fazer alterações estará disponível somente se Cortana ativação de voz  estiver habilitada no nível do dispositivo.  Para habilitar Cortana _ativação de_ voz durante uma reunião, mova a opção **Ativar** ou **Desativar** para desabilitar. Depois que a reunião terminar, Cortana retornará às configurações de nível de dispositivo definidas.


Fazer alterações no nível da reunião estará disponível se Cortana estiver habilitado no nível do dispositivo.

Para habilitar Cortana _ativação_ de voz durante uma reunião, mova a opção **Ativar** ou **Desativar**. Depois que a reunião terminar, Cortana retornará às configurações de nível de dispositivo definidas.


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana certificados para Salas do Teams
Cortana _a ativação_ de voz poderá ser habilitada se você estiver usando um Lenovo Hub 500 ou se você tiver qualquer um desses dispositivos conectados à sua sala:
- Jabra Panacast 50 
- Microfones do Rally
- Bose Video Bar VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech  

