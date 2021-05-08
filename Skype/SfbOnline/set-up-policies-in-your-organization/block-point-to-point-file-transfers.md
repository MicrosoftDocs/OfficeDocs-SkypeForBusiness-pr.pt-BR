---
title: Bloquear transferências de arquivos ponto a ponto
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: No Skype for Business Online, você tem a capacidade de controlar transferências de arquivos ponto a ponto (P2P) como parte das configurações de política de conferência existentes. No entanto, isso permite ou bloqueia transferências de arquivos para os usuários se eles estão ou não transferindo arquivos para um usuário que está dentro da mesma organização ou para um usuário federado de outra organização. Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações federadas ou parceiros.
ms.openlocfilehash: e20cf0d5ff7a884e81fe2ee5de57ed026c53552e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240170"
---
# <a name="block-point-to-point-file-transfers"></a>Bloquear transferências de arquivos ponto a ponto

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

No Skype for Business Online, você tem a capacidade de controlar transferências de arquivos ponto a ponto (P2P) como parte das configurações de política de conferência existentes. No entanto, isso permite ou bloqueia transferências de arquivos para os usuários se eles estão ou não transferindo arquivos para um usuário que está dentro da mesma organização ou para um usuário federado de outra organização. Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações federadas ou parceiros.
  
 Um cenário muito comum é quando você deseja permitir que os usuários internos usem a transferência de arquivos P2P, mas bloqueiem a transferência de arquivos com parceiros federados. Para esse cenário, você precisaria fazer:
  
- Atribua uma política de conferência com transferência de arquivo P2P habilitada (_EnableP2PFileTransfer_ definido como _True_) aos usuários em sua organização.
    
- Crie uma política de comunicação externa do usuário global definida para bloquear transferências de arquivos P2P externos (_EnableP2PFileTransfer_ definido como _False_) e atribuí-la a um usuário em sua organização. 
    
Você pode saber mais sobre essas configurações [aqui](/previous-versions//mt228132(v=technet.10)).
  
Se um usuário federado fora da sua organização tentar enviar um arquivo para um usuário no qual a política foi aplicada, ele receberá um erro **de** Falha na Transferência. E se um usuário tentar enviar um arquivo, ele receberá um **erro de** transferência de arquivo.
  
Para que isso funcione, o usuário deve estar usando uma versão com suporte de um aplicativo de Skype for Business clique para executar 2016. A seguinte versão mínima do Skype for Business 2016 Click-to-Run client é necessária:
  
|**Tipo**|**Data de lançamento**|**Versão**|**Compilação**|
|:-----|:-----|:-----|:-----|
|Primeira versão do Canal Atual  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versão 1611 (build 7571.2006)  <br/> |
|Canal Atual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versão 1611 (build 7571.2072)  <br/> |
|Canal Adiado  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versão 1609 (build 7369.2118)  <br/> |
   
> [!CAUTION]
> Os usuários que estão usando versões mais antigas Skype for Business Windows aplicativos ou clientes Mac ainda poderão transferir arquivos. 
  
## <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

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
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Desabilitar transferências de arquivos P2P para sua organização

Por padrão, _EnableP2PFileTransfer_ está habilitado na política global da organização. Quando ele foi criado, seus usuários foram atribuídos à _política BposSAllModality._
  
Para permitir transferências P2P para dentro da sua organização, mas bloquear transferências de arquivos externos para outra organização, você só precisa alterá-la em nível global. Para fazer isso, execute:
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Desabilitar transferências de arquivos P2P para um usuário

Você pode aplicar isso a um usuário criando uma nova política e concedendo-a a esse usuário. Para fazer isso, execute: 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
