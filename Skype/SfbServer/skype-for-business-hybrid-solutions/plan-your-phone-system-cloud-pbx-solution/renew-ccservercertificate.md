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
ms.localizationpriority: medium
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: O Renew-CcServerCertificate cmdlet renova os certificados para Skype for Business Cloud Connector Edition quando eles estão próximos de expirar ou já expiraram. Esse comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores.
ms.openlocfilehash: 564f947462248bb65c8514c9699f2f867312c365
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589935"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
O Renew-CcServerCertificate cmdlet renova os certificados para Skype for Business Cloud Connector Edition quando eles estão próximos de expirar ou já expiraram. Esse comando foi alterado para Update-CcServerCertificate no Cloud Connector 2.0 e versões posteriores. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir renova os certificados para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda quando os certificados estão quase expirados ou já expirados:
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo renova os certificados para Servidor de Mediação e Servidor de Borda quando eles estão próximos da expiração ou já expiraram:
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Os certificados internos do Cloud Connector emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos após a emissão de um serviço de Autoridade de Certificação. Se os certificados estão próximos da expiração ou já expiraram, execute o cmdlet Renew-CcServerCertificate para renovar os certificados. 
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|Funções  <br/> |Opcional  <br/> |System.Array  <br/> | Matriz de funções de servidor do Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Renew-CcServerCertificate cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

