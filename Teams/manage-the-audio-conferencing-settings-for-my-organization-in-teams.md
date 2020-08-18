---
title: Gerenciar as configurações de conferência de áudio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Consulte as etapas para atribuir uma licença de conferência discada e um ID de conferência a um usuário no Microsoft Teams e várias outras configurações de conferência discada. '
ms.openlocfilehash: 8a01be430e8c3993325c5ef6759e520664a21e55
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788765"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Gerenciar as configurações de Audioconferência de sua organização no Microsoft Teams

Pode ser mais fácil para você visualizar todas as configurações de audioconferência em um só lugar. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Atribui licença de audioconferência

> [!NOTE]
> Não é possível atribuir licenças usando o Teams. Você deve usar o centro de administração do Microsoft 365. Consulte [atribuir licenças de Complementos do Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing). 
  
 **Atribuir uma licença a um usuário**
  
1. Entre no Microsoft 365 com sua conta corporativa ou de estudante.
    
2. Na navegação à esquerda do **centro de administração do Microsoft 365**, vá para usuários ativos do **usuários**  >  **Active users**e selecione o usuário ou os usuários na lista de usuários disponíveis.
    
    > [!NOTE]
    > [!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição. Em seguida, clique em **Editar**, **Próximo** duas vezes, selecione a licença e clique em **Enviar**.  
  
3. No painel Ação em **Licenças de produto**, clique em **Editar**. 
    
4. Na página **Licenças de produto**, ative **Audioconferência** e clique em **Salvar**. Para saber mais sobre licenciamento, consulte [Licenciamento de Complementos do Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).
    
   > [!NOTE]
   > Depois de atribuir a licença, a Microsoft pode não aparecer inicialmente na lista como provedor de audioconferência. Se isso acontecer, desconecte-se do centro de administração ou pressione CTRL + F5 para atualizar a janela do navegador. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar ou desabilitar o envio de e-mails para usuários de audioconferência

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**. 

3. No painel **Configurações de ponte**, habilite ou desabilite **Enviar e-mails aos usuários automaticamente de suas configurações de discagem forem alteradas**.

4. Clique em **Salvar**.

    
**Usar o Windows PowerShell**
  
Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="reset-the-meeting-conference-id"></a>Redefinir a ID de conferência de reunião

![Um ícone mostrando o logotipo do teams ](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.

2. Em **conferência de áudio**, clique em **Redefinir ID de conferência**.  

3. Na janela **Redefinir ID de conferência?** , clique em **Redefinir**. Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado. Está ativado por padrão.

Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva. Embora uma ID de conferência seja criada automaticamente e atribuída a um usuário, pode haver ocasiões em que um usuário não queira usar essa e você deseja defini-la como um número específico ou que seus usuários não se lembram ou perderam a ID de conferência. 

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.

2. Em **conferência de áudio**, clique em **Redefinir PIN**e em **Redefinir**. 
  
Os usuários receberão um email com o PIN quando estiverem habilitados para videoconferência ou quando o PIN for redefinido. Mas se você tiver desabilitado o envio de emails automaticamente, um email de redefinição de PIN não será enviado e você terá que enviar o PIN manualmente para o usuário. O PIN será exibido somente uma vez depois de ser redefinido. Depois que ele é exibido logo após a redefinição, o pino não é mais mostrado nas propriedades do usuário; em vez disso, * * * será mostrado. 
  
Consulte [redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com as informações de conferência de áudio para um usuário

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.

2. Em **conferência de áudio**, clique em **enviar informações de conferência por email**. 

    > [!NOTE]
    > Quando você faz isso, o pino de audioconferência não é enviado para o usuário. 

Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Definir os números de telefone incluídos em convites

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.

2. Ao lado de **conferência de áudio**, clique em **Editar**.
 
3. No painel **conferência de áudio** , você pode definir o **número de chamada tarifada** e, se permitido, o **número de chamada gratuita**.

4. Clique em **Salvar**.
    
Consulte [definir os números de telefone incluídos nos convites](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Escolher configurações de ponte de áudio audioconferência

**Definir a experiência da reunião quando os chamadores entrarem em uma reunião**

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**. 

3. No painel **Configurações da ponte**, ative ou desative **Notificações de entrada/saída de reuniões**.

    Isso é habilitado por padrão. Se você desabilitar essa opção, por padrão, os usuários que já entraram na reunião não serão notificados quando alguém entrar ou sair da reunião.

4. Em **tipo de anúncio de entrada/saída**, escolha **toques** ou **nomes ou números de telefone**. 

    Se você escolher **nomes ou números de telefone**, também poderá optar por habilitar ou desabilitar **o recurso pedir que os chamadores registrem o nome antes de ingressar na reunião**. 
    > [!NOTE]
    > Por padrão, os participantes externos não conseguem ver os números de telefone dos participantes discadas. Se você quiser manter a privacidade desses números de telefone, selecione **Tons** para o **tipo de anúncio de entrada/saída** (isso impede que os números sejam lidos pelas equipes).


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

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Selecione um número de telefone na lista e clique em **Editar**.

3. Escolha os idiomas desejados em **idioma padrão** e **idiomas alternativos (opcional)**.

4. Clique em **Salvar**.


Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Consulte números de discagem de conferência de áudio

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Selecione um número de telefone na lista e clique em **Editar**. Aqui você pode:
    
   - Veja os números de telefone que devem ser usados para videoconferências. 
    
   - Exiba o local e o idioma principal que serão usados pelo atendedor automático de audioconferência.

  
Veja [ver uma lista de números de audioconferência](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
    
## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência de um usuário](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


