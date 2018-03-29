---
title: CcCertificationAuthority de backup
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: "O cmdlet Backup-CcCertificationAuthority \nfaz backup do serviço de autoridade de certificação do Skype for Business Cloud Connector Edition em um arquivo e salva na pasta AC no diretório de compartilhamento de site."
ms.openlocfilehash: b3cb566dc72b3966eaa1480f3e17e4d6b46c06a2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="backup-cccertificationauthority"></a>CcCertificationAuthority de backup
 
O cmdlet Backup-CcCertificationAuthority 
faz backup do serviço de autoridade de certificação do Skype for Business Cloud Connector Edition em um arquivo e salva na pasta AC no diretório de compartilhamento de site.
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte faz backup do serviço de autoridade de certificação em um arquivo e salva na pasta AC no diretório de compartilhamento de site:
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Backup de autoridade de certificação pode ser útil se você planeja reimplantar um aparelho de conector de nuvem com o mesmo certificado em caso de desastre, ou se você deseja mover o aparelho para novo hardware. O comando salva a cópia do serviço de autoridade de certificação de nuvem conector do servidor AD para "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Backup-CcCertificationAuthority não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

