---
title: Remove-CcLegacyServerCertificate
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
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: O cmdlet Remove-CcLegacyServerCertificate remove certificados de servidor herdados no Armazenamento de Gerenciamento Central, no Servidor de Mediação e no Servidor de Borda depois de executar os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824277"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
O cmdlet Remove-CcLegacyServerCertificate remove certificados de servidor herdados no Armazenamento de Gerenciamento Central, no Servidor de Mediação e no Servidor de Borda depois de executar os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir remove os certificados herdados emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda após a renovação dos certificados:
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo remove os certificados emitidos para o Servidor de Mediação e o Servidor de Borda após a renovação dos certificados: 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Parâmetros
<a name="Examples"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Funções <br/> |Opcional  <br/> |System.Array  <br/> | Matriz de funções de servidor do Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Remove-CcLegacyServerCertificate cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

