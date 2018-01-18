---
title: "Alterar as configurações de uma ponte de conferência de áudio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that''s used to prompt callers and gather names and pins for meeting organizers when they''re not using Skype for Business clients. '
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Alterar as configurações de uma ponte de conferência de áudio

Quando você estiver configurando a conferência de áudio no Office 365, você receberá os números de telefone para seus usuários a partir o que é acionado uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone. Esses números de telefone são usados quando os chamadores discam para uma reunião. O número de telefone está incluído na parte inferior do Skype para o convite de reunião de negócios ou Teams da Microsoft.
  
A ponte de conferência atende uma chamada e solicita que o chamador com os prompts de voz usando um automático de reunião attendant e em seguida, dependendo das suas configurações, ele pode reproduzir notificações, será feita aos chamadores registrar seus nomes e controlar as configurações de PIN. PINs são fornecidas aos organizadores de reuniões para permitir que eles para iniciar uma reunião quando forem não estiver usando um Skype para aplicativo de negócios ou Teams da Microsoft.

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Alterar as configurações de uma ponte de conferência de áudio

 **Configurar a experiência da reunião, quando os chamadores ingressem em uma reunião**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Na página **configurações de ponte da Microsoft** , em que a **experiência de participação da reunião**, selecione:
    
  - **Habilitar a entrada da reunião e sair notificações para ser ativado** Isso é selecionado por padrão. Se você desmarcar a caixa de seleção, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.
    
    Quando você seleciona **Ativar entrada de reunião e sair notificações para ser ativado**, você pode selecionar essas opções na lista **tipo de anúncio de entrada/saída** :
    
  - **Nomes ou números de telefone** Quando os usuários discam para uma reunião, seu número de telefone será reproduzido quando eles entrarem-lo.
    
  - **Toques** Quando os usuários discam para uma reunião, um tom de áudio será reproduzido quando eles entrarem-lo.
    
    > [!NOTE]
    > [!OBSERVAçãO] O uso do **Tom** como tipo de comunicado está disponível para todos os clientes de visualização atualmente.
  
  - **Chamadores Ask registrar seus nomes antes de ingressar na reunião** Isso é selecionado por padrão. Se você desmarcar a caixa de seleção, os chamadores não solicitados registrar seus nomes antes de ingressar em uma reunião.
    
5. Depois de fazer suas alterações, clique em **Salvar**.
    
**Definir o tamanho PIN para reuniões**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Na página **configurações de ponte da Microsoft** , em **segurança**, insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.
    
    > [!IMPORTANT]
    > O PIN deve ter entre 4 e 12 dígitos. 
  
**Selecione se deseja enviar o email para seus usuários**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Na página **configurações de ponte da Microsoft** , marque ou desmarque **Enviar automaticamente os e-mails para os usuários se altera sua configuração de conferência de áudio**e clique em **Salvar**.
    
    Para obter mais informações, consulte [Emails enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change.md) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar esse processo, você pode usar o cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Como usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Como usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar a Audioconferência para o Skype for Business e o Microsoft Teams](set-up-audio-conferencing.md)

