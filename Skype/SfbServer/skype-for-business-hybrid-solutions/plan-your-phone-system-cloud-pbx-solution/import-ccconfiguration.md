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
description: Importa a configuração Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do Cloud Connector.
ms.openlocfilehash: 4ac32f460c2c493f5d78f1a38adcdd0728763bbbcf57a67470823fb88d407d09
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349493"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importa a configuração Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do Cloud Connector.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir copia o CloudConnector.ini do diretório do dispositivo da instância do Cloud Connector para %SystemDrive%\ProgramData\Diretório CloudConnector:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="Examples"> </a>

Este cmdlet copia o CloudConnector.ini do diretório do dispositivo do dispositivo Cloud Connector para o diretório %SystemDrive%\ProgramData\CloudConnector. O diretório do dispositivo é especificado usando o cmdlet Set-CcApplianceDirectory de usuário. O cmdlet substituirá qualquer arquivo existente em %SystemDrive%\ProgramData\CloudConnector. Este comando se aplica ao Cloud Connector Edition versão 2.0.1 e posterior.
  
## <a name="parameters"></a>Parâmetros
<a name="Examples"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Substituir o arquivo existente em %SystemDrive%\ProgramData\CloudConnector sem notificação.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="Examples"> </a>

Nenhum. O Import-CcConfiguration cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="Examples"> </a>

Nenhum.
  
## <a name="see-also"></a>Confira também
<a name="Examples"> </a>

Export-CcConfiguration
  

