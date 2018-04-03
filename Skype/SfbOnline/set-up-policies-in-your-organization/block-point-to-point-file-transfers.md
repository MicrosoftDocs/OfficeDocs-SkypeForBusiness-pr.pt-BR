---
title: Transferências de arquivos ponto a ponto do bloco
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: No Skype para Business Online, você tem capacidade de controlar as transferências de arquivos ponto a ponto (P2P) como parte das configurações de política de conferência existente. No entanto, isso permite ou transferências para usuários ou não eles são transferência de arquivos para um usuário que esteja na mesma organização ou para um usuário federado de outra organização de arquivo de blocos. Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações federadas ou parceiros.
ms.openlocfilehash: 8e3fd112d46a88752b0d6d19cf2e1fbb1787df32
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="block-point-to-point-file-transfers"></a>Transferências de arquivos ponto a ponto do bloco

No Skype para Business Online, você tem capacidade de controlar as transferências de arquivos ponto a ponto (P2P) como parte das configurações de política de conferência existente. No entanto, isso permite ou transferências para usuários ou não eles são transferência de arquivos para um usuário que esteja na mesma organização ou para um usuário federado de outra organização de arquivo de blocos. Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações federadas ou parceiros.
  
 Um cenário muito comum é quando você deseja permitir que usuários internos para transferência de arquivos de uso P2P mas transferência de arquivo do bloco com parceiros federados. Para este cenário, você precisa fazer:
  
- Atribua uma política de conferência com a transferência de arquivos de P2P habilitada (_EnableP2PFileTransfer_ definida como _True_) aos usuários em sua organização.
    
- Crie uma política de comunicação de usuário externo global definida como bloquear transferências de arquivos externas P2P (_EnableP2PFileTransfer_ definido como _False_) e atribuí-lo a um usuário em sua organização. 
    
Você pode encontrar mais informações sobre essas configurações [aqui](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Se um usuário federado fora da sua organização tenta enviar um arquivo para um usuário onde a política foi aplicada, eles receberão um erro **Transferir falha** . E se um usuário tentar enviar um arquivo, ele receberá um erro de **transferência de arquivo está desativada** .
  
Para que isso funcione, o usuário deve estar usando uma versão compatível do Skype de Click-to-Run 2016 para o aplicativo de negócios que lhe fornecer apoio. A seguinte versão mínima do Skype para negócios 2016 Click-to-Run cliente é necessária:
  
|**Tipo**|**Data de lançamento**|**Versão**|**Compilação**|
|:-----|:-----|:-----|:-----|
|Primeira versão do canal atual  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Versão 1611 (compilação 7571.2006)  <br/> |
|Canal atual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versão 1611 (compilação 7571.2072)  <br/> |
|Canal adiada  <br/> |22/2/2017  <br/> |16.0.7369.2118  <br/> |Versão 1609 (compilação 7369.2118)  <br/> |
   
> [!CAUTION]
> Usuários que estejam usando versões mais antigas do Skype para aplicativos do Windows de negócios ou clientes Mac ainda poderá transferir arquivos. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifica a versão digitando o _Get-Host_ na janela do **Windows PowerShell** .
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
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

  Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Conectando-se ao Skype para negócios Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Desabilitar as transferências de arquivos P2P para sua organização

Por padrão, _EnableP2PFileTransfer_ está habilitada na diretiva global da organização. Quando ela foi criada, os usuários foram atribuídos a política de _BposSAllModality_ .
  
Para permitir transferências de P2P para dentro de suas transferências de arquivo externo de organização, mas bloco para outra organização, você precisa apenas alterá-lo em um nível global. Para fazer isso, execute:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Desabilitar as transferências de arquivos P2P para um usuário

Você pode aplicar isso a um usuário criando uma nova política e concedendo-lo para o usuário. Para fazer isso, execute: 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados
[Criar políticas personalizadas de acesso externo](create-custom-external-access-policies.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência na sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 