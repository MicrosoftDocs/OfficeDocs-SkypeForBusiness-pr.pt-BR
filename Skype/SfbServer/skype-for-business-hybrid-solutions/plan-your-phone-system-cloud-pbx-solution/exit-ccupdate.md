---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: O Exit-CcUpdate cmdlet sai do modo de manutenção de atualização no servidor host do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801761"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
O Exit-CcUpdate cmdlet sai do modo de manutenção de atualização no servidor host do Skype for Business Cloud Connector Edition. 
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O comando a seguir coloca o dispositivo no qual ele é executado novamente no modo de produção: 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se você tiver dispositivos que você colocou no modo de manutenção especificando o cmdlet Enter-CcUpdate, o cmdlet Exit-CcUpdate os colocará de volta no modo de produção. 
  
Para obter mais informações sobre como colocar dispositivos no modo de manutenção, consulte Enter-CcUpdate.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Exit-CcUpdate cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

