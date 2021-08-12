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
description: O Stop-CcLogging cmdlet deixa de gerar o log de chamadas de entrada e saída para um Skype for Business Cloud Connector Edition de entrada.
ms.openlocfilehash: 7813acf9867829cadaa26d84a0e8a6c33f825ef45b9fca781840a44f94574930
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347556"
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

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

