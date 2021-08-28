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
ms.localizationpriority: medium
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: O Get-CcApplianceLogDirectory cmdlet mostra o diretório atual onde os logs de um Skype for Business Cloud Connector Edition estão armazenados.
ms.openlocfilehash: 826599ab785d8b4d74f0792c6091b2a5e78b74e3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580355"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
O Get-CcApplianceLogDirectory cmdlet mostra o diretório atual onde os logs de um Skype for Business Cloud Connector Edition estão armazenados.
  
Este cmdlet se aplica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a pasta atual onde os logs do dispositivo atual do Cloud Connector são armazenados:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Get-CcApplianceLogDirectory cmdlet mostra o diretório atual onde os logs de um dispositivo Cloud Connector são armazenados. A pasta padrão é C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
Você pode alterar o diretório usando o Set-CcApplianceDirectory cmdlet. 
  
Observação: não há cmdlet que altera apenas o local da pasta de log sem alterar o diretório do dispositivo.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Get-CcApplianceLogDirectory cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Este comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

