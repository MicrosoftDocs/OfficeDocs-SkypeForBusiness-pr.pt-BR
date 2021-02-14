---
title: Get-CcApplianceLogDirectory
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
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: O Get-CcApplianceLogDirectory cmdlet mostra o diretório atual onde os logs de um dispositivo do Skype for Business Cloud Connector Edition são armazenados.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800821"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
O Get-CcApplianceLogDirectory cmdlet mostra o diretório atual onde os logs de um dispositivo do Skype for Business Cloud Connector Edition são armazenados.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a pasta atual onde os logs do dispositivo atual do Cloud Connector estão armazenados:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Get-CcApplianceLogDirectory cmdlet mostra o diretório atual onde os logs de um dispositivo do Cloud Connector estão armazenados. A pasta padrão é C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
Você pode alterar o diretório usando o Set-CcApplianceDirectory cmdlet. 
  
Observação: não há cmdlet que altera apenas o local da pasta de log sem alterar o diretório do dispositivo.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Get-CcApplianceLogDirectory cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Este comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

