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
description: Você pode configurar como seus usuários se conectam ao Skype for Business Online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas no celular usando o número de telefone comercial em vez do número de telefone celular. As políticas de mobilidade também podem ser usadas para exigir Wi-Fi conexões ao fazer ou receber chamadas.
ms.openlocfilehash: 5094a536a636300ea70a7d358e24ee5c0f511379
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814740"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Configurar políticas móveis para sua organização

Você pode configurar como seus usuários se conectam ao Skype for Business Online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas no celular usando o número de telefone comercial em vez do número de telefone celular. As políticas de mobilidade também podem ser usadas para exigir Wi-Fi conexões ao fazer ou receber chamadas.
  
As configurações de política móvel podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsMobilityPolicy** para modificar as configurações de uma política existente.
  
## <a name="set-your-mobile-policies"></a>Definir suas políticas de dispositivos móveis

> [!NOTE]
> Para todas as configurações de política móvel no Skype for Business Online, você deve usar o Windows PowerShell e não pode **usar** o Centro de **administração do Skype for Business.** 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
    1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
        
    2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
        
    3. Se você não tiver a versão 3.0 ou superior, será necessário baixar e instalar atualizações para o Windows PowerShell. Confira [o Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
        
    4. Você também precisará instalar o módulo do Windows PowerShell para Teams que permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online.
    
    Se precisar saber mais, confira Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx)em uma única janela do Windows PowerShell.
    
- **Iniciar uma sessão do Windows PowerShell**
    
    1. No **Menu Iniciar** > **Windows PowerShell**.
        
    2. Na janela **do Windows PowerShell,** conecte-se ao Microsoft 365 ou ao Office 365 executando:
        
       > [!NOTE]
       > No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.
       >
       > Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Se quiser saber mais sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela do Windows PowerShell ou Configurar seu computador para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Requerer uma conexão WiFi para vídeo para um usuário

- Para criar uma nova política para essas configurações, execute:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Veja mais no cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Veja mais no cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
  Se você já criou uma política, pode usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e usar o cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos usuários.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Impedir que um usuário use o app Skype for Business

- Para criar uma nova política para essas configurações, execute:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Veja mais no cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Para conceder a nova política criada ao Amos Marble, execute:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Veja mais no cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
  Se você já criou uma política, pode usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos usuários.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Impedir que um usuário faça chamadas IP usando um dispositivo móvel

- Para criar uma nova política para essas configurações, execute:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Veja mais no cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Para conceder a nova política criada a todos os usuários em sua organização, execute:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Veja mais no cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
Se você já criou uma política, pode usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e usar o cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos usuários.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Microsoft 365 ou o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 
