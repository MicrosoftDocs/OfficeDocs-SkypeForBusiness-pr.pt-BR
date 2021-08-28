---
title: Set-CcExternalCertificateFilePath
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
ms.localizationpriority: medium
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: O Set-CcExternalCertificateFilePath cmdlet especifica o caminho onde o certificado para o Servidor de Mediação ou Servidor de Borda está armazenado.
ms.openlocfilehash: b8555d3a3c6770481e1a66f79fd4a1060d3d9936
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615517"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
O Set-CcExternalCertificateFilePath cmdlet especifica o caminho onde o certificado para o Servidor de Mediação ou Servidor de Borda está armazenado.
  
Esse certificado é necessário durante a implantação ou ao adicionar novos dispositivos de Skype for Business Cloud Connector Edition. O comando também permite importar um novo certificado para o Servidor de Mediação após a implantação.
  
Este cmdlet se aplica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir define o caminho do certificado para o Servidor de Borda:
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo define o caminho do certificado para o Servidor de Mediação:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Exemplo 3

O próximo exemplo atualiza o certificado para o Servidor de Mediação:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Durante a implantação ou durante a modificação da topologia, você precisa especificar o caminho para o certificado do Servidor de Borda e, opcionalmente, para o certificado do Servidor de Mediação. 
  
O certificado para o Servidor de Mediação será necessário se o TLS for usado entre o gateway (s) e o Servidor de Mediação. Quando você implanta um dispositivo do Cloud Connector e deseja implantar o TLS, você só pode especificar o caminho para o certificado que será implantado no Servidor de Mediação. No entanto, se você quiser atualizar o certificado de Mediação em um dispositivo já implantado, será necessário especificar o caminho e o parâmetro -Import. Para ver o caminho, use o Get-CCExternalCertificateFilePath cmdlet.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Target <br/> | Obrigatório <br/> |System.String  <br/> |Tipo de caminho de arquivo solicitado. Os tipos incluem:  <br/> EdgeServer (padrão)  <br/> MediationServer  <br/> |
|Importar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Indica que o certificado deve ser importado para o Servidor de Mediação. Esse parâmetro não será necessário se você implantar um dispositivo pela primeira vez. O parâmetro é necessário se você quiser alterar o certificado existente em uma versão já implantada.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

O Set-CcExternalCertificateFilePath cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

