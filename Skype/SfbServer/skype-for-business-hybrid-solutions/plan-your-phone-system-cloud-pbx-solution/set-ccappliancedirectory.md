---
title: Set-CcApplianceDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: O cmdlet Set-CcApplianceDirectory define o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório.
ms.openlocfilehash: 67fda4f1ef7da0f9a7e61b1099c7edb3b96ad62c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
O cmdlet Set-CcApplianceDirectory define o diretório de trabalho no servidor host do Skype for Business Cloud Connector Edition. Todos os arquivos de implantação são armazenados nesse diretório.
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir define o diretório de trabalho no servidor host como c:\cloudconnector\applianceroot:
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>Parâmetros
<a name="Examples"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Obrigatório <br/> |System. String  <br/> | Especifica o caminho onde todos os arquivos da implantação são armazenados. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Set-CcApplianceDirectory não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

Nenhum
  

