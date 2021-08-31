---
title: Gerenciar configurações de Audioconferência
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
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Consulte Microsoft Teams para atribuir uma licença de conferência discada e uma ID de conferência a um usuário e muitas outras configurações de conferência discada. '
ms.openlocfilehash: df2dc849424eed7b6c72cf4a63496a73deb53035
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731350"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Gerenciar as Configurações de audioconferência da sua organização no Microsoft Teams

Pode ser mais fácil para você ver todas as configurações de audioconferência para Microsoft Teams em um só lugar. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Atribuir uma licença de Audioconferência

> [!NOTE]
> Não é possível atribuir licenças usando Teams. Você deve usar o Centro de administração do Microsoft 365. Consulte [Atribuir Microsoft Teams licenças de complemento.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 
  
 **Para atribuir uma licença para um usuário**
  
1. Entre no Microsoft 365 com sua conta de trabalho ou de estudante.
    
2. Na navegação à esquerda do **Centro de administração do Microsoft 365,** vá para **Usuários**  >  **Usuários ativos e** selecione o usuário ou os usuários na lista de usuários disponíveis.
    
    > [!NOTE]
    > [!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição. Em seguida, **clique** em Editar , **Em** seguida, selecione a licença e clique em **Enviar**.  
  
3. No painel Ação em **Licenças de**, clique em **Editar**. 
    
4. Na página **Licenças de produtos**, ligue a **Audioconferência** e em seguida clique em **Salvar**. Para obter mais informações sobre licenciamento, [consulte Microsoft Teams licenciamento de complemento.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
   > [!NOTE]
   > Depois de atribuir a licença, a Microsoft pode não aparecer inicialmente na lista como um provedor de audioconferência. Se isso acontecer, saia do centro de administração ou pressione CTRL+F5 para atualizar a janela do navegador. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar ou desabilitar emails enviados para usuários de audioconferência

![Um ícone mostrando o logotipo Microsoft Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de Conferência,** clique em **Configurações de ponte.** 

3. No painel **Configurações de** ponte, habilita ou desabilita Enviar emails automaticamente aos usuários se suas configurações de **discagem mudarem**.

4. Clique em **Salvar**.

    
**Usando Windows PowerShell**
  
Consulte a [Microsoft Teams referência do PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="reset-the-meeting-conference-id"></a>Redefinir a ID de conferência de reunião

![Um ícone mostrando o logotipo Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Em **Audioconferência,** clique **em Redefinir a ID da conferência.**  

3. Na janela **Redefinir iD** da conferência? clique em **Redefinir**. Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado. Está ativado por padrão.

Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Redefinir o PIN de um organizador da conferência

Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva. Embora uma ID de conferência seja criada e atribuída automaticamente a um usuário, pode haver momentos em que um usuário não deseja usá-lo e você deseja defini-lo como um determinado número, ou seus usuários não podem se lembrar ou perder a ID da conferência. 

![Um ícone mostrando o logotipo Microsoft Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Em **Audioconferência,** clique em **Redefinir PIN** e clique em **Redefinir**. 
  
Os usuários receberão um email com seu PIN quando eles estão habilitados para audioconferência ou quando o PIN é redefinido. Mas se você tiver desabilitado o envio automático de emails, um email de redefinição de PIN não será enviado e você terá que enviar manualmente o PIN para o usuário. O PIN será exibido somente uma vez depois de ser redefinido. Depois que ele é exibido logo após ser redefinido, o PIN não será mais mostrado nas propriedades do usuário; em vez disso, ***** será mostrado. 
  
Consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar um email com informações de Audioconferência para um usuário

![Um ícone mostrando o logotipo Microsoft Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Em **Audioconferência,** clique **em Enviar informações de conferência no email**. 

    > [!NOTE]
    > Quando você faz isso, o PIN de audioconferência não é enviado ao usuário. 

Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Definir os números de telefone incluídos em convites

![Um ícone mostrando o logotipo Microsoft Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Ao lado **de Audioconferência,** clique em **Editar**.
 
3. No painel **Audioconferência,** você pode definir o número de toll **e,** se permitido, o **número gratuito**.

4. Clique em **Salvar**.
    
Consulte [Definir os números de telefone incluídos em convites](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Escolher configurações de ponte de audioconferência

**Definir a experiência de reunião quando os chamadores ingressarem em uma reunião**

![Um ícone mostrando o logotipo Microsoft Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de Conferência,** clique em **Configurações de ponte.** 

3. No painel **Configurações da ponte**, ative ou desative **Notificações de entrada/saída de reuniões**.

    Isso é habilitado por padrão. Se você desabilitar essa opção, os usuários que já ingressaram na reunião por padrão não serão notificados quando alguém entrar ou sair da reunião.

4. Em **Tipo de comunicado de entrada/saída,** escolha **Tons** ou Nomes ou números **de telefone**. 

    Se você escolher **Nomes ou** números de telefone, também poderá optar por habilitar ou desabilitar Solicitar que os chamadores gravem seus nomes antes de ingressar **na reunião**. 
    > [!NOTE]
    > Por padrão, os participantes externos não podem ver os números de telefone de participantes discados. Se você quiser manter a privacidade desses números de telefone, selecione **Tons** para o **tipo de anúncio de entrada/saída** (isso impede que os números sejam lidos pelas equipes).


5. Clique em **Salvar**.

    
Consulte [Alterar as configurações de uma ponte de Audioconferência.](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **Definir o tamanho do PIN para reuniões**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de Conferência,** clique em **Configurações de ponte.** 

3. No painel **Configurações de** ponte, insira o número de dígitos que você deseja para o PIN na lista de comprimento **do PIN** e clique em **Salvar**.

    O PIN deve ter entre 4 e 12 dígitos. O padrão é 5.

    
Consulte [Alterar as configurações de uma ponte de Audioconferência.](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **Habilitar ou desabilitar o envio de emails para usuários de áudio**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de Conferência,** clique em **Configurações de ponte.** 

3. No painel **Configurações de** ponte, habilita ou desabilita Enviar emails automaticamente aos usuários se suas configurações de **audioconferência mudarem**.

4. Clique em **Salvar**. 
 
    Você também pode enviar emails para o usuário com as configurações de audioconferência, indo para as propriedades de audioconferência do usuário e clicando em Enviar informações de conferência **no email**.
    
    Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.

Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Consulte e defina os idiomas principal (padrão) e secundário (alternativo) em uma ponte de audioconferência

![Um ícone mostrando o logotipo Microsoft Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Selecione um número de telefone na lista e clique em **Editar**.

3. Escolha os idiomas que você deseja em **Idioma padrão** e **idiomas alternativos (opcional)**.

4. Clique em **Salvar**.


Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Consulte números de discagem de audioconferência

![Um ícone mostrando o logotipo Microsoft Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Selecione um número de telefone na lista e clique em **Editar**. Aqui você pode:
    
   - Exibir os números de telefone que devem ser usados para Audioconferência. 
    
   - Exibir o local e o idioma principal que será usado pelo assistente automático de Audioconferência.

  
Consulte [Ver uma lista de números de Audioconferência](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
    
## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar as configurações de audioconferência de um usuário](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)