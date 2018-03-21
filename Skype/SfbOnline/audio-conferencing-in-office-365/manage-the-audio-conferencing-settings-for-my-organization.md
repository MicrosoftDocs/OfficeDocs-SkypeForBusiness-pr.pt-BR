---
title: "Gerenciar as configurações de áudio da conferência para minha organização"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: 6fb10654c5845fb5524264219e642cd0a250e860
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>Gerenciar as configurações de áudio da conferência para minha organização

Talvez seja mais fácil para ver todas as configurações de serviços de audioconferência para Skype para Teams da Microsoft em um único local e de negócios. 
  
## <a name="assign-an-audio-conferencing-license"></a>Atribuir uma licença de conferência de áudio

> [!NOTE]
> Não é possível atribuir licenças usando o **Skype para centro de administração de negócios**. Você deve usar o Centro de administração do Office 365. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 **Para atribuir uma licença para um usuário**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. No painel de navegação à esquerda do **Centro de administração do Office 365**, vá para **usuários** > **usuários ativos**e selecione o usuário ou usuários da lista de usuários disponíveis.
    
    > [!NOTE]
    > [!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição. Em seguida, clique em **Editar**, **próximo** duas vezes e em seguida, selecione a licença e clique em **Enviar**. Você também pode atribuir licenças a vários usuários usando o Windows Powershell. Para obter instruções e scripts do PowerShell de amostra, consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. No painel Ação em **Licenças de**, clique em **Editar**. 
    
4. Na página **Licenças do produto** , ligue a **Conferência de áudio** e, em seguida, clique em **Salvar**. Para obter mais informações sobre licenciamento, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Após atribuir a licença, Microsoft talvez não sejam exibidos inicialmente na lista como um provedor de serviços de audioconferência. Caso isso aconteça, saia do Centro de administração do Office 365 ou pressione CTRL+F5 para atualizar a janela do navegador. 
  
## <a name="assign-a-conference-id-for-a-user"></a>Atribuir uma ID de conferência a um usuário

Uma ID de conferência é atribuída automaticamente a um usuário quando eles estiverem configurados para conferência de áudio usando o Microsoft como um provedor de serviços de audioconferência. A ID de conferência atribuída pode ser estáticos ou dinâmicos e é enviada no convite da reunião, quando a reunião foi agendada. 
  
IDs estáticas são usadas quando as pessoas na sua organização não desejam Lembre-se de um número aleatório; eles podem selecionar um certo número ou escolha que é fácil de lembrar. Se IDs de conferência dinâmicas estiverem sendo usadas, cada reunião agendada por um usuário terá uma ID de conferência exclusiva atribuída. Se você desejar atribuir dinâmico em vez de IDs de conferência estático, consulte [IDs de conferência de áudio usando dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
O Centro de administração do Skype for Business não pode ser usado para atribuir uma ID de conferência a um usuário, mas você pode usar o Windows PowerShell para fazer isso.
  
Para definir a ID de conferência para um usuário, execute:
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Uma ID de conferência deve conter 7 dígitos, e você não pode alterá-lo no Skype para centro de administração de negócios ou usando o Windows PowerShell. 
  
Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.
  
> [!IMPORTANT]
>  [!IMPORTANTE]  Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites. Os usuários podem usar o Skype para ferramenta de migração de reunião de negócios para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar o Skype para ferramenta de atualização de reunião de negócios, consulte: [Ferramenta de atualização de reunião para Skype para negócios e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negócios Online, a ferramenta de migração de reunião (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype para Business Online Meeting Ferramenta de migração (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Veja [Consulte, alterar e redefina um ID de conferência atribuído a um usuário](see-change-and-reset-a-conference-id-assigned-to-a-user.md).
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a>Alterar o provedor de serviços de audioconferência da Microsoft a um provedor de terceiros

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e então e selecione o usuário que você deseja alterar o provedor de serviços de audioconferência para.
    
4. No Painel de Ações, clique em **Editar**. 
    
5. Na página **Propriedades** , em **nome do provedor**, escolha o provedor de serviços de audioconferência para o usuário.
    
    > [!NOTE]
    > Você só pode selecionar Microsoft como o provedor de serviços de audioconferência ou **Nenhum** se você tiver selecionado vários usuários.
  
6. Clique em **Salvar**. 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar ou desabilitar os e-mails enviados para usuários de serviços de audioconferência

Você pode usar o Skype para centro de administração de negócios ou o Windows PowerShell para habilitar ou desabilitar o email enviado aos usuários.
  
 **Usando o Skype para o Centro de administração de negócios**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Na página **configurações de ponte da Microsoft** , marque ou desmarque a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.
    
4. Clique em **Salvar**.
    
    Você também pode enviar emails para o usuário com as configurações de serviços de audioconferência indo para propriedades de conferência de áudio do usuário e clicar em **Enviar informações de conferência via email**. Número de telefone do serviços de audioconferência a conferência ID e o padrão é incluído no convite da reunião, mas não o PIN.
    
    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).
    
 **Usando o Windows PowerShell**
  
- Também é possível usar o Windows PowerShell e executar: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    Você pode usar o [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo email.
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Alterar as informações de contato do remetente nas mensagens de email enviadas aos usuários

Você pode fazer alterações para email que será enviado automaticamente aos seus usuários, incluindo o endereço de email real e o nome para exibição de informações de contato do remetente. Por padrão, o remetente dos emails é o Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Para fazer alterações para o endereço de email que está enviando email aos usuários, você deve:
  
- Insira o endereço de email no parâmetro _SendEmailFromAddress_ .
    
- Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.
    
- Defina o parâmetro _SendEmailOverride_ como _True_.
    
Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.
  
Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo email.
  
Consulte [Emails que são enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="reset-the-meeting-conference-id"></a>Redefinir a ID de conferência de reunião

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**e, no painel de ação em **ID da conferência**, clique em **Redefinir**.
    
4. No **Redefinir ID de conferência?** janela, clique em **Sim**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.
    
    > [!IMPORTANT]
    >  [!IMPORTANTE] Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites. Os usuários podem usar o Skype para ferramenta de migração de reunião de negócios para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar o Skype para ferramenta de atualização de reunião de negócios, consulte: [ferramenta de atualização de reunião para Skype para negócios e Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4) [Skype para Business Online Ferramenta de migração (64 bits) da reunião](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype para negócios on-line, a ferramenta de migração de reunião (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Veja [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

IDs estáticas são usadas quando as pessoas na sua organização não desejam Lembre-se de um número aleatório; eles podem selecionar um certo número ou use um que seja fácil de lembrar. Se IDs de conferência dinâmicas estiverem sendo usadas, cada reunião agendada por um usuário terá uma ID de conferência exclusiva atribuída. Se você deseja atribuir dinâmico em vez de conferência estática IDs, [IDs de conferência de áudio usando dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Embora uma ID de conferência estática será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número ou os usuários não conseguir se lembrar ou tem perdido sua ID de conferência. Você pode usar o Skype para centro de administração de negócios e do Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários**e, em seguida, selecione o usuário que você deseja redefinir o PIN para.
    
4. No painel de ações, em **PIN**, clique em **Redefinir**.
    
Os usuários receberão um email com o PIN quando elas são habilitadas para conferência de áudio ou quando o PIN ser redefinido. Mas, se você desabilitou automaticamente enviando e-mails, um email de redefinição PIN não será enviado e você terá que enviar manualmente o PIN para o usuário. O PIN será exibido somente uma vez depois de ser redefinido. Depois que ele é exibido depois de ser redefinido, o PIN não será mostrado mais sobre as propriedades de usuário; em vez disso, * * * serão exibidos. 
  
Veja [Redefinir o PIN de conferência de áudio para um usuário](reset-the-audio-conferencing-pin-for-a-user.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com informações de conferência de áudio a um usuário

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários**e, em seguida, selecione o usuário que você deseja redefinir o PIN para.
    
4. No painel Ação, clique em **Enviar informações da conferência por email**.
    
    > [!NOTE]
    > Quando você fizer isso, os serviços de audioconferência PIN não será enviado ao usuário. 
  
Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>Definindo o número de telefone de conferência de áudio padrão para organizadores de reunião

 **Para definir o número de telefone de conferência de áudio padrão para organizadores de reunião, quando você estiver habilitando um usuário para conferência de áudio**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No painel de navegação esquerdo, vá para **conferência de áudio** > **usuários**. Selecione o usuário que você deseja habilitar para conferência de áudio.
    
4. No painel de ações, nas propriedades do usuário, clique em **Editar**.
    
5. Na página **Propriedades** , em **nome do provedor**, use a lista suspensa para selecionar o provedor de serviços de audioconferência.
    
  - Se você selecionar Microsoft como um provedor de serviços de audioconferência, você pode escolher o número de telefone de conferência de áudio padrão da lista.  
    
  - Se você selecionar um ACP de terceiros como o provedor de serviços de audioconferência, você precisará digitar manualmente as tarifas e, se necessário, o número de telefone gratuitos. Esses números de telefone serão o número de telefone padrão.
    
    O número de telefone de conferência de áudio padrão de um usuário é o número que é exibido no convite da reunião, quando eles agendam uma reunião.
    
6. Clique em **Salvar**. 
    
Consulte [Definir convidam números incluídos no telefone](set-the-phone-numbers-included-on-invites.md).
  
 **Para definir o número de telefone de conferência de áudio padrão para organizadores de reunião depois de habilitar um usuário para conferência de áudio**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**, selecione o usuário desejado e na página ação, clique em **Editar**.
    
4. Na página **Propriedades** , em **nome do provedor**, use a lista suspensa para selecionar o provedor de serviços de audioconferência.
    
  - Se o usuário usa o Microsoft como um provedor de serviços de audioconferência, você pode escolher o número de telefone de conferência de áudio padrão da lista.  
    
  - Se o usuário utilizar um ACP de terceiros como o provedor de serviços de audioconferência, você precisará digitar manualmente as tarifas e, se necessário, o número de telefone gratuitos.
    
    O número de telefone de conferência de áudio padrão de um usuário é o número que é exibido no convite da reunião, quando eles agendam uma reunião.
    
5. Clique em **Salvar**. 
    
Consulte [Definir convidam números incluídos no telefone](set-the-phone-numbers-included-on-invites.md).
  
## <a name="setting-audio-conferencing-bridge-settings"></a>Definindo as configurações de ponte de conferência de áudio

 **Definir a experiência da reunião, quando os chamadores ingressem em uma reunião**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Em que **a experiência de participação da reunião**, selecione as seguintes ações:
    
  - **Habilitar a ativação de notificações de entrada e saída de reunião** Esta opção é selecionada por padrão. Se você desmarcar essa caixa de seleção, os usuários que já tenham ingressado na reunião por padrão não serão notificados quando alguém entra ou sai da reunião.
    
    Isso pode ser definido em uma base de reunião por reunião quando um usuário ingressa em uma reunião usando um Skype para o aplicativo de negócios ou Teams da Microsoft e eles modificam a configuração de **anunciar quando as pessoas entrar ou sair** do menu Skype reunião ou Microsoft Teams **Opções** do reunião.
    
  - **Peça que os chamadores registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão. Se você desmarcar essa caixa de seleção, os chamadores não solicitados registrar seus nomes antes de ingressar em uma reunião.
    
5. Depois de fazer suas alterações, clique em **Salvar**.
    
Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Definir o tamanho PIN para reuniões**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Em **segurança**, insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.
    
    O PIN deve ter entre 4 e 12 dígitos. O padrão é 5.
    
Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Habilitar ou desabilitar o email que está sendo enviado a usuários de áudio**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Na página **configurações de ponte da Microsoft** , marque ou desmarque a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.
    
4. Clique em **Salvar**.
    
    Você também pode enviar email para o usuário com as configurações de conferência de áudio, indo para propriedades de conferência de áudio do usuário e clicar em **Enviar informações de conferência via email**.
    
    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.
    
    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a>Consulte e definir os idiomas principais e secundários em uma ponte de conferência de áudio

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**e, em seguida, clique em **Microsoft ponte**.
    
4. Selecione um número de telefone na lista, clique em **definir idiomas** no painel de ações e na página **conjunto** de idiomas, clique em uso na lista de **idioma principal** para exibir a lista completa dos idiomas com suporte.
    
    Você também pode definir os idiomas principais e secundários que têm suporte quando você seleciona Microsoft como o provedor de serviços de audioconferência. A ordem em que você selecione nas listas é a mesma ordem em que idiomas serão apresentados aos chamadores.
    
Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Consulte serviços de audioconferência discada números

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **ponte da Microsoft**. Aqui, você pode:
    
  - Exiba os números de telefone definidos pelo Office 365 a serem usados para conferência de áudio. 
    
  - Exiba o local e os idiomas principais e secundários, que serão usados pelo atendedor automático conferência de áudio.
    
  - Selecione o número de telefone padrão que será fornecido aos usuários quando eles estão habilitados para conferência de áudio. No entanto, se o número de telefone de ponte de conferência de áudio padrão for alterado, não alterará o número de telefone padrão para usuários existentes.
    
Você pode ir para a **conferência de áudio** > **usuários** e selecione Propriedades do usuário para alterar o padrão de número de um usuário escolhendo um novo número da lista de números que estão disponíveis em sua organização.
  
Consulte [ver uma lista de números de conferência de áudio](see-a-list-of-audio-conferencing-numbers.md).
  
## <a name="see-a-list-of-users-that-are-enabled"></a>Visualizar uma lista de usuários habilitados

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**> e, em seguida, **os usuários**.
    
Veja [Ver uma lista de usuários habilitados para conferência de áudio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

Existem diversas configurações que podem ser gerenciadas no nível da organização usando o Windows PowerShell. Isso facilita aplicar as configurações para todos os usuários. 
    
Para obter mais ajuda sobre cada cmdlet, consulte [Cmdlets do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=627324).

Aqui estão as configurações de nível de organização: 
> 
- **Definir notificações de entrada/saída** O padrão é _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- **A definição de registro de nome** O padrão é _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **A definição do comprimento do PIN** O padrão é 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Configuração somente discada reuniões de um telefone** O padrão _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Definindo-se enviar email aos usuários** O padrão é _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Definindo-se enviar email a partir de uma conta diferente** O padrão é _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Definindo o endereço From em que é enviado aos usuários de email** O padrão é _$null_. 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Definir o nome de exibição para o email que será enviado aos usuários** O padrão é _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell   
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
    
## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência de um usuário](manage-the-audio-conferencing-settings-for-a-user.md)

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing.md)

