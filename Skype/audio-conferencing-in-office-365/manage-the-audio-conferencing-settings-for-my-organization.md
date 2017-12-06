---
title: "Gerenciar as configurações de conferência de áudio para minha organização"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
description: "See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. "
---

# Gerenciar as configurações de conferência de áudio para minha organização

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](bc9bd328-c5b2-44e5-af15-e02bf00e1c81.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/bc9bd328-c5b2-44e5-af15-e02bf00e1c81). 
  
Talvez seja mais fácil de ver todas as configurações de conferência de áudio do Skype for Business e Teams da Microsoft em um só lugar.
  
## Atribuir uma licença de conferência de áudio

> [!NOTE]
> Você não pode atribuir licenças usando o **Centro de administração do Skype for Business**. Você deve usar o Centro de administração do Office 365. Consulte [Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 **Para atribuir uma licença para um usuário**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. No painel esquerdo do **Centro de administração do Office 365**, vá para **usuários** > **usuários ativos** e selecione o usuário ou usuários na lista de usuários disponíveis.
    
    > [!NOTE]
    > Se você estiver atribuindo licenças aos usuários até 20 ao mesmo tempo, você pode usar na lista **Selecione uma exibição** suspensa e em seguida, escolha uma das opções ou criar seu próprio modo de exibição. Clique em **Editar**, **Avançar** duas vezes, em seguida, selecione a licença e clique em **Enviar**. Você também pode atribuir licenças a vários usuários usando o Windows Powershell. Para obter instruções e scripts de exemplo do PowerShell, consulte [Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. No painel Ação em **Licenças de**, clique em **Editar**. 
    
4. Na página **Licenças de produto**, ative a **Conferência de áudio** e clique em **Salvar**. Para obter mais informações sobre o licenciamento, consulte [Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Depois de atribuir a licença, Microsoft pode não aparecer inicialmente na lista como um provedor de audioconferência. Se isso acontecer, faça logout do Centro de administração do Office 365 ou pressione CTRL + F5 para atualizar a janela do navegador. 
  
## Atribuir uma ID de conferência a um usuário

Um ID de conferência é atribuído automaticamente a um usuário quando eles estão configurados para conferência de áudio usando o Microsoft como provedor de audioconferência. A ID de conferência atribuída pode ser estáticas ou dinâmicas e é enviada no convite da reunião quando a reunião está agendada.
  
Identificações estáticas são usadas quando as pessoas em sua organização não desejam se lembrar de um número aleatório; ele poderá selecionar um determinado número ou escolher um que seja fácil de lembrar. Quando IDs de conferência dinâmicos forem usados, cada reunião que um cronogramas do usuário serão obter atribuída uma ID de conferência exclusivo. Se você quiser atribuir dinâmico em vez de conferência estático IDs, [Usando IDs de dinâmico de conferência de áudio em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
O Centro de administração do Skype for Business não pode ser usado para atribuir uma ID de conferência a um usuário, mas você pode usar o Windows PowerShell para fazer isso.
  
Para definir a ID de conferência para um usuário, execute:
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Um ID de conferência deve conter 7 dígitos, e você não pode alterá-lo no Skype para o Centro de administração de negócios ou usando o Windows PowerShell. 
  
Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.
  
> [!IMPORTANT]
>  Após uma nova ID de conferência é criada, a ID de conferência antigo não pode ser usada por chamadores. Você deve notificar os usuários reagendar seus convites para garantir que a conferência nova que identificação é adicionada aos convites de reunião existente. Os usuários podem usar o Skype for Business ferramenta de migração de reunião para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar o Skype para Business ferramenta de atualização de reunião, consulte:> [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business Online, ferramenta de migração de reuniões (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business Online, a ferramenta de migração de reunião (32 bits)](https://go.microsoft.com/fwlink/?LinkID=626046)
  
Consulte [Consulte, alterar e redefina um ID de conferência atribuído a um usuário](see-change-and-reset-a-conference-id-assigned-to-a-user.md).
  
## Alterar o provedor de conferência de áudio da Microsoft para um provedor de terceiros

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **usuários** e selecione o usuário que você deseja alterar o provedor de audioconferência.
    
4. No Painel de Ações, clique em **Editar**.
    
5. Na página **Propriedades**, em **nome do provedor**, escolha o provedor de audioconferência para o usuário.
    
    > [!NOTE]
    > Você só pode selecionar a Microsoft como o provedor de audioconferência ou **Nenhum** se você tiver selecionado vários usuários.
  
6. Clique em **Salvar**.
    
Consulte [Alterar o provedor de conferência discada dos usuários](https://support.office.com/article/9b74f053-4d23-485f-9232-3d30370a8c6e).
  
## Habilitar ou desabilitar emails enviados para usuários de conferência de áudio

Você pode usar o Skype para o Centro de administração de negócios ou o Windows PowerShell para habilitar ou desabilitar emails enviados para os usuários.
  
 **Usando o Skype para o Centro de administração de negócios**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Na página **configurações de ponte da Microsoft**, marque ou desmarque **Enviar automaticamente os emails para os usuários se alterar suas configurações de conferência de áudio**.
    
4. Clique em **Salvar**.
    
    Você também pode enviar emails para o usuário com as configurações de audioconferência indo para as propriedades do usuário audioconferência e clicando em **Enviar informações de conferência via email**. O ID e padrão audioconferência telefone número da conferência está incluído no convite da reunião, mas não o PIN.
    
    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
    
 **Usando o Windows PowerShell**
  
- Também é possível usar o Windows PowerShell e executar:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    Você pode usar o [Conjunto CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações de sua organização, incluindo email.
    
## Alterar informações de contato do remetente em mensagens de email enviadas aos usuários

Você pode fazer alterações para o email que será enviado automaticamente aos seus usuários, incluindo o endereço de email real e o nome de exibição das informações de contato do remetente. Por padrão, o remetente dos emails é o Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Para fazer alterações ao endereço de email que está enviando o email para os usuários, faça o seguinte:
  
- Digite o endereço de email no parâmetro  _SendEmailFromAddress_.
    
- Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.
    
- Defina o parâmetro  _SendEmailOverride_ como _True_.
    
Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.
  
Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações de sua organização, incluindo email.
  
Consulte [Emails que são automaticamente enviados aos usuários quando alterar suas configurações de conferência de áudio](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md).
  
## Redefinir a ID de conferência de reunião

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **a conferência de áudio** e, no painel ação em **ID de conferência**, clique em **Redefinir**.
    
4. No **Redefinir o ID de conferência?** janela, clique em **Sim**. Um ID de conferência será criado automaticamente e um email enviado para o usuário com a nova ID de conferência se enviando emails para seus usuários está habilitado. Ela é ativada por padrão.
    
    > [!IMPORTANT]
    >  Após uma nova ID de conferência é criada, a ID de conferência antigo não pode ser usada por chamadores. Você deve notificar os usuários reagendar seus convites para garantir que a conferência nova que identificação é adicionada aos convites de reunião existente. Os usuários podem usar o Skype for Business ferramenta de migração de reunião para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar o Skype para Business ferramenta de atualização de reunião, consulte:> [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business Online, ferramenta de migração de reuniões (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business Online, a ferramenta de migração de reunião (32 bits)](https://go.microsoft.com/fwlink/?LinkID=626046)
  
Veja [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).
  
## Redefinir o PIN de um organizador da conferência

Identificações estáticas são usadas quando as pessoas em sua organização não desejam se lembrar de um número aleatório; ele poderá selecionar um determinado número ou use uma que seja fácil de lembrar. Quando IDs de conferência dinâmicos forem usados, cada reunião que um cronogramas do usuário serão obter atribuída uma ID de conferência exclusivo. Se você quiser atribuir dinâmico em vez de conferência estático IDs, [Usando IDs de dinâmico de conferência de áudio em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Embora um ID de conferência estático será automaticamente criada e atribuída a um usuário, pode haver ocasiões quando um usuário não quer usar este e desejar defini-lo para um determinado número ou seus usuários não lembra ou tem perdido sua ID de conferência. Você pode usar o Skype para o Centro de administração de negócios e o Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários** e, em seguida, selecione o usuário que você deseja redefinir o PIN.
    
4. No painel ação, em **PIN**, clique em **Redefinir**.
    
Os usuários receberão um email com seu PIN quando estão habilitados para conferência de áudio ou quando o PIN é redefinido. Mas se você desativou automaticamente enviando emails, um email de redefinição PIN não será enviado e você precisará enviar manualmente o PIN para o usuário. O PIN só será mostrado uma vez depois que ela foi redefinida. Depois que é exibida logo após sendo redefinido, o PIN não será mostrado mais sobre as propriedades do usuário; em vez disso, * * * serão mostrados.
  
Veja [Redefinir o PIN de conferência de áudio para um usuário](reset-the-audio-conferencing-pin-for-a-user.md).
  
## Enviar um email com informações de conferência de áudio para um usuário

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários** e, em seguida, selecione o usuário que você deseja redefinir o PIN.
    
4. No painel Ação, clique em **Enviar informações da conferência por email**.
    
    > [!NOTE]
    > Quando você fizer isso, a conferência de áudio PIN não é enviada para o usuário. 
  
Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
  
## Definir o número de telefone de conferência de áudio padrão para organizadores de reunião

 **Para definir o número de telefone de conferência de áudio padrão organizadores da reunião quando você estiver ativando um usuário para conferência de áudio**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No painel de navegação esquerdo, vá para **a conferência de áudio** > **usuários**. Selecione o usuário que você deseja habilitar para conferência de áudio.
    
4. No painel ação, em Propriedades do usuário, clique em **Editar**.
    
5. Na página **Propriedades**, em **nome do provedor**, use a lista suspensa para selecionar o provedor de audioconferência.
    
  - Se você selecionar Microsoft como provedor de conferência de áudio, você pode escolher o número de telefone de conferência de áudio padrão na lista.
    
  - Se você selecionar um ACP de terceiros como provedor de audioconferência, você precisará digitar manualmente Tarifada e, se necessário, o número de telefone de chamada gratuita. Esses números de telefone será o número de telefone padrão.
    
    O número de telefone de conferência de áudio padrão de um usuário é o número que é mostrado no convite da reunião quando eles agendarem uma reunião.
    
6. Clique em **Salvar**.
    
Consulte [Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
 **Para definir o número de telefone de conferência de áudio padrão organizadores da reunião após habilitar um usuário para conferência de áudio**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **usuários**, selecione o usuário que você deseja e na página de ação, clique em **Editar**.
    
4. Na página **Propriedades**, em **nome do provedor**, use a lista suspensa para selecionar o provedor de audioconferência.
    
  - Se o usuário usa o Microsoft como provedor de conferência de áudio, você pode escolher o número de telefone de conferência de áudio padrão na lista.
    
  - Se o usuário usa um ACP de terceiros como provedor de audioconferência, você precisará digitar manualmente Tarifada e, se necessário, o número de telefone de chamada gratuita.
    
    O número de telefone de conferência de áudio padrão de um usuário é o número que é mostrado no convite da reunião quando eles agendarem uma reunião.
    
5. Clique em **Salvar**.
    
Consulte [Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
## Definir as configurações de ponte de conferência de áudio

 **Defina a experiência de reunião quando os chamadores ingressar em uma reunião**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Em **experiência de participar da reunião**, selecione as seguintes ações:
    
  - **Habilitar a entrada da reunião e sair notificações para ser ativado** Isso é selecionado por padrão. Se você desmarcar esta caixa de seleção, os usuários que já ingressou na reunião por padrão não serão notificados quando alguém entra ou sai da reunião.
    
    Isso pode ser definido em uma base de reunião por reunião quando um usuário ingressa em uma reunião usando um Skype para Business ou Teams Microsoft aplicativo e eles modificar a configuração de **anunciar quando as pessoas entrarem ou saírem** no menu de reunião do Skype ou Teams Microsoft **Opções** a reunião.
    
  - **Chamadores Ask gravem o nome antes de ingressar na reunião** Isso é selecionado por padrão. Se você desmarcar esta caixa de seleção, os chamadores não serão solicitados a gravarem o nome antes de ingressar em uma reunião.
    
5. Depois de fazer suas alterações, clique em **Salvar**.
    
Consulte [Alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Definir o comprimento do PIN para reuniões**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Em **segurança**, insira o número de dígitos desejado para o PIN na lista **tamanho do PIN** e clique em **Salvar**.
    
    O PIN deve estar entre 4 e 12 dígitos. O padrão é 5.
    
Consulte [Alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Habilitar ou desabilitar o email seja enviado a usuários de áudio**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Na página **configurações de ponte da Microsoft**, marque ou desmarque **Enviar automaticamente os emails para os usuários se alterar suas configurações de conferência de áudio**.
    
4. Clique em **Salvar**.
    
    Você também pode enviar email para o usuário com as configurações de conferência de áudio, indo para as propriedades do usuário audioconferência e clicando em **Enviar informações de conferência via email**.
    
    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.
    
    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
    
## Ver e configurar os idiomas primário e secundários em uma ponte de conferência de áudio

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **a conferência de áudio** e clique em **ponte da Microsoft**.
    
4. Selecione um número de telefone na lista, clique em **definir idiomas** no painel ação e na página **definir idiomas**, clique em usar a lista de **idioma primário** para exibir a lista completa de idiomas aceitos.
    
    Você também pode definir os idiomas primárias e secundários que têm suporte quando você selecionar a Microsoft como provedor de audioconferência. A ordem que você selecionar nas listas é mesma ordem em que idiomas serão apresentados aos chamadores.
    
Consulte [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md).
  
## Consulte números de discagem conferência de áudio

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **ponte da Microsoft**. Aqui, você pode:
    
  - Exiba os números de telefone definidos pelo Office 365 para ser usado para conferência de áudio.
    
  - Exiba a localização e os idiomas primárias e secundários, que serão usados pelo atendedor automático da conferência de áudio.
    
  - Selecione o número de telefone padrão fornecido aos usuários quando eles estão habilitados para conferência de áudio. Entretanto, se o número de telefone padrão da ponte de conferência de áudio mudar, não alterar o número de telefone padrão para usuários existentes.
    
Você pode ir para **a conferência de áudio** > **usuários** e selecione as propriedades do usuário para alterar o padrão de número para um usuário, escolhendo um novo número na lista de números disponíveis em sua organização.
  
Consulte [Ver uma lista de números de conferência de áudio](see-a-list-of-audio-conferencing-numbers.md).
  
## Visualizar uma lista de usuários habilitados

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **usuários**.
    
Consulte [Ver uma lista de usuários habilitados para conferência de áudio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## Quer saber como gerenciar com o Windows PowerShell?

- Há várias configurações que você pode gerenciar no nível da organização usando o Windows PowerShell. Isso facilita aplicar configurações para todos os seus usuários. Aqui estão as configurações de nível de organização:
    
    Para obter mais ajuda sobre cada cmdlet, confira o [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

    O padrão é  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

    O padrão é  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

    O padrão é 5.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

    O padrão é  _$false_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    O padrão é  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

    O padrão é  _$false_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

    O padrão é  _$null_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

    O padrão é  _$null_.
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem várias vantagens em velocidade, simplicidade e produtividade sobre usando somente o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações para vários usuários ao mesmo tempo. Saiba mais sobre estas vantagens nos tópicos a seguir:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    O módulo do Windows PowerShell para Skype for Business Online permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, aceito somente em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft, em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  
## Consulte Também
<a name="MT_Footer"> </a>

#### 

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

