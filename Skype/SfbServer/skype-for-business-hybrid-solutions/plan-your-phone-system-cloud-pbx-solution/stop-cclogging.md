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
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: O cmdlet Stop-CcLogging para de gerar logs de chamadas de entrada e de saída para o dispositivo do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 4528f7c1458093874f59f347585a736666a9ea08
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003161"
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
  

