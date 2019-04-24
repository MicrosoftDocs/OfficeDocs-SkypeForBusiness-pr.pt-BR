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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: 'Obtenha as etapas que necessárias para alterar configurações para uma ponte de conferência que é usado para solicitar que os chamadores e coletar nomes e pins para organizadores de reunião, quando eles não estão usando Skype para aplicativos de negócios ou Teams da Microsoft. '
ms.openlocfilehash: 2f3f08254409086ee99b3c5f60d243f893fff4e6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198546"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Alterar as configurações de uma ponte de audioconferência

Quando você estiver configurando a conferência de áudio no Office 365, você receberá os números de telefone para seus usuários a partir o que é acionado uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone. Esses números de telefone são usados quando os chamadores discam para uma reunião. O número de telefone está incluído na parte inferior do Skype para o convite de reunião de negócios ou Teams da Microsoft.
  
A ponte de conferência atende uma chamada e solicita que o chamador com os prompts de voz usando um automático de reunião attendant e em seguida, dependendo das suas configurações, ele pode reproduzir notificações, será feita aos chamadores registrar seus nomes e controlar as configurações de PIN. PINs são fornecidas aos organizadores de reuniões para permitir que eles para iniciar uma reunião quando forem não estiver usando um Skype para aplicativo de negócios ou Teams da Microsoft.

  > [!IMPORTANT]
  > Um PIN só é necessário para o organizador da reunião quando um Skype para o usuário de aplicativo de negócios ou Microsoft Teams já não tiver iniciado a reunião. Se todos estiver discando para a reunião, o PIN é necessário para o organizador da reunião iniciar a reunião. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) Usando o Centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá para **reuniões** > **pontes de conferência**. 

2. Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**. 

3. No painel de **configurações de ponte** , selecione: 
   - **Entrada de reunião e sair notificações** Se você desativar esse recurso, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.
    
     Quando você ativa **as notificações de entrada e saída de reunião**, você pode selecionar estas opções:
    
   - **Nomes ou números de telefone** Quando os usuários discam para uma reunião, seu número de telefone será reproduzido quando eles entrarem-lo.
    
   - **Toques** Quando os usuários discam para uma reunião, um tom de áudio será reproduzido quando eles entrarem-lo.
      
   - **Chamadores Ask registrar seus nomes antes de ingressar na reunião** Se você desativar esse recurso, os chamadores não solicitados registrar seus nomes antes de ingressar em uma reunião.

4. Para definir o tamanho PIN para reuniões, selecione o número de dígitos que você deseja para o PIN na lista **tamanho PIN** .

5. Para especificar se deseja enviar email para seus usuários, habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se altera sua configuração de serviços de audioconferência**.
    Para obter mais informações, consulte [Emails enviados automaticamente para os usuários quando suas configurações de conferência de áudio alterar em equipes da Microsoft](emails-sent-to-users-when-their-settings-change-in-teams.md) ou [Emails enviados para os usuários quando suas configurações de alteração nos Skype para negócios Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .
 
6. Clique em **Salvar**. 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png)  Usar o Centro de administração do Skype for Business

 **Configurar a experiência da reunião, quando os chamadores ingressem em uma reunião**
    
1. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
2. Na página **configurações de ponte da Microsoft** , em que a **experiência de participação da reunião**, selecione:
    
   - **Habilitar a ativação de notificações de entrada e saída de reunião** Esta opção é selecionada por padrão. Se você desmarcar a caixa de seleção, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.
    
   - Quando você seleciona **Ativar entrada de reunião e sair notificações para ser ativado**, você pode selecionar essas opções na lista **tipo de anúncio de entrada/saída** :
    
   - **Nomes ou números de telefone** Quando os usuários discam para uma reunião, seu número de telefone será reproduzido quando eles entrarem-lo.
    
   - **Toques** Quando os usuários discam para uma reunião, um tom de áudio será reproduzido quando eles entrarem-lo.
  
   - **Peça que os chamadores registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão. Se você desmarcar a caixa de seleção, os chamadores não solicitados registrar seus nomes antes de ingressar em uma reunião.
    
3. Depois de fazer suas alterações, clique em **Salvar**.
    
**Definir o tamanho PIN para reuniões**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Na página **configurações de ponte da Microsoft** , em **segurança**, insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.
    
    > [!IMPORTANT]
    > O PIN deve ter entre 4 e 12 dígitos. 
  
**Selecione se deseja enviar o email para seus usuários**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Na página **configurações de ponte da Microsoft** , marque ou desmarque **Enviar automaticamente os e-mails para os usuários se altera suas informações de discagem**e, em seguida, clique em **Salvar**.
    
    Para obter mais informações, consulte [Emails enviados automaticamente para os usuários quando suas configurações de conferência de áudio alterar em equipes da Microsoft](emails-sent-to-users-when-their-settings-change-in-teams.md) ou [Emails enviados para os usuários quando suas configurações de alteração nos Skype para negócios Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar esse processo, você pode usar o cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configure a conferência de áudio para Skype para Business Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
