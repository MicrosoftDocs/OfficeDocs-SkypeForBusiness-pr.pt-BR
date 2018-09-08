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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprender a habilitar ou desabilitar chamadores anônimos para ingressar em uma reunião a partir do centro de administração Skype for Business ou usando um script do PowerShell. '
ms.openlocfilehash: 746e21b7b1a8d15c31dfe11e46ac09edfbb29b99
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858701"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Iniciar uma audioconferência por telefone sem um PIN no Skype for Business Online

> [!Note]
> Para obter informações sobre como iniciar uma audioconferência de áudio sem um PIN no Microsoft Teams, consulte [Iniciar uma audioconferência de áudio por telefone sem um PIN no Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Para usuários que discam para uma reunião, pode ser frustrante ficar no lobby da reunião ouvindo música porque o organizador da reunião no Skype for Business não iniciou a reunião. 
  
Por padrão, se o organizador da reunião telefona para a reunião, é necessário um PIN para o início da reunião. Você pode configurar para que qualquer pessoa possa discar para a reunião sem que seja solicitado um PIN para iniciá-la. Você pode usar o centro de administração do Skype for Business para habilitar ou desabilitar essa configuração para um único usuário.
  
Um PIN não é necessário para o organizador da reunião se alguém tiver iniciado a reunião a partir do aplicativo Skype for Business. Um PIN só é necessário quando o organizador da reunião ingressa na reunião por telefone. O PIN para reuniões é enviado aos usuários de áudio quando eles recebem a licença de **Audioconferência** e estão habilitados para Audioconferência. Consulte [Enviar email a um usuário com suas informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md) e [Emails que são enviados automaticamente aos usuários quando eles alteram suas configurações de Audioconferência](emails-sent-to-users-when-their-settings-change.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Ativar ou desativar chamadores anônimos para participar de uma reunião
    
1. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, ir para **Audioconferência** > **Usuários**. 
    
2. Na lista, selecionar o usuário e, no painel Ação, clicar em **Edição**. 
    
3. Na página de propriedades do usuário, em **Opções da reunião**, marcar ou desmarcar **Permitir que chamadores não autenticados sejam as primeiras pessoas em uma reunião. Caso contrário, eles aguardarão no lobby até que um usuário autenticado ingresse**.
    
4. Clicar em **Salvar**. 


    
 **Usando o Windows PowerShell**
  
- Executar o seguinte: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Se você quiser redefinir o PIN, consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin.md).
    
- Se o acesso anônimo ou a não exigência de um PIN para o início de uma reunião estiver ativado:
    
  - Se a reunião ainda não iniciou (não há ninguém na reunião ainda): Será perguntado a um chamador se ele é o organizador; Se ele disser que sim, seu PIN será solicitado e, depois que ele inserir o PIN, a reunião iniciará e o usuário ingressará na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a um chamador se ele é o organizador e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e o chamador ingressará.
    
- Se o acesso anônimo ou a não exigência de um PIN para o início de uma reunião estiver desativado:
    
  - Se a reunião ainda não iniciou (não há ninguém na reunião ainda): Não será perguntado a uma chamadora se ela é a organizadora e nunca lhe será solicitado o PIN. Como a configuração do organizador está definida como desativada, a reunião terá início e os chamadores anônimos poderão ingressar na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a uma chamadora se ele é a organizadora e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e a chamadora ingressará.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo e automatizar a tarefa para mais de um usuário, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
-  No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. No Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar o trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens de velocidade, simplicidade e produtividade em comparação ao uso exclusivo do centro de administração do Office 365, por exemplo quando você realiza alterações de configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
