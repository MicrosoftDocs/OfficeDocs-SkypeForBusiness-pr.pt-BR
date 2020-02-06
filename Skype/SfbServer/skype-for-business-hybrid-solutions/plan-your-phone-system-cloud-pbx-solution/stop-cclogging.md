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
description: O cmdlet Stop-CcLogging para de gerar logs de chamadas de entrada e de saída para o dispositivo do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824155"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
O cmdlet Stop-CcLogging para de gerar logs de chamadas de entrada e de saída para o dispositivo do Skype for Business Cloud Connector Edition.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte para de gerar logs de chamadas de entrada e de saída:  
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Exemplo 2

O exemplo seguinte para de gerar logs de chamadas de entrada e de saída e limpa os arquivos em cache:
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Stop-CcLogging para de registrar em log as chamadas de entrada e de saída em um dispositivo. Por padrão, o registro em log para automaticamente depois de quatro horas.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Opcional <br/> | System.Management.Automation.SwitchParameter <br/> |Remove o registro em log de arquivos em cache.   <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Stop-CcLogging não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

