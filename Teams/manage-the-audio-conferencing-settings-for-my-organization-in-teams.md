---
title: Gerenciar as configurações de áudio da conferência para minha organização em Teams da Microsoft
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulte as etapas de Teams da Microsoft para atribuir uma ID de conferência e a licença de conferência discada a um usuário e outras configurações de conferência discada. '
ms.openlocfilehash: 2e372c76cbbedeaa7558b4308366262e93cb5b91
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780368"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>Gerenciar as configurações de áudio da conferência para minha organização em Teams da Microsoft

Talvez seja mais fácil para ver todas as configurações de serviços de audioconferência for Microsoft Teams em um único local. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Atribuir uma licença de Audioconferência

> [!NOTE]
> Não é possível atribuir licenças usando equipes. Você deve usar o Centro de administração do Office 365. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). 
  
 **Para atribuir uma licença para um usuário**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. No painel de navegação à esquerda do **Centro de administração do Office 365**, vá para **usuários** > **usuários ativos**e selecione o usuário ou usuários da lista de usuários disponíveis.
    
    > [!NOTE]
    > [!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição. Em seguida, clique em **Editar**, **próximo** duas vezes e em seguida, selecione a licença e clique em **Enviar**.  
  
3. No painel Ação em **Licenças de**, clique em **Editar**. 
    
4. Na página **Licenças de produtos**, ligue a **Audioconferência** e em seguida clique em **Salvar**. Para obter mais informações sobre licenciamento, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
> [!NOTE]
> Após atribuir a licença, Microsoft talvez não sejam exibidos inicialmente na lista como um provedor de serviços de audioconferência. Caso isso aconteça, saia do Centro de administração do Office 365 ou pressione CTRL+F5 para atualizar a janela do navegador. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar ou desabilitar os e-mails enviados para usuários de serviços de audioconferência

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**. 

3. No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de discagem**.

4. Clique em **Salvar**.

    
**Usando o Windows PowerShell**
  
Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Alterar as informações de contato do remetente nas mensagens de email enviadas aos usuários

Você pode fazer alterações para email que será enviado automaticamente aos seus usuários, incluindo o endereço de email real e o nome para exibição de informações de contato do remetente. Por padrão, o remetente dos emails é o Office 365, mas você pode alterar o endereço de email e usando o Windows PowerShell de nome de exibição. Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="reset-the-meeting-conference-id"></a>Redefinir a ID de conferência de reunião

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, clique em **Redefinir ID de conferência**.  

4. No **Redefinir ID de conferência?** janela, clique em **Redefinir**. Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado. Está ativado por padrão.

Veja [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

Cada reunião que um usuário agenda será obtido atribuída uma ID de conferência exclusivas. Embora uma ID de conferência será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número ou os usuários não conseguir se lembrar ou tem perdido sua ID de conferência. 

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, clique em **Redefinir PIN**e clique em **Redefinir**. 
  
    
Os usuários receberão um email com o PIN quando elas são habilitadas para conferência de áudio ou quando o PIN ser redefinido. Mas, se você desabilitou automaticamente enviando e-mails, um email de redefinição PIN não será enviado e você terá que enviar manualmente o PIN para o usuário. O PIN será exibido somente uma vez depois de ser redefinido. Depois que ele é exibido depois de ser redefinido, o PIN não será mostrado mais sobre as propriedades de usuário; em vez disso, * * * serão exibidos. 
  
Consulte [Redefinir o PIN de conferência de áudio](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com informações de conferência de áudio a um usuário

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Em **Conferência de áudio**, clique em **Enviar informações de conferência no email**. 

    > [!NOTE]
    > Quando você fizer isso, os serviços de audioconferência PIN não será enviado ao usuário. 

  
Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>Configuração do telefone convidam números incluídos no

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Ao lado de **Conferência de áudio**, clique em **Editar**.
 
3. No painel de **Conferência de áudio** , você pode definir o **número de Chamada Tarifada** e, se permitido, o **número de chamada gratuito**.

4. Clique em **Salvar**.
    
Consulte [Definir convidam números incluídos no telefone](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>Escolher as configurações de ponte de audioconferência

**Definir a experiência da reunião, quando os chamadores ingressem em uma reunião**


1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**. 

3. No painel de **configurações de ponte** , habilitar ou desabilitar a **entrada de reunião e sair de notificações**.

    Isso é ativado por padrão. Se você desabilitar essa opção, os usuários que já tenham ingressado na reunião por padrão não serão notificados quando alguém entra ou sai da reunião.

4. Em **tipo de anúncio de entrada/saída**, escolha **tons** ou **nomes ou números de telefone**. 

    Se você escolher **nomes ou números de telefone**, você também pode optar por habilitar ou desabilitar **os chamadores Ask registrar seus nomes antes de ingressar na reunião**. 

5. Clique em **Salvar**.

    
Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Definir o tamanho PIN para reuniões**

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**. 

3. No painel de **configurações de ponte** , insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.

    O PIN deve ter entre 4 e 12 dígitos. O padrão é 5.

    
Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Habilitar ou desabilitar o email que está sendo enviado a usuários de áudio**


1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**. 

3. No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.

4. Clique em **Salvar**. 
 
    Você também pode enviar email para o usuário com as configurações de conferência de áudio, indo para propriedades de conferência de áudio do usuário e clicar em **Enviar informações de conferência no email**.
    
    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.

Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Consulte e defina o principal (padrão) e os idiomas secundários de (alternativos) em uma ponte de conferência de áudio

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Selecione um número de telefone na lista e clique em **Editar**.

3. Escolha os idiomas desejado em **idioma padrão** e **idiomas alternativos (opcionais)**.


Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Consulte serviços de audioconferência discada números


1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Selecione um número de telefone na lista e clique em **Editar**. Aqui, você pode:
    
  - Exiba os números de telefone definidos pelo Office 365 a serem usados para conferência de áudio. 
    
  - Exiba o local e o idioma principal, que será usado pelo atendedor automático conferência de áudio.

  
Consulte [ver uma lista de números de conferência de áudio](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/en-us/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
    
## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência de um usuário](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


