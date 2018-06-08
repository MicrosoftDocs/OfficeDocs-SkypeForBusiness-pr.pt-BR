---
title: Gerenciar as configurações de áudio da conferência para minha organização
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulte as etapas para atribuir uma ID de conferência e a licença de conferência discada a um usuário e outras configurações de conferência discada. '
ms.openlocfilehash: 26d80b71344227aeaec7089e2bb9f9a9dfe32ad2
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703664"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>Gerenciar as configurações de áudio da conferência para minha organização

Talvez seja mais fácil para ver todas as configurações de serviços de audioconferência para Skype para Teams da Microsoft em um único local e de negócios. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
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
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar ou desabilitar os e-mails enviados para usuários de serviços de audioconferência

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**. 

3. No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de discagem**.

4. Clique em **Salvar**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**
  
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

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, clique em **Redefinir ID de conferência**.  

4. No **Redefinir ID de conferência?** janela, clique em **Redefinir**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**  

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**e, no painel de ação em **ID da conferência**, clique em **Redefinir**.
    
4. No **Redefinir ID de conferência?** janela, clique em **Sim**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.
    
    > [!IMPORTANT]
    >  [!IMPORTANTE] Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites. Os usuários podem usar o Skype para ferramenta de migração de reunião de negócios para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar o Skype para ferramenta de atualização de reunião de negócios, consulte: [Ferramenta de atualização de reunião para Skype para negócios e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negócios Online, a ferramenta de migração de reunião (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype para Business Online Meeting Ferramenta de migração (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Veja [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

Cada reunião que um usuário agenda será obtido atribuída uma ID de conferência exclusivas. Embora uma ID de conferência será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número ou os usuários não conseguir se lembrar ou tem perdido sua ID de conferência. Você pode usar o Skype para centro de administração de negócios e do Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, clique em **Redefinir PIN**e clique em **Redefinir**. 
  
![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios** 

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários**e, em seguida, selecione o usuário que você deseja redefinir o PIN para.
    
4. No painel de ações, em **PIN**, clique em **Redefinir**.
    
Os usuários receberão um email com o PIN quando elas são habilitadas para conferência de áudio ou quando o PIN ser redefinido. Mas, se você desabilitou automaticamente enviando e-mails, um email de redefinição PIN não será enviado e você terá que enviar manualmente o PIN para o usuário. O PIN será exibido somente uma vez depois de ser redefinido. Depois que ele é exibido depois de ser redefinido, o PIN não será mostrado mais sobre as propriedades de usuário; em vez disso, * * * serão exibidos. 
  
Consulte [Redefinir o PIN de conferência de áudio](reset-the-audio-conferencing-pin.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com informações de conferência de áudio a um usuário

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, clique em **Enviar informações de conferência no email**. 

    > [!NOTE]
    > Quando você fizer isso, os serviços de audioconferência PIN não será enviado ao usuário. 

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**  

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários**e, em seguida, selecione o usuário que você deseja redefinir o PIN para.
    
4. No painel Ação, clique em **Enviar informações da conferência por email**.
    
    > [!NOTE]
    > Quando você fizer isso, os serviços de audioconferência PIN não será enviado ao usuário. 
  
Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>Configuração do telefone convidam números incluídos no

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Ao lado de **Conferência de áudio**, clique em **Editar**.
 
3. No painel de **Conferência de áudio** , você pode definir o **número de Chamada Tarifada** e, se permitido, o **número de chamada gratuito**.

4. Clique em **Salvar**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**  
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No painel de navegação esquerdo, vá para **conferência de áudio** > **usuários**. Selecione o usuário que você deseja habilitar para conferência de áudio.
    
4. No painel de ações, você pode definir o **número de Chamada Tarifada** e, se permitido, o **número de chamada gratuito**.

5. Clique em **Salvar**.
    
Consulte [Definir convidam números incluídos no telefone](set-the-phone-numbers-included-on-invites.md).
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>Escolher configurações de ponte de conferência de áudio

**Definir a experiência da reunião, quando os chamadores ingressem em uma reunião**

 ![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**. 

3. No painel de **configurações de ponte** , habilitar ou desabilitar a **entrada de reunião e sair de notificações**.

    Isso é ativado por padrão. Se você desabilitar essa opção, os usuários que já tenham ingressado na reunião por padrão não serão notificados quando alguém entra ou sai da reunião.

4. Em **tipo de anúncio de entrada/saída**, escolha **tons** ou **nomes ou números de telefone**. 

    Se você escolher **nomes ou números de telefone**, você também pode optar por habilitar ou desabilitar **os chamadores Ask registrar seus nomes antes de ingressar na reunião**. 

1. Clique em **Salvar**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios** 
  
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

 ![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**. 

3. No painel de **configurações de ponte** , insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.

    O PIN deve ter entre 4 e 12 dígitos. O padrão é 5.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios** 
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Em **segurança**, insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.
    
    O PIN deve ter entre 4 e 12 dígitos. O padrão é 5.
    
Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Habilitar ou desabilitar o email que está sendo enviado a usuários de áudio**

 ![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**. 

3. No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.

4. Clique em **Salvar**. 
 
    Você também pode enviar email para o usuário com as configurações de conferência de áudio, indo para propriedades de conferência de áudio do usuário e clicar em **Enviar informações de conferência no email**.
    
    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios** 
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Na página **configurações de ponte da Microsoft** , marque ou desmarque a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.
    
4. Clique em **Salvar**.
    
    Você também pode enviar email para o usuário com as configurações de conferência de áudio, indo para propriedades de conferência de áudio do usuário e clicar em **Enviar informações de conferência via email**.
    
    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.
    
    Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Consulte e defina o principal (padrão) e os idiomas secundários de (alternativos) em uma ponte de conferência de áudio

 ![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Selecione um número de telefone na lista e clique em **Editar**.

3. Escolha os idiomas desejado em **idioma padrão** e **idiomas alternativos (opcionais)**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios** 

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**e, em seguida, clique em **Microsoft ponte**.
    
4. Selecione um número de telefone na lista, clique em **definir idiomas** no painel de ações e na página **conjunto** de idiomas, clique em uso na lista de **idioma principal** para exibir a lista completa dos idiomas com suporte.
    
    Você também pode definir os idiomas principais e secundários que têm suporte quando você seleciona Microsoft como o provedor de serviços de audioconferência. A ordem em que você selecione nas listas é a mesma ordem em que idiomas serão apresentados aos chamadores.
    
Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Consulte serviços de audioconferência discada números

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Selecione um número de telefone na lista e clique em **Editar**. Aqui, você pode:
    
  - Exiba os números de telefone definidos pelo Office 365 a serem usados para conferência de áudio. 
    
  - Exiba o local e o idioma principal, que será usado pelo atendedor automático conferência de áudio.


![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**  

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **ponte da Microsoft**. Aqui, você pode:
    
  - Exiba os números de telefone definidos pelo Office 365 a serem usados para conferência de áudio. 
    
  - Exiba o local e os idiomas principais e secundários, que serão usados pelo atendedor automático conferência de áudio.
    
  - Selecione o número de telefone padrão que será fornecido aos usuários quando eles estão habilitados para conferência de áudio. No entanto, se o número de telefone de ponte de conferência de áudio padrão for alterado, não alterará o número de telefone padrão para usuários existentes.
    
Você pode ir para a **conferência de áudio** > **usuários** e selecione Propriedades do usuário para alterar o padrão de número de um usuário escolhendo um novo número da lista de números que estão disponíveis em sua organização.
  
Consulte [ver uma lista de números de conferência de áudio](see-a-list-of-audio-conferencing-numbers.md).
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) Visualizar uma lista de usuários habilitados

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**> e, em seguida, **os usuários**.
    
Veja [Ver uma lista de usuários habilitados para conferência de áudio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

Existem diversas configurações que podem ser gerenciadas no nível da organização usando o Windows PowerShell. Isso facilita aplicar as configurações para todos os usuários. 
    
Para obter mais ajuda sobre cada cmdlet, consulte [Cmdlets do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=627324).

Aqui estão as configurações de nível de organização: 
 
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


