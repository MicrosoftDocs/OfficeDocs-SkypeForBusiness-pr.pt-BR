---
title: Gerenciar as configurações de audioconferência para a minha organização no Microsoft Teams
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulte as etapas para atribuir uma licença de conferência discada e um ID de conferência a um usuário no Microsoft Teams e várias outras configurações de conferência discada. '
ms.openlocfilehash: 7af89da74b0b83872954444a847d40f0d7851087
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884701"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>Gerenciar as configurações de audioconferência para a minha organização no Microsoft Teams

Pode ser mais fácil para você visualizar todas as configurações de audioconferência em um só lugar. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Atribui licença de audioconferência

> [!NOTE]
> Não é possível atribuir licenças usando o Teams. É necessário usar o centro de administração do Office 365. Consulte [Atribuir licenças do Skype for Business e do Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). 
  
 **Atribuir uma licença a um usuário**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. No painel de navegação esquerdo do **centro de administração do Office 365**, vá para **Usuários** > **Usuários ativos**, e selecione o usuário ou os usuários na lista de usuários disponíveis.
    
    > [!NOTE]
    > [!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição. Em seguida, clique em **Editar**, **Próximo** duas vezes, selecione a licença e clique em **Enviar**.  
  
3. No painel Ação em **Licenças de produto**, clique em **Editar**. 
    
4. Na página **Licenças de produto**, ative **Audioconferência** e clique em **Salvar**. Para obter mais informações sobre licenças, consulte [Licenciamento de complementos do Skype for Business e do Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
> [!NOTE]
> Depois de atribuir a licença, a Microsoft pode não aparecer inicialmente na lista como provedor de audioconferência. Caso isso aconteça, saia do centro de administração do Office 365 ou pressione CTRL+F5 para atualizar a janela do navegador. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar ou desabilitar o envio de e-mails para usuários de audioconferência

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**. 

3. No painel **Configurações de ponte**, habilite ou desabilite **Enviar e-mails aos usuários automaticamente de suas configurações de discagem forem alteradas**.

4. Clique em **Salvar**.

    
**Usar o Windows PowerShell**
  
Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Alterar as informações de contato do remetente das mensagens de e-mail enviadas aos usuários

É possível fazer alterações nos e-mails enviados automaticamente para seus usuários, incluindo o endereço de e-mail real e o nome de exibição das informações de contato do remetente. Por padrão, o remetente dos e-mails é o Office 365, mas é possível alterar o endereço de e-mail e o nome exibido com o Windows PowerShell. Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="reset-the-meeting-conference-id"></a>Redefinir o ID de conferência de reunião

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Em **Audio conferência**, clique em **Redefinir ID de conferência**.  

4. Na janela **Redefinir ID de conferência?**, clique em **Redefinir**. Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado. Está ativado por padrão.

Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

Cada reunião agendada por um usuário terá um ID de conferência exclusivo atribuído. Embora um ID de conferência seja automaticamente criado e atribuído a um usuário, pode haver ocasiões em que um usuário não queira usá-lo e você deseja configurá-lo para um certo número, ou os usuários não conseguem lembrar ou perderam o ID de conferência. 

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Em **Audioconferência**, clique em **Redefinir PIN**, e então clique em **Redefinir**. 
  
    
Os usuários receberão um e-mail com o PIN quando forem habilitados para audioconferência ou quando o PIN for redefinido. Entretanto, se você tiver desabilitado o envio automático de e-mails, o e-mail de redefinição de PIN não será enviado para o usuário e você precisará enviar o PIN manualmente. O PIN será exibido somente uma vez depois de ser redefinido. Depois se ser exibido após a redefinição, o PIN não será mais mostrado nas propriedades do usuário e aparecerá como *****. 
  
Veja [Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um e-mail com as informações da audioconferência para um usuário

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Em **Audioconferência**, clique em **Enviar informações da conferência por e-mail**. 

    > [!NOTE]
    > Ao fazer isso, o PIN da audioconferência não é enviado ao usuário. 

  
Consulte [Enviar um e-mail para um usuário com suas informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>Definir os números de telefone incluídos em convites

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Próximo a **Audioconferência**, clique em **Editar**.
 
3. No painel **Audioconferência**, é possível definir o **Número tarifado** e, se permitido, o **Número gratuito**.

4. Clique em **Salvar**.
    
Consulte [Definir os números de telefone incluídos em convites](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>Escolher as configurações de ponte de audioconferência

**Definir a experiência da reunião quando os chamadores entram**


1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**. 

3. No painel **Configurações da ponte**, ative ou desative **Notificações de entrada/saída de reuniões**.

    Isso está ativado por padrão. Se você desativar essa opção, por padrão, os usuários que já entraram na reunião não serão notificados quando alguém entrar ou sair da reunião.

4. Em **Tipo de anúncio de entrada/saída**, escolha **Tons** ou **Nomes ou números de telefone**. 

    Se escolher **Nomes ou números de telefone**, também será possível optar por ativar ou desativar **Solicitar que os chamadores gravem seu nome antes de entrar na reunião**. 

5. Clique em **Salvar**.

    
Consulte [Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Definir o tamanho do PIN para reuniões**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**. 

3. No painel **Configurações da ponte**, insira o número de dígitos que deseja para o PIN na lista **Tamanho do PIN** e clique em **Salvar**.

    O PIN deve ter entre 4 e 12 dígitos. O padrão é 5.

    
Consulte [Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Habilitar ou desabilitar o envio de e-mails para usuários de áudio**


1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**. 

3. No painel **Configurações da ponte**, ative ou desative **Enviar e-mails automaticamente aos usuários se suas configurações de audioconferência forem alteradas**.

4. Clique em **Salvar**. 
 
    Você também pode enviar e-mails para o usuário com as configurações da audioconferência acessando as propriedades de audioconferência do usuário clicando em **Enviar informações da conferência por e-mail**.
    
    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.

Consulte [Enviar um e-mail para um usuário com suas informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Visualizar e definir os idiomas primário (padrão) e secundários (alternativos) para uma ponte de audioconferência

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Selecione um número de telefone na lista e clique em **Editar**.

3. Escolha os idiomas desejados em **Idioma padrão** e **Idiomas alternativos (opcional)**.


Consulte [Definir idiomas do atendedor automático para audioconferência](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Visualizar os números de discagem de audioconferência


1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Selecione um número de telefone na lista e clique em **Editar**. Aqui, você pode:
    
  - Visualizar os números de telefone definidos pelo Office 365 para serem usados para audioconferência. 
    
  - Visualizar a localização e o idioma primário que serão usados pelo atendedor automático da audioconferência.

  
Consulte [Ver uma lista de números de Audioconferência](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
    
## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência de um usuário](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


