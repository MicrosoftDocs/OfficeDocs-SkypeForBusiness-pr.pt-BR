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
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 'O cmdlet Exit-CcUpdate sai do modo de manutenção de atualização no servidor host do Skype for Business Cloud Connector Edition.  '
ms.openlocfilehash: f79023c50e951e6678abdccc29b12cb30a329dfc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003441"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
O cmdlet Exit-CcUpdate sai do modo de manutenção de atualização no servidor host do Skype for Business Cloud Connector Edition.   
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1 e 1.4.2.  
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O comando a seguir coloca o dispositivo novamente no modo de produção:  
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se você tiver dispositivos que foram colocados no modo de manutenção especificando o cmdlet Enter-CcUpdate, o cmdlet Exit-CcUpdate os colocará novamente no modo de produção.   
  
Para obter mais informações sobre como colocar os dispositivos no modo de manutenção, veja Enter-CcUpdate.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Exit-CCUpdate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum  
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

