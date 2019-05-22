---
title: Alterar as configurações de uma ponte de audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: 'Obtenha as etapas necessárias para alterar as configurações de uma ponte de conferência que é usada para solicitar chamadas e obter nomes e Pins para organizadores da reunião quando eles não estiverem usando o Skype for Business ou aplicativos do Microsoft Teams. '
ms.openlocfilehash: eaccf6b09499c819451aabd4c1785b326f98ac6d
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344865"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Alterar as configurações de uma ponte de audioconferência

Ao configurar a conferência de áudio no Office 365, você receberá números de telefone para seus usuários do que é chamado de ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone. Esses números de telefone são usados quando os chamadores discam para uma reunião. O número de telefone está incluído na parte inferior do convite de reunião do Skype for Business ou do Microsoft Teams.
  
A ponte de conferência atende a uma chamada e solicita o chamador com prompts de voz usando um atendedor automático de reunião e, em seguida, dependendo das suas configurações, ele pode executar notificações, pedir para os chamadores gravarem o nome e controlar as configurações de pino. Os PINs são fornecidos aos organizadores da reunião para permitir que eles iniciem uma reunião quando não estão usando um aplicativo Skype for Business ou Microsoft Teams.

  > [!IMPORTANT]
  > Um PIN só é necessário para o organizador da reunião quando um usuário do Skype for Business ou do aplicativo do Microsoft Teams ainda não iniciou a reunião. Se todos estiverem discando para a reunião, o PIN será necessário para que o organizador da reunião inicie a reunião. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) Usar o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá para **reuniões** > **conferência pontes**. 

2. Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**. 

3. No painel **configurações de ponte** , selecione: 
   - **Notificações de entrada e saída de reunião** Se você desativar esta opção, os usuários que já participaram da reunião não serão notificados quando alguém entrar ou sair da reunião.
    
     Ao ativar as **notificações de entrada e saída de reunião**, você pode selecionar estas opções:
    
   - **Nomes ou números de telefone** Quando os usuários discarem para uma reunião, o número de telefone deles será reproduzido quando ele ingressar.
    
   - **Toques** Quando os usuários discarem para uma reunião, um tom de áudio será reproduzido quando ele ingressar.
      
   - **Pedir para os chamadores gravarem o nome antes de ingressar na reunião** Se você desativar essa opção, os chamadores não serão solicitados a gravarem o nome antes de participarem de uma reunião.

4. Para definir o comprimento do PIN para reuniões, selecione o número de dígitos que você deseja para o pino na lista **comprimento do pino** .

5. Para especificar se deseja enviar emails para seus usuários, habilite ou desabilite **enviar emails automaticamente aos usuários se as alterações de configuração de audioconferência forem alteradas**.
    Veja os [emails enviados automaticamente para os usuários quando as configurações de audioconferência forem alteradas no Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) ou emails [enviados para os usuários quando as configurações forem alteradas no Skype for Business online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obter mais informações.
 
6. Clique em **Salvar**. 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![SFB-logo-30x30. png](media/sfb-logo-30x30.png)  Usar o Centro de administração do Skype for Business

 **Configurar a experiência da reunião quando os chamadores entrarem em uma reunião**
    
1. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para configurações de ponte de **áudio** > da**Microsoft Bridge**.
    
2. Na página **configurações da ponte da Microsoft** , em **experiência de ingresso na reunião**, selecione:
    
   - **Habilitar a ativação de notificações de entrada e saída de reunião** Esta opção é selecionada por padrão. Se você desmarcar a caixa de seleção, os usuários que já ingressaram na reunião não serão notificados quando alguém entrar ou sair da reunião.
    
   - Quando você seleciona **a opção habilitar notificações de entrada e saída de reunião para ser ativada**, você pode selecionar essas opções na lista **tipo de anúncio de entrada/saída** :
    
   - **Nomes ou números de telefone** Quando os usuários discarem para uma reunião, o número de telefone deles será reproduzido quando ele ingressar.
    
   - **Toques** Quando os usuários discarem para uma reunião, um tom de áudio será reproduzido quando ele ingressar.
  
   - **Peça que os chamadores registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão. Se você desmarcar a caixa de seleção, os chamadores não serão solicitados a gravarem o nome antes de participarem de uma reunião.
    
3. Depois de fazer suas alterações, clique em **Salvar**.
    
**Definir o comprimento do PIN para reuniões**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro** > de administração do Microsoft 365**Skype for Business**.
    
3. No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.
    
4. Na página **configurações da ponte da Microsoft** , em **segurança**, insira o número de dígitos que você deseja para o pino na lista **comprimento do PIN** e clique em **salvar**.
    
    > [!IMPORTANT]
    > O PIN deve ter entre 4 e 12 dígitos. 
  
**Selecione se deseja enviar emails para seus usuários**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro** > de administração do Microsoft 365**Skype for Business**.
    
3. No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.
    
4. Na página **configurações da ponte da Microsoft** , marque ou desmarque **enviar emails automaticamente aos usuários se as informações de discagem forem alteradas**e clique em **salvar**.
    
    Veja os [emails enviados automaticamente para os usuários quando as configurações de audioconferência forem alteradas no Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) ou emails [enviados para os usuários quando as configurações forem alteradas no Skype for Business online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obter mais informações.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para poupar tempo ou automatizar esse processo, você pode usar o cmdlet [set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurar a conferência de áudio para o Skype for Business Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
