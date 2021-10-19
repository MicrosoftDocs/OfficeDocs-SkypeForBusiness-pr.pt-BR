---
title: Cortana de voz no Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 4a9dba32e74bcc1538f75e35f5c70172fe72ec1b
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462475"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana de voz no Teams

> [!Note]
> Cortana Microsoft Teams assistência de voz é suportada em aplicativos móveis para iOS e Android e Microsoft Teams para usuários nos Estados Unidos, Reino Unido, Canadá, Índia e Austrália. Salas do Microsoft Teams no Windows é suportado apenas para dispositivos com localidade definida como en-us. Cortana assistência de voz não está disponível atualmente para locatários de EDU GCC, GCC-High, DoD e não-US. Cortana de voz no aplicativo móvel Teams agora está disponível para clientes EDU no en-US. A expansão para idiomas e regiões adicionais acontecerá como parte de versões futuras.


Cortana assistência de voz no aplicativo móvel Teams, no Salas do Microsoft Teams no Windows e em dispositivos de exibição Microsoft Teams permite que Microsoft 365 Enterprise usuários agilizem a comunicação, colaboração e tarefas relacionadas a reuniões usando linguagem natural falada. Os usuários podem falar com Cortana selecionando o botão de microfone localizado na parte superior direita do aplicativo móvel do Teams ou dizendo &#8220;Cortana&#8221; na sala Microsoft Teams ou ao usar uma tela Microsoft Teams de vídeo. Para se conectar rapidamente com sua equipe de mãos livres e enquanto estão em tempo livre, os usuários podem dizer consultas como &#8220;chamar Megan&#8221; ou &#8220;enviar uma mensagem para minha próxima reunião&#8221;. Os usuários também podem participar de reuniões dizendo &#8220;minha próxima reunião&#8221; e usar assistência de voz para compartilhar arquivos, verificar seu calendário e muito mais. Essas experiências de assistência [](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) de voz são entregues usando Cortana de nível empresarial que estão em conformidade com as promessas de privacidade, segurança e conformidade do Office 365 da Office 365, conforme refletido nos Termos de Serviços [Online (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

## <a name="admin-control-and-limitations"></a>Controle de administrador e limitações

Cortana assistência de voz no Teams Office 365 é entregue usando serviços que estão em conformidade com as promessas de privacidade, segurança e conformidade no nível da empresa, conforme refletido nos Termos de Serviços Online (OST). O recurso será habilitado por padrão para locatários.

Os administradores de locatários podem controlar quem em seu locatário pode usar Cortana de voz Teams usando uma política (TeamsCortanaPolicy). Essa política é definida em um nível de conta de usuário ou de locatário. Os administradores podem usar o campo CortanaVoiceInvocationMode dentro deste controle de política para determinar se o Cortana está desabilitado, habilitado somente com invocação por botão ou com invocação de palavra de alerta também (aplicável a dispositivos que a suportam, como a Microsoft Teams display).

Os administradores podem usar os seguintes cmdlets do PowerShell para gerenciar essa política (a política não está disponível no Microsoft Teams de administração).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por exemplo, o comando a seguir cria uma nova política com o nome &#8220;EmployeeCortanaPolicy&#8221; onde Cortana assistência de voz no Microsoft Teams está desabilitada.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Este exemplo mostra a atualização de uma política existente com o nome &#8220;EmployeeCortanaPolicy&#8221; e habilitando Cortana assistência de voz no Microsoft Teams somente com invocação por botão. Os usuários poderão invocar o Cortana selecionando o botão Cortana microfone no Teams. Palavra de acordar (&#8220;chamada hey Cortana&#8221; ou &#8220;Cortana&#8221;) será desabilitada.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Este exemplo mostra a atualização da política e a habilitação Cortana de voz com o botão push e a invocação de palavra de alerta.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

No momento, da versão inicial para Microsoft 365 Enterprise usuários nos EUA em inglês, as seguintes funções estão disponíveis:

- O Teams aplicativo móvel não dará suporte à ativação de palavra de alerta, mas ele terá suporte no futuro.  

- Salas do Microsoft Teams em Windows e Microsoft Teams de exibição darão suporte à ativação de palavra de alerta.

## <a name="user-control"></a>Controle do usuário

Usuários individuais podem tentar Cortana de voz em diferentes dispositivos:

- Selecione o botão microfone no aplicativo Teams celular.

- Selecione o botão de microfone ou diga "Cortana" no Salas do Microsoft Teams.

- Diga "Cortana" em Microsoft Teams exibe dispositivos.

Você pode controlar se Cortana no Teams está habilitado para seu dispositivo usando uma configuração no dispositivo.

![mostra a progressão das janelas móveis quando você habilita Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salas do Microsoft Teams no Windows

Fazer alterações no nível do dispositivo só estará disponível se Cortana estiver habilitado no nível do locatário. 

No nível do dispositivo, você pode configurar Cortana ser usado de duas maneiras diferentes. Você pode habilitar uma opção ou ambas ao mesmo tempo: 
- tocando em um microfone, que é chamado Cortana _Push to talk_
- dizendo "Ei, Cortana", que é _chamado Cortana ativação de voz_

Cortana _Push to talk_ está habilitado por padrão se seu dispositivo estiver definido para usar a localidade en-us. [Saiba Mais.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language)  Cortana ícone deslocará o botão _Presente_ em _Mais..._ menu em seu console Teams Room. Para desabilitar Cortana _Push para falar,_ use o PowerShell. [Saiba mais.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Para habilitar Cortana _ativação de_ voz, essas condições devem ser atendidas:
- um Cortana certificado deve estar conectado ao seu Teams Room. Você pode encontrar uma lista de dispositivos certificados no final deste artigo.
- a Teams Sala deve ser configurada para usar a localidade en-us. Mais idiomas estarão disponíveis em uma data posterior.
- uma das seguintes alterações de configuração deve ser feita:
  - ativar o recurso no centro de administração Teams [Saiba mais.](/microsoftteams/rooms/rooms-manage)
  - adicione o seguinte atributo XML ao arquivo XML skypeSettings:
```xml
<SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
</SkypeSettings> 
```
No nível da reunião, fazer alterações só estará disponível se Cortana Ativação de _Voz_ estiver habilitada no nível do dispositivo.  Para habilitar Cortana _ativação_ de voz durante uma reunião, mova o botão **Ativar** ou **Desativar** para desabilitar. Depois que a reunião terminar, Cortana retornará às configurações de nível do dispositivo definidas.


Fazer alterações no nível da reunião estará disponível se Cortana estiver habilitado no nível do dispositivo.

Para habilitar Cortana _de_ voz durante uma reunião, mova a alternância **Ativado** ou **Desligado.** Depois que a reunião terminar, Cortana retornará às configurações de nível do dispositivo definidas.


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana certificados para Salas do Teams
Cortana _ativação_ de voz pode ser habilitada se você estiver usando um Lenovo Hub 500 ou se você tiver qualquer um desses dispositivos conectados à sua sala:
- Jabra Panacast 50 
- Microfones de comício
- Bose Video Bar VB1 __
