---
title: Gerenciar as configurações da Audioconferência para minha organização no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Confira as etapas do Skype for Business online para atribuir uma ID de conferência e uma licença de conferência discada para um usuário e muitas outras configurações de conferência discada. '
ms.openlocfilehash: aef115d2882a368e085880a66332dc7d22e4ff04
ms.sourcegitcommit: e65411a739c539d5232ebc89af3630d07d518b89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "35638560"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gerenciar as configurações da Audioconferência para minha organização no Skype for Business Online

> [!NOTE]
> Se você quiser gerenciar essas configurações em equipes, consulte [Gerenciar as configurações de Audioconferência para minha organização no Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Pode ser mais fácil para você ver todas as configurações de audioconferência para o Skype for Business em um só lugar.


## <a name="assign-an-audio-conferencing-license"></a>Atribuir uma licença de Audioconferência

> [!NOTE]
> You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **Para atribuir uma licença para um usuário**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Na navegação à esquerda do **centro de administração do Office 365**, vá **** > para usuários**ativos**do Office e selecione o usuário ou os usuários na lista de usuários disponíveis.

    > [!NOTE]
    > If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. No painel Ação em **Licenças de**, clique em **Editar**.

4. On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar ou desabilitar emails enviados para usuários de audioconferência

![Um ícone mostrando o logotipo](../images/sfb-logo-30x30.png) do Skype for Business **usando o centro de administração do Skype for Business**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **Centro** > de administração do Office 365**Skype for Business** e, no painel de navegação esquerdo, clique em **conferência de áudio**.

3. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.

4. Clique em **Salvar**.

    You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.

    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Usando o Windows PowerShell**

- Também é possível usar o Windows PowerShell e executar:

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Você pode usar o [set-csonlinedialinconferencingtenantsettingshttp](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) para gerenciar outras configurações de sua organização, incluindo o email.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Alterar as informações de contato do remetente nas mensagens de email enviadas aos usuários

You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet. To make changes to the email address that is sending the email to the users, you must:

- Digite o endereço de email no parâmetro _SendEmailFromAddress_ .

- Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.

- Defina o parâmetro _SendEmailOverride_ como _Verdadeiro_.

Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:

```
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.

Você pode usar o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) para gerenciar outras configurações de sua organização, incluindo o email.

Veja [os emails enviados automaticamente para os usuários quando as configurações de conferência de áudio mudam](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Redefinir a ID de conferência de reunião

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência**, e no painel Ação, em **ID da conferência**, clique em **Redefinir**.

4. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **Centro** > de administração do Office 365**Skype for Business** e, no painel de navegação esquerdo, clique em **conferência de áudio**.

3. Clique em **usuários**e selecione o usuário para o qual você deseja redefinir o PIN.

4. No painel Ação, em **PIN**, clique em **Redefinir**.

Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, ***** will be shown.

Consulte [redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com as informações de conferência de áudio para um usuário

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **Centro** > de administração do Office 365**Skype for Business** e, no painel de navegação esquerdo, clique em **conferência de áudio**.

3. Clique em **usuários**e selecione o usuário para o qual você deseja redefinir o PIN.

4. No painel Ação, clique em **Enviar informações da conferência por email**.

    > [!NOTE]
    > Quando você faz isso, o pino de audioconferência não é enviado para o usuário.

Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Configurar os números de telefone incluídos nos convites

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.

3. In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.

4. No painel de Ação você pode definir o **Número de chamada tarifada** e, se permitido, o **Número de chamada gratuita**.

5. Clique em **Salvar**.

Consulte [definir os números de telefone incluídos nos convites](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Escolher as configurações de ponte de audioconferência

**Definir a experiência da reunião quando os chamadores entrarem em uma reunião**


1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.

4. Em **experiência de participação na reunião**, selecione as seguintes ações:

   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.

     Isso pode ser definido de acordo com a reunião quando um usuário ingressa em uma reunião usando um aplicativo Skype for Business e ele modifica a configuração **anunciar quando as pessoas entram ou saem** no menu **Opções** de reunião do Skype da reunião.

   - **Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.

5. Depois de fazer suas alterações, clique em **Salvar**.
    
Consulte [alterar as configurações de uma ponte de conferência de áudio](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Definir o comprimento do PIN para reuniões**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.

4. Em **segurança**, insira o número de dígitos que você deseja para o pino na lista **comprimento do pino** e clique em **salvar**.

    The PIN must be between 4 and 12 digits. The default is 5.
    
Consulte [alterar as configurações de uma ponte de conferência de áudio](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Habilitar ou desabilitar o envio de emails para usuários de áudio**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **Centro** > de administração do Office 365**Skype for Business** e, no painel de navegação esquerdo, clique em **conferência de áudio**.

3. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.

4. Clique em **Salvar**.

    Você também pode enviar emails para o usuário com as configurações de audioconferência, acessando as propriedades de videoconferência do usuário e clicando em **enviar informações de conferência por e-mail**.

    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.

    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Ver e definir os idiomas principais (padrão) e secundários (alternativos) em uma ponte de audioconferência


1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **videoconferências**e clique em ponte da **Microsoft**.

4. Selecione um número de telefone na lista, clique em **definir idiomas** no painel ação e, na página **definir idiomas** , clique na lista usar o **idioma principal** para exibir a lista completa de idiomas com suporte.

    You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.

Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Consulte números de discagem de conferência de áudio

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:

   - Veja os números de telefone definidos pelo Office 365 a serem usados para videoconferências.

   - Exiba o local e os idiomas primário e secundário, que serão usados pelo atendedor automático da conferência de áudio.

   - Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.

Você pode acessar**usuários** de **audioconferência** > e selecionar as propriedades do usuário para alterar o número padrão de um usuário, escolhendo um novo número na lista de números disponíveis em sua organização.

Veja [ver uma lista de números de audioconferência](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Visualizar uma lista de usuários habilitados

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **videoconferências**> e depois **usuários**.

Veja [Ver uma lista de usuários habilitados para conferência de áudio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.

Para obter mais ajuda sobre cada cmdlet, consulte [Cmdlets do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=627324).

Aqui estão as configurações no nível da organização:

- **Configurar notificações de entrada/saída** O padrão é _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Configurar registro de nome** O padrão é _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Configurar comprimento do PIN** O padrão é 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Configurar apenas reuniões por telefone** O padrão _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Configurar o envio de email para usuários** O padrão é _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Configurar o envio de email a partir de uma conta diferente** O padrão é _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Configurar o endereço De no email enviado aos usuários** O padrão é _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Configurar o nome para exibição do email que é enviado aos usuários** O padrão é _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:

  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência de um usuário](manage-the-audio-conferencing-settings-for-a-user.md)


