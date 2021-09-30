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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Consulte Skype for Business online para atribuir uma licença de conferência discada e uma ID de conferência a um usuário e muitas outras configurações de conferência discada. '
ms.openlocfilehash: eb5313729c2071a64e5d6495e460dbaa475df305
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012125"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gerenciar as configurações da Audioconferência para minha organização no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Se você quiser gerenciar essas configurações em equipes, consulte [Gerenciar as configurações de Audioconferência para minha organização no Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Pode ser mais fácil para você ver todas as configurações de audioconferência para Skype for Business em um só lugar.


## <a name="assign-an-audio-conferencing-license"></a>Atribuir uma licença de Audioconferência

> [!NOTE]
> Não é possível atribuir licenças usando o Skype for Business **de administração.** Você deve usar o Centro de administração do Microsoft 365. Consulte [Atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **Para atribuir uma licença para um usuário**

1. Entre com sua conta de trabalho ou de estudante.

2. Na navegação à esquerda do centro de administração, vá para **Usuários**  >  **Usuários ativos e** selecione o usuário ou os usuários na lista de usuários disponíveis.

    > [!NOTE]
    > [!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição. Em seguida, **clique** em Editar , **Em** seguida, selecione a licença e clique em **Enviar**. Você também pode atribuir licenças a vários usuários usando o Windows Powershell. Para obter instruções e scripts de amostra do PowerShell, consulte [Atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. No painel Ação em **Licenças de**, clique em **Editar**.

4. Na página **Licenças de produtos**, ligue a **Audioconferência** e em seguida clique em **Salvar**. Para mais informações sobre licenciamento, consulte [Licenciamento de complementos do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Depois de atribuir a licença, a Microsoft pode não aparecer inicialmente na lista como um provedor de audioconferência. Se isso acontecer, saia do centro de administração ou pressione CTRL+F5 para atualizar a janela do navegador.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar ou desabilitar emails enviados para usuários de audioconferência

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração**

1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique **em Audioconferência**.

3. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.

4. Clique em **Salvar**.

    Você também pode enviar emails para o usuário com as configurações de audioconferência indo para as propriedades de audioconferência do usuário e clicando em Enviar informações de conferência **por email**. A ID da conferência e o número de telefone de audioconferência padrão estão incluídos no convite da reunião, mas não no PIN.

    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Usando Windows PowerShell**

- Também é possível usar o Windows PowerShell e executar:

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Você pode usar [o Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) para gerenciar outras configurações para sua organização, incluindo email.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Alterar as informações de contato do remetente em mensagens de email enviadas aos usuários

Você pode fazer alterações no email que é enviado automaticamente para seus usuários, incluindo o endereço de email real e o nome de exibição das informações de contato do remetente. Por padrão, o remetente dos emails é Microsoft 365 ou Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Para fazer alterações no endereço de email que está enviando o email para os usuários, você deve:

- Insira o endereço de email no _parâmetro SendEmailFromAddress._

- Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.

- Defina o parâmetro _SendEmailOverride_ como _Verdadeiro_.

Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.

Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) para gerenciar outras configurações para sua organização, incluindo email.

Consulte [Emails que são enviados automaticamente aos usuários quando suas configurações de Audioconferência mudam](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Redefinir a ID de conferência de reunião

1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business**.

3. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência**, e no painel Ação, em **ID da conferência**, clique em **Redefinir**.

4. Na janela **Redefinir iD** da conferência? clique em **Sim**. Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado. Está ativado por padrão.

    > [!IMPORTANT]
    >  [!IMPORTANTE] Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites. Os usuários podem usar o Skype for Business de Migração de Reunião para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar Skype for Business Ferramenta de Atualização de Reunião do Skype for Business, consulte: Ferramenta de Atualização de Reunião para Skype for Business e [Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), Skype for Business Online, Ferramenta de Migração de Reunião [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047) [e Skype for Business Online, Ferramenta de Migração de Reunião (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079).

Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva. Embora uma ID de conferência seja criada e atribuída automaticamente a um usuário, pode haver momentos em que um usuário não deseja usá-lo e você deseja defini-lo como um determinado número, ou seus usuários não podem se lembrar ou perder a ID da conferência. Você pode usar o centro de administração do Skype for Business e o Windows PowerShell para exibir, alterar e redefinir seu ID da conferência.


1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique **em Audioconferência**.

3. Clique **em Usuários** e selecione o usuário para o que você deseja redefinir o PIN.

4. No painel Ação, em **PIN,** clique em **Redefinir**.

Os usuários receberão um email com seu PIN quando eles estão habilitados para audioconferência ou quando o PIN é redefinido. Mas se você tiver desabilitado o envio automático de emails, um email de redefinição de PIN não será enviado e você terá que enviar manualmente o PIN para o usuário. O PIN será exibido somente uma vez depois de ser redefinido. Depois que ele é exibido logo após ser redefinido, o PIN não será mais mostrado nas propriedades do usuário; em vez disso, ***** será mostrado.

Consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com informações de Audioconferência para um usuário

1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique **em Audioconferência**.

3. Clique **em Usuários** e selecione o usuário para o que você deseja redefinir o PIN.

4. No painel Ação, clique em **Enviar informações da conferência por email**.

    > [!NOTE]
    > Quando você faz isso, o PIN de audioconferência não é enviado ao usuário.

Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Definindo os números de telefone incluídos em convites

1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business**.

3. No painel de navegação esquerdo, vá para **Audioconferência** > **Usuários**. Selecione o usuário que você deseja habilitar para Audioconferência.

4. No painel de Ação você pode definir o **Número de chamada tarifada** e, se permitido, o **Número de chamada gratuita**.

5. Clique em **Salvar**.

Consulte [Definir os números de telefone incluídos em convites](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Escolher as configurações de ponte de audioconferência

**Definir a experiência de reunião quando os chamadores ingressarem em uma reunião**


1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business**.

3. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Configurações** de ponte da Microsoft de audioconferência.  >  

4. Em **Experiência de junção de reunião,** selecione as seguintes ações:

   - **Habilitar a ativação de notificações de entrada e saída de reunião** Esta opção é selecionada por padrão. Se você limpar essa caixa de seleção, os usuários que já ingressaram na reunião por padrão não serão notificados quando alguém entrar ou sair da reunião.

     Isso pode ser definido em uma base de reunião por reunião quando um usuário ingresse em uma reunião usando um aplicativo Skype for Business e eles modificam a configuração Anunciar quando as pessoas entram ou saem no **menu** Opções do Reunião do Skype da reunião. 

   - **Peça que os chamadores registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão. Se você limpar essa caixa de seleção, os chamadores não serão solicitados a gravar seus nomes antes de ingressarem em uma reunião.

5. Depois de fazer suas alterações, clique em **Salvar**.
    
Consulte [Alterar as configurações de uma ponte de Audioconferência.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Definir o tamanho do PIN para reuniões**

1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business**.

3. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Configurações** de ponte da Microsoft de audioconferência.  >  

4. Em **Segurança**, insira o número de dígitos que você deseja para o PIN na lista de comprimento **do PIN** e clique em **Salvar**.

    O PIN deve ter entre 4 e 12 dígitos. O padrão é 5.
    
Consulte [Alterar as configurações de uma ponte de Audioconferência.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Habilitar ou desabilitar o envio de emails para usuários de áudio**

1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique **em Audioconferência**.

3. Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.

4. Clique em **Salvar**.

    Você também pode enviar emails para o usuário com as configurações de audioconferência, indo para as propriedades de audioconferência do usuário e clicando em Enviar informações de conferência **por email**.

    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.

    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Consulte e defina os idiomas principal (padrão) e secundário (alternativo) em uma ponte de audioconferência


1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business**.

3. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Audioconferência** e clique em **Ponte da Microsoft**.

4. Selecione um número de telefone na lista, clique em Definir  idiomas no painel Ação  e, na página Definir idiomas, clique na lista usar o idioma principal para exibir a lista completa de idiomas com suporte. 

    Você também pode definir os idiomas primários e secundários com suporte ao selecionar a Microsoft como provedor de audioconferência. A ordem que você seleciona nas listas é a mesma ordem em que os idiomas serão apresentados aos autores de chamadas.

Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Consulte números de discagem de audioconferência

1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business**.
 
3. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Audioconferência**  >  **ponte microsoft**. Aqui você pode:

   - Exibir os números de telefone que são definidos por Microsoft 365 ou Office 365 a serem usados para Audioconferência.

   - Exibir o local e os idiomas primários e secundários que serão usados pelo atendimento automático de Audioconferência.

   - Selecione o número de telefone padrão que será dado aos usuários quando eles estão habilitados para Audioconferência. No entanto, se o número de telefone padrão da ponte de audioconferência mudar, o número de telefone padrão para usuários existentes não mudará.

Você pode ir até Usuários de **Audioconferência** e selecionar as propriedades do usuário para alterar o número padrão de um usuário escolhendo um novo número na lista de números que estão disponíveis em  >   sua organização.

Consulte [Ver uma lista de números de Audioconferência](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Visualizar uma lista de usuários habilitados

1. Entre com sua conta de trabalho ou de estudante.

2. Vá para o centro de administração > **Skype for Business**.

3. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Audioconferência**> **e,** em seguida, Usuários .

Veja [Ver uma lista de usuários habilitados para conferência de áudio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

Há várias configurações que você pode gerenciar no nível da organização usando Windows PowerShell. Isso facilita a aplicação de configurações a todos os usuários.

Para obter mais ajuda sobre cada cmdlet, consulte [Cmdlets do Skype for Business Online](/previous-versions//mt228132(v=technet.10)).

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

  ## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre Windows PowerShell
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que é suportado apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em Baixar e instalar o módulo [Teams PowerShell](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência de um usuário](manage-the-audio-conferencing-settings-for-a-user.md)
