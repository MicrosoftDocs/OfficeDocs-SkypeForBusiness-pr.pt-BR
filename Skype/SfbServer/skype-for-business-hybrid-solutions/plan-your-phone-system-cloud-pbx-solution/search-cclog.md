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
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: O Search-CcLog cmdlet pesquisa os logs de chamadas de entrada e saída no diretório de log de dispositivos do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: a512d715f1640184217ce07e0b666954a6541fd2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824227"
---
# <a name="search-cclog"></a>Search-CcLog
 
O Search-CcLog cmdlet pesquisa os logs de chamadas de entrada e saída no diretório de log de dispositivos do Skype for Business Cloud Connector Edition.
  
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

O próximo exemplo pesquisa os logs de chamadas de entrada e saída usando o nome e o caminho de arquivo determinados:
  
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

Nenhum. O Search-CcLog cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

