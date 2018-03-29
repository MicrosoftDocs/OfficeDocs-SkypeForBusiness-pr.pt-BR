---
title: Renovar-CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: O cmdlet Renew-CcCACertificate renova o certficado de Autoridade de Certificação raiz do Skype for Business Cloud Connector Edition que está prestes a expirar ou já expirou. Este comando foi alterado para atualização-CcCACertificate na nuvem conector 2.0 e versões posteriores.
ms.openlocfilehash: bfcf7c69e27af8ebf83c85a8c90cc46491fbc454
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="renew-cccacertificate"></a>Renovar-CcCACertificate
 
O cmdlet Renew-CcCACertificate renova o certficado de Autoridade de Certificação raiz do Skype for Business Cloud Connector Edition que está prestes a expirar ou já expirou. Este comando foi alterado para atualização-CcCACertificate na nuvem conector 2.0 e versões posteriores.
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte renova o certificado de Autoridade de Certificação raiz:  
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O certificado de Autoridade de Certificação raiz do Cloud Connector é válido por cinco anos a partir da data em que o serviço de Autoridade de Certificação foi instalado.
  
Se o certificado raiz estiver prestes a expirar ou já expirou, execute o cmdlet Renew-CcCACertificate para renovar o certificado. Depois que o certificado raiz tiver sido renovado, serão emitidos novos certificados automaticamente para o servidor AD, o Repositório de Gerenciamento Central e o Servidor de Borda.
  
Se existirem vários dispositivos no mesmo site PSTN, execute o cmdlet Renew-CcCACertificate em todos os dispositivos do mesmo site PSTN.
  
Na última etapa, execute o cmdlet Export-CcRootCertificate para exportar o certificado raiz para um arquivo local no primeiro dispositivo e depois copie e instale o certificado exportado para seus gateways PSTN.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Renew-CcCACertificate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renovar-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

