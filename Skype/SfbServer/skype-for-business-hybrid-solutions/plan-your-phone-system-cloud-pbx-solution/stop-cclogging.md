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
ms.localizationpriority: medium
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: O Stop-CcLogging cmdlet deixa de gerar o log de chamadas de entrada e saída para um Skype for Business Cloud Connector Edition de entrada.
ms.openlocfilehash: cfa07602f8465ce3c931010f835f52acc44e2ee2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580336"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
O Stop-CcLogging cmdlet deixa de gerar o log de chamadas de entrada e saída para um Skype for Business Cloud Connector Edition de entrada.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir deixa de gerar o log de chamadas de entrada e saída: 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo deixa de gerar o log de chamadas de entrada e saída e limpa os arquivos de cache:
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Stop-CcLogging cmdlet interrompe o registro em log de chamadas de entrada e saída em um dispositivo. Por padrão, o registro em log será automaticamente parado após quatro horas.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Opcional <br/> | System.Management.Automation.SwitchParameter <br/> |Remove os arquivos de cache de registro em log.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Stop-CcLogging cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

