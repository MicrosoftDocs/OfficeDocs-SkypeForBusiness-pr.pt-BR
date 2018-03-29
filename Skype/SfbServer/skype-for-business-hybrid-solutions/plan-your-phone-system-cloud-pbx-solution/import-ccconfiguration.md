---
title: Import-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa o Skype para que a configuração do conector de nuvem Business Edition de um arquivo local para o servidor de host do conector de nuvem.
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importa o Skype para que a configuração do conector de nuvem Business Edition de um arquivo local para o servidor de host do conector de nuvem.
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir copia o CloudConnector.ini do diretório de aparelho da instância do conector de nuvem para o diretório de %SystemDrive%\ProgramData\CloudConnector:
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="Examples"> </a>

Este cmdlet copia o CloudConnector.ini do diretório appliance do aparelho de conector de nuvem para o diretório %SystemDrive%\ProgramData\CloudConnector. Esse diretório é especificado usando o cmdlet Set-CcApplianceDirectory. O cmdlet substituirá qualquer arquivo existente na pasta % SystemDrive%\ProgramData\CloudConnector. Este comando se aplica a nuvem conector Edition versão 2.0.1 e posterior.
  
## <a name="parameters"></a>Parâmetros
<a name="Examples"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Forçar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Substitua arquivo existente no %SystemDrive%\ProgramData\CloudConnector sem notificação.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Nenhum. O cmdlet Import-CcConfiguration não aceita a entrada.
  
## <a name="return-types"></a>Tipos de retorno
<a name="Examples"> </a>

Nenhum.
  
## <a name="see-also"></a>Consulte também
<a name="Examples"> </a>

Export-CcConfiguration
  

