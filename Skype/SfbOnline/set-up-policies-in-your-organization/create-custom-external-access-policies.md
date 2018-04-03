---
title: Criar políticas de acesso externo personalizadas
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype para Business Online permite que você crie políticas de acesso externo adicionais. Ao contrário de políticas de cliente ou de conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinido que podem abranger a maioria dos cenários.
ms.openlocfilehash: 6eb0d9ecd3eaacc34e8392bbd32329c801505c34
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="create-custom-external-access-policies"></a>Criar políticas de acesso externo personalizadas

Skype para Business Online permite que você crie políticas de acesso externo adicionais. Ao contrário de políticas de cliente ou de conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinido que podem abranger a maioria dos cenários. São elas:
  
- Não federado ou acesso de consumidor do Skype (_Marca: NoFederationAndPIC_ )
    
- Somente acesso federado (_Marca: FederationOnly_ )
    
- Federados e consumidor acessar (_FederationAndPICDefault_)
    
Políticas externas personalizadas permitem que você criar adicionais políticas que não estão cobertos pelas configurações acima. Quando a diretiva tiver sido criada, você poderia ser necessário para configurar todos os parâmetros necessários e não pôde alterá-los mais tarde. Criando novas políticas personalizadas permitem que você os recursos de controle, como acesso de consumidor do Skype ou uma diretiva para desabilitar público na nuvem áudio/vídeo, que é algo que não foi coberto com configurações predefinidas. Políticas de acesso externo personalizadas siga a mesma sintaxe de políticas de cliente, mobilidade e conferência. Você pode encontrar mais informações sobre essas configurações [aqui](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Para que isso funcione, o usuário deve estar usando uma versão compatível do 2016 Skype Click-to-Run para o aplicativo de negócios que lhe fornecer apoio. A seguinte versão mínima do Skype para negócios 2016 Click-to-Run cliente é necessária:
  
|**Tipo**|**Data de lançamento**|**Versão**|**Compilação**|
|:-----|:-----|:-----|:-----|
|Primeira versão do canal atual  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Versão 1611 (compilação 7571.2006)  <br/> |
|Canal atual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versão 1611 (compilação 7571.2072)  <br/> |
|Canal adiada  <br/> |22/2/2017  <br/> |16.0.7369.2118  <br/> |Versão 1609 (compilação 7369.2118)  <br/> |
   
> [!CAUTION]
> Usuários que estiverem usando versões mais antigas do Skype para aplicativos do Windows de negócios ou clientes Mac ainda poderá transferir arquivos. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
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
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Criar uma política de acesso externo personalizadas para um usuário

Para fazer isso, execute:
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
[Transferências de arquivos ponto a ponto de bloqueio](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência na sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 