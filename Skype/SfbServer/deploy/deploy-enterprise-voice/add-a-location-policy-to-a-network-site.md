---
title: Adicionar uma política de local a um site de rede no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Atribua políticas de localização E9-1-1 a sites de rede no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: bf2b8675ebaa14e98f8a362b3a0714037000de95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a>Adicionar uma política de local a um site de rede no Skype for Business Server 2015
 
Atribua políticas de localização E9-1-1 a sites de rede no Skype para Business Server Enterprise Voice. 
  
Os seguintes exemplos mostram como adicionar a política de local de **Redmond** definida no [criar políticas de local no Skype para Business Server 2015](create-location-policies.md) a um site de rede existente e como criar um novo site de rede que usa o local de **Redmond** política.
  
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


