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
description: O Skype for Business Online permite criar políticas de acesso externo adicionais. Ao contrário das políticas de cliente ou conferência, onde você pode ter várias combinações, há três políticas predefinidas de acesso externo que podem abranger a maioria dos cenários.
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814190"
---
# <a name="create-custom-external-access-policies"></a>Criar políticas personalizadas de acesso externo

O Skype for Business Online permite criar políticas de acesso externo adicionais. Ao contrário das políticas de cliente ou conferência, onde você pode ter várias combinações, há três políticas predefinidas de acesso externo que podem abranger a maioria dos cenários. São elas:
  
- No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )
    
- Acesso Federado Somente (_Tag:FederationOnly)_
    
- Acesso federado e ao consumidor (_FederationAndPICDefault)_
    
As políticas externas personalizadas permitem criar políticas adicionais que não são cobertas pelas configurações acima. Quando a política foi criada, você seria obrigado a definir todos os parâmetros necessários e não poderia alterá-los mais tarde. A criação de novas políticas personalizadas permite controlar recursos como o acesso ao consumidor do Skype ou uma política para desabilitar o áudio/vídeo na nuvem pública, que é algo que não foi abordado com configurações predefinidas. As políticas de acesso externo personalizado seguem a mesma sintaxe que as políticas de cliente, mobilidade e conferência. Saiba mais sobre essas configurações [aqui.](https://technet.microsoft.com/library/mt228132.aspx)
  
Para fazer isso funcionar, o usuário deve estar usando uma versão com suporte do aplicativo Clique para Executar do Skype for Business 2016 que oferece suporte a ele. A seguinte versão mínima do cliente Clique para Executar do Skype for Business 2016 é necessária:
  
|**Tipo**|**Data do lançamento**|**Versão**|**Compilação**|
|:-----|:-----|:-----|:-----|
|Primeiro Lançamento do Canal Atual  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versão 1611 (build 7571.2006)  <br/> |
|Canal Atual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versão 1611 (build 7571.2072)  <br/> |
|Canal Adiado  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versão 1609 (build 7369.2118)  <br/> |
   
> [!CAUTION]
> Os usuários que estão usando versões mais antigas de aplicativos do Skype for Business windows ou clientes Mac ainda poderão transferir arquivos. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [o Windows Management Framework 4.0 para](https://www.microsoft.com/download/details.aspx?id=40855) baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
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
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Criar uma política de acesso externo personalizado para um usuário

Para fazer isso, execute:
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
[Bloquear transferências de arquivo ponto a ponto](block-point-to-point-file-transfers.md)

[Configurar políticas de clientes para sua organização](set-up-client-policies-for-your-organization.md)

[Configurar políticas de conferência em sua organização](set-up-conferencing-policies-for-your-organization.md)

  
 
