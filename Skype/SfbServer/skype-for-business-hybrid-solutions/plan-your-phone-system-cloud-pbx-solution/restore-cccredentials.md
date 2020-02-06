---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: O cmdlet Restore CC-Credentials restaura todas as credenciais da implantação atual do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824237"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
O cmdlet Restore CC-Credentials restaura todas as credenciais da implantação atual do Skype for Business Cloud Connector Edition. 
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 2,1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Descrição detalhada

O cmdlet Restore-CcCredentials limpa todas as credenciais e solicita que você insira novamente todas as credenciais usadas para a implantação atual do Skype for Business Cloud Connector.
  
## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="input-types"></a>Tipos de entrada

Nenhum. O cmdlet Restore-CcCredentials não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de retorno

Nenhuma.
  
## <a name="example"></a>Exemplo

O exemplo a seguir restaura todas as credenciais da implantação do conector de nuvem atual:
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Consulte também

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

