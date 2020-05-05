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
description: Retorna a versão do dispositivo do Cloud Connector. Get-CCVersion só pode ser usado no computador host do Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799841"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Retorna a versão do dispositivo do Cloud Connector. Get-CCVersion só pode ser usado no computador host do Cloud Connector.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Descrição detalhada

Retorna a versão do dispositivo do Cloud Connector com base em scripts do PowerShell instalados, arquivos no diretório do dispositivo e as máquinas virtuais implantadas no servidor host.
  
## <a name="parameters"></a>Parâmetros

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Opcional  <br/> |System. String  <br/> |Tipo de versão. O valor do parâmetro pode ser RunningScripts, RunningBits, BackupBits ou ALL. O valor padrão é RunningScripts.  <br/> |
   
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a versão do Cloud Connector do script em execução no momento no console aberto do PowerShell:
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Exemplo 2

O exemplo a seguir mostra a versão do Cloud Connector dos binários atualmente em execução implantados para as máquinas virtuais. Você pode ver a versão nos nomes da máquina virtual em execução no Gerenciador do Hyper-v:
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Tipos de Entrada
<a name="Examples"> </a>

Nenhum. O cmdlet Get-CcVersion não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="Examples"> </a>

Nenhum.
  
## <a name="see-also"></a>Confira também
<a name="Examples"> </a>

Nenhum
  

