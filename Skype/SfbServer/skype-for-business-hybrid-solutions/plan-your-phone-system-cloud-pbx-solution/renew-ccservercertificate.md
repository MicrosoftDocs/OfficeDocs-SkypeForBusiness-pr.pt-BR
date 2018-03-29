---
title: Renovar-CcServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: O cmdlet Renew-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão prestes a expirar ou já expiraram. Este comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores.
ms.openlocfilehash: 3d895a24c4cc8b400aa48ce394324435cfbb3979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="renew-ccservercertificate"></a>Renovar-CcServerCertificate
 
O cmdlet Renew-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão prestes a expirar ou já expiraram. Este comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores. 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte renova os certificados para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda quando estão prestes a expirar ou já expiraram:
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a>Exemplo 2

O exemplo seguinte renova os certificados para o Servidor de Mediação e o Servidor de Borda quando estão prestes a expirar ou já expiraram:
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Conector de nuvem internos certificados emitidos para o repositório de gerenciamento Central, o servidor de mediação e o servidor de borda são válidas por dois anos depois que eles são emitidos a partir de um serviço de autoridade de certificação. Se os certificados estiverem prestes a expirar ou já expiraram, execute cmdlet Renew-CcServerCertificate para renovar os certificados. 
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Funções  <br/> |Opcional  <br/> |System. Array  <br/> | Matriz das funções do servidor do Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Renew-CcServerCertificate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renovar-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

