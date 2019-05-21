---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'O cmdlet Export-CcRootCertificate exporta o Certificado de Autoridade de Certificação raiz para um arquivo local no servidor host do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: 7d6d0978698b4b20b570107b51c9a89ff237b730
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287374"
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
|Path  <br/> |Obrigatório  <br/> |System.String  <br/> |Caminho do arquivo em que o certificado será armazenado.   <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Export-CcRootCertificate não aceita a entrada por pipeline.  
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

Nenhum
  

