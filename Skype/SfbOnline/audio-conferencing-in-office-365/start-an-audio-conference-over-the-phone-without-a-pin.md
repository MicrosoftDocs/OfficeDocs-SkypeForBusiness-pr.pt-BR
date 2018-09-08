---
title: Iniciar uma audioconferência por telefone sem um PIN no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprender a habilitar ou desabilitar chamadores anônimos para ingressar em uma reunião a partir do centro de administração Skype for Business ou usando um script do PowerShell. '
ms.openlocfilehash: a87fe66eca889e7424ed34376dbf499f8bbfef81
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885157"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Iniciar uma audioconferência por telefone sem um PIN no Skype for Business Online

> [!Note]
> Para obter informações sobre como iniciar uma audioconferência de áudio sem um PIN no Microsoft Teams, consulte [Iniciar uma audioconferência de áudio por telefone sem um PIN no Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Talvez seja frustrante para usuários que discam para uma reunião para ser mantidos no lobby da reunião escutando música porque o Skype para o organizador da reunião de negócios não tiver iniciado a reunião. 
  
Se o organizador da reunião chama reunião, por padrão, é necessário um PIN para iniciar uma reunião. Você pode montá-lo para que qualquer pessoa pode discar para uma reunião e não ser solicitado a fornecer um PIN para iniciar a reunião. Você pode usar o Centro de administração do Skype for Business para habilitar ou desabilitar essa configuração para um único usuário.
  
Um PIN não é necessário para o organizador da reunião, se alguém tiver iniciado a reunião a partir do Skype para o aplicativo de negócios. É necessário inserir um PIN somente quando o organizador da reunião participa da reunião por telefone. O PIN para reuniões é enviado ao usuário áudio quando eles recebem a licença de **Serviços de audioconferência** e estão habilitados para conferência de áudio. Consulte [Enviar um email a um usuário com as informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md) e [Emails que são enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar ou desabilitar chamadores anônimos para participar de uma reunião
    
1. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**. 
    
2. Na lista, selecione o usuário e no painel de ações, clique em **Editar**. 
    
3. Na página de propriedades do usuário, em **Opções de reunião**, marque ou desmarque **chamadores de permitir não autenticado para ser as primeira pessoas em uma reunião. Se não, em seguida, eles aguardará no lobby até que um usuário autenticado**.
    
4. Clique em **Salvar**. 


    
 **Usando o Windows Powershell**
  
- Execute o seguinte: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Se você deseja redefinir o PIN, consulte [Redefinir o PIN de conferência de áudio](reset-the-audio-conferencing-pin.md).
    
- Se o acesso anônimo ou não exigir um PIN iniciar uma reunião, estiver habilitado:
    
  - Se a reunião ainda não iniciado (há ninguém na reunião ainda): um chamador será solicitado se ele for o organizador; Se ele diz Sim, ele será solicitado para seu PIN e depois que ele insere o PIN, iniciará a reunião e o usuário será ingressar na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a um chamador se ele é o organizador e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e o chamador ingressará.
    
- Se o acesso anônimo ou não exigir um PIN iniciar uma reunião, está desativado:
    
  - Se a reunião ainda não iniciou (não há ninguém na reunião ainda): Não será perguntado a uma chamadora se ela é a organizadora e nunca lhe será solicitado o PIN. Como a configuração do organizador é definida como desativado, a reunião será iniciada e os chamadores anônimos serão ingressar na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a uma chamadora se ele é a organizadora e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e a chamadora ingressará.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo e automatizar a tarefa para mais de um usuário, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
-  No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. No Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar o trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
