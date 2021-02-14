---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa a configuração do Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do Cloud Connector.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799851"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importa a configuração do Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do Cloud Connector.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir copia o CloudConnector.ini do diretório de dispositivos da instância do Cloud Connector para o diretório %SystemDrive%\ProgramData\CloudConnector:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="Examples"> </a>

Este cmdlet copia o CloudConnector.ini do diretório de dispositivos do dispositivo do Cloud Connector para o diretório %SystemDrive%\ProgramData\CloudConnector. O diretório de dispositivos é especificado usando o Set-CcApplianceDirectory cmdlet. O cmdlet substituirá qualquer arquivo existente em %SystemDrive%\ProgramData\CloudConnector. Este comando se aplica à versão 2.0.1 e posterior do Cloud Connector Edition.
  
## <a name="parameters"></a>Parâmetros
<a name="Examples"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Substituir o arquivo existente em %SystemDrive%\ProgramData\CloudConnector sem notificação.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="Examples"> </a>

Nenhum. O Import-CcConfiguration cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="Examples"> </a>

Nenhum.
  
## <a name="see-also"></a>Confira também
<a name="Examples"> </a>

Export-CcConfiguration
  

