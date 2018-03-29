---
title: Get-CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Retorna a versão do dispositivo do Cloud Connector. O Get-CCVersion só pode ser usado no computador host do Cloud Connector.
ms.openlocfilehash: 8391264603a73e3f594122dcdd2eb62b9ba19978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Retorna a versão do dispositivo do Cloud Connector. O Get-CCVersion só pode ser usado no computador host do Cloud Connector.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descrição detalhada

Retorna a versão do aparelho de conector de nuvem, com base em scripts do PowerShell instalados, arquivos no diretório aparelho e as máquinas virtuais implantadas em um servidor host.
  
## <a name="parameters"></a>Parâmetros

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Opcional  <br/> |System. String  <br/> |Tipo de versão. O valor do parâmetro pode ser RunningScripts, RunningBits, BackupBits ou todos. O valor padrão é RunningScripts.  <br/> |
   
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a versão do conector de nuvem do script atualmente em execução no seu console aberto do PowerShell:
  
```
Get-CcVersion
```

### <a name="example-2"></a>Exemplo 2

O exemplo a seguir mostra a versão do conector de nuvem de binários implantado para as máquinas virtuais em execução no momento. Você pode ver a versão nos nomes das máquinas virtuais em execução no Hyper-v Manager:
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Nenhum. O cmdlet Get-CcVersion não aceita entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="Examples"> </a>

Nenhum.
  
## <a name="see-also"></a>Consulte também
<a name="Examples"> </a>

Nenhum.
  

