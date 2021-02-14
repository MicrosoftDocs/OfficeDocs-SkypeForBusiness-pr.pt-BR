---
title: Update-CcCACertificate
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
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: O Update-CcCACertificate cmdlet renova o certificado de AC raiz do Skype for Business Cloud Connector Edition que está próximo de expirar ou já expirou.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824115"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
O Update-CcCACertificate cmdlet renova o certificado de AC raiz do Skype for Business Cloud Connector Edition que está próximo de expirar ou já expirou. 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>Parâmetros

Nenhum.
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir renova o certificado ca raiz: 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O certificado de autoridade de certificação raiz do Cloud Connector é válido por cinco anos a partir da data em que o serviço de Autoridade de Certificação está instalado.
  
Se o certificado raiz estiver próximo de expirar ou já tiver expirado, execute o Update-CcCACertificate cmdlet para renovar o certificado. Depois que o certificado raiz for renovado, o Servidor do AD, o Armazenamento de Gerenciamento Central e o Servidor de Borda receberão novos certificados automaticamente.
  
Se houver vários dispositivos no mesmo site PSTN, execute o cmdlet Update-CcCACertificate em todos os dispositivos do mesmo site PSTN.
  
Como última etapa, execute Export-CcRootCertificate para exportar o certificado raiz para um arquivo local no primeiro dispositivo e, em seguida, copie e instale o certificado exportado para seus gateways PSTN.
  
Este comando substitui o Renew-CcCACertificate cmdlet no Cloud Connector 2.0 e versões posteriores.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Update-CcCACertificate cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum. 
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

