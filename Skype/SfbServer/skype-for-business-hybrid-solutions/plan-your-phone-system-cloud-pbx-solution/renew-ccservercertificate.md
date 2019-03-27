---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 'O cmdlet Renew-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão prestes a expirar ou já expiraram. Este comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores. '
ms.openlocfilehash: ad366bdf7f6c27552a8e7621ee9244762dd864eb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894814"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
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
|Funções  <br/> |Opcional  <br/> |System.Array   <br/> | Matriz das funções do servidor do Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Renew-CcServerCertificate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

