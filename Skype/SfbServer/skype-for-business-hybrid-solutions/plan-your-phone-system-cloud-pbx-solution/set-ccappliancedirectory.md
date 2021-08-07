---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: O Set-CcApplianceDirectory cmdlet define o diretório de trabalho no servidor Skype for Business Cloud Connector Edition host. Todos os arquivos de implantação são armazenados neste diretório.
ms.openlocfilehash: 8ca6b8b8e175058e5f19c86a9dd1c6e0cf8a43ab6ef7a439eee4e09b5430f6a2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306592"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
O Set-CcApplianceDirectory cmdlet define o diretório de trabalho no servidor Skype for Business Cloud Connector Edition host. Todos os arquivos de implantação são armazenados neste diretório.
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir define o diretório de trabalho no servidor host como c:\cloudconnector\applianceroot:
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>Parâmetros
<a name="Examples"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Obrigatório <br/> |System.String  <br/> | Especifica o caminho onde todos os arquivos de implantação são armazenados. <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Set-CcApplianceDirectory cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

None
  

