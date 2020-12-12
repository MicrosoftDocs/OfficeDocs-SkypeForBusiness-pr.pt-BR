---
title: Habilitar dispositivos de salas de equipe para participar de reuniões de terceiros
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
description: Este artigo discute como configurar os dispositivos da sua organização e salas de equipe para dar suporte à reunião de terceiros de acordo com o Cisco WebEx e o zoom.
ms.openlocfilehash: 8079b6fc231bf30a654e2513af55a806433eb83f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662356"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Habilitar dispositivos da sala de equipe para participar de reuniões de terceiros

Os dispositivos de salas do Microsoft Teams dão suporte a uma experiência de toque único para a associação online de reuniões online de terceiros. Quando habilitado, você pode usar um dispositivo de salas de equipe para ingressar em reuniões hospedadas no Cisco WebEx e fazer o zoom de<sup>1</sup> tão facilmente quanto você pode ingressar em reuniões hospedadas no Microsoft Teams.

Antes de poder ingressar em reuniões de terceiros a partir de um dispositivo de salas de equipe, você precisa fazer o seguinte:

1. Configurar a caixa de correio da sala do Exchange Online do dispositivo de salas de equipe para processar convites para reuniões de terceiros
2. Verifique se a sua organização não tem nenhuma política que impeça você de se conectar a serviços de reunião de terceiros
3. Configurar dispositivos de salas de equipe para permitir reuniões de terceiros

As seções a seguir mostram como executar cada uma dessas etapas.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Etapa 1: permitir o processamento de convites de calendário para reuniões de terceiros

A primeira coisa que você precisa fazer para habilitar uma experiência de junção de um toque a partir de um dispositivo de salas de equipe é definir as regras de processamento de calendário para a caixa de correio da sala do Exchange Online do dispositivo. A caixa de correio da sala precisa permitir reuniões externas e manter o corpo da mensagem e o assunto para que ele possa ver a URL necessária para ingressar na reunião de terceiros. Para definir essas opções da caixa de correio de sala usando o cmdlet [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) , faça o seguinte:

1. Conecte-se ao PowerShell do Exchange Online. Para obter mais informações, consulte [conectar ao PowerShell do Exchange Online com autenticação básica](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) ou [conectar-se ao PowerShell do Exchange Online usando a autenticação multifator](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), dependendo do método de autenticação.

2. Obtenha o nome UPN da caixa de correio da sala, se não souber, executando o seguinte comando:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. Localize o nome da caixa de correio da sala associada ao dispositivo de salas de equipe e anote seu UPN

4. Depois de encontrar o UPN da caixa de correio da sala, execute o seguinte comando. Substituir `<UserPrincipalName>` pelo UPN da caixa de correio da sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Saiba mais sobre o [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Etapa 2: configurar a proteção contra ameaças e a regravação de links do Office 365

Para habilitar a experiência de junção de toque único, as informações do link de ingresso na reunião de terceiros devem estar presentes e legíveis no convite da reunião. Se a sua organização usa o recurso de [links seguros da proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) ou se você usa uma solução de terceiros que examina todas as URLs de entrada e saída para ameaças, ela pode alterar as URLs de junção da reunião e torná-la irreconhecível para o dispositivo de salas de equipe. Para verificar se isso não acontece, você precisa adicionar as URLs de um serviço de reunião de terceiros à lista de links de segurança ATP "não reescrever" ou à lista de exceções de regravação de URL de terceiros.

Para adicionar URLs de serviços de reunião de terceiros à lista de links seguros ATP "não reescrever", siga as etapas em [Configurar uma lista de URLs do not Rewrite usando links de segurança ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide). Se você usa uma solução de terceiros, consulte as instruções dessa solução para adicionar URLs à sua lista de exceções de regravação de URL.

Aqui estão alguns exemplos de entradas que talvez você precise adicionar à lista de exceções ATP "não reescrever" ou à lista de exceções de regravação de URL de terceiros:

- **Cisco WebEx**`*.webex.com*`
- **Zoom** `*.zoom.us*` , `*.zoom.com*` , `*.zoomgov.com*`

Para obter uma lista completa de URLs a serem adicionadas à lista de exceções ATP "não reescrever" ou à lista de exceções de terceiras URLs, entre em contato com o provedor de serviços de reunião de terceiros do qual você deseja aceitar os convites de reunião. 

> [!CAUTION]
> Adicione somente URLs confiáveis à lista de exceções ATP "não reescrever" ou à lista de exceções de regravação de URL de terceiros.

## <a name="step-3-enable-third-party-meetings-on-device"></a>Etapa 3: habilitar reuniões de terceiros no dispositivo

A última etapa que você precisa fazer é permitir que cada dispositivo de salas de equipe ingresse em reuniões de terceiros. Reuniões de terceiros exigem um nome de usuário e um endereço de e-mail para ingressar. Se o nome de usuário e o endereço de email que você precisa usar forem diferentes da caixa de correio da sala do dispositivo, você precisará adicioná-los ao seu dispositivo. Você pode fazer isso nas configurações do dispositivo ou no arquivo XML de configuração.

### <a name="use-device-settings"></a>Usar as configurações do dispositivo

Para configurar o dispositivo de salas de equipe usando o Touch Touch, faça o seguinte:

1. No dispositivo salas do Microsoft Teams, selecione **mais..** .
2. Selecione **configurações** e, em seguida, digite o nome de usuário e a senha do administrador do dispositivo
3. Vá para a guia **reuniões** e selecione **Cisco WebEx**, **zoom**<sup>1</sup>ou ambos
4. Se você deseja ingressar em reuniões com o nome de usuário e o endereço de email associados à caixa de correio da sala, selecione **ingressar com informações de sala**
5. Se você quiser ingressar em reuniões com um nome de usuário e um endereço de email alternativos, selecione **ingressar com informações personalizadas** e insira o nome de usuário e o endereço de email que deseja usar
6. Selecione **salvar e sair**. Seu dispositivo será reiniciado.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar o arquivo de configuração SkypeSettings.xml

As configurações a seguir podem ser adicionadas ao `SkypeSettings.xml` arquivo localizado em `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` . Para obter mais informações sobre o `SkypeSettings.xml` arquivo, consulte [gerenciar configurações de console de salas do Microsoft Teams remotamente com um arquivo de configuração XML](xml-config-file.md).

Para habilitar reuniões Cisco WebEx, defina o `WebExMeetingsEnabled` elemento XML como **true**, da seguinte maneira.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Para habilitar o zoom <sup>1</sup> reuniões, defina o `ZoomMeetingsEnabled` elemento XML como **verdadeiro**, da seguinte maneira.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

Opcionalmente, você pode especificar um nome de usuário e um endereço de email personalizados para ingressar em reuniões de terceiros usando os seguintes elementos XML. Se os valores fornecidos não forem válidos, o dispositivo de salas de equipe usará como padrão usar o nome de usuário e o endereço de email da caixa de correio.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Para ingressar em uma reunião do Cisco WebEx a partir de um dispositivo de salas de equipe, a reunião da Cisco precisa ser hospedada usando a versão WBS 40,7 ou posterior do aplicativo Web Cisco WebEx.

<sup>1</sup> o zoom das reuniões de zoom só está disponível no momento para selecionar clientes de salas do Microsoft Teams com o programa de acesso à tecnologia (toque).
