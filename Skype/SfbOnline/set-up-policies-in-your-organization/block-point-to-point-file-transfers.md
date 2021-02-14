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
description: No Skype for Business Online, você pode controlar transferências de arquivos ponto a ponto (P2P) como parte das configurações de política de conferência existentes. No entanto, isso permite ou bloqueia transferências de arquivos para os usuários se eles estão ou não transferindo arquivos para um usuário que está dentro da mesma organização ou para um usuário federado de outra organização. Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações ou parceiros federados.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814630"
---
# <a name="block-point-to-point-file-transfers"></a>Bloquear transferências de arquivos ponto a ponto

No Skype for Business Online, você pode controlar transferências de arquivos ponto a ponto (P2P) como parte das configurações de política de conferência existentes. No entanto, isso permite ou bloqueia transferências de arquivos para os usuários se eles estão ou não transferindo arquivos para um usuário que está dentro da mesma organização ou para um usuário federado de outra organização. Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações ou parceiros federados.
  
 Um cenário muito comum é quando você deseja permitir que os usuários internos usem a transferência de arquivos P2P, mas bloqueiem a transferência de arquivos com parceiros federados. Para esse cenário, você precisa fazer:
  
- Atribua uma política de conferência com a transferência de arquivo P2P habilitada _(EnableP2PFileTransfer_ definida como _True)_ aos usuários em sua organização.
    
- Crie uma política de comunicação de usuário externo global definida para bloquear transferências de arquivo P2P externas (_EnableP2PFileTransfer_ definida como _False)_ e atribua-a a um usuário em sua organização. 
    
Saiba mais sobre essas configurações [aqui.](https://technet.microsoft.com/library/mt228132.aspx)
  
Se um usuário federado fora da sua organização tentar enviar um arquivo para um usuário no qual a política foi aplicada, ele receberá um erro de Falha **na** Transferência. E se um usuário tentar enviar um arquivo, ele receberá um erro de transferência de **arquivo.**
  
Para fazer isso funcionar, o usuário deve estar usando uma versão com suporte de um aplicativo Do Skype for Business 2016 com suporte. A seguinte versão mínima do cliente Clique para Executar do Skype for Business 2016 é necessária:
  
|**Tipo**|**Data do lançamento**|**Versão**|**Compilação**|
|:-----|:-----|:-----|:-----|
|Primeiro Lançamento do Canal Atual  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versão 1611 (build 7571.2006)  <br/> |
|Canal Atual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versão 1611 (build 7571.2072)  <br/> |
|Canal Adiado  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versão 1609 (build 7369.2118)  <br/> |
   
> [!CAUTION]
> Os usuários que estão usando versões mais antigas dos aplicativos do Skype for Business para Windows ou clientes Mac ainda poderão transferir arquivos. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
    1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
        
    2. Verifique a versão digitando _Get-Host_ na **janela do Windows PowerShell.**
        
    3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [o Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
        
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
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Desabilitar transferências de arquivos P2P para sua organização

Por padrão, _EnableP2PFileTransfer_ está habilitado na política global da organização. Quando ele foi criado, seus usuários foram atribuídos a _política BposSAllModality._
  
Para permitir transferências P2P para dentro de sua organização, mas bloquear transferências de arquivos externos para outra organização, basta alterá-la em um nível global. Para fazer isso, execute:
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Desabilitar transferências de arquivos P2P para um usuário

Você pode aplicá-la a um usuário criando uma nova política e concedendo-a a esse usuário. Para fazer isso, execute: 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o Microsoft 365 ou o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 
