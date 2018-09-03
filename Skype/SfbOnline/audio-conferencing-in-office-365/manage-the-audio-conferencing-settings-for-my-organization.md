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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulte as etapas do Skype for Business Online para atribuir uma licença de conferência discada e um ID de conferência a um usuário e muitas outras configurações de conferência discada. '
ms.openlocfilehash: 7f4387e7d818730de3b2b0336453a3f6ec9b39e7
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780487"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gerenciar as configurações da Audioconferência para minha organização no Skype for Business Online

> [!NOTE]
> Se você quiser gerenciar essas configurações em equipes, consulte [Gerenciar as configurações de Audioconferência para minha organização no Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Pode ser mais fácil para você ver todas as configurações de audioconferência do Skype for Business em um só lugar.


## <a name="assign-an-audio-conferencing-license"></a>Atribuir uma licença de Audioconferência

> [!NOTE]
> Não é possível atribuir licenças usando o **centro de administração do Skype for Business**. Você deve usar o centro de administração do Office 365. Consulte [Atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **Para atribuir uma licença para um usuário**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Na barra de navegação esquerda do **centro de administração do Office 365**, vá até **Usuários** > **Usuários ativos**, e selecione o usuário ou usuários na lista de usuários disponíveis.

    > [!NOTE]
    > [!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição. Em seguida, clique em **Editar**, **Avançar** duas vezes, selecione a licença e clique em **Enviar**. Você também pode atribuir licenças a vários usuários usando o Windows Powershell. Para obter instruções e scripts de amostra do PowerShell, consulte [Atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. No painel de Ação em **Licenças de produtos**, clique em **Editar**.

4. Na página **Licenças de produtos**, ligue a **Audioconferência** e em seguida clique em **Salvar**. Para mais informações sobre licenciamento, consulte [Licenciamento de suplementos do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Depois de atribuir a licença, a Microsoft pode não aparecer inicialmente na lista como um provedor de audioconferência. Caso isso aconteça, saia do centro de administração do Office 365 ou pressione CTRL+F5 para atualizar a janela do navegador.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Ativar ou desativar emails enviados para usuários de audioconferência

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business** e, no painel de navegação esquerdo, clique em **Audioconferência**.

3. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.

4. Clique em **Salvar**.

    Você também pode enviar emails para o usuário com as configurações da audioconferência acessando as propriedades de audioconferência do usuário e clicando em **Enviar informações da conferência via email**. O ID da conferência e o número de telefone padrão da audioconferência estão incluídos no convite da reunião, mas não o PIN.

    Veja [Enviar um email para um usuário com as informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Usar o Windows PowerShell**

- Também é possível usar o Windows PowerShell e executar:

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Você pode usar [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo o email.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Alterar as informações de contato do remetente nas mensagens de email enviadas aos usuários

Você pode fazer alterações nos emails enviados automaticamente para seus usuários, incluindo o endereço de email real e o nome para exibição das informações de contato do remetente. Por padrão, o remetente dos emails é o Office 365, mas é possível alterar o endereço de email e o nome para exibição com o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285). Para fazer alterações no endereço do email enviado para seus usuários, você deve:

- Insira o endereço de email no parâmetro _SendEmailFromAddress_.

- Insira o nome para exibição no email no parâmetro  _SendEmailFromDisplayName_.

- Defina o parâmetro _SendEmailOverride_ como _Verdadeiro_.

Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.

Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações de sua organização, incluindo o email.

Veja [Emails enviados automaticamente para os usuários quando suas configurações de Audioconferência forem alteradas](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Redefinir a ID de conferência de reunião

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência**, e no painel Ação, em **ID da conferência**, clique em **Redefinir**.

4. Na janela **Redefinir o ID da conferência?** , clique **Sim**. Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado. Está ativado por padrão.

    > [!IMPORTANT]
    >  [!IMPORTANTE] Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar os usuários para reagendar os convites de reunião para garantir que o novo ID da conferência seja inserido nos convites. Os usuários podem usar a Ferramenta de Migração de Reunião do Skype for Business para atualizar suas reuniões marcadas. Para ver como baixar, instalar e executar a Ferramenta de Atualização de Reunião do Skype for Business, consulte: [Ferramenta de Atualização de Reunião do Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Ferramenta de Migração de Reunião (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype for Business Online, Ferramenta de Migração de Reunião (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

Veja [Redefinir o ID de conferência para um usuário](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

A cada reunião agendada por um usuário será atribuído um ID de conferência único. Embora um ID de conferência seja criado e atribuído a um usuário automaticamente, podem existir ocasiões em que um usuário não deseje usá-lo e você precise configurá-lo para um determinado número, ou seus usuários não lembrem ou tenham perdido o ID da conferência. Você pode usar o centro de administração do Skype for Business e o Windows PowerShell para exibir, alterar e redefinir seu ID da conferência.


1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business** e, no painel de navegação esquerdo, clique em **Audioconferência**.

3. Clique em **Usuários**, e selecione o usuário para o qual você deseja redefinir o PIN.

4. No painel de Ação, em **PIN**, clique em **Redefinir**.

Os usuários receberão um email com seu PIN quando estiverem habilitados para a audioconferência ou quando o PIN for redefinido. Entretanto, se você desabilitou o envio automático de emails, o email de redefinição do PIN não será enviado e você deverá enviar manualmente o PIN para o usuário. O PIN será exibido somente uma vez depois de ser redefinido. Depois de ser exibido, logo após ser redefinido, o PIN não será mais mostrado nas propriedades do usuário; em vez disso, será mostrado *****.

Consulte [Redefinir o PIN da Audioconferência](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com informações da Audioconferência para um usuário

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business** e, no painel de navegação esquerdo, clique em **Audioconferência**.

3. Clique em **Usuários**, e selecione o usuário para o qual você deseja redefinir o PIN.

4. No painel Ação, clique em **Enviar informações da conferência por email**.

    > [!NOTE]
    > Ao fazer isso, o PIN da audioconferência não é enviado ao usuário.

Veja [Enviar um email para um usuário com as informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Definir os números de telefone incluídos em convites

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business**.

3. No painel de navegação esquerdo, vá para **Audioconferência** > **Usuários**. Selecione o usuário que você deseja habilitar para a Audioconferência.

4. No painel de Ação você pode definir o **Número de chamada tarifada** e, se permitido, o **Número de chamada gratuita**.

5. Clique em **Salvar**.

Consulte [Definir os números de telefone incluídos em convites](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Escolher as configurações de ponte de audioconferência

**Definir a experiência da reunião quando quem está ligando ingressa em uma reunião**


1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, acesse **Audioconferência** > **Configurações de ponte da Microsoft**.

4. Em **Experiência de participação na reunião**, selecione as seguintes ações:

  - **Habilitar notificações de entrada e saída de reunião** Esta opção é selecionada por padrão. Se você desmarcar essa caixa de seleção, por padrão, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entrar ou sair.

    Isso pode ser definido para cada reunião quando um usuário entra em uma reunião usando um aplicativo do Skype for Business e modifica a configuração no Skype Meeting **Anunciar quando as pessoas entram ou saem** no menu da reunião **Opções**.

  - **Solicitar que os autores de chamadas registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão. Se você desmarcar essa caixa de seleção, os participantes não precisarão registrar seu nome antes de ingressar em uma reunião.

5. Depois de fazer suas alterações, clique em **Salvar**.
    
Consulte [Alterar as configurações de uma ponte de Audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Definir o comprimento do PIN para reuniões**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, acesse **Audioconferência** > **Configurações de ponte da Microsoft**.

4. Em **Segurança**, insira o número de dígitos que você deseja para o PIN na lista **Comprimento do PIN** e clique em **Salvar**.

    O PIN deve ter entre 4 e 12 dígitos. O padrão é 5.
    
Consulte [Alterar as configurações de uma ponte de Audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Ativar ou desativar o envio de email para usuários de áudio**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business** e, no painel de navegação esquerdo, clique em **Audioconferência**.

3. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.

4. Clique em **Salvar**.

    Você também pode enviar um email para o usuário com as configurações da audioconferência acessando as propriedades de audioconferência do usuário e clicando em **Enviar informações da conferência via email**.

    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.

    Veja [Enviar um email para um usuário com as informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Veja e defina os idiomas principal (padrão) e secundário (alternativo) em uma ponte de audioconferência


1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência** e clique em **Ponte Microsoft**.

4. Selecione um número de telefone da lista, clique em **Definir idiomas** no painel de Ação e depois na página **Configurar idiomas** clique uso da lista de **Idioma principal** para exibir a lista completa dos idiomas com suporte.

    Você também pode definir os idiomas primário e secundário com suporte quando você seleciona Microsoft como o provedor de audioconferência. A ordem que você seleciona nas listas é a mesma ordem em que os idiomas serão apresentados aos autores de chamadas.

Veja [Definir idiomas do assistente automático para Audioconferência](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Consultar os números de discagem de audioconferência

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, acesse **Audioconferência** > **Ponte Microsoft**. Aqui você pode:

  - Exibir os números de telefone definidos pelo Office 365 para a Audioconferência.

  - Exibir o local e o idioma principal e secundário que será usado pelo assistente automático da Audioconferência.

  - Selecionar o número de telefone padrão que será fornecido aos usuários quando eles forem habilitados para a Audioconferência. No entanto, se o número de telefone padrão da ponte de audioconferência for alterado, o número de telefone padrão dos usuários existentes não será alterado.

Você pode ir para **Audioconferência** > **Usuários** e selecionar as propriedades do usuário para alterar o número padrão do usuário selecionando um número novo da lista de números disponíveis na sua organização.

Consulte [Ver uma lista de números de Audioconferência](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Ver uma lista de usuários habilitados

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do Office 365** > **do Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência** e clique em **Usuários**.

Consulte [Ver uma lista de usuários habilitados para Audioconferência](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

Existem várias configurações que você pode gerenciar no nível da organização usando o Windows PowerShell. Isso facilita a aplicação de configurações a todos os usuários.

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

 ## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:

  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- O Windows PowerShell tem muitas vantagens de velocidade, simplicidade e produtividade em comparação ao uso exclusivo do centro de administração do Office 365, por exemplo quando você realiza alterações de configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de Audioconferência de um usuário](manage-the-audio-conferencing-settings-for-a-user.md)


