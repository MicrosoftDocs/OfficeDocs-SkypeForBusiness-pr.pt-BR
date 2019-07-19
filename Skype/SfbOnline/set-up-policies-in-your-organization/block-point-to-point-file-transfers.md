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
f1keywords: None
ms.custom:
- Setup
description: No Skype for Business Online, você pode controlar as transferências de arquivo ponto a ponto (P2P) como parte das configurações de política de conferência existentes. No entanto, isso permite ou bloqueia transferências de arquivos para usuários se eles estão ou não transferindo arquivos para um usuário que está dentro da mesma organização ou para um usuário federado de outra organização. Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações federadas ou parceiros.
ms.openlocfilehash: 8e9f2bba654f2e44e4e7360f46730a6e1d2d9426
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792510"
---
# <a name="block-point-to-point-file-transfers"></a>Bloquear transferências de arquivos ponto a ponto

No Skype for Business Online, você pode controlar as transferências de arquivo ponto a ponto (P2P) como parte das configurações de política de conferência existentes. No entanto, isso permite ou bloqueia transferências de arquivos para usuários se eles estão ou não transferindo arquivos para um usuário que está dentro da mesma organização ou para um usuário federado de outra organização. Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações federadas ou parceiros.
  
 Um cenário muito comum é quando você deseja permitir que usuários internos usem a transferência de arquivo ponto a ponto, mas bloquear a transferência de arquivos com parceiros federados. Para esse cenário, você precisaria fazer o seguinte:
  
- Atribua uma política de conferência com a transferência de arquivo P2P habilitada (_EnableP2PFileTransfer_ definida como _true_) aos usuários em sua organização.
    
- Crie uma política de comunicação de usuário externo global definida para bloquear transferências de arquivo P2P externas (_EnableP2PFileTransfer_ definidas como _false_) e atribuí-las a um usuário em sua organização. 
    
Você pode saber mais sobre essas configurações [aqui](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Se um usuário federado fora da sua organização tentar enviar um arquivo para um usuário em que a política foi aplicada, ele receberá um erro de **transferência com falha** . E se um usuário tentar enviar um arquivo, ele receberá um erro de **transferência de arquivo** desativado.
  
Para fazer isso funcionar, o usuário deve estar usando uma versão com suporte do 2016 clique para executar o aplicativo Skype for Business com suporte. A seguinte versão mínima do Skype for Business 2016 clique para executar cliente é necessária:
  
|**Tipo**|**Data do lançamento**|**Versão**|**Compilação**|
|:-----|:-----|:-----|:-----|
|Primeiro lançamento do canal atual  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versão 1611 (Build 7571,2006)  <br/> |
|Canal atual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versão 1611 (Build 7571,2072)  <br/> |
|Canal adiado  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versão 1609 (Build 7369,2118)  <br/> |
   
> [!CAUTION]
> Os usuários que usam versões mais antigas dos aplicativos do Windows ou clientes Mac do Skype for Business ainda poderão transferir arquivos. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando _Get-Host_ na janela do **Windows PowerShell** .
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
    Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Iniciar uma sessão do Windows PowerShell**
    
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Desabilitar transferências de arquivos P2P para sua organização

Por padrão, o _EnableP2PFileTransfer_ está habilitado na política global da organização. Quando ele foi criado, a política _BposSAllModality_ foi atribuída a seus usuários.
  
Para permitir transferências P2P para dentro da sua organização, mas bloquear transferências de arquivos externos para outra organização, você precisa apenas alterá-lo em um nível global. Para fazer isso, execute:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Desabilitar transferências de arquivo P2P para um usuário

Você pode aplicar isso a um usuário criando uma nova política e concedendo-a a esse usuário. Para fazer isso, execute: 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 
