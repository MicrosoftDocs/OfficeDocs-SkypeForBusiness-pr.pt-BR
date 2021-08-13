---
title: Renew-CcCACertificate
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
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: O Renew-CcCACertificate cmdlet renova o certificado Skype for Business Cloud Connector Edition CA raiz que está quase expirando ou já expirou. Esse comando foi alterado para Update-CcCACertificate no Cloud Connector 2.0 e versões posteriores.
ms.openlocfilehash: 49b58e18d6393d5a3f9665fea98cba73f22d9c3259f0036dc93dce9dbf67e567
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340777"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
O Renew-CcCACertificate cmdlet renova o certificado Skype for Business Cloud Connector Edition CA raiz que está quase expirando ou já expirou. Esse comando foi alterado para Update-CcCACertificate no Cloud Connector 2.0 e versões posteriores.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir renova o certificado ca raiz: 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O certificado ca raiz do Cloud Connector é válido por cinco anos a partir da data em que o serviço de Autoridade de Certificação está instalado.
  
Se o certificado raiz estiver próximo da expiração ou já tiver expirado, execute o cmdlet Renew-CcCACertificate para renovar o certificado. Depois que o certificado raiz for renovado, o AD Server, o Armazenamento de Gerenciamento Central e o Servidor de Borda serão emitidos automaticamente novos certificados.
  
Se houver vários dispositivos no mesmo site PSTN, execute o cmdlet Renew-CcCACertificate em todos os dispositivos do mesmo site PSTN.
  
Como última etapa, execute Export-CcRootCertificate para exportar o certificado raiz para um arquivo local no primeiro dispositivo e, em seguida, copie e instale o certificado exportado para seus gateways PSTN.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Renew-CcCACertificate cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

