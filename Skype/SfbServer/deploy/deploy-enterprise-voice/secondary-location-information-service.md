---
title: Configurar um Serviço de Informações de Local secundário no Skype for Business Server 2015
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configure um banco de dados de origem (SLS) de localização secundária para E9-1-1 em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 03de4369b8473142e7a76e3698bb9fe7f129d546
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a>Configurar um Serviço de Informações de Local secundário no Skype for Business Server 2015
 
Configure um banco de dados de origem (SLS) de localização secundária para E9-1-1 em Skype para Business Server Enterprise Voice. 
  
Skype para Business Server fornece uma interface de serviço web que você pode usar para apontar o serviço de informações de local para um banco de dados de origem de localização secundário (SLS). A interface de serviço da web que se conecta ao banco de dados SLS deve se adequar ao WSDL do serviço de informações de local. Se um banco de dados local e o banco de dados de localização secundária forem configurados, o serviço de informações de local primeiro consulta o banco de dados local e se nenhuma correspondência for encontrada, envia a solicitação de localização do cliente para o banco de dados SLS. Se o local existe no SLS, o serviço de informações de local envia o local de volta para o cliente. 
  
### <a name="to-configure-a-secondary-location-database"></a>Para configurar o banco de dados de localização secundária

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Consulte também

#### 

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

