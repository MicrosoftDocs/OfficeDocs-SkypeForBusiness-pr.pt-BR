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
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: 'O cmdlet Update-CcCACertificate renova o certificado da autoridade de certificação raiz do Skype for Business Cloud Connector Edition que está próximo de expirar ou que já tenha expirado. '
ms.openlocfilehash: 15be5d4518d7e375b4804ed2d9f22bd35a45ca7e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003121"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
O cmdlet Update-CcCACertificate renova o certificado da autoridade de certificação raiz do Skype for Business Cloud Connector Edition que está próximo de expirar ou que já tenha expirado.  
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>Parâmetros

Nenhum.
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte renova o certificado de Autoridade de Certificação raiz:  
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O certificado de Autoridade de Certificação raiz do Cloud Connector é válido por cinco anos a partir da data em que o serviço de Autoridade de Certificação foi instalado.
  
Se o certificado raiz estiver quase expirado ou já tiver expirado, execute o cmdlet Update-CcCACertificate para renovar o certificado. Depois que o certificado raiz for renovado, o Servidor AD, o Repositório de Gerenciamento Central e o Servidor de Borda receberão novos certificados automaticamente.
  
Se houver vários dispositivos no mesmo local de PSTN, execute o cmdlet Update-CcCACertificate em todos os dispositivos do mesmo local de PSTN.
  
Na última etapa, execute o cmdlet Export-CcRootCertificate para exportar o certificado raiz para um arquivo local no primeiro dispositivo e depois copie e instale o certificado exportado para seus gateways PSTN.
  
Este comando substitui o cmdlet Renew-CcCACertificate no Cloud Connector 2.0 e versões posteriores.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Update-CcCACertificate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum. 
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

