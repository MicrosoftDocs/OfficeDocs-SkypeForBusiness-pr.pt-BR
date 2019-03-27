---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: O cmdlet Remove-CcLegacyServerCertificate remove os certificados do servidor herdados do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda depois que você executa os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.
ms.openlocfilehash: 5f148aa083b646565adf0158f34fb15314296170
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882457"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
O cmdlet Remove-CcLegacyServerCertificate remove os certificados do servidor herdados do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda depois que você executa os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo seguinte remove os certificados herdados emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda depois de você renovar os certificados:
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Exemplo 2

O exemplo seguinte remove os certificados emitidos para o Servidor de Mediação e o Servidor de Borda depois de você renovar os certificados:  
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Parâmetros
<a name="Examples"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Funções <br/> |Opcional  <br/> |System.Array   <br/> | Matriz das funções do servidor do Cloud Connector. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Remove-CcLegacyServerCertificate não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

