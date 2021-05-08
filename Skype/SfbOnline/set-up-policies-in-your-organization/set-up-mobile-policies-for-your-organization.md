---
title: Configurar políticas móveis para sua organização
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Você pode configurar como seus usuários se conectam ao Skype for Business Online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas em seus celulares usando seu número de telefone de trabalho em vez de seu número de telefone celular. As políticas de mobilidade também podem ser usadas para requerer conexões Wi-Fi ao fazer ou receber chamadas.
ms.openlocfilehash: e29a02bddcb9ace29ebd059f8cbc42c5a85c3f12
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240063"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Configurar políticas móveis para sua organização

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Você pode configurar como seus usuários se conectam ao Skype for Business Online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas em seus celulares usando seu número de telefone de trabalho em vez de seu número de telefone celular. As políticas de mobilidade também podem ser usadas para requerer conexões Wi-Fi ao fazer ou receber chamadas.
  
As configurações de política móvel podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsMobilityPolicy** para modificar as configurações de uma política existente.
  
## <a name="set-your-mobile-policies"></a>Definir suas políticas de dispositivos móveis

> [!NOTE]
> Para todas as configurações de política móvel no Skype for Business Online, você deve usar o Windows PowerShell e não pode **usar** o centro de administração do **Skype for Business.** 
  
### <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

> [!NOTE]
> O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.
1. Instale o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra um prompt Windows PowerShell de comando e execute os seguintes comandos: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Se você quiser mais informações sobre como iniciar Windows PowerShell, consulte Conexão para todos os serviços Microsoft 365 ou [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Requerer uma conexão WiFi para vídeo para um usuário

- Para criar uma nova política para essas configurações, execute:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Consulte mais no cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Consulte mais no cmdlet [Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
  Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar a configuração aos seus usuários.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Impedir que um usuário use o app Skype for Business

- Para criar uma nova política para essas configurações, execute:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Consulte mais no cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Para conceder a nova política criada para o Amos Marble, execute:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Consulte mais no cmdlet [Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
  Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar a configuração aos seus usuários.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Impedir que um usuário faça chamadas IP usando um dispositivo móvel

- Para criar uma nova política para essas configurações, execute:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Consulte mais no cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Consulte mais no cmdlet [Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar a configuração aos seus usuários.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Seis motivos pelos quais você pode querer usar Windows PowerShell gerenciar Microsoft 365 ou Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
