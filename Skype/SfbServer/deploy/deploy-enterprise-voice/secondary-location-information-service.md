---
title: Configurar um serviço de Informações de Local secundário no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configure um banco de dados de Origem de Local Secundária (SLS) para E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830641"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurar um serviço de Informações de Local secundário no Skype for Business Server
 
Configure um banco de dados de Origem de Local Secundária (SLS) para E9-1-1 no Skype for Business Server Enterprise Voice. 
  
O Skype for Business Server fornece uma interface de serviço Web que você pode usar para apontar o serviço informações de local para um banco de dados de Origem de Local Secundário (SLS). A interface do serviço Web que se conecta ao banco de dados SLS deve estar em conformidade com o WSDL do serviço de Informações de Local. Se um banco de dados de localização e um banco de dados de localização secundário estão configurados, o serviço de Informações de Local primeiro consulta o banco de dados de localização e, se nenhuma combinação for encontrada, envia a solicitação de local do cliente para o banco de dados SLS. Se o local existir no SLS, o serviço de Informações de Local enviará o local de volta para o cliente. 
  
### <a name="to-configure-a-secondary-location-database"></a>Para configurar um banco de dados de Localização Secundária

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
2. Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Confira também

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

