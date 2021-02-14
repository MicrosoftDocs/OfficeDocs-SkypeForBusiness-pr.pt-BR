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
description: O Reset-CcCACertificate cmdlet reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de AUTORIDADE de Certificação raiz.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824247"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
O Reset-CcCACertificate cmdlet reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de AUTORIDADE de Certificação raiz.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de autoridade de certificação raiz:
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se o certificado de AC raiz estiver comprometido ou não for mais seguro, você deverá atualizar o certificado de ac raiz e todos os certificados emitidos pela CA raiz. O cmdlet Reset-CcCACertificate revoga todos os certificados, desinstala e reinstala a Autoridade de Certificação e limpa todos os certificados relacionados ao antigo serviço de Autoridade de Certificação. 
  
Para obter mais informações, consulte "Certificados de autoridade de certificação ou certificados internos emitidos para CMS, Servidor de Mediação e Servidor de Borda estão próximos de expirar ou estão comprometidos" na Solução de problemas de sua implantação do Cloud Connector.
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Reset-CcCACertificate cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum.
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Somente a versão 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Somente a versão 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Versão 2.0 e posterior
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Versão 2.0 e posterior
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

