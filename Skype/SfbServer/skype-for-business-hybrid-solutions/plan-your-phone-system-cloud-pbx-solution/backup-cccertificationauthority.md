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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: O Backup-CcCertificationAuthority o cmdlet faz o back up do serviço de autoridade de certificação do Skype for Business Cloud Connector Edition em um arquivo e o salva na pasta ac no diretório de compartilhamento de site.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803801"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
O Backup-CcCertificationAuthority o cmdlet faz o back up do serviço de autoridade de certificação do Skype for Business Cloud Connector Edition em um arquivo e o salva na pasta ac no diretório de compartilhamento de site.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir faz o back up do serviço de autoridade de certificação em um arquivo e o salva na pasta AC sob o diretório de compartilhamento de site:
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O backup da autoridade de certificação pode ser útil se você planeja reimplantar um dispositivo do Cloud Connector com o mesmo certificado em caso de desastre ou se quiser mover o dispositivo para um novo hardware. O comando salva a cópia do serviço de autoridade de certificação do Cloud Connector do Servidor AD em " \< SiteRootDirectory \> \CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Backup-CcCertificationAuthority cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Remover-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

