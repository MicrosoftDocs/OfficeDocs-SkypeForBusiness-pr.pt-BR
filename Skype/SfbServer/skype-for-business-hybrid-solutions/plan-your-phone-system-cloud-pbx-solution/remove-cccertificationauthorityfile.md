---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: O Remove-CcCertificationAuthorityFile cmdlet remove o arquivo de backup do serviço de autoridade de certificação na pasta ca sob o diretório de compartilhamento de sites para Skype for Business Cloud Connector Edition.
ms.openlocfilehash: aaff21023a63e8933235f4c462c1152339381ca0d9571ded57f6b43742679624
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288769"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
O cmdlet Remove-CcCertificationAuthorityFile remove o arquivo de backup do serviço de autoridade de certificação " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" na pasta CA no diretório de compartilhamento de sites para Skype for Business Cloud Connector Edition. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir remove o arquivo de backup do serviço de autoridade de certificação " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" na pasta CA no diretório de compartilhamento de sites:
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Remove-CcCertificationAuthorityFile cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

