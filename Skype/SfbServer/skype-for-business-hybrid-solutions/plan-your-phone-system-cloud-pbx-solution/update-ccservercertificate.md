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
description: 'O cmdlet Update-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão próximos de expirar ou já tiverem expirado. '
ms.openlocfilehash: da52efcd3fdf6a0793e085098bf6f72725115e9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824105"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
O cmdlet Update-CcServerCertificate renova os certificados para o Skype for Business Cloud Connector Edition quando estão próximos de expirar ou já tiverem expirado.  
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte renova os certificados para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda quando estão prestes a expirar ou já expiraram:
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>Exemplo 2

O exemplo seguinte renova os certificados para o Servidor de Mediação e o Servidor de Borda quando estão prestes a expirar ou já expiraram:
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Os certificados internos do conector de nuvem emitidos para o repositório de gerenciamento central, servidor de mediação e Edge Server são válidos por dois anos após serem emitidos a partir de um serviço de autoridade de certificação. Se os certificados estiverem próximos de expirar ou já tiverem expirado, execute o cmdlet Update-CcServerCertificate para renovar os certificados. 
  
Este comando substitui o cmdlet Renew-CcServerCertificate no Cloud Connector 2.0 e versões posteriores.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Funções  <br/> |Opcional  <br/> |System.Array   <br/> | Matriz das funções do servidor do Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Update-CcServerCertificate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

