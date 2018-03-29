---
title: Get-CcExternalCertificateFilePath
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: O cmdlet Get-CcExternalCertificateFilePath retorna o caminho do arquivo do certificado externo para a implantação do Skype for Business Cloud Connector Edition. O usuário prepara este certificado.
ms.openlocfilehash: 9ceba99310ab25676a7cd3938ed386c4752f453e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
O cmdlet Get-CcExternalCertificateFilePath retorna o caminho do arquivo do certificado externo para a implantação do Skype for Business Cloud Connector Edition. O usuário prepara este certificado.
  
Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O seguinte exemplo mostra o caminho do certificado para o Servidor de Borda:
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Exemplo 2

O seguinte exemplo mostra o certificado definido para o Servidor de Mediação:
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Durante a implantação ou ao modificar a topologia, você precisa especificar o caminho para o certificado do Servidor de Borda e, opcionalmente, para o Servidor de Mediação. O certificado para o Servidor de Mediação será obrigatório se o TLS for usado entre o(s) gateway(s) e o Servidor de Mediação. Para altera o caminho, use cmdlet o Set-CcExternalCertificateFilePath.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Destino   <br/> |Opcional  <br/> | System.Management.Automation.SwitchParameter <br/> |Digite o caminho do arquivo solicitado. Os tipos incluem:  <br/> EdgeServer (padrão)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

O cmdlet Get-CcExternalCertificateFilePath não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

O comando retorna um caminho de arquivo.
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

