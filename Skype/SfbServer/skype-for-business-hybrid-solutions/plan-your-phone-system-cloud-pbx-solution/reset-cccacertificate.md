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
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: O cmdlet Reset-CcCACertificate reinstala o servidor AD de serviço de Autoridade de Certificação para criar um novo certificado de Autoridade de Certificação raiz.
ms.openlocfilehash: 50c3b1afc29503b2b292ce578ea01b03aeeba368
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003251"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
O cmdlet Reset-CcCACertificate reinstala o servidor AD de serviço de Autoridade de Certificação para criar um novo certificado de Autoridade de Certificação raiz.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte reinstala o servidor AD de serviço de Autoridade de Certificação para criar um novo certificado de Autoridade de Certificação raiz:
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se o certificado de Autoridade de Certificação raiz estiver comprometido ou não for mais seguro, você deverá atualizar o certificado de Autoridade de Certificação raiz e todos os certificados emitidos pela Autoridade de Certificação raiz. O cmdlet Reset-CcCACertificate revoga todos os certificados, desinstala e reinstala a Autoridade de Certificação e depois limpa todos os certificados relacionados ao serviço de Autoridade de Certificação antigo. 
  
Para obter mais informações, consulte "certificados de autoridade de certificação ou certificados internos emitidos para o CMS, o servidor de mediação e o Edge Server estão próximos de expiração ou comprometidos" na solução de problemas na implantação do conector de nuvem.
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Reset-CcCACertificate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum.
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Somente a versão 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Somente a versão 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Versão 2.0 e posterior
  
[Renovar-CcServerCertificate](renew-ccservercertificate.md) Versão 2,0 e posterior
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

