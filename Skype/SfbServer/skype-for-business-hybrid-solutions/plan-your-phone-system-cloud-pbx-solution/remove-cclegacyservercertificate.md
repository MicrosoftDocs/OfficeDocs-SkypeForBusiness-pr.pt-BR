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
description: O cmdlet Remove-CcLegacyServerCertificate remove certificados de servidor herdados no Armazenamento de Gerenciamento Central, Servidor de Mediação e Servidor de Borda depois de executar os cmdlets Renew-CcCACertificate ou Renovar CcServerCertificate.
ms.openlocfilehash: 6c1665d0c21e5afd25ed630fc1da4f1987264d9325fec2058981fe91a1edc0bb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288729"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
O cmdlet Remove-CcLegacyServerCertificate remove certificados de servidor herdados no Armazenamento de Gerenciamento Central, Servidor de Mediação e Servidor de Borda depois de executar os cmdlets Renew-CcCACertificate ou Renovar CcServerCertificate.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir remove certificados herdados emitidos para o Armazenamento de Gerenciamento Central, Servidor de Mediação e Servidor de Borda depois que você renovou os certificados:
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo remove certificados emitidos para Servidor de Mediação e Servidor de Borda depois que você renovou os certificados: 
  
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

Nenhum. O Remove-CcLegacyServerCertificate cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

