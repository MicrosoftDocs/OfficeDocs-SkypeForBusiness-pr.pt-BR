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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Veja as etapas do Skype for Business Online para atribuir uma licença de conferência discada e uma ID de conferência a um usuário e muitas outras configurações de conferência discada. '
ms.openlocfilehash: aa8e9cbaf063ebf1780e3f8ce45b7bd54ced474f
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164140"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gerenciar as configurações da Audioconferência para minha organização no Skype for Business Online

> [!NOTE]
> Se você quiser gerenciar essas configurações em equipes, consulte [Gerenciar as configurações de Audioconferência para minha organização no Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Talvez seja mais fácil para você ver todas as configurações de audioconferência do Skype for Business em um só lugar.


## <a name="assign-an-audio-conferencing-license"></a>Atribuir uma licença de Audioconferência

> [!NOTE]
> Não é possível atribuir licenças usando o Centro **de administração do Skype for Business.** Você deve usar o Centro de administração do Microsoft 365. Consulte [Atribuir licenças do Skype for Business.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

 **Para atribuir uma licença para um usuário**

1. Entre com sua conta do trabalho ou da escola.

2. Na navegação à esquerda do centro de administração, vá para Usuários Ativos e selecione o usuário ou usuários na lista  >  de usuários disponíveis.

    > [!NOTE]
    > If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. No painel Ação em **Licenças de**, clique em **Editar**.

4. On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Depois que você atribuir a licença, a Microsoft pode não aparecer inicialmente na lista como um provedor de serviços de audioconferência. Se isso acontecer, saia do centro de administração ou pressione Ctrl+F5 para atualizar a janela do navegador.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar ou desabilitar emails enviados para usuários de audioconferência

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique em **Audioconferência.**

3. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.

4. Clique em **Salvar**.

    You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.

    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Usando o Windows PowerShell**

- Também é possível usar o Windows PowerShell e executar:

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Você pode usar [o Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) para gerenciar outras configurações da sua organização, incluindo email.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Alterar as informações de contato do remetente em mensagens de email enviadas aos usuários

Você pode fazer alterações no email que é enviado automaticamente aos usuários, incluindo o endereço de email real e o nome de exibição das informações de contato do remetente. Por padrão, o remetente dos emails é o Microsoft 365 ou o Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Para fazer alterações no endereço de email que está enviando o email para os usuários, você deve:

- Insira o endereço de email no parâmetro _SendEmailFromAddress._

- Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.

- Defina o parâmetro _SendEmailOverride_ como _Verdadeiro_.

Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.

Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) para gerenciar outras configurações para sua organização, incluindo email.

Veja [emails que são enviados automaticamente aos usuários quando suas configurações de Audioconferência mudarem.](emails-sent-to-users-when-their-settings-change.md)

## <a name="reset-the-meeting-conference-id"></a>Redefinir a ID de conferência de reunião

1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business.**

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência**, e no painel Ação, em **ID da conferência**, clique em **Redefinir**.

4. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).

Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique em **Audioconferência.**

3. Clique **em** Usuários e selecione o usuário para o que você deseja redefinir o PIN.

4. No painel Ação, em **PIN,** clique em **Redefinir.**

Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, ***** will be shown.

Consulte [Redefinir o PIN de Audioconferência.](reset-the-audio-conferencing-pin.md)

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com informações de Audioconferência para um usuário

1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique em **Audioconferência.**

3. Clique **em** Usuários e selecione o usuário para o que você deseja redefinir o PIN.

4. No painel Ação, clique em **Enviar informações da conferência por email**.

    > [!NOTE]
    > Quando você faz isso, o PIN de audioconferência não é enviado ao usuário.

Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Definir os números de telefone incluídos nos convites

1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business.**

3. In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.

4. No painel de Ação você pode definir o **Número de chamada tarifada** e, se permitido, o **Número de chamada gratuita**.

5. Clique em **Salvar**.

Consulte [Definir os números de telefone incluídos nos convites.](set-the-phone-numbers-included-on-invites.md)


## <a name="choosing-audio-conferencing-bridge-settings"></a>Escolher as configurações de ponte de audioconferência

**Definir a experiência da reunião quando os chamadores ingressarem em uma reunião**


1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business.**

3. No Centro **de administração do Skype for Business,** na navegação à esquerda, vá para configurações da ponte da Microsoft de **audioconferência.**  >  

4. Em **Experiência de junção de reunião,** selecione as seguintes ações:

   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.

     Isso pode ser definido em uma reunião por reunião quando um usuário ingressa  em uma reunião usando um aplicativo do Skype for Business e modifica a configuração Anunciar quando as pessoas entram ou saem da configuração no **menu** Opções de Reunião do Skype da reunião.

   - **Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.

5. Depois de fazer suas alterações, clique em **Salvar**.
    
Consulte [Alterar as configurações de uma ponte de audioconferência.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Definir o tamanho do PIN para reuniões**

1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business.**

3. No Centro **de administração do Skype for Business,** na navegação à esquerda, vá para configurações da ponte da Microsoft de **audioconferência.**  >  

4. Em **Segurança,** insira o número de dígitos que você deseja para o PIN na lista de comprimento **do PIN** e clique em **Salvar.**

    The PIN must be between 4 and 12 digits. The default is 5.
    
Consulte [Alterar as configurações de uma ponte de audioconferência.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Habilitar ou desabilitar o envio de emails para usuários de áudio**

1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique em **Audioconferência.**

3. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.

4. Clique em **Salvar**.

    Você também pode enviar emails para o usuário com as configurações de audioconferência, indo para as propriedades de audioconferência do usuário e clicando em Enviar informações de conferência **por email.**

    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.

    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Ver e definir os idiomas primário (padrão) e secundários (alternativos) em uma ponte de audioconferência


1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business.**

3. No Centro **de administração do Skype for Business,** na navegação à esquerda, vá para **Audioconferência** e clique na ponte **da Microsoft.**

4. Selecione um número de telefone na lista, clique em Definir  idiomas no painel Ação  e, na página Definir idiomas, clique na lista de idiomas principal para exibir a lista completa de idiomas com suporte. 

    You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.

Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Ver números de discagem de audioconferência

1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business.**
 
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:

   - Exibir os números de telefone definidos pelo Microsoft 365 ou pelo Office 365 a serem usados para Audioconferência.

   - Exibir o local e os idiomas primário e secundário que serão usados pelo assistente automático de Audioconferência.

   - Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.

Você pode ir para Usuários de **Audioconferência** e selecionar as propriedades do usuário para alterar o número padrão de um usuário escolhendo um novo número na lista de números disponíveis em  >   sua organização.

Veja [uma lista de números de Audioconferência.](see-a-list-of-audio-conferencing-numbers.md)

## <a name="see-a-list-of-users-that-are-enabled"></a>Visualizar uma lista de usuários habilitados

1. Entre com sua conta do trabalho ou da escola.

2. Vá para o centro de administração > **Skype for Business.**

3. No Centro **de administração do Skype for Business,** na navegação à esquerda, vá para a> de audioconferência e, em  **seguida, usuários.**

Veja [Ver uma lista de usuários habilitados para conferência de áudio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.

Para obter mais ajuda sobre cada cmdlet, consulte [Cmdlets do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=627324).

Aqui estão as configurações no nível da organização:

- **Configurar notificações de entrada/saída** O padrão é _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Configurar registro de nome** O padrão é _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Configurar comprimento do PIN** O padrão é 5.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Configurar apenas reuniões por telefone** O padrão _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Configurar o envio de email para usuários** O padrão é _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Configurar o envio de email a partir de uma conta diferente** O padrão é _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Configurar o endereço De no email enviado aos usuários** O padrão é _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Configurar o nome para exibição do email que é enviado aos usuários** O padrão é _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell
- O Windows PowerShell gerencia os usuários e o que os usuários podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, consulte estes tópicos:

  - [Por que você precisa usar o Microsoft 365 ou o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do centro de administração, como quando você está fazendo alterações nas configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência de um usuário](manage-the-audio-conferencing-settings-for-a-user.md)


