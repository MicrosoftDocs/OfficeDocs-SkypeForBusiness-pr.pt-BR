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
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa a configuração do Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do conector da nuvem.
ms.openlocfilehash: c72a72351ecb6936832bc5d6a2493c5fa8dfe324
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003331"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importa a configuração do Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do conector da nuvem.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir copia o CloudConnector. ini do diretório do aplicativo da instância do conector de nuvem para o diretório%SystemDrive%\ProgramData\CloudConnector:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="Examples"> </a>

Esse cmdlet copia o CloudConnector. ini do diretório do aparelho do aparelho do conector de nuvem para o diretório%SystemDrive%\ProgramData\CloudConnector. Esse diretório é especificado usando o cmdlet Set-CcApplianceDirectory. O cmdlet substituirá qualquer arquivo existente no%SystemDrive%\ProgramData\CloudConnector. Este comando se aplica à versão 2.0.1 e posterior do Cloud Connector Edition.
  
## <a name="parameters"></a>Parâmetros
<a name="Examples"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Forçar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Substituir o arquivo existente no%SystemDrive%\ProgramData\CloudConnector sem notificação.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="Examples"> </a>

Nenhum. O cmdlet Import-CcConfiguration não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="Examples"> </a>

Nenhum.
  
## <a name="see-also"></a>Consulte também
<a name="Examples"> </a>

Export-CcConfiguration
  

