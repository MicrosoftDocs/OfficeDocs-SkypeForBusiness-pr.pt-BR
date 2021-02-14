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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: O Renew-CcServerCertificate cmdlet renova os certificados para o Skype for Business Cloud Connector Edition quando eles estão próximos de expirar ou já expiraram. Esse comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824257"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
O Renew-CcServerCertificate cmdlet renova os certificados para o Skype for Business Cloud Connector Edition quando eles estão próximos de expirar ou já expiraram. Esse comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir renova os certificados para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda quando os certificados estão próximos de expirar ou já expiraram:
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo renova os certificados para o Servidor de Mediação e o Servidor de Borda quando eles estão próximos de expirar ou já expiraram:
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Os certificados internos do Cloud Connector emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos após a emissão de um serviço de Autoridade de Certificação. Se os certificados estão próximos de expirar ou já expiraram, execute o cmdlet Renew-CcServerCertificate para renovar os certificados. 
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Funções  <br/> |Opcional  <br/> |System.Array  <br/> | Matriz de funções de servidor do Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Renew-CcServerCertificate cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

