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
ms.localizationpriority: medium
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: O Update-CcCACertificate cmdlet renova o certificado Skype for Business Cloud Connector Edition CA raiz que está quase expirando ou já expirou.
ms.openlocfilehash: 824959ab053c7eb7cc71eb60a5d6ecbeb2c7a847
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628403"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
O Update-CcCACertificate cmdlet renova o certificado Skype for Business Cloud Connector Edition CA raiz que está quase expirando ou já expirou. 
  
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

O certificado ca raiz do Cloud Connector é válido por cinco anos a partir da data em que o serviço de Autoridade de Certificação está instalado.
  
Se o certificado raiz estiver próximo da expiração ou já tiver expirado, execute o cmdlet Update-CcCACertificate para renovar o certificado. Depois que o certificado raiz for renovado, o AD Server, o Armazenamento de Gerenciamento Central e o Servidor de Borda serão emitidos automaticamente novos certificados.
  
Se houver vários dispositivos no mesmo site PSTN, execute o cmdlet Update-CcCACertificate em todos os dispositivos do mesmo site PSTN.
  
Como última etapa, execute Export-CcRootCertificate para exportar o certificado raiz para um arquivo local no primeiro dispositivo e, em seguida, copie e instale o certificado exportado para seus gateways PSTN.
  
Este comando substitui o cmdlet Renew-CcCACertificate no Cloud Connector 2.0 e versões posteriores.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Update-CcCACertificate cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum. 
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

