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
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: O Set-CcExternalCertificateFilePath cmdlet especifica o caminho onde o certificado para o Servidor de Mediação ou Servidor de Borda está armazenado.
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824195"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
O Set-CcExternalCertificateFilePath cmdlet especifica o caminho onde o certificado para o Servidor de Mediação ou Servidor de Borda está armazenado.
  
Esse certificado é necessário durante a implantação ou ao adicionar novos dispositivos do Skype for Business Cloud Connector Edition. O comando também permite importar um novo certificado para o Servidor de Mediação após a implantação.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
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

Durante a implantação ou ao modificar a topologia, você precisa especificar o caminho para o certificado do Servidor de Borda e, opcionalmente, para o certificado do Servidor de Mediação. 
  
O certificado para o Servidor de Mediação é necessário se o TLS for usado entre o (s) gateway(s) e o Servidor de Mediação. Quando você implanta um dispositivo do Cloud Connector e deseja implantar o TLS, só é possível especificar o caminho para o certificado que será implantado no Servidor de Mediação. No entanto, se você quiser atualizar o certificado de Mediação em um dispositivo já implantado, será necessário especificar o caminho e o parâmetro -Import. Para ver o caminho, use o Get-CCExternalCertificateFilePath cmdlet.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Target <br/> | Obrigatório <br/> |System.String  <br/> |Tipo de caminho de arquivo solicitado. Os tipos incluem:  <br/> EdgeServer (padrão)  <br/> MediationServer  <br/> |
|Importar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Indica que o certificado deve ser importado para o Servidor de Mediação. Esse parâmetro não será necessário se você implantar um dispositivo pela primeira vez. O parâmetro é necessário se você quiser alterar o certificado existente em uma versão já implantada.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

O Set-CcExternalCertificateFilePath cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

