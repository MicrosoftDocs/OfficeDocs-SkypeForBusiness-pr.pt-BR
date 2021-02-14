---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: O Stop-CcLogging cmdlet para de gerar o log de chamadas de entrada e saída para um dispositivo do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824155"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
O Stop-CcLogging cmdlet para de gerar o log de chamadas de entrada e saída para um dispositivo do Skype for Business Cloud Connector Edition.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir para de gerar o log de chamadas de entrada e saída: 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo para de gerar o log de chamadas de entrada e saída e limpa os arquivos de cache:
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Stop-CcLogging cmdlet interrompe o registro em log de chamadas de entrada e saída em um dispositivo. Por padrão, o registro em log será automaticamente parar após quatro horas.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Opcional <br/> | System.Management.Automation.SwitchParameter <br/> |Remove os arquivos de cache de registro em log.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Stop-CcLogging cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

