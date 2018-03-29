---
title: Export-CcRootCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: O cmdlet Export-CcRootCertificate exporta o Certificado de Autoridade de Certificação raiz para um arquivo local no servidor host do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 9af3701fd89cf881b4f966c2b00500ad4e55bc9b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
O cmdlet Export-CcRootCertificate exporta o Certificado de Autoridade de Certificação raiz para um arquivo local no servidor host do Skype for Business Cloud Connector Edition. 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir define o parâmetro Path como um caminho de diretório, não um caminho de arquivo. Ele gera o arquivo c:\test\CCERootCertificates.p7b.
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Export-CcRootCertificate permite que você salve os certificados raiz e intermediário em um caminho de arquivo. Isso pode ser útil em um cenário de recuperação de desastre. 
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |Obrigatório  <br/> |System. String  <br/> |Caminho do arquivo em que o certificado será armazenado.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Export-CcRootCertificate não aceita a entrada por pipeline. 
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

Nenhum
  

