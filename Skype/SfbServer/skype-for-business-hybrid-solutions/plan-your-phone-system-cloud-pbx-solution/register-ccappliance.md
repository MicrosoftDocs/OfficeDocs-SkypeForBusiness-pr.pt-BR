---
title: Register-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: O cmdlet Register-CcAppliance registra as informações do dispositivo para um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes de ele poder ser implantado e gerenciado pelo serviço de gerenciamento do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 8f1156ccd32b101e6eab957bc3ce7549a3bcc7d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
O cmdlet Register-CcAppliance registra as informações do dispositivo para um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes de ele poder ser implantado e gerenciado pelo serviço de gerenciamento do Skype for Business Cloud Connector Edition.
  
```
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O seguinte exemplo registra as informações atuais do dispositivo para uma configuração de locatário online:
  
```
Register-CcAppliance
```

### <a name="example-2"></a>Exemplo 2

O exemplo a seguir verifica a configuração para registro local sem conexão com uma configuração de locatário online:
  
```
Register-CcAppliance -Local
```

### <a name="example-3"></a>Exemplo 3

O exemplo a seguir registra o dispositivo atual com o nome e "Appliance1" para o site PSTN "Site1":
  
```
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Você deve fornecer o nome e a senha da conta do administrador do locatário. Use a conta que você criou para o gerenciamento on-line do conector de nuvem. 
  
Em versão 1.4.2 e anteriormente, siga as instruções para fornecer a senha do certificado externo, senha de admin do modo de segurança, senha de admin do domínio e senha de admin VM. 
  
Na versão 2.0 e posteriores, siga as instruções para fornecer a senha do certificado externo, a senha do CceService e a senha do CABackupFile.
  
No final do registro, reinicie o serviço de gerenciamento do conector de nuvem e faça logon no serviços como conta de CceService.
  
O SiteName combinado com o FQDN externo do Servidor de Borda no arquivo do CloudConnector.ini é considerado uma identidade do site PSTN. Se o SiteName ou o FQDN externo do Servidor de Borda não tiver sido usado para registrar um site, um novo site será criado para este dispositivo em uma configuração de locatário online. Se uma identidade do site PSTN for localizada, um site PSTN usará esta identidade e o dispositivo será registrado para este site PSTN.  
  
Na seguinte situação, o cmdlet falhará e indicará que o Site1 já foi registrado:  
  
- O SiteName é o Site1 e o FQDN externo do Servidor da Borda é edgserver1.contoso.com.  
    
- Um site PSTN cujo SiteName é o Site1 e o FQDN externo do Servidor da Borda é o edgserver1.contoso.com.
    
- Um site PSTN cujo SiteName é o NewSite e o FQDN externo do Servidor da Borda é o edgserver1.contoso.com foi registrado.  
    
O ApplianceName combinado com o FQDN do Servidor de Mediação no arquivo do CloudConnector.ini é considerado uma identidade do dispositivo. Se o ApplianceName ou o FQDN do Servidor de Mediação não tiver sido usado para registrar um dispositivo, um novo dispositivo será criado na configuração de locatário online. Se o dispositivo já estiver registrado, o cmdlet falhará.
  
Na seguinte situação, o cmdlet falhará e indicará que o dispositivo já foi registrado:  
  
- O ApplianceName é o Appliance1 e o FQDN do servidor de mediação é ms1.vdomain.com.
    
- No site PSTN atual, se um dispositivo cujo nome Appliance1 e o FQDN do Servidor de Mediação for ms.vdomain.com ou um dispositivo cujo nome NewAppliance e o FQDN do Servidor de Mediação for ms1.vdomain.com tiver sido registrado.
    
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Opcional  <br/> |System. String  <br/> |O nome do site PSTN com o qual o dispositivo foi registrado. O valor padrão é o SiteName no arquivo CloudConnector.ini.  <br/> |
|ApplianceName  <br/> |Opcional  <br/> |System. String  <br/> |Nome do dispositivo padrão. O valor padrão é o nome do computador do servidor host.  <br/> |
|Local  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Verifique as configurações para registro local sem conexão com a configuração de locatário online.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Register-CcAppliance não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Cancelar o registro de CcAppliance](unregister-ccappliance.md)
  
[Publicar-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Desinstalar-CcAppliance](uninstall-ccappliance.md)
  

