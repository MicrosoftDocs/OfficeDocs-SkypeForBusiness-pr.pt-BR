---
title: Configurar um aplicativo SNMP no Skype for Business Server 2015
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configure um aplicativo SNMP para funcionar com o E9-1-1 em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 5c10d00e05979c2a3e0efff015da61e5ff2c6ee9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a>Configurar um aplicativo SNMP no Skype for Business Server 2015
 
Configure um aplicativo SNMP para funcionar com o E9-1-1 em Skype para Business Server Enterprise Voice. 
  
Skype para Business Server inclui uma interface de serviço da web padrão que você pode usar para conectar-se o serviço de informações de local aos aplicativos de protocolo de gerenciamento de rede simples (SNMP) que correspondem endereços MAC com porta e trocar informações. 
  
Se um aplicativo SNMP é instalado e o serviço de informações de local não conseguir localizar uma correspondência no banco de dados local, o serviço de informações de local de consulta automaticamente o aplicativo usando o endereço MAC fornecido pelo cliente. O serviço de informações de local, em seguida, usa as informações de porta e opção retornadas pelo aplicativo SNMP para consultar novamente o banco de dados local.
  
> [!NOTE]
> Endereços MAC não estão disponíveis em computadores que executam o Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Para configurar a URL do aplicativo SNMP

1.  Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o seguinte cmdlet para configurar a URL do aplicativo SNMP. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Consulte também

#### 

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

