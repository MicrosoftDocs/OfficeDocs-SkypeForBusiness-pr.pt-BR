---
title: Configurar um serviço de informações de localização secundário no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configure um banco de dados de origem (SLS) de localização secundária para E9-1-1 em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 047fd1a7dca0c4c2b76d01fd0c5d67230246441e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892290"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurar um serviço de informações de localização secundário no Skype para Business Server
 
Configure um banco de dados de origem (SLS) de localização secundária para E9-1-1 em Skype para Business Server Enterprise Voice. 
  
Skype para Business Server fornece uma interface de serviço web que você pode usar para apontar o serviço de informações de local para um banco de dados de origem de localização secundário (SLS). A interface de serviço da web que se conecta ao banco de dados SLS deve se adequar ao WSDL do serviço de informações de local. Se um banco de dados local e o banco de dados de localização secundária forem configurados, o serviço de informações de local primeiro consulta o banco de dados local e se nenhuma correspondência for encontrada, envia a solicitação de localização do cliente para o banco de dados SLS. Se o local existe no SLS, o serviço de informações de local envia o local de volta para o cliente. 
  
### <a name="to-configure-a-secondary-location-database"></a>Para configurar o banco de dados de localização secundária

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Confira também

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

