---
title: Configurar um serviço de informações de localização secundário no Skype for Business Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurar um banco de dados de endereço de local secundário (SLS) para E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 1743a4c5f49fcc01fe2f0878c596e0d1bb530621
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001991"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurar um serviço de informações de localização secundário no Skype for Business Server
 
Configurar um banco de dados de endereço de local secundário (SLS) para E9-1-1 no Skype for Business Server Enterprise Voice. 
  
O Skype for Business Server oferece uma interface de serviço Web que você pode usar para apontar o serviço de informações de localização para um banco de dados de local secundário (SLS). A interface do serviço Web que se conecta ao banco de dados SLS deve estar de acordo com o WSDL do serviço de informações de localização. Se o banco de dados de localização e o banco de dados de local secundário estiverem configurados, o serviço informações de localização primeiro consultará o banco de dados de localização e, se nenhuma correspondência for encontrada, envia a solicitação de localização do cliente para o banco de dados SLS. Se o local existir no SLS, o serviço de informações de localização enviará o local de volta ao cliente. 
  
### <a name="to-configure-a-secondary-location-database"></a>Para configurar o banco de dados de localização secundária

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Confira também

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

