---
title: Adicionar uma política de localização a um site de rede no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Atribua políticas de localização E9-1-1 a sites de rede no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 36885fadddddd1fd0bf5ba91a6e0c30e79ef8b90
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001421"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Adicionar uma política de localização a um site de rede no Skype for Business Server
 
Atribua políticas de localização E9-1-1 a sites de rede no Skype for Business Server Enterprise Voice. 
  
Os exemplos a seguir mostram como adicionar a política de localização de **Redmond** definida em [criar políticas de localização no Skype for Business Server](create-location-policies.md) a um site de rede existente e como criar um novo site de rede que usa a política de localização de **Redmond** .
  
Para obter detalhes sobre como trabalhar com sites de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Para atribuir uma política de local a um site de rede existente

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute os cmdlets a seguir para modificar um site de rede existente.
    
    Atribua a política de Local marcada **Redmond** a um site de rede existente denominado **Redmond**.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Para atribuir uma política de local a um novo site de rede

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o seguinte cmdlet para criar um novo site de rede.
    
    Crie um novo site de rede na região de rede e atribua a política de local marcada **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


