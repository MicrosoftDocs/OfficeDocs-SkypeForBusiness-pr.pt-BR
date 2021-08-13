---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: O Update-CcServerCertificate cmdlet renova os certificados para Skype for Business Cloud Connector Edition quando eles estão próximos de expirar ou já expiraram.
ms.openlocfilehash: 0545f4923a4f1abd654674024313c6f22665cb7123d87d9d21c3676452bd8fcf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344520"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
O Update-CcServerCertificate cmdlet renova os certificados para Skype for Business Cloud Connector Edition quando eles estão próximos de expirar ou já expiraram. 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir renova os certificados para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda quando os certificados estão quase expirados ou já expirados:
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo renova os certificados para Servidor de Mediação e Servidor de Borda quando eles estão próximos da expiração ou já expiraram:
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Os certificados internos do Cloud Connector emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos após a emissão de um serviço de Autoridade de Certificação. Se os certificados estão próximos da expiração ou já expiraram, execute o cmdlet Update-CcServerCertificate para renovar os certificados. 
  
Este comando substitui o cmdlet Renew-CcServerCertificate no Cloud Connector 2.0 e versões posteriores.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Funções  <br/> |Opcional  <br/> |System.Array  <br/> | Matriz de funções de servidor do Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Update-CcServerCertificate cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

