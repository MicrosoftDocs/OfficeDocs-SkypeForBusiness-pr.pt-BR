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
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: O cmdlet Search-CcLog pesquisa os logs da chamada de entrada e saída no diretório de log do dispositivo do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: c248720931ef1c15d633c51bb6daa6c414631a18
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003231"
---
# <a name="search-cclog"></a>Search-CcLog
 
O cmdlet Search-CcLog pesquisa os logs da chamada de entrada e saída no diretório de log do dispositivo do Skype for Business Cloud Connector Edition.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte pesquisa os logs de chamada de entrada e saída no diretório de log do dispositivo usando o nome do arquivo padrão:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo pesquisa os logs de chamada de entrada e saída usando o caminho e o nome do arquivo especificados:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet  Search-CsClsLogging fornece uma opção de linha de comando para pesquisar os arquivos de log gerados pelo serviço de registro centralizado.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|StartTime   <br/> | Obrigatório <br/> |System.Datetime  <br/> | Data e hora inicial das entradas de log a serem pesquisadas. Especificada no fuso horário local. <br/> |
|EndTime  <br/> |Obrigatório  <br/> |System.Datetime  <br/> |Data e hora final das entradas de log a serem pesquisadas. Especificada no fuso horário local.  <br/> |
|FileName  <br/> |Obrigatório  <br/> |System.String  <br/> |Especifica o caminho completo do arquivo de texto que contém os resultados da pesquisa.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Search-CcLog não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

