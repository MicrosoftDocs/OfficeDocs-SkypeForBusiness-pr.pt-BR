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
description: O Exit-CcUpdate cmdlet sai do modo de manutenção de atualização no servidor Skype for Business Cloud Connector Edition host.
ms.openlocfilehash: d55004f071caa67492d5368e36007d9c3c307b90aabbc33d79d1feeb4aa37356
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288829"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
O Exit-CcUpdate cmdlet sai do modo de manutenção de atualização no servidor Skype for Business Cloud Connector Edition host. 
  
Este cmdlet se aplica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2. 
  
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

Se você tiver dispositivos que você colocou no modo de manutenção especificando o cmdlet Enter-CcUpdate, o cmdlet Exit-CcUpdate os colocará novamente no modo de produção. 
  
Para obter mais informações sobre como colocar dispositivos no modo de manutenção, consulte Enter-CcUpdate.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Exit-CcUpdate cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None 
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

