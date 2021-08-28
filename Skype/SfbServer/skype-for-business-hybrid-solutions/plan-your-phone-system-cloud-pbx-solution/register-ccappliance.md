---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: O Register-CcAppliance registra informações do dispositivo em um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes de poder ser implantado e gerenciado pelo serviço Skype for Business Cloud Connector Edition de gerenciamento.
ms.openlocfilehash: 159e74f91ca26cd0f8bdd214c9cd6ac45b5c1196
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589955"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
O Register-CcAppliance registra informações do dispositivo em um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes de poder ser implantado e gerenciado pelo serviço Skype for Business Cloud Connector Edition de gerenciamento.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir registra as informações atuais do dispositivo para uma configuração de locatário online:
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo verifica a configuração de registro localmente sem se conectar a uma configuração de locatário online:
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>Exemplo 3

O próximo exemplo registra o dispositivo atual com o nome "Appliance1" no site PSTN "Site1":
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Você deve fornecer o nome e a senha da conta de administrador do locatário. Use a conta que você criou para o gerenciamento online do Cloud Connector. 
  
Na versão 1.4.2 e anterior, siga as instruções para fornecer a senha de certificado externo, senha de administrador de modo seguro, senha de administrador de domínio e senha de administrador de VM. 
  
Na versão 2.0 e posterior, siga as instruções para fornecer a senha de certificado externo, a senha do CceService e a senha caBackupFile.
  
No final do registro, reinicie o serviço de gerenciamento do Cloud Connector e faça logon nos serviços como conta CceService.
  
SiteName combinado com o FQDN externo do Servidor de Borda no arquivo CloudConnector.ini é considerado uma identidade de site PSTN. Se o SiteName ou o FQDN externo do Servidor de Borda tiver sido usado para registrar um site, um novo site será criado para esse dispositivo em uma configuração de locatário online. Se uma identidade de site PSTN for encontrada, um site PSTN usará essa identidade e o dispositivo será registrado nesse site PSTN. 
  
Na seguinte situação, o cmdlet falhará e indicará que o Site1 já está registrado: 
  
- SiteName é Site1 e o FQDN externo do Servidor de Borda é edgserver1.contoso.com. 
    
- Um site PSTN cujo SiteName é Site1 e FQDN externo do Servidor de Borda é edgserver.contoso.com.
    
- Um site PSTN cujo SiteName é NewSite e O FQDN externo do Servidor de Borda edgserver1.contoso.com foi registrado. 
    
ApplianceName combinado com o FQDN do Servidor de Mediação no CloudConnector.ini é considerado uma Identidade do Dispositivo. Se o ApplianceName ou o FQDN do Servidor de Mediação tiver sido usado para registrar um dispositivo, um novo dispositivo será criado na configuração de locatário online. Se o dispositivo já estiver registrado, o cmdlet falhará.
  
Na seguinte situação, o cmdlet falhará e indicará que o dispositivo já está registrado: 
  
- ApplianceName é Appliance1 e o FQDN do servidor de mediação ms1.vdomain.com.
    
- No site PSTN atual, se um dispositivo cujo nome Appliance1 e FQDN do Servidor de Mediação for ms.vdomain.com ou um dispositivo cujo nome NewAppliance e FQDN do servidor de mediação for ms1.vdomain.com tiver sido registrado.
    
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Opcional  <br/> |System.String  <br/> |Nome do site PSTN ao qual o dispositivo está registrado. O valor padrão é o valor SiteName no arquivo CloudConnector.ini arquivo.  <br/> |
|ApplianceName  <br/> |Opcional  <br/> |System.String  <br/> |Nome do dispositivo atual. Valor padrão é o nome do computador do servidor host.  <br/> |
|Local  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Verifique configurações para registro localmente sem se conectar à configuração de locatário online.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Register-CcAppliance cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

