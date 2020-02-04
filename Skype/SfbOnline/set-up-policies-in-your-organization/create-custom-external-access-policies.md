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
description: O Skype for Business Online permite que você crie políticas de acesso externo adicionais. Ao contrário das políticas de cliente ou de conferência, em que você pode ter várias combinações, há três políticas de acesso externo predefinidas que podem abranger a maioria dos cenários.
ms.openlocfilehash: 49572dc1aaef3d595bd0de41fd6359d90e8d803a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706656"
---
# <a name="create-custom-external-access-policies"></a>Criar políticas personalizadas de acesso externo

O Skype for Business Online permite que você crie políticas de acesso externo adicionais. Ao contrário das políticas de cliente ou de conferência, em que você pode ter várias combinações, há três políticas de acesso externo predefinidas que podem abranger a maioria dos cenários. São elas:
  
- Sem acesso ao consumidor federado ou Skype (_marca: NoFederationAndPIC_ )
    
- Somente acesso federado (_marca: FederationOnly_ )
    
- Acesso federado e de consumidor (_FederationAndPICDefault_)
    
Políticas externas personalizadas permitem que você crie políticas adicionais que não estão incluídas nas configurações acima. Após a criação da política, você será solicitado a definir todos os parâmetros obrigatórios e não poderá alterá-los mais tarde. A criação de novas políticas personalizadas permite que você controle recursos como o acesso do consumidor do Skype ou uma política para desabilitar o áudio/vídeo de nuvem pública, que é algo que não está coberto por configurações predefinidas. As políticas personalizadas de acesso externo seguem a mesma sintaxe das políticas de cliente, mobilidade e conferência. Você pode saber mais sobre essas configurações [aqui](https://technet.microsoft.com/library/mt228132.aspx).
  
Para fazer isso funcionar, o usuário deve estar usando uma versão com suporte do 2016 clique para executar o aplicativo Skype for Business compatível com ele. A seguinte versão mínima do Skype for Business 2016 clique para executar cliente é necessária:
  
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
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Consulte [Windows Management Framework 4,0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) para baixar e atualizar o Windows PowerShell para a versão 4,0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
    Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Iniciar uma sessão do Windows PowerShell**
    
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > [!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Criar uma política de acesso externo personalizada para um usuário

Para fazer isso, execute:
  
> 
>   ```PowerShell
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```PowerShell
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 
