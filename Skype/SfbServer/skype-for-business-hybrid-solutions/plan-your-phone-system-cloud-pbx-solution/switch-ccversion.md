---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: O Switch-CcVersion cmdlet desconecta o dispositivo em execução e alterna para um dispositivo recém-implantado ou de backup.
ms.openlocfilehash: 1558f34d2388dc75bf4398ba15fc09cd36c439e2d70a39588ee697bc0ef04341
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320034"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
O Switch-CcVersion cmdlet desconecta o dispositivo em execução e alterna para um dispositivo recém-implantado ou de backup. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir esvazia os serviços do dispositivo em execução atual e alterna para um dispositivo recém-implantado ou de backup:
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo esvazia os serviços do dispositivo em execução atual e interrompe os serviços à força se o esvaziamento dos serviços falhar. Em seguida, o comando alterna para um dispositivo recém-implantado ou de backup:
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Switch-CcVersion o cmdlet drena os serviços do Cloud Connector no Servidor de Mediação e no Servidor de Borda. Todas as chamadas em execução serão concluídas, mas o dispositivo rejeitará quaisquer novas chamadas. Após o esvaziamento, o cmdlet desconecta o dispositivo em execução das redes corporativas e da Internet, desliga todas as máquinas virtuais pertencentes ao dispositivo e conecta o dispositivo de backup às redes corporativas e da Internet.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Opcional <br/> |System.Management.Automation.SwitchParameter  <br/> | Interrompe os serviços à força se o esvaziamento dos serviços falhar. <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

None
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

None
  

