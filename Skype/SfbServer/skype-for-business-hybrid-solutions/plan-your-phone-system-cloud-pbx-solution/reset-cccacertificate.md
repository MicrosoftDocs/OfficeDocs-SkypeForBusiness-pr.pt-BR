---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: O cmdlet Reset-CcCACertificate reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de AC raiz.
ms.openlocfilehash: 8e0cb93e6f10f28df28213579674a6cda6e7e2cd1cf201319f77dc26be69de80
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340717"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
O cmdlet Reset-CcCACertificate reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de AC raiz.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de AC raiz:
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se o certificado de AC raiz estiver comprometido ou não estiver mais seguro, você deverá atualizar o certificado ca raiz e todos os certificados emitidos pela AC raiz. O cmdlet Reset-CcCACertificate revoga todos os certificados, desinstala e reinstala a Autoridade de Certificação e limpa todos os certificados relacionados ao antigo serviço de Autoridade de Certificação. 
  
Para obter mais informações, consulte "Certificados de autoridade de certificado ou certificados internos emitidos para CMS, Servidor de Mediação e Servidor de Borda estão próximos da expiração ou estão comprometidos" em Solução de problemas da implantação do Cloud Connector.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Reset-CcCACertificate cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum.
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Versão 1.4.2 somente
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Versão 1.4.2 somente
  
[Update-CcCACertificate](update-cccacertificate.md) Versão 2.0 e posterior
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Versão 2.0 e posterior
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

