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
description: O Remove-CcCertificationAuthorityFile cmdlet remove o arquivo de backup do serviço de autoridade de certificação na pasta ac sob o diretório de compartilhamento de site do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824287"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
O cmdlet Remove-CcCertificationAuthorityFile remove o arquivo de backup do serviço de autoridade de certificação " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" na pasta CA no diretório de compartilhamento de site do Skype for Business Cloud Connector Edition. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir remove o arquivo de backup do serviço de autoridade de certificação " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" na pasta CA sob o diretório de compartilhamento de site:
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Remove-CcCertificationAuthorityFile cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

