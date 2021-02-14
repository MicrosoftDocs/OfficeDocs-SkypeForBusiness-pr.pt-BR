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
description: O Uninstall-CcAppliance cmdlet desinstala o dispositivo do Skype for Business Cloud Connector Edition em execução no servidor host.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824135"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
O Uninstall-CcAppliance cmdlet desinstala o dispositivo do Skype for Business Cloud Connector Edition em execução no servidor host. 
  
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

O próximo exemplo esvazia e força a desinstalação do dispositivo do Cloud Connector em execução no servidor host, mesmo se o processo de esvaziamento falhar:
  
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

Se você estiver desinstalando a versão atual em execução do Cloud Connector, os serviços de esvaziamento serão executados primeiro no Servidor de Mediação e no Servidor de Borda para permitir que as chamadas simultâneas sejam finalizada antes de desinstalar as máquinas virtuais. Se você estiver desinstalando uma versão de backup, a drenagem não será executada.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Versão <br/> | Opcional <br/> |System.String  <br/> | A versão do Cloud Connector que será desinstalada do servidor host. Se não for especificado, desinstale a versão atual em execução. <br/> |
|Force  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se estiver desinstalando a versão atual em execução, tente esvaziar os servidores no Servidor de Mediação e no Servidor de Borda antes de desinstalar as máquinas virtuais. Se você especificar a opção "Force", mesmo se os serviços de esvaziamento falharem, as máquinas virtuais serão desinstaladas. Esse parâmetro só é usado para desinstalar a versão atual em execução.  <br/> |
|Confirmar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Peça confirmação ao usuário para desinstalar as máquinas virtuais. O valor padrão é TRUE.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Uninstall-CcAppliance cmdlet não aceita entrada em pipeline.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

