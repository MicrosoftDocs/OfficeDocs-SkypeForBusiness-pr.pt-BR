---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: O Get-CcCredential cmdlet retorna a credencial da implantação Skype for Business Cloud Connector Edition atual.
ms.openlocfilehash: 158f6e35f667410a0070e2f7030932bd6fc35ade
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596355"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
O Get-CcCredential cmdlet retorna a credencial da implantação Skype for Business Cloud Connector Edition atual. 
  
Com a versão 2.0 e posterior, você também pode usar o parâmetro -DisplayPassword para mostrar as senhas para TenantAdmin, DomainAdmin e VMAdmin.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir retorna a credencial do administrador de domínio do domínio da máquina virtual do Cloud Connector:
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Get-CcCredential cmdlet retorna as informações de credencial sobre o tipo de conta especificado. Essas credenciais são especificadas pelo administrador que executa os cmdlets Register-CcAppliance e Install-CcAppliance ao implantar o dispositivo atual. 
  
O Get-CcCredential cmdlet retorna uma instância do objeto System.Management.Automation.PSCredential. A propriedade password do objeto de retorno é System.Security.SecureString.
  
Se você quiser obter o texto claro da senha do administrador de domínio, certifique-se de que a senha é entrada pela sua conta de logon atual no servidor host e abra um console do PowerShell como administrador e execute o script abaixo:
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Obrigatório  <br/> | System.String <br/> | O valor AccountType pode ser um dos seguintes: <br/>  VmAdmin: o administrador local de máquinas virtuais do Cloud Connector. <br/>  DomainAdmin: Administrador de domínio do domínio da máquina virtual do Cloud Connector. <br/>  SafeModeAdmin: SafeModeAdmin do controlador de domínio da máquina virtual do Cloud Connector. <br/>  ExternalCert: conta do certificado externo instalado no Servidor de Borda. <br/>  TenantAdmin: Administrador do locatário do O365. <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Get-CcCredential cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

O Get-CcCredential cmdlet retorna uma instância do objeto System.Management.Automation.PSCredential.
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

