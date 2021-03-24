---
title: Criar políticas personalizadas de acesso externo
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: O Skype for Business Online permite que você crie políticas de acesso externo adicionais. Ao contrário das políticas de cliente ou conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinidas que podem abranger a maioria dos cenários.
ms.openlocfilehash: 3e5e8cf1c464b1011a49b06b2d1958246d332c91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100607"
---
# <a name="create-custom-external-access-policies"></a>Criar políticas personalizadas de acesso externo

O Skype for Business Online permite que você crie políticas de acesso externo adicionais. Ao contrário das políticas de cliente ou conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinidas que podem abranger a maioria dos cenários. São elas:
  
- No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )
    
- Somente acesso federado (_Tag:FederationOnly_ )
    
- Acesso federado e de consumidor (_FederationAndPICDefault_)
    
Políticas externas personalizadas permitem que você crie políticas adicionais que não são cobertas pelas configurações acima. Quando a política foi criada, você seria obrigado a definir todos os parâmetros necessários e não poderia alterá-los posteriormente. A criação de novas políticas personalizadas permite controlar recursos como o acesso ao consumidor do Skype ou uma política para desabilitar o áudio/vídeo em nuvem pública, que é algo que não foi abordado com configurações predefinidas. Políticas de acesso externo personalizadas seguem a mesma sintaxe que as políticas de cliente, mobilidade e conferência. Você pode saber mais sobre essas configurações [aqui](/previous-versions//mt228132(v=technet.10)).
  
Para que isso funcione, o usuário deve estar usando uma versão com suporte do aplicativo Clique para Executar do Skype for Business de 2016 que a suporte. A seguinte versão mínima do cliente Clique para Executar do Skype for Business 2016 é necessária:
  
|**Tipo**|**Data de lançamento**|**Versão**|**Compilação**|
|:-----|:-----|:-----|:-----|
|Primeira versão do Canal Atual  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versão 1611 (build 7571.2006)  <br/> |
|Canal Atual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versão 1611 (build 7571.2072)  <br/> |
|Canal Adiado  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versão 1609 (build 7369.2118)  <br/> |
   
> [!CAUTION]
> Os usuários que estão usando versões mais antigas de aplicativos do Skype for Business ou clientes Mac ainda poderão transferir arquivos. 
  
## <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

> [!NOTE]
> O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.
1. Instale o [módulo do Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra um prompt Windows PowerShell de comando e execute os seguintes comandos: 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Criar uma política de acesso externo personalizada para um usuário

Para fazer isso, execute:
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Tópicos relacionados
[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
