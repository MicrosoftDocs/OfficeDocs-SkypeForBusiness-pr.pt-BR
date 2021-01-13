---
title: Configurar um aplicativo SNMP no Skype for Business Server
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configure um aplicativo SNMP para trabalhar com o E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804151"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configurar um aplicativo SNMP no Skype for Business Server
 
Configure um aplicativo SNMP para trabalhar com o E9-1-1 no Skype for Business Server Enterprise Voice. 
  
O Skype for Business Server inclui uma interface de serviço Web padrão que você pode usar para conectar o serviço de Informações de Local a aplicativos SNMP (Simple Network Management Protocol) que combinam endereços MAC com informações de porta e de comutamento. 
  
Se um aplicativo SNMP estiver instalado e o serviço de Informações de Local não encontrar uma combinação no banco de dados de localização, o serviço de Informações de Local consultará automaticamente o aplicativo usando o endereço MAC fornecido pelo cliente. Em seguida, o serviço de Informações de Local usa as informações de porta e de comutadores retornadas pelo aplicativo SNMP para consultar o banco de dados de localização novamente.
  
> [!NOTE]
> Os endereços MAC não estão disponíveis em computadores que executam o Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Para configurar a URL do aplicativo SNMP

1.  Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
2. Execute o seguinte cmdlet para configurar a URL do aplicativo SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Confira também

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

