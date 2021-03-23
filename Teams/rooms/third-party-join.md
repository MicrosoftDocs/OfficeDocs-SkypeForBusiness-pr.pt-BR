---
title: Habilitar dispositivos teams rooms para ingressar em reuniões de terceiros
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
description: Este artigo discute como configurar sua organização e dispositivos de Salas do Teams para dar suporte à junção de reuniões de terceiros ao Cisco WebEx e zoom.
ms.openlocfilehash: ac4c57dc5cc743fb7b141ecaaaf3531b35912e77
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997429"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Habilitar dispositivos de Sala do Teams para ingressar em reuniões de terceiros

Os dispositivos de Salas do Microsoft Teams suportam uma experiência de toque único para ingressar em reuniões online de terceiros, também conhecidas como participação de convidados diretos. Quando habilitado, você pode usar um dispositivo salas do Teams para participar de reuniões hospedadas no Cisco WebEx e zoom da mesma forma que você pode participar de reuniões hospedadas no Microsoft Teams.

Antes de ingressar em reuniões de terceiros de um dispositivo teams Rooms, você precisa fazer o seguinte:

1. Configure a caixa de correio de sala do Exchange Online do dispositivo Teams Rooms para processar convites para reuniões de terceiros.
2. Certifique-se de que sua organização não tenha políticas que o impeçam de se conectar a serviços de reunião de terceiros.
3. Configure seus dispositivos de Salas do Teams para permitir reuniões de terceiros.

As seções a seguir mostram como fazer cada uma dessas etapas.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Etapa 1: Permitir o processamento de convites de calendário para reuniões de terceiros

A primeira coisa que você precisa fazer para habilitar uma experiência de junção de um toque de um dispositivo de Salas de Equipe é definir as regras de processamento de calendário para a caixa de correio de sala do Exchange Online do dispositivo. A caixa de correio de sala precisa permitir reuniões externas e manter o corpo e o assunto da mensagem para que ela possa ver a URL necessária para ingressar na reunião de terceiros. Para definir essas opções de caixa de correio de sala usando o cmdlet [Set-CalendarProcessing,](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) faça o seguinte:

1. Conecte-se ao PowerShell do Exchange Online. Para obter mais informações, consulte [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) with Basic authentication or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), dependendo do seu método de autenticação.

2. Obter o Nome de Entidade de Usuário (UPN) da caixa de correio de sala se você não a conhece executando o seguinte comando:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Encontre o nome da caixa de correio de sala associada ao dispositivo Salas do Teams e anote seu UPN.

4. Depois de encontrar o UPN da caixa de correio da sala, execute o seguinte comando. Substitua `<UserPrincipalName>` pelo UPN da caixa de correio da sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Saiba mais sobre [o PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Etapa 2: Configurar a Proteção contra Ameaças do Office 365 e a reescrita de link

Para habilitar a experiência de junção de um toque, as informações de link de junção de reunião da reunião de terceiros precisam estar presentes e habilitadas no convite da reunião. Se a sua organização usar o recurso Links Seguros de Proteção Avançada contra Ameaças do [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) ou se você usar uma solução de terceiros que verifica todas as URLs de entrada e saída em busca de ameaças, ele pode alterar as URLs de participação na reunião e tornar a reunião irreconhecível pelo dispositivo Salas do Teams. Para garantir que isso não aconteça, você precisa adicionar AS URLs do serviço de reunião de terceiros à lista de links seguros da ATP "não reescrever" ou à lista de exceção de regravar URL de terceiros.

Para adicionar URLs de serviço de reunião de terceiros à lista de Links Seguros da ATP "não reescrever", siga as etapas em Configurar uma lista de [URLs personalizadas](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)que não reescrevem usando links seguros atp . Se você usar uma solução de terceiros, consulte as instruções para que essa solução adicione URLs à lista de exceção de reescrita de URL.

Aqui estão algumas entradas de exemplo que talvez você precise adicionar à sua lista de Links Seguros da ATP "não reescrever" ou lista de exceção de regravar URL de terceiros:

- **Cisco WebEx**`*.webex.com*`
- **Zoom** `*.zoom.us*` , `*.zoom.com*``*.zoomgov.com*`

Para uma lista completa de URLs a adicionar à sua lista de Links Seguros da ATP "não reescrever" ou lista de exceção de regravações de URL de terceiros, contate o provedor de serviços de reunião de terceiros de onde você deseja aceitar convites de reunião. 

> [!CAUTION]
> Adicione apenas URLs que você confia à sua lista de links seguros atp "não reescrever" ou lista de exceção de regravações de URL de terceiros.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Etapa 3: Habilitar reuniões de terceiros no dispositivo

A última etapa que você precisa fazer é permitir que cada dispositivo teams Rooms participe de reuniões de terceiros. As reuniões de terceiros exigem um nome de usuário e um endereço de email para ingressar neles. Se o nome de usuário e o endereço de email que você precisa usar for diferente da caixa de correio de sala do dispositivo, você precisará adicioná-los ao dispositivo. Você pode fazer isso nas configurações do dispositivo ou no arquivo de configuração XML.

### <a name="use-device-settings"></a>Usar configurações de dispositivo

Para configurar o dispositivo Teams Rooms usando sua tela touchscreen, faça o seguinte:

1. No dispositivo Salas do Microsoft Teams, selecione **Mais ...**.
2. Selecione **Configurações** e insira o nome de usuário e a senha do administrador do dispositivo.
3. Vá até a **guia Reuniões** e selecione **Cisco WebEx,** **Zoom** ou ambos.
4. Se você quiser participar de reuniões com o nome de usuário e o endereço de email associado à caixa de correio de sala, selecione **Participar com informações da sala.**
5. Se você quiser participar de reuniões com um nome de usuário alternativo e endereço de email, selecione **Ingressar** com informações personalizadas e insira nome de usuário e endereço de email que você gostaria de usar.
6. Selecione **Salvar e sair**. Seu dispositivo será reiniciado.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar o arquivo SkypeSettings.xml configuração

As configurações a seguir podem ser adicionadas ao `SkypeSettings.xml` arquivo localizado em `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Para obter mais informações sobre o `SkypeSettings.xml` arquivo, consulte [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).

Para habilitar reuniões do Cisco WebEx, de definir o `WebExMeetingsEnabled` elemento XML como **True**, da seguinte forma.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Para habilitar reuniões do Zoom, de definir o `ZoomMeetingsEnabled` elemento XML como **True**, da seguinte forma.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Opcionalmente, você pode especificar um nome de usuário personalizado e um endereço de email para ingressar em reuniões de terceiros usando os seguintes elementos XML. Se os valores que você fornece não são válidos, o dispositivo Salas do Teams usará o nome de usuário da caixa de correio de sala e o endereço de email.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Para ingressar na reunião do Cisco WebEx a partir de um dispositivo Teams Rooms, a reunião da Cisco precisa ser hospedada usando o aplicativo Web Do Cisco WebEx versão WBS 40.7 ou posterior.
