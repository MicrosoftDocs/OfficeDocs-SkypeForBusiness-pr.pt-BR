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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configure um aplicativo SNMP para trabalhar com o E9-1-1 em Skype for Business Server Enterprise Voice.
ms.openlocfilehash: ec93aa572b2acf80afa104bba3b5fd1f9573f985
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597755"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Configurar um aplicativo SNMP no Skype for Business Server
 
Configure um aplicativo SNMP para trabalhar com o E9-1-1 em Skype for Business Server Enterprise Voice. 
  
Skype for Business Server inclui uma interface de serviço Web padrão que você pode usar para conectar o serviço de Informações de Localização a aplicativos SNMP (Protocolo de Gerenciamento de Rede Simples) que combinam endereços MAC com informações de porta e de comutamento. 
  
Se um aplicativo SNMP estiver instalado e o serviço de Informações de Localização não encontrar uma combinação no banco de dados de localização, o serviço de Informações de Local consultará automaticamente o aplicativo usando o endereço MAC fornecido pelo cliente. Em seguida, o serviço Informações de Local usa as informações de porta e alternam retornadas pelo aplicativo SNMP para consultar o banco de dados de localização novamente.
  
> [!NOTE]
> Os endereços MAC não estão disponíveis em computadores que executam Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>Para configurar a URL do aplicativo SNMP

1.  Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**
    
2. Execute o seguinte cmdlet para configurar a URL do aplicativo SNMP. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Confira também

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)