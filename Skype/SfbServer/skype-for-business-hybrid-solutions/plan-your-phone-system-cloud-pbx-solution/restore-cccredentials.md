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
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: O cmdlet Restore CC-Credentials restaura todas as credenciais da implantação atual do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: efa1bcda9af6abccd2ced0faf1e772e779a4483f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287080"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
O cmdlet Restore CC-Credentials restaura todas as credenciais da implantação atual do Skype for Business Cloud Connector Edition. 
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 2,1.
  
```
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
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Consulte também

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

