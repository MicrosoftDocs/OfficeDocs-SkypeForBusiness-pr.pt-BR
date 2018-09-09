---
title: Adicionar uma política de local a um site de rede no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Atribua políticas de localização E9-1-1 a sites de rede no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: e8ff532d66531cbe92ca661d9eaa5780e5b9f56c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885739"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Adicionar uma política de local a um site de rede no Skype para Business Server
 
Atribua políticas de localização E9-1-1 a sites de rede no Skype para Business Server Enterprise Voice. 
  
Os exemplos a seguir mostram como adicionar a política de local de **Redmond** definida no [criar políticas de local no Skype para Business Server](create-location-policies.md) a um site de rede existente e como criar um novo site de rede que usa a diretiva de local de **Redmond** .
  
Para obter detalhes sobre como trabalhar com sites de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:
  
- **New-CsNetworkSite.**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite.**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Para atribuir uma política de local a um site de rede existente

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute os cmdlets a seguir para modificar um site de rede existente.
    
    Atribua a política de Local marcada **Redmond** a um site de rede existente denominado **Redmond**.
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Para atribuir uma política de local a um novo site de rede

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o seguinte cmdlet para criar um novo site de rede.
    
    Crie um novo site de rede na região de rede e atribua a política de local marcada **Redmond**.
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


