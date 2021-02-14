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
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824145"
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

O próximo exemplo esvazia os serviços do dispositivo em execução no momento e interrompe os serviços à força se a drenagem dos serviços falhar. Em seguida, o comando alterna para um dispositivo recém-implantado ou de backup:
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Switch-CcVersion cmdlet esvazia os serviços do Cloud Connector no Servidor de Mediação e no Servidor de Borda. Todas as chamadas em execução serão concluídas, mas o dispositivo rejeitará todas as novas chamadas. Após a drenagem, o cmdlet desconecta o dispositivo em execução das redes corporativas e da Internet, desliga todas as máquinas virtuais pertencentes ao dispositivo e, em seguida, conecta o dispositivo de backup às redes corporativas e de Internet.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Opcional <br/> |System.Management.Automation.SwitchParameter  <br/> | Interrompe os serviços à força se a drenagem dos serviços falhar. <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

Nenhum
  

