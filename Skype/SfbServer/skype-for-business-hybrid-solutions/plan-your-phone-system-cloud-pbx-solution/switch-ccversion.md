---
title: Opção-CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: O cmdlet Switch-CcVersion desconecta o dispositivo em execução e alterna para um dispositivo recentemente implantado ou de backup.
ms.openlocfilehash: 651dad80ef5c9907eb6c182527b646da7aa5acc8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="switch-ccversion"></a>Opção-CcVersion
 
O cmdlet Switch-CcVersion desconecta o dispositivo em execução e alterna para um dispositivo recentemente implantado ou de backup. 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir drena os serviços do dispositivo em execução no momento e, em seguida, alterna para um dispositivo recentemente implantado ou de backup:
  
```
Switch-CcVersion
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo drena os serviços do dispositivo em execução no momento e interrompe os serviços  compulsoriamente, quando a drenagem dos serviços falha.  O comando, então, alterna para um dispositivo implantado recentemente ou de backup:
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet do comutador-CcVersion esvazia os serviços de nuvem conector no servidor de mediação e o servidor de borda. Todas as chamadas em execução serão concluídas, mas o dispositivo rejeitará novas chamadas. Depois de drenar, o cmdlet desconecta o dispositivo em execução das redes corporativas e de Internet, desliga todas as máquinas virtuais pertencentes ao dispositivo, e então conecta o dispositivo de backup às redes corporativas e de Internet.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Forçar <br/> | Opcional <br/> |System.Management.Automation.SwitchParameter  <br/> | Interrompe compulsoriamente os serviços, quando a drenagem dos serviços falha. <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

Nenhum
  

