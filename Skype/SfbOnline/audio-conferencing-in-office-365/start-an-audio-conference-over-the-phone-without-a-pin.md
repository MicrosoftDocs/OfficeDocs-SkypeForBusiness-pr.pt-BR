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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Aprender a habilitar ou desabilitar chamadores anônimos para ingressar em uma reunião a partir do centro de administração Skype for Business ou usando um script do PowerShell. '
ms.openlocfilehash: d420acff8d5822aa4badd8980481d67bd2eae35b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013365"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Iniciar uma audioconferência por telefone sem um PIN no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Para obter informações sobre como iniciar uma audioconferência de áudio sem um PIN no Microsoft Teams, consulte [Iniciar uma audioconferência de áudio por telefone sem um PIN no Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Pode ser frustrante para os usuários que discam para uma reunião ser realizada no lobby da reunião ouvindo música porque o organizador da reunião Skype for Business não iniciou a reunião. 
  
Se um organizador da reunião chamar a reunião, por padrão, um PIN será necessário para iniciar uma reunião. Você pode defini-lo para que qualquer pessoa possa discar para uma reunião e não ser solicitado que um PIN inicie a reunião. Você pode usar o Centro de administração do Skype for Business para habilitar ou desabilitar essa configuração para um único usuário.
  
Um PIN não será necessário para o organizador da reunião se alguém tiver iniciado a reunião do aplicativo Skype for Business. É necessário inserir um PIN somente quando o organizador da reunião participa da reunião por telefone. O PIN para reuniões é enviado ao usuário de áudio quando ele recebe a licença de **Audioconferência** e está habilitado para Audioconferência. Consulte Enviar um email para um usuário com suas informações de [Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md) e Emails que são enviados automaticamente aos usuários quando suas configurações de [Audioconferência mudarem.](emails-sent-to-users-when-their-settings-change.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar ou desabilitar chamadores anônimos para participar de uma reunião
    
1. No centro **Skype for Business de** administração , na navegação à esquerda, vá para Usuários **de Audioconferência**  >  . 
    
2. Na lista, selecione o usuário e, no painel Ação, clique em **Editar**. 
    
3. Na página propriedades do usuário, em **Opções** de reunião , selecione ou desembaixe Permitir que chamadores não autenticados sejam as primeiras pessoas **em uma reunião. Caso não seja, eles aguardarão no lobby até que um usuário autenticado insussesse**.
    
4. Clique em **Salvar**. 


    
 **Usando Windows Powershell**
  
- Execute o seguinte: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Se você deseja redefinir o PIN, consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin.md).
    
- Se o acesso anônimo ou não exigir um PIN para iniciar uma reunião, será desabilitado:
    
  - Se a reunião ainda não tiver começado (ainda não há ninguém na reunião): um chamador será solicitado se ele for o organizador; se ele disser que sim, ele será solicitado a solicitar seu PIN e, depois de inserir o PIN, a reunião será iniciar e o usuário ingressará na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a um chamador se ele é o organizador e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e o chamador ingressará.
    
- Se o acesso anônimo ou não exigir um PIN para iniciar uma reunião, será habilitado:
    
  - Se a reunião ainda não iniciou (não há ninguém na reunião ainda): Não será perguntado a uma chamadora se ela é a organizadora e nunca lhe será solicitado o PIN. Como a configuração do organizador está definida como off, a reunião será inicial e os chamadores anônimos ingressarão na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a uma chamadora se ele é a organizadora e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e a chamadora ingressará.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo e automatizar a tarefa para mais de um usuário, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que é suportado apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em Baixar e instalar o módulo [Teams PowerShell](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
