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
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: O cmdlet Get-CcApplianceLogDirectory mostra o diretório atual em que os logs do dispositivo do Skype for Business Cloud Connector Edition são armazenados.
ms.openlocfilehash: a8b7e1b13302bec27c2fe784804f8f43fe2e023c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003391"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
O cmdlet Get-CcApplianceLogDirectory mostra o diretório atual em que os logs do dispositivo do Skype for Business Cloud Connector Edition são armazenados.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra a pasta atual em que os logs do aplicativo do conector de nuvem atual são armazenados:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Get-CcApplianceLogDirectory mostra o diretório atual em que os logs para um aparelho de conector de nuvem são armazenados. A pasta padrão é C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot\Logs. 
  
Você pode alterar o diretório usando o cmdlet Set-CcApplianceDirectory.  
  
Observação: não há cmdlet que altere somente o local da pasta de log sem alterar o diretório do dispositivo.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Get-CcApplianceLogDirectory não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Este comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

