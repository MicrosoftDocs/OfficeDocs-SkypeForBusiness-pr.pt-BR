---
title: Habilitar dispositivos de Salas do Teams para ingressar em reuniões de terceiros
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este artigo aborda como configurar sua organização e dispositivos de Salas do Teams para dar suporte à junção de reuniões de terceiros à Cisco WebEx e ao Zoom.
ms.openlocfilehash: 82369c534a616796382b1de69e37c64f15392f9b
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682380"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Habilitar dispositivos de Sala do Teams para ingressar em reuniões de terceiros

Os dispositivos Microsoft Teams Rooms são compatíveis com uma experiência de um toque para ingressar em reuniões online de terceiros, também conhecidas como Participação direta de convidados. Quando habilitado, você pode usar um dispositivo salas do Teams para ingressar em reuniões hospedadas no Cisco WebEx e no Zoom da mesma forma que pode ingressar em reuniões hospedadas no Microsoft Teams.

Antes de ingressar em reuniões de terceiros em um dispositivo de Salas do Teams, você precisa fazer o seguinte:

1. Configure a caixa de correio da sala do Exchange Online do dispositivo Teams Rooms para processar convites para reuniões de terceiros.
2. Certifique-se de que sua organização não tenha políticas que impeçam que você se conecte a serviços de reunião de terceiros.
3. Configure seus dispositivos de Salas do Teams para permitir reuniões de terceiros.

As seções a seguir mostram como fazer cada uma dessas etapas.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Etapa 1: permitir o processamento de convites de calendário para reuniões de terceiros

A primeira coisa que você precisa fazer para habilitar uma experiência de junção de um toque em um dispositivo de Salas de Equipe é definir as regras de processamento de calendário para a caixa de correio da sala do Exchange Online do dispositivo. A caixa de correio da sala precisa permitir reuniões externas e manter o corpo da mensagem e o assunto para que ela possa ver a URL necessária para ingressar na reunião de terceiros. Para definir essas opções de caixa de correio de sala usando o cmdlet [Set-CalendarProcessing,](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) faça o seguinte:

1. Conecte-se ao PowerShell do Exchange Online. Para obter mais informações, consulte Conectar-se ao [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) do Exchange Online com autenticação básica ou [Conectar-se](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)ao PowerShell do Exchange Online usando autenticação multifato, dependendo do método de autenticação.

2. Obter o UPN (Nome de Usuário Principal) da caixa de correio da sala se você não a conhece executando o seguinte comando:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Encontre o nome da caixa de correio da sala associada ao seu dispositivo Salas do Teams e anote seu UPN.

4. Depois de encontrar o UPN da caixa de correio da sala, execute o seguinte comando. Substitua `<UserPrincipalName>` pelo UPN da caixa de correio da sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Saiba mais sobre [o PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Etapa 2: Configurar a Proteção contra Ameaças do Office 365 e a reescrita de vínculos

Para habilitar a experiência de junção com um toque, as informações do link de junção da reunião de terceiros precisam estar presentes e acessível no convite da reunião. Se sua organização usar o recurso Links Seguros de Proteção Avançada contra Ameaças do [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) ou se você usar uma solução de terceiros que verifica todas as URLs de entrada e saída de ameaças, isso pode alterar as URLs de participação da reunião e tornar a reunião irreconhecível pelo dispositivo Salas do Teams. Para garantir que isso não aconteça, você precisa adicionar as URLs do serviço de reunião de terceiros à lista de links seguros da ATP "não reescrever" ou a lista de exceções de reescrita de URL de terceiros.

Para adicionar URLs de serviço de reunião de terceiros à lista "Não reescrever" links seguros da ATP, siga as etapas em Configurar uma lista personalizada de URLs não regravadas usando Links Seguros [da ATP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) Se você usar uma solução de terceiros, confira as instruções para que essa solução adicione URLs à sua lista de exceções de reescrita de URL.

Aqui estão algumas entradas de exemplo que talvez você precise adicionar à sua lista de links seguros da ATP "não reescrever" ou lista de exceções de reescrita de URL de terceiros:

- **Cisco WebEx**`*.webex.com*`
- **Zoom,** `*.zoom.us*` `*.zoom.com*``*.zoomgov.com*`

Para ver uma lista completa de URLs para adicionar à sua lista de Links Seguros da ATP "não reescrever" ou a lista de exceções de reescrita de URL de terceiros, entre em contato com o provedor de serviços de reunião de terceiros do onde você deseja aceitar convites de reunião. 

> [!CAUTION]
> Adicione apenas URLs em que você confia à sua lista de Links Seguros da ATP "não reescrever" ou lista de exceções de reescrita de URL de terceiros.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Etapa 3: habilitar reuniões de terceiros no dispositivo

A última etapa que você precisa fazer é permitir que cada dispositivo de Salas do Teams participe de reuniões de terceiros. Reuniões de terceiros exigem um nome de usuário e um endereço de email para ingressar neles. Se o nome de usuário e o endereço de email que você precisa usar for diferente da caixa de correio da sala do dispositivo, você precisará adicioná-los ao seu dispositivo. Você pode fazer isso nas configurações do dispositivo ou no arquivo de configuração XML.

### <a name="use-device-settings"></a>Usar configurações do dispositivo

Para configurar o dispositivo Salas do Teams usando a tela touch, faça o seguinte:

1. No dispositivo Salas do Microsoft Teams, selecione **Mais...**.
2. Selecione **Configurações e** insira o nome de usuário e a senha do administrador do dispositivo.
3. Vá para a **guia Reuniões** e selecione **Cisco WebEx,** **Zoom** ou ambos.
4. Se você quiser ingressar em reuniões com o nome de usuário e o endereço de email associados à caixa de correio da sala, selecione **Ingressar com as informações da sala.**
5. Se você quiser ingressar em reuniões com um  nome de usuário e endereço de email alternativos, selecione Ingressar com informações personalizadas e insira o nome de usuário e o endereço de email que você deseja usar.
6. Selecione **Salvar e sair.** Seu dispositivo será reiniciado.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar o arquivo SkypeSettings.xml configuração

As configurações a seguir podem ser adicionadas ao `SkypeSettings.xml` arquivo localizado em `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Para obter mais informações sobre o arquivo, consulte Gerenciar remotamente as configurações de um console de `SkypeSettings.xml` Salas do Microsoft Teams com um arquivo de [configuração XML.](xml-config-file.md)

Para habilitar reuniões do Cisco WebEx, de definir o elemento XML como `WebExMeetingsEnabled` **True,** da seguinte forma.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Para habilitar reuniões de Zoom, de definir o `ZoomMeetingsEnabled` elemento XML **como True,** da seguinte forma.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Opcionalmente, você pode especificar um nome de usuário e um endereço de email personalizados para ingressar em reuniões de terceiros usando os seguintes elementos XML. Se os valores que você fornecer não são válidos, o dispositivo Salas do Teams usará o nome de usuário da caixa de correio da sala e o endereço de email.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Para ingressar na reunião do Cisco WebEx a partir de um dispositivo de Salas do Teams, a reunião cisco precisa ser hospedada usando o aplicativo Web Cisco WebEx versão WBS 40.7 ou posterior.

