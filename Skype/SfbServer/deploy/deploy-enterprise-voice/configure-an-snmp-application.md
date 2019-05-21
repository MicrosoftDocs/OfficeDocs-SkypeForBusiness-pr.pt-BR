---
title: Configurar um aplicativo SNMP no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurar um aplicativo SNMP para funcionar com o E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 575c982dae20ed085e49690edfbb141786390516
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303415"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configurar um aplicativo SNMP no Skype for Business Server
 
Configurar um aplicativo SNMP para funcionar com o E9-1-1 no Skype for Business Server Enterprise Voice. 
  
O Skype for Business Server inclui uma interface de serviço Web padrão que você pode usar para conectar o serviço de informações de localização a aplicativos de protocolo de gerenciamento de rede simples (SNMP) que correspondem a endereços MAC com informações de porta e switch. 
  
Se um aplicativo SNMP estiver instalado e o serviço de informações de localização não conseguir encontrar uma correspondência no banco de dados de localização, o serviço de informações de localização consultará automaticamente o aplicativo usando o endereço MAC fornecido pelo cliente. Em seguida, o serviço de informações de localização usa a porta e as informações de troca retornadas pelo aplicativo SNMP para consultar o banco de dados de localização novamente.
  
> [!NOTE]
> Os endereços MAC não estão disponíveis em computadores que executam o Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Para configurar a URL do aplicativo SNMP

1.  Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o seguinte cmdlet para configurar a URL do aplicativo SNMP. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Confira também

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

