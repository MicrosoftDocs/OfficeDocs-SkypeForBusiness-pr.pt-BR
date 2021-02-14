---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: O Get-CcExternalCertificateFilePath cmdlet retorna o caminho do arquivo de certificado externo para a implantação do Skype for Business Cloud Connector Edition. O usuário prepara esse certificado.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799901"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
O Get-CcExternalCertificateFilePath cmdlet retorna o caminho do arquivo de certificado externo para a implantação do Skype for Business Cloud Connector Edition. O usuário prepara esse certificado.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra o caminho do certificado para o Servidor de Borda:
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Exemplo 2

O exemplo a seguir mostra o conjunto de certificados para o Servidor de Mediação:
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Durante a implantação ou ao modificar a topologia, você precisa especificar o caminho para o certificado do Servidor de Borda e, opcionalmente, para o Servidor de Mediação. O certificado para o Servidor de Mediação é necessário se o TLS for usado entre o (s) gateway(s) e o Servidor de Mediação. Para alterar o caminho, use o Set-CcExternalCertificateFilePath cmdlet.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Target  <br/> |Opcional  <br/> | System.Management.Automation.SwitchParameter <br/> |Tipo de caminho de arquivo solicitado. Os tipos incluem:  <br/> EdgeServer (padrão)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

O Get-CcExternalCertificateFilePath cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

O comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

