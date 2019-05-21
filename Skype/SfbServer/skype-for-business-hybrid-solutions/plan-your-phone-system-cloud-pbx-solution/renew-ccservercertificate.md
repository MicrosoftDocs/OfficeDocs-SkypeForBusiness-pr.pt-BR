---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 'O cmdlet Renew-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão prestes a expirar ou já expiraram. Este comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores. '
ms.openlocfilehash: 611eeb648c88411afa5d74cc7564703a5e37e9bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287059"
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

Os certificados internos do conector de nuvem emitidos para o repositório de gerenciamento central, servidor de mediação e Edge Server são válidos por dois anos após serem emitidos a partir de um serviço de autoridade de certificação. Se os certificados estiverem prestes a expirar ou já expiraram, execute cmdlet Renew-CcServerCertificate para renovar os certificados. 
  
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
  

