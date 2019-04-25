---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: 'O cmdlet Get-CcCredential retorna a credencial da implantação atual do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: 651190f31ad44e0bb2375bbf4a70951c2011e1a7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233992"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
O cmdlet Get-CcCredential retorna a credencial da implantação atual do Skype for Business Cloud Connector Edition.  
  
Com a versão 2.0 e posterior, você também pode usar o parâmetro - DisplayPassword para mostrar as senhas para TenantAdmin, DomainAdmin e VMAdmin.
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte retorna a credencial do administrador do domínio da máquina virtual do Cloud Connector:
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Get-CcCredential retorna as informações de credencial sobre o tipo de conta especificado. Essas credenciais são especificadas pelo administrador que executa os cmdlets Register-CcAppliance e Install-CcAppliance ao implantar o dispositivo atual.  
  
O cmdlet Get-CcCredential retorna instâncias do objeto System.Management.Automation.PSCredential. A propriedade da senha do objeto de retorno é o System.Security.SecureString.
  
Se você deseja obter o texto claro da senha do administrador de domínio, verifique se a senha foi inserida pela conta de logon atual no servidor host e, em seguida, abra o console do PowerShell como administrador e execute o script a seguir:
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Obrigatório  <br/> | System.String <br/> | O valor AccountType pode ser um dos seguintes: <br/>  VmAdmin: o administrador local de máquinas virtuais do conector de nuvem. <br/>  DomainAdmin: o administrador de domínio da máquina virtual do Cloud Connector. <br/>  SafeModeAdmin: o SafeModeAdmin do controlador de domínio da máquina virtual do Cloud Connector. <br/>  ExternalCert: conta do certificado externo instalado no Servidor de Borda. <br/>  TenantAdmin: administrador do locatário do O365. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Get-CcCredential não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

O cmdlet Get-CcCredential retorna instâncias do objeto System.Management.Automation.PSCredential.
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

