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
ms.localizationpriority: medium
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: O Backup-CcCertificationAuthority cmdlet faz backup do serviço de autoridade de certificação do Skype for Business Cloud Connector Edition em um arquivo e o salva na pasta ac no diretório de compartilhamento do site.
ms.openlocfilehash: 4dc67fa9e1b4a9a52b3e447b09d91a74704be690
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675453"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority

O Backup-CcCertificationAuthority cmdlet faz backup do serviço Skype for Business Cloud Connector Edition autoridade de certificação em um arquivo. O cmdlet também o salva na pasta ac no diretório de compartilhamento do site.

```powershell
Backup-CcCertificationAuthority
```

## <a name="parameters"></a>Parâmetros

Nenhum

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir faz backup do serviço de autoridade de certificação em um arquivo e o salva na pasta ac no diretório de compartilhamento do site:

```powershell
Backup-CcCertificationAuthority
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O backup da autoridade de certificação pode ser útil se você planeja reimplantar um dispositivo do Cloud Connector com o mesmo certificado. Por exemplo:

- Recuperação de desastre.
- Mova o dispositivo para um novo hardware.

O comando salva a cópia do serviço de autoridade de certificação do Cloud Connector do Servidor do AD para `"<SiteRootDirectory>\CA\SfB CCE Root.p12"`.

## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Backup-CcCertificationAuthority cmdlet não aceita entrada em pipeline.

## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum

## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Remover-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  