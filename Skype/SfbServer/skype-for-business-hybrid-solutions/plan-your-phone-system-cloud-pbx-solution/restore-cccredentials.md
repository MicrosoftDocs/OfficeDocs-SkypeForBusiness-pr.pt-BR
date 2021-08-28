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
ms.localizationpriority: medium
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: O cmdlet Restore Cc-Credentials restaura todas as credenciais da implantação Skype for Business Cloud Connector Edition atual.
ms.openlocfilehash: 050c4265bff7673a7db620ff41a56a2735d6b4a7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588433"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
O cmdlet Restore Cc-Credentials restaura todas as credenciais da implantação Skype for Business Cloud Connector Edition atual. 
  
Este cmdlet se aplica Skype for Business Cloud Connector Edition 2.1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Descrição detalhada

O Restore-CcCredentials cmdlet limpa todas as credenciais e solicita que você insira todas as credenciais usadas para a implantação atual do Skype for Business Cloud Connector.
  
## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="input-types"></a>Tipos de entrada

Nenhum. O Restore-CcCredentials cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de retorno

Nenhum.
  
## <a name="example"></a>Exemplo

O exemplo a seguir restaura todas as credenciais da implantação atual do Cloud Connector:
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Confira também

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

