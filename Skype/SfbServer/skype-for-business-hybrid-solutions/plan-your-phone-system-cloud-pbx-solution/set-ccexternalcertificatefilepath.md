---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: O cmdlet Set-CcExternalCertificateFilePath especifica o caminho onde o certificado para o Servidor de Mediação ou para o Servidor de Borda é armazenado.
ms.openlocfilehash: 059d0f2fbf5fee708ceccd0d6e10ad4286fe4f85
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895346"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
O cmdlet Set-CcExternalCertificateFilePath especifica o caminho onde o certificado para o Servidor de Mediação ou para o Servidor de Borda é armazenado.
  
Este certificado é necessário durante a implantação ou adição de novos dispositivos do Skype for Business Cloud Connector Edition. O comando também permite a importação de um novo certificado para o Servidor de Mediação após a implantação.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1 e 1.4.2.
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O seguinte exemplo mostra o caminho do certificado para o Servidor de Borda:
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Exemplo 2

O exemplo seguinte define o caminho do certificado para o Servidor de Mediação:
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Exemplo 3

O exemplo seguinte atualiza o certificado do Servidor de Mediação:
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Durante a implantação ou ao modificar a topologia, você precisa especificar o caminho para o certificado do Servidor de Borda e, opcionalmente, para o certificado do Servidor de Mediação. 
  
O certificado do Servidor de Mediação será necessário se o TLS for usado entre os gateways e o Servidor de Mediação. Quando você implantar um aparelho de conector de nuvem e deseja implantar o TLS, você pode apenas especificar o caminho para o certificado que será implantado no servidor de mediação. No entanto, se você desejar atualizar o certificado de mediação em um dispositivo já implantado, você deve especificar o caminho e o parâmetro -Import. Para ver o caminho, use o cmdlet Get-CCExternalCertificateFilePath.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Destino  <br/> | Obrigatório <br/> |System.String  <br/> |Digite o caminho do arquivo solicitado. Os tipos incluem:  <br/> EdgeServer (padrão)  <br/> MediationServer  <br/> |
|Importar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Indica que o certificado deve ser importado para o Servidor de Mediação. Este parâmetro não será necessário se você implantar um dispositivo pela primeira vez. O parâmetro será necessário se você desejar alterar o certificado existente em uma versão já implantada.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

O cmdlet Set-CcExternalCertificateFilePath não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

