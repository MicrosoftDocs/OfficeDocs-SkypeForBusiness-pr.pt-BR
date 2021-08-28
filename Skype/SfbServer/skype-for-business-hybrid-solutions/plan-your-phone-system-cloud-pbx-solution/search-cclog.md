---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: O Search-CcLog cmdlet pesquisa os logs de chamadas de entrada e de saída no diretório de log Skype for Business Cloud Connector Edition de dispositivos.
ms.openlocfilehash: b96e0bea7c8a7ac9d3a12c135c828440eea9fb32
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618687"
---
# <a name="search-cclog"></a>Search-CcLog
 
O Search-CcLog cmdlet pesquisa os logs de chamadas de entrada e de saída no diretório de log Skype for Business Cloud Connector Edition de dispositivos.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir pesquisa os logs de chamadas de entrada e saída no diretório de log do dispositivo usando o nome de arquivo padrão:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo pesquisa os logs de chamadas de entrada e saída usando o caminho e o nome de arquivo determinados:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Search-CsClsLogging fornece uma opção de linha de comando para pesquisar os arquivos de log gerados pelo serviço de registro centralizado.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Obrigatório <br/> |System.Datetime  <br/> | Data e hora inicial das entradas de log a serem pesquisadas. Especificada no fuso horário local. <br/> |
|EndTime  <br/> |Obrigatório  <br/> |System.Datetime  <br/> |Data e hora final das entradas de log a serem pesquisadas. Especificada no fuso horário local.  <br/> |
|FileName  <br/> |Obrigatório  <br/> |System.String  <br/> |Especifica o caminho completo do arquivo de texto que contém os resultados da pesquisa.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Search-CcLog cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

