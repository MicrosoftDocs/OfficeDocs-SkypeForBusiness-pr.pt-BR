---
title: Habilitar Salas do Teams dispositivos para ingressar em reuniões de terceiros
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Este artigo discute como configurar sua organização e Salas do Teams dispositivos para dar suporte à ingresso em reuniões de terceiros no Cisco Webex e no Zoom.
ms.openlocfilehash: 70d2cf03dea3fcfef3d08c07f4f771bd8a2ea70e
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67794990"
---
# <a name="enable-teams-rooms-devices-to-join-third-party-meetings"></a>Habilitar Salas do Teams dispositivos para ingressar em reuniões de terceiros

Salas do Microsoft Teams dispositivos dão suporte a uma experiência de toque único para ingressar em reuniões online de terceiros, também conhecidas como Ingresso Direto para Convidados. Quando habilitado, você pode usar o Salas do Teams para ingressar em reuniões hospedadas no Cisco Webex e no Zoom da mesma forma que pode ingressar em reuniões hospedadas no Microsoft Teams.

Dispositivos e serviços com suporte:

- Salas do Teams no Windows, todos os modelos certificados – Zoom, Cisco Webex

- Salas do Teams no Android, todos os modelos certificados – Zoom, Cisco Webex

    > [!NOTE]
    > A Microsoft lança novos recursos para Salas do Teams no Android regularmente. No entanto, pode haver um atraso entre quando os recursos são lançados e quando eles ficam disponíveis em um dispositivo. Se um recurso não estiver disponível em seu dispositivo, verifique com o fabricante do dispositivo informações sobre quando ele pode ficar disponível.

> [!NOTE]
> Para ingressar em uma reunião do Cisco Webex de um dispositivo Salas do Teams, a reunião da Cisco precisa ser hospedada no Webex Meetings Pro usando o cisco Webex web application versão WBS 40.7 ou posterior.

Antes de ingressar em reuniões de terceiros Salas do Teams, você precisa fazer o seguinte:

1. Configure a Salas do Teams da Exchange Online sala para processar convites para reuniões de terceiros.
2. Verifique se sua organização não tem políticas que impeçam que você se conecte a serviços de reunião de terceiros.
3. Configure Salas do Teams para permitir reuniões de terceiros.

As seções a seguir mostram como concluir cada uma dessas etapas.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>Etapa 1: Permitir o processamento de convite de calendário para reuniões de terceiros

A primeira coisa que você precisa fazer para habilitar uma experiência de ingresso com um toque nas Salas de Equipe é definir as regras de processamento de calendário para a caixa de correio da sala de Exchange Online do dispositivo. A caixa de correio da sala precisa permitir reuniões externas e manter o corpo e o assunto da mensagem para que ele possa ver a URL necessária para ingressar na reunião de terceiros. Para definir essas opções de caixa de correio de sala usando o cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing.) , faça o seguinte:

1. Conecte-se Exchange Online PowerShell. Para obter mais informações, consulte Conectar-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) com autenticação básica ou [conectar-se ao Exchange Online PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell) usando a autenticação multifator, dependendo do método de autenticação.

2. Obtenha o NOME UPN da caixa de correio da sala se você não o souber executando o seguinte comando:

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Localize o nome da caixa de correio da sala associada ao seu Salas do Teams e anote seu UPN.

4. Depois de encontrar o UPN da caixa de correio da sala, execute o comando a seguir. Substitua `<UserPrincipalName>` pelo UPN da caixa de correio da sala:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

Saiba mais sobre [o Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>Etapa 2: Configurar a proteção Office 365 ameaças e a reescrita de link

Para habilitar a experiência de ingresso com um toque, as informações de link de ingresso na reunião de terceiros precisam estar presentes e legível no convite da reunião. Se sua organização usar o recurso de links seguros do Microsoft Defender para Office 365 ou se você usar uma solução de terceiros que examina todas as URLs de entrada e saída em busca de ameaças, ela poderá alterar as URLs de ingresso na reunião e tornar [a](/microsoft-365/security/office-365-security/safe-links) reunião irreconhecível pelo dispositivo Salas do Teams. Para garantir que isso não aconteça, você precisa adicionar as URLs do serviço de reunião de terceiros ao Office 365 Defender para Links Seguros não reescrever [a ](/microsoft-365/security/office-365-security/safe-links) lista ou a lista de exceções de reescrita de URL de terceiros.

 Se você usar uma solução de terceiros, consulte as instruções dessa solução para adicionar URLs à sua lista de exceções de reescrita de URL.

Aqui estão alguns exemplos de entradas que talvez você precise adicionar ao seu *Defender para Office 365 Links Seguros* Não reescrever lista ou lista de exceções de reescrita de URL de terceiros:

- **Cisco Webex** `*.webex.com/*`
- **Zoom**`*.zoom.us/*`, `*.zoom.com/*``*.zoomgov.com/*`

Para obter uma lista completa de URLs a serem adicionadas *aos links seguros* do Defender para Office 365 Não reescrever lista ou lista de exceções de reescrita de URL de terceiros, entre em contato com o provedor de serviços de reunião de terceiros do qual você deseja aceitar convites de reunião.

> [!CAUTION]
> Adicione apenas URLs em que você confia *Microsoft Defender para Office 365 Links Seguros* Não reescreva a lista ou a lista de exceções de reescrita de URL de terceiros.

## <a name="step-3a-enable-third-party-meetings-on-teams-rooms-on-windows"></a>Etapa 3a: Habilitar reuniões de terceiros Salas do Teams no Windows

A última etapa que você precisa fazer é permitir que Salas do Teams ingressar em reuniões de terceiros. As reuniões de terceiros exigem um nome de usuário e um endereço de email para ingressá-las. Se o nome de usuário e o endereço de email que você precisa usar for diferente da caixa de correio da sala do dispositivo, você precisará adicioná-los ao seu dispositivo. Você pode fazer isso nas Salas do Teams configurações ou no arquivo de configuração XML. Você pode fazer isso nas Salas do Teams configurações em qualquer Salas do Teams ou no arquivo de configuração XML para Salas do Teams no Windows.

### <a name="use-device-settings"></a>Usar configurações do dispositivo

Para configurar Salas do Teams no Windows usando o console touchscreen, faça o seguinte:

1. No console Salas do Microsoft Teams, selecione **Mais**.
2. Selecione **Configurações e** insira o nome de usuário e a senha do administrador do dispositivo.
3. Vá para a **guia Reuniões** e selecione um provedor de reunião de terceiros que você deseja habilitar (por exemplo, **Webex**, **Zoom** etc.).
4. Se você quiser ingressar em reuniões com o nome de usuário e o endereço de email associados à caixa de correio da sala, selecione **Ingressar com as informações da sala**.
5. Se você quiser ingressar em reuniões com um nome de usuário e endereço de email  alternativos, selecione Ingressar com informações personalizadas e insira o nome de usuário e o endereço de email que deseja usar.
6. Selecione **Salvar e sair**. Seu dispositivo será reiniciado.

### <a name="use-the-skypesettingsxml-configuration-file"></a>Usar o arquivo SkypeSettings.xml configuração

As configurações a seguir podem ser adicionadas ao `SkypeSettings.xml` arquivo localizado em `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. Para obter mais informações sobre o arquivo`SkypeSettings.xml`, consulte [Gerenciar um Salas do Microsoft Teams console remotamente com um arquivo de configuração XML](xml-config-file.md).

Para habilitar reuniões do Cisco Webex, defina o `WebexMeetingsEnabled` elemento XML como **True**, da seguinte maneira.

```xml
<WebexMeetingsEnabled>True</WebexMeetingsEnabled>
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
## <a name="step-3b-enable-third-party-meetings-on-teams-rooms-on-android"></a>Etapa 3b: Habilitar reuniões de terceiros Salas do Teams no Android

Para configurar Salas do Teams no Android usando o console touchscreen ou a tela frontal da sala, faça o seguinte:

1.  No console Salas do Microsoft Teams ou na tela frontal da sala, selecione **Mais**.
2.  Selecione **Configurações** e:
    -   Se estiver usando uma conta pessoal (por exemplo, uma conta com uma licença E5), escolha a **opção** Reuniões.
    -   Se estiver usando uma conta compartilhada (por exemplo, uma conta de recurso com uma licença do Salas do Teams), escolha Configurações do **dispositivo,** localize as configurações do **Teams Administração**, insira uma senha de administrador e escolha uma opção **Reuniões**.
      > [!NOTE]
      > Alguns fabricantes de dispositivos exigem uma senha de administrador antes **que as configurações do** dispositivo possam ser acessadas.

    ![Configurações de reuniões para MTR no Android](..\media\mtrandroid.png)

3.  Selecione um provedor de reunião de terceiros que você deseja habilitar.
4.  Se você quiser ingressar em reuniões com um nome de usuário personalizado e um endereço de email, selecione **Ingressar com o nome e o email personalizados**. Para atualizar informações pessoais personalizadas, pressione **Editar informações personalizadas** e insira seu nome e endereço de email preferidos.

