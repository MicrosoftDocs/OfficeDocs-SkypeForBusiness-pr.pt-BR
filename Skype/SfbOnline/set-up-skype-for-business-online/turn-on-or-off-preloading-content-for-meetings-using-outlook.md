---
title: Ativar ou desativar a permissão para que o conteúdo seja pré-carregado para reuniões usando o Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 7a59edb72b72cb42661cdf0e2cb350d7617a47bf
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568897"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Ativar ou desativar a permissão para que o conteúdo seja pré-carregado para reuniões usando o Outlook

Os usuários podem pré-carregar conteúdo, arquivos ou anexos anexados a um convite de reunião do Outlook a uma reunião do Skype for Business Online, mas você pode ativar ou desativar. Ele está ligado por padrão para todas as organizações que estão usando o Skype for Business Online. Veja como [Pré-carregar anexos de uma reunião do Skype for Business](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).
  
> [!NOTE]
> Atualmente, não há cmdlets disponíveis no Skype for Business Online para definir ou exibir valores online para  _MaxContentStorageMB_ e _MaxUploadFileMB_. Eles estão disponíveis apenas para implantações locais. É importante saber que o conteúdo não será carregado em uma reunião se o conteúdo anexado exceder o  _MaxUploadFileSizeMB_ ou se o limite _MaxContentStorageMB_ for atingido.
  
## <a name="to-get-you-started"></a>Para começar

## <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

> [!NOTE]
> O Skype for Business Online Connector atualmente faz parte do módulo mais recente do Teams PowerShell. Se você estiver usando a versão pública mais recente do Teams PowerShell, não será necessário instalar o Conector do Skype for Business Online.
1. Instale o [módulo do Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Abra um prompt Windows PowerShell de comando e execute os seguintes comandos: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="turning-it-on-or-off"></a>Ativar ou desativar o recurso

A capacidade de pré-carregar conteúdo anexado a um convite de reunião do Outlook para reuniões do Skype for Business Online está ativa por padrão, mas talvez seja necessário impedir que os usuários em sua organização pré-carregarem conteúdo em suas reuniões.
  
> [!IMPORTANT]
> Essa configuração só pode ser 1 ou 2016 para toda a sua organização; não é possível a ativar ou desativar para um único usuário. 
  
 **Para desativá-la, abra o Windows PowerShell e faça o seguinte:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Se quiser ativá-la, abra o Windows PowerShell e faça o seguinte:**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos pelos quais você pode querer usar o Windows PowerShell gerenciar o Microsoft 365 ou o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
