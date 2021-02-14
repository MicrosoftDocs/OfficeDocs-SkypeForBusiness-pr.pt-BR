---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: O Unregister-CcAppliance o cmdlet não tem o registro do dispositivo atual do Skype for Business Cloud Connector Edition de um site PSTN na configuração de locatário online.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824125"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
O Unregister-CcAppliance o cmdlet não tem o registro do dispositivo atual do Skype for Business Cloud Connector Edition de um site PSTN na configuração de locatário online.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir não registrou um dispositivo atual da configuração de locatário online:
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo verifica a configuração para o registro local sem se conectar à configuração de locatário online:
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Exemplo 3

O próximo exemplo desastana o registro do dispositivo atual com o nome "Appliance1" para o site PSTN "Site1":
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Semelhante ao cmdlet Register-CcAppliance, o SiteName combinado com o FQDN externo do Servidor de Borda no arquivo CloudConnector.ini é considerado uma identidade de site PSTN. Da mesma forma, ApplianceName combinado com o FQDN do Servidor de Mediação no arquivo CloudConnector.ini é considerado uma identidade de dispositivo.
  
Após o registro do dispositivo, reinicie o serviço de gerenciamento do Cloud Connector e faça logon como a conta NetworkService.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Opcional  <br/> |System.String  <br/> |Nome do site PSTN em que o dispositivo está registrado. O valor padrão é SiteName no CloudConnector.ini arquivo.  <br/> |
|ApplianceName  <br/> |Opcional  <br/> |System.String  <br/> |Nome do dispositivo atual. O valor padrão é o nome do computador do servidor host.  <br/> |
|Local  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Verifique a configuração do registro localmente sem se conectar a uma configuração de locatário online.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Unregister-CcAppliance cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

