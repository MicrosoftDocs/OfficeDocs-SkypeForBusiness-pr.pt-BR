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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Retorna a versão do dispositivo Cloud Connector. Get-CCVersion pode ser usado apenas no computador host do Cloud Connector.
ms.openlocfilehash: d3da9813fd67228f8e198cd21edce3cc187ac9359617eb660a352b38c51a95ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349503"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Retorna a versão do dispositivo Cloud Connector. Get-CCVersion pode ser usado apenas no computador host do Cloud Connector.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descrição detalhada

Retorna a versão do dispositivo Cloud Connector com base em scripts do PowerShell instalados, arquivos no diretório Appliance e as máquinas virtuais implantadas no servidor host.
  
## <a name="parameters"></a>Parâmetros

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Opcional  <br/> |System.String  <br/> |Tipo de versão. O valor do parâmetro pode ser RunningScripts, RunningBits, BackupBits ou All. O valor padrão é RunningScripts.  <br/> |
   
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a versão do Cloud Connector do script em execução no console aberto do PowerShell:
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Exemplo 2

O exemplo a seguir mostra a versão do Cloud Connector dos binários em execução atualmente implantados nas máquinas virtuais. Você pode ver a versão nos nomes de máquina virtual em execução no Hyper-v Manager:
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Tipos de Entrada
<a name="Examples"> </a>

Nenhum. O Get-CcVersion cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="Examples"> </a>

Nenhum.
  
## <a name="see-also"></a>Confira também
<a name="Examples"> </a>

Nenhum
  

