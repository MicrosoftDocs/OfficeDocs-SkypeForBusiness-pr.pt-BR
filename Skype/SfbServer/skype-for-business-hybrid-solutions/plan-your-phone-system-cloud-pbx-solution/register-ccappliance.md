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
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: O Register-CcAppliance cmdlet registra as informações do dispositivo em um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes que possa ser implantado e gerenciado pelo serviço de gerenciamento do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824297"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
O Register-CcAppliance cmdlet registra as informações do dispositivo em um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes que possa ser implantado e gerenciado pelo serviço de gerenciamento do Skype for Business Cloud Connector Edition.
  
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

O próximo exemplo verifica a configuração do registro localmente sem se conectar a uma configuração de locatário online:
  
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
  
Na versão 1.4.2 e anteriores, siga as instruções para fornecer a senha do certificado externo, a senha do administrador do modo de segurança, a senha do administrador do domínio e a senha do administrador da VM. 
  
Na versão 2.0 e posteriores, siga as instruções para fornecer a senha do certificado externo, a senha do CceService e a senha do CABackupFile.
  
No final do registro, reinicie o serviço de gerenciamento do Cloud Connector e faça logon nos serviços como conta do CceService.
  
SiteName combinado com o FQDN externo do Servidor de Borda no arquivo CloudConnector.ini é considerado uma identidade de site PSTN. Se o SiteName ou o FQDN externo do Servidor de Borda não tiver sido usado para registrar um site, um novo site será criado para esse dispositivo em uma configuração de locatário online. Se uma identidade de site PSTN for encontrada, um site PSTN usará essa identidade e o dispositivo será registrado nesse site PSTN. 
  
Na seguinte situação, o cmdlet falhará e indicará que o Site1 já está registrado: 
  
- SiteName é o Site1 e o FQDN externo do Servidor de Borda edgserver1.contoso.com. 
    
- Um site PSTN cujo SiteName é Site1 e o FQDN externo do Servidor de Borda é edgserver.contoso.com.
    
- Um site PSTN cujo SiteName é NewSite e o FQDN externo do Servidor de Borda edgserver1.contoso.com foi registrado. 
    
ApplianceName combinado com o FQDN do Servidor de Mediação CloudConnector.ini arquivo é considerado uma Identidade do Dispositivo. Se o ApplianceName ou o FQDN do Servidor de Mediação não tiver sido usado para registrar um dispositivo, um novo dispositivo será criado na configuração de locatário online. Se o dispositivo já estiver registrado, o cmdlet falhará.
  
Na seguinte situação, o cmdlet falhará e indicará que o dispositivo já está registrado: 
  
- ApplianceName é Appliance1 e o FQDN do servidor de Mediação ms1.vdomain.com.
    
- No site PSTN atual, se um dispositivo cujo nome Appliance1 e FQDN do Servidor de Mediação for ms.vdomain.com ou um dispositivo cujo nome For NewAppliance e FQDN do servidor de Mediação ms1.vdomain.com tiver sido registrado.
    
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Opcional  <br/> |System.String  <br/> |Nome do site PSTN no qual o dispositivo está registrado. O valor padrão é SiteName no arquivo CloudConnector.ini arquivo.  <br/> |
|ApplianceName  <br/> |Opcional  <br/> |System.String  <br/> |Nome do dispositivo atual. O valor padrão é o nome do computador do servidor host.  <br/> |
|Local  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Verifique as configurações de registro localmente sem se conectar à configuração de locatário online.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Register-CcAppliance cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

