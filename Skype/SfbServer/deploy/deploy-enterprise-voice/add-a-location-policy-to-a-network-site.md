---
title: Adicionar uma política de local a um site de rede Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Atribua políticas de localização E9-1-1 a sites de rede Skype for Business Server Enterprise Voice.
ms.openlocfilehash: ae35958d9ff95e32f129d3992d52145e3bef51b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848044"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Adicionar uma política de local a um site de rede Skype for Business Server
 
Atribua políticas de localização E9-1-1 a sites de rede Skype for Business Server Enterprise Voice. 
  
Os exemplos a seguir mostram como adicionar a política de local **de Redmond** definida em Criar políticas de localização no [Skype for Business Server](create-location-policies.md) a um site de rede existente e como criar um novo site de rede que usa a política de local **redmond.**
  
Para obter detalhes sobre como trabalhar com sites de rede, consulte a documentação do Shell de Gerenciamento do Lync Server para os seguintes cmdlets:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Para atribuir uma política de local a um site de rede existente

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
2. Execute os cmdlets a seguir para modificar um site de rede existente.
    
    Atribua a política local com marcação **redmond** a um site de rede existente chamado **Redmond**.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Para atribuir uma política de local a um novo site de rede

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
2. Execute o seguinte cmdlet para criar um novo site de rede.
    
    Crie um novo site de rede na região de rede e atribua a política de local marcada **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


