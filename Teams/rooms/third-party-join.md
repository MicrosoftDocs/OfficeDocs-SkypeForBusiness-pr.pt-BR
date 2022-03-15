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
description: Este artigo discute como configurar sua organização e Salas do Teams dispositivos para dar suporte à junção de reuniões de terceiros à Cisco WebEx e zoom.
ms.openlocfilehash: a4ae34593570d4b81eb381eb0fe68f1dea26d578
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503898"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Habilitar Teams de sala para ingressar em reuniões de terceiros

Salas do Microsoft Teams dispositivos suportam uma experiência de toque único para ingressar em reuniões online de terceiros, também conhecidas como Participação direta de Convidados. Quando habilitado, você pode usar o Salas do Teams para participar de reuniões hospedadas no Cisco WebEx e zoom da mesma forma que você pode participar de reuniões hospedadas em Microsoft Teams.

Antes de ingressar em reuniões de terceiros Salas do Teams, você precisa fazer o seguinte:

1. Configure a Salas do Teams da Exchange Online de sala para processar convites para reuniões de terceiros.
2. Certifique-se de que sua organização não tenha políticas que o impeçam de se conectar a serviços de reunião de terceiros.
3. Configure Salas do Teams para permitir reuniões de terceiros.

As seções a seguir mostram como fazer cada uma dessas etapas.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Etapa 1: Permitir o processamento de convites de calendário para reuniões de terceiros

A primeira coisa que você precisa fazer para habilitar uma experiência de junção de um toque das Salas de Equipe é definir as regras de processamento de calendário para a caixa de correio de sala Exchange Online do dispositivo. A caixa de correio de sala precisa permitir reuniões externas e manter o corpo e o assunto da mensagem para que ela possa ver a URL necessária para ingressar na reunião de terceiros. Para definir essas opções de caixa de correio de sala usando o cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , faça o seguinte:

1. Conexão para Exchange Online PowerShell. Para obter mais informações, consulte Conexão para Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) com autenticação básica ou Conexão para Exchange Online PowerShell usando autenticação [multifato](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), dependendo do método de autenticação.

2. Obter o Nome de Entidade de Usuário (UPN) da caixa de correio de sala se você não a conhece executando o seguinte comando:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Encontre o nome da caixa de correio de sala associada ao dispositivo Salas do Teams e anote seu UPN.

4. Depois de encontrar o UPN da caixa de correio da sala, execute o seguinte comando. Substitua `<UserPrincipalName>` pelo UPN da caixa de correio da sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Saiba mais sobre [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Etapa 2: Configurar Office 365 Proteção contra Ameaças e regravar link

Para habilitar a experiência de junção de um toque, as informações de link de junção de reunião da reunião de terceiros precisam estar presentes e habilitadas no convite da reunião. Se a sua organização usa o recurso de Links de Proteção Avançada contra Ameaças [Cofre Office 365](/microsoft-365/security/office-365-security/atp-safe-links) ou se você usar uma solução de terceiros que verifica todas as URLs de entrada e saída para ameaças, ele pode alterar as URLs de participação da reunião e tornar a reunião irreconhecível pelo dispositivo Salas do Teams. Para garantir que isso não aconteça, você precisa adicionar AS URL Cofre s do serviço de reunião de terceiros à lista de links "não reescrever" ou à lista de exceção de regravar URL de terceiros.

Para adicionar URLs de serviço de reunião de terceiros à lista de links do atp Cofre "não reescrever", siga as etapas em Configurar uma lista de [URLs personalizadas](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) que não regravem usando links do ATP Cofre. Se você usar uma solução de terceiros, consulte as instruções para que essa solução adicione URLs à lista de exceção de reescrita de URL.

Aqui estão algumas entradas de exemplo que talvez você precise adicionar à sua lista de links "não reescrever" da AT Cofre P ou da lista de exceção de regravar URL de terceiros:

- **Cisco WebEx** `*.webex.com*`
- **Zoom** `*.zoom.us*`, `*.zoom.com*``*.zoomgov.com*`

Para uma lista completa de URLs para adicionar à sua lista de links do COFRE ATP "não reescrever" ou lista de exceção de regravar URL de terceiros, entre em contato com o provedor de serviços de reunião de terceiros de onde você deseja aceitar convites de reunião. 

> [!CAUTION]
> Adicione apenas URLs que você confia à sua lista de Cofre links "não reescreve" ou lista de exceção de regravações de URL de terceiros.

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>Etapa 3: Habilitar reuniões de terceiros em Salas do Teams

A última etapa que você precisa fazer é permitir Salas do Teams participar de reuniões de terceiros. As reuniões de terceiros exigem um nome de usuário e um endereço de email para ingressar neles. Se o nome de usuário e o endereço de email que você precisa usar for diferente da caixa de correio de sala do dispositivo, você precisará adicioná-los ao dispositivo. Você pode fazer isso nas configurações Salas do Teams ou no arquivo de configuração XML.

### <a name="use-device-settings"></a>Usar configurações de dispositivo

Para configurar Salas do Teams usando o console touchscreen, faça o seguinte:

1. No console Salas do Microsoft Teams, selecione **Mais ...**.
2. Selecione **Configurações** e insira o nome de usuário e a senha do administrador do dispositivo.
3. Vá até a **guia Reuniões** e selecione **Cisco WebEx**, **Zoom** ou ambos.
4. Se você quiser participar de reuniões com o nome de usuário e o endereço de email associado à caixa de correio de sala, selecione **Participar com informações da sala**.
5. Se você quiser participar de reuniões com um nome de usuário alternativo e endereço de email, selecione **Ingressar** com informações personalizadas e insira nome de usuário e endereço de email que você gostaria de usar.
6. Selecione **Salvar e sair**. Seu dispositivo será reiniciado.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar o arquivo SkypeSettings.xml configuração

As configurações a seguir podem ser adicionadas ao arquivo `SkypeSettings.xml` localizado em `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Para obter mais informações sobre o arquivo`SkypeSettings.xml`, consulte [Manage a Salas do Microsoft Teams console settings remotely with an XML configuration file](xml-config-file.md).

Para habilitar reuniões do Cisco WebEx, de definir o `WebExMeetingsEnabled` elemento XML como **True**, da seguinte forma.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Para habilitar reuniões zoom, de definir o `ZoomMeetingsEnabled` elemento XML como **True**, da seguinte forma.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Opcionalmente, você pode especificar um nome de usuário personalizado e um endereço de email para ingressar em reuniões de terceiros usando os seguintes elementos XML. Se os valores que você fornece não são válidos, o dispositivo Salas do Teams padrão para usar o nome de usuário da caixa de correio de sala e o endereço de email.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Para ingressar em uma reunião do Cisco WebEx a partir de um dispositivo Salas do Teams, a reunião da Cisco precisa ser hospedada no WebEx Meetings Pro usando o aplicativo Web Da Cisco WebEx versão WBS 40.7 ou posterior. 
