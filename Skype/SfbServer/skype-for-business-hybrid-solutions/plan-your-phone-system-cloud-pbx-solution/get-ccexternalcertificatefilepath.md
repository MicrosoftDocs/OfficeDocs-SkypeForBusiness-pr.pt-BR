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
ms.localizationpriority: medium
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: O Get-CcExternalCertificateFilePath cmdlet retorna o caminho de arquivo de certificado externo para a implantação Skype for Business Cloud Connector Edition de certificação. O usuário prepara esse certificado.
ms.openlocfilehash: 9b06958d68d73bc68fc0fda4e681af2e7b9b4f9e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622033"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
O Get-CcExternalCertificateFilePath cmdlet retorna o caminho de arquivo de certificado externo para a implantação Skype for Business Cloud Connector Edition de certificação. O usuário prepara esse certificado.
  
Este cmdlet se aplica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
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

Durante a implantação ou ao modificar a topologia, você precisa especificar o caminho para o certificado do Servidor de Borda e, opcionalmente, para o Servidor de Mediação. O certificado para o Servidor de Mediação será necessário se o TLS for usado entre o gateway (s) e o Servidor de Mediação. Para alterar o caminho, use o Set-CcExternalCertificateFilePath cmdlet.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Target  <br/> |Opcional  <br/> | System.Management.Automation.SwitchParameter <br/> |Tipo de caminho de arquivo solicitado. Os tipos incluem:  <br/> EdgeServer (padrão)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

O Get-CcExternalCertificateFilePath cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

O comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

