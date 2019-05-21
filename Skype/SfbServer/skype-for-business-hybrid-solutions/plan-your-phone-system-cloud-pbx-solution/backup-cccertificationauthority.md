---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: "O cmdlet Backup-CcCertificationAuthority \nfaz backup do serviço de autoridade de certificação do Skype for Business Cloud Connector Edition em um arquivo e salva na pasta AC no diretório de compartilhamento de site."
ms.openlocfilehash: 463aab2516deec5b47e549aec67bcba6a0a80bc0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294415"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
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

O backup da autoridade de certificação pode ser útil se você planeja reimplantar um aparelho do conector de nuvem com o mesmo certificado em caso de desastre ou se quiser mover o aparelho para um novo hardware. O comando salva a cópia do serviço da autoridade de certificação do conector de nuvem do servidor de\<anúncios\>em "SiteRootDirectory \CA\SfB CCE root. p12".
  
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Backup-CcCertificationAuthority não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum 
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

