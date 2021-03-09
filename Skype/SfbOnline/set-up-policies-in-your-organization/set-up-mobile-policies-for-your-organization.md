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
description: Você pode configurar como seus usuários se conectam ao Skype for Business Online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas no celular usando o número de telefone comercial em vez do número de telefone celular. As políticas de mobilidade também podem ser usadas para requerer conexões Wi-Fi ao fazer ou receber chamadas.
ms.openlocfilehash: 36162c64490edf58bbfac5c7022bebf6f39595ca
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569193"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Configurar políticas móveis para sua organização

Você pode configurar como seus usuários se conectam ao Skype for Business Online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas no celular usando o número de telefone comercial em vez do número de telefone celular. As políticas de mobilidade também podem ser usadas para requerer conexões Wi-Fi ao fazer ou receber chamadas.
  
As configurações de política móvel podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsMobilityPolicy** para modificar as configurações de uma política existente.
  
## <a name="set-your-mobile-policies"></a>Definir suas políticas de dispositivos móveis

> [!NOTE]
> Para todas as configurações de política móvel no Skype for Business Online, você deve usar o Windows PowerShell e não **pode usar** o Centro de administração do Skype **for Business.** 
  
### <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

> [!NOTE]
> O Skype for Business Online Connector atualmente faz parte do módulo mais recente do Teams PowerShell. Se você estiver usando a versão pública mais recente do Teams PowerShell, não será necessário instalar o Conector do Skype for Business Online.
1. Instale o [módulo do Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Abra um prompt Windows PowerShell de comando e execute os seguintes comandos: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Requerer uma conexão WiFi para vídeo para um usuário

- Para criar uma nova política para essas configurações, execute:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Consulte mais no cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Consulte mais no cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
  Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e, em seguida, usar o cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos seus usuários.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Impedir que um usuário use o app Skype for Business

- Para criar uma nova política para essas configurações, execute:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Consulte mais no cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Para conceder a nova política criada para o Amos Marble, execute:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Consulte mais no cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
  Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos seus usuários.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Impedir que um usuário faça chamadas IP usando um dispositivo móvel

- Para criar uma nova política para essas configurações, execute:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Consulte mais no cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Consulte mais no cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e, em seguida, usar o cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos seus usuários.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos pelos quais você pode querer usar o Windows PowerShell gerenciar o Microsoft 365 ou o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 
