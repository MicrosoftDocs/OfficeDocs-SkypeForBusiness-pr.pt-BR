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
ms.openlocfilehash: 212491b6a21cb2586237bc3ba8d5bf48382e23d888af044f40908b73ff0fbc9c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304613"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Ativar ou desativar a permissão para que o conteúdo seja pré-carregado para reuniões usando o Outlook

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Os usuários podem pré-carregar conteúdo, arquivos ou anexos anexados a um convite de reunião Outlook a uma reunião do Skype for Business Online, mas você pode acoplá-lo ou desativar. Ele está ligado por padrão para todas as organizações que estão usando Skype for Business Online. Veja como [Pré-carregar anexos de uma reunião do Skype for Business](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).
  
> [!NOTE]
> Atualmente, não há cmdlets disponíveis no Skype for Business Online para definir ou exibir valores online para _MaxContentStorageMB_ e _MaxUploadFileMB_. Eles estão disponíveis apenas para implantações locais. É importante saber que o conteúdo não será carregado em uma reunião se o conteúdo anexado exceder o  _MaxUploadFileSizeMB_ ou se o limite _MaxContentStorageMB_ for atingido.
  
## <a name="to-get-you-started"></a>Para começar

## <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

> [!NOTE]
> O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.
1. Instale o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra um prompt Windows PowerShell de comando e execute os seguintes comandos: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

Se você quiser mais informações sobre como iniciar Windows PowerShell, consulte Conexão para todos os serviços Microsoft 365 ou [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="turning-it-on-or-off"></a>Ativar ou desativar o recurso

A capacidade de pré-carregar conteúdo anexado a um convite de reunião Outlook reuniões do Skype for Business Online está ativa por padrão, mas talvez seja necessário impedir que os usuários em sua organização pré-carregarem conteúdo em suas reuniões.
  
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

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Seis motivos pelos quais você pode querer usar Windows PowerShell gerenciar Microsoft 365 ou Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)

  
