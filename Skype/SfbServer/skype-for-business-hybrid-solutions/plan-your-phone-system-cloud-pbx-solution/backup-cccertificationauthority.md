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
description: O Backup-CcCertificationAuthority cmdlet faz o back-up do serviço de autoridade de certificação do Skype for Business Cloud Connector Edition em um arquivo e o salva na pasta ca no diretório de compartilhamento de sites.
ms.openlocfilehash: abf94977abe2a0c3548b549ae0101ae399e124769eaaa9f05aabf203c69656a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282953"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
O Backup-CcCertificationAuthority cmdlet faz o back-up do serviço de autoridade de certificação do Skype for Business Cloud Connector Edition em um arquivo e o salva na pasta ca no diretório de compartilhamento de sites.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parâmetros

Nenhum
  
## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir faz o back up the certification authority service to a file and saves it to the CA folder under the site share directory:
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O backup da autoridade de certificação pode ser útil se você planeja reimplantar um dispositivo do Cloud Connector com o mesmo certificado em caso de desastre ou se quiser mover o dispositivo para um novo hardware. O comando salva a cópia do serviço de autoridade de certificação do Cloud Connector do AD Server para " \<SiteRootDirectory\> \CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Backup-CcCertificationAuthority cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Remover-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

