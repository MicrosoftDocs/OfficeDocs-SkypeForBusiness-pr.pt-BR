---
title: Habilitar Salas do Teams dispositivos para ingressar em reuniões de terceiros
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Este artigo discute como configurar sua organização e Salas do Teams dispositivos para dar suporte à junção de reuniões de terceiros no Cisco WebEx e no Zoom.
ms.openlocfilehash: 91b730f998a1c17ed41f42a1e2990c82045d3117
ms.sourcegitcommit: 54cb804e6e8338f2d09499e53416e6d55ef1cc40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2022
ms.locfileid: "65441997"
---
# <a name="enable-teams-rooms-devices-to-join-third-party-meetings"></a>Habilitar Salas do Teams dispositivos para ingressar em reuniões de terceiros

> [!NOTE]
> Atualmente, esse recurso só está disponível no Salas do Teams no Windows.

Salas do Microsoft Teams dispositivos dão suporte a uma experiência de toque único para ingressar em reuniões online de terceiros, também conhecidas como Ingresso Direto para Convidados. Quando habilitado, você pode usar o Salas do Teams para ingressar em reuniões hospedadas no Cisco WebEx e no Zoom da mesma forma que pode ingressar em reuniões hospedadas no Microsoft Teams.

Antes de ingressar em reuniões de terceiros Salas do Teams, você precisa fazer o seguinte:

1. Configure a Salas do Teams da Exchange Online sala para processar convites para reuniões de terceiros.
2. Verifique se sua organização não tem políticas que impeçam que você se conecte a serviços de reunião de terceiros.
3. Configure Salas do Teams para permitir reuniões de terceiros.

As seções a seguir mostram como executar cada uma dessas etapas.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Etapa 1: Permitir o processamento de convite de calendário para reuniões de terceiros

A primeira coisa que você precisa fazer para habilitar uma experiência de ingresso com um toque nas Salas de Equipe é definir as regras de processamento de calendário para a caixa de correio da sala de Exchange Online do dispositivo. A caixa de correio da sala precisa permitir reuniões externas e manter o corpo e o assunto da mensagem para que ele possa ver a URL necessária para ingressar na reunião de terceiros. Para definir essas opções de caixa de correio de sala usando o cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , faça o seguinte:

1. Conexão para Exchange Online PowerShell. Para obter mais informações, consulte Conexão para Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) com autenticação básica ou Conexão para Exchange Online PowerShell usando a autenticação [multifator](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), dependendo do método de autenticação.

2. Obtenha o NOME UPN da caixa de correio da sala se você não o souber executando o seguinte comando:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Localize o nome da caixa de correio da sala associada ao seu Salas do Teams e anote seu UPN.

4. Depois de encontrar o UPN da caixa de correio da sala, execute o comando a seguir. Substitua `<UserPrincipalName>` pelo UPN da caixa de correio da sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Saiba mais sobre [o Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Etapa 2: Configurar a proteção Office 365 ameaças e a reescrita de link

Para habilitar a experiência de ingresso com um toque, as informações de link de ingresso na reunião de terceiros precisam estar presentes e legível no convite da reunião. Se sua organização usar o recurso de links seguros do Microsoft Defender para Office 365 ou se você usar uma solução de terceiros que examina todas as URLs de entrada e saída em busca de ameaças, ela poderá alterar as URLs de ingresso na reunião e tornar [a](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide) reunião irreconhecível pelo dispositivo Salas do Teams. Para garantir que isso não aconteça, você precisa adicionar as URLs do serviço de reunião de terceiros aos Links do Defender para Office 365 Cofre Não reescrever [a ](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide) lista ou a lista de exceções de reescrita de URL de terceiros.

 Se você usar uma solução de terceiros, consulte as instruções dessa solução para adicionar URLs à sua lista de exceções de reescrita de URL.

Aqui estão alguns exemplos de entradas que talvez você precise adicionar ao *seu Defender para Office 365 Cofre Links* Não reescrever lista ou lista de exceções de reescrita de URL de terceiros:

- **Cisco WebEx** `*.webex.com/*`
- **Zoom**`*.zoom.us/*`, `*.zoom.com/*``*.zoomgov.com/*`

Para obter uma lista completa de URLs a serem adicionadas *aos links do* Defender para Office 365 Cofre Não reescrever lista ou lista de exceções de reescrita de URL de terceiros, entre em contato com o provedor de serviços de reunião de terceiros do qual você deseja aceitar convites de reunião.

> [!CAUTION]
> Adicione apenas URLs em que você confia ao *seu Microsoft Defender para Office 365 Cofre Links* Não reescreva lista ou lista de exceções de reescrita de URL de terceiros.

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>Etapa 3: Habilitar reuniões de terceiros no Salas do Teams

A última etapa que você precisa fazer é permitir que Salas do Teams ingressar em reuniões de terceiros. As reuniões de terceiros exigem um nome de usuário e um endereço de email para ingressá-las. Se o nome de usuário e o endereço de email que você precisa usar for diferente da caixa de correio da sala do dispositivo, você precisará adicioná-los ao seu dispositivo. Você pode fazer isso nas Salas do Teams configurações ou no arquivo de configuração XML.

### <a name="use-device-settings"></a>Usar configurações do dispositivo

Para configurar Salas do Teams usando o console touchscreen, faça o seguinte:

1. No console Salas do Microsoft Teams, selecione **Mais...**.
2. Selecione **Configurações** e insira o nome de usuário e a senha do administrador do dispositivo.
3. Vá para a **guia Reuniões** e selecione **Cisco WebEx**, **Zoom** ou ambos.
4. Se você quiser ingressar em reuniões com o nome de usuário e o endereço de email associados à caixa de correio da sala, selecione **Ingressar com as informações da sala**.
5. Se você quiser ingressar em reuniões com um nome de usuário e endereço de email  alternativos, selecione Ingressar com informações personalizadas e insira o nome de usuário e o endereço de email que deseja usar.
6. Selecione **Salvar e sair**. Seu dispositivo será reiniciado.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar o arquivo SkypeSettings.xml configuração

As configurações a seguir podem ser adicionadas ao `SkypeSettings.xml` arquivo localizado em `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Para obter mais informações sobre o arquivo`SkypeSettings.xml`, consulte [Gerenciar um Salas do Microsoft Teams console remotamente com um arquivo de configuração XML](xml-config-file.md).

Para habilitar reuniões do Cisco WebEx, defina o `WebExMeetingsEnabled` elemento XML como **True**, da seguinte maneira.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Para habilitar reuniões de Zoom, defina o `ZoomMeetingsEnabled` elemento XML **como True**, da seguinte maneira.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Opcionalmente, você pode especificar um nome de usuário personalizado e um endereço de email para ingressar em reuniões de terceiros usando os seguintes elementos XML. Se os valores fornecidos não forem válidos, o Salas do Teams padrão será usar o nome de usuário e o endereço de email da caixa de correio da sala.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Para ingressar em uma reunião do Cisco WebEx de um dispositivo Salas do Teams, a reunião da Cisco precisa ser hospedada no WebEx Meetings Pro usando o aplicativo Web Cisco WebEx versão WBS 40.7 ou posterior. 
