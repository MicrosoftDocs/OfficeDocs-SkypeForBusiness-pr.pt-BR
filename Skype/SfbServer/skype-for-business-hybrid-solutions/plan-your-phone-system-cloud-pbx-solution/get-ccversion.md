---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Retorna a versão do dispositivo do Cloud Connector. O Get-CCVersion só pode ser usado no computador host do Cloud Connector.
ms.openlocfilehash: a7d50bbcd01dc80fe3e2202286c1adc1b5d5f9bd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003341"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Retorna a versão do dispositivo do Cloud Connector. O Get-CCVersion só pode ser usado no computador host do Cloud Connector.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descrição detalhada

Retorna a versão do aparelho do conector de nuvem com base em scripts do PowerShell instalados, arquivos no diretório de aplicativos e máquinas virtuais implantadas no servidor host.
  
## <a name="parameters"></a>Parâmetros

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Opcional  <br/> |System.String  <br/> |Tipo de versão. O valor do parâmetro pode ser RunningScripts, RunningBits, BackupBits ou todos. O valor padrão é RunningScripts.   <br/> |
   
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a versão do conector de nuvem do script em execução no momento no console do PowerShell aberto:
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Exemplo 2

O exemplo a seguir mostra a versão do conector de nuvem dos binários em execução implantados nas máquinas virtuais. Você pode ver a versão nos nomes das máquinas virtuais em execução no Hyper-v Manager:
  
```powershell
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
  

