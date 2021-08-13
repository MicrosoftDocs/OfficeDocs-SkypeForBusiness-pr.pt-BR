---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: O Uninstall-CcAppliance cmdlet desinstala o dispositivo Skype for Business Cloud Connector Edition do servidor host.
ms.openlocfilehash: f82459e71ee3c7eea88030a2f265f0076a633a280ee3182920e599402f69a96c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344550"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
O Uninstall-CcAppliance cmdlet desinstala o dispositivo Skype for Business Cloud Connector Edition do servidor host. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir esvazia e desinstala o dispositivo do Cloud Connector do servidor host:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo esvazia e desinstala à força o dispositivo do Cloud Connector em execução no servidor host, mesmo se o processo de drenagem falhar:
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Exemplo 3

O próximo exemplo desinstala uma versão de backup do Cloud Connector sem a confirmação do usuário:
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se você estiver desinstalando a versão atual em execução do Cloud Connector, os serviços de drenagem serão executados pela primeira vez no Servidor de Mediação e no Servidor de Borda para permitir que as chamadas simultâneas terminem antes de desinstalar as máquinas virtuais. Se você estiver desinstalando uma versão de backup, o esvaziamento não será executado.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Versão <br/> | Opcional <br/> |System.String  <br/> | A versão do Cloud Connector que será desinstalada do servidor host. Se não for especificado, desinstale a versão em execução atual. <br/> |
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se desinstalar a versão em execução atual, tente drenar servidores no Servidor de Mediação e no Servidor de Borda antes de desinstalar as máquinas virtuais. Se você especificar a opção "Force", mesmo que os serviços de drenagem falhem, as máquinas virtuais serão desinstaladas. Esse parâmetro é usado apenas para desinstalar a versão em execução atual.  <br/> |
|Confirmar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Peça confirmação do usuário para desinstalar as máquinas virtuais. O valor padrão é TRUE.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Uninstall-CcAppliance cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

