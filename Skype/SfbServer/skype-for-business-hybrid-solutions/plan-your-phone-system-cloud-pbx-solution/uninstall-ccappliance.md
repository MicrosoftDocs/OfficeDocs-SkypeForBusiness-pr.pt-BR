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
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'O cmdlet Uninstall-CcAppliance cancela a instalação do dispositivo  em execução do Skype for Business Cloud Connector Edition no servidor host. '
ms.openlocfilehash: f37c3092103832c9efd3b24d2efbedf00e8f54ac
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003141"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
O cmdlet Uninstall-CcAppliance cancela a instalação do dispositivo  em execução do Skype for Business Cloud Connector Edition no servidor host.  
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir esvazia e desinstala o dispositivo do conector de nuvem do servidor host:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo drena e forçosamente desinstala o dispositivo de conector de nuvem em execução no servidor host, mesmo que o processo de descarga falhasse:
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Exemplo 3

O próximo exemplo desinstala uma versão de backup do conector de nuvem sem a confirmação do usuário:
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se você estiver desinstalando a versão atual do conector de nuvem, os serviços de descarga serão executados primeiro no servidor de mediação e no servidor de borda para que as chamadas simultâneas sejam concluídas antes da desinstalação das máquinas virtuais. Se você estiver desinstalando uma versão do backup, os esvaziamento não será executado.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Versão <br/> | Opcional <br/> |System.String  <br/> | A versão do conector de nuvem que será desinstalada do servidor host. Se não for especificado, desinstale a versão atual em execução. <br/> |
|Forçar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se você estiver desinstalando a versão atual em execução, tente esvaziar os servidores no Servidor de Mediação e do Servidor de Borda antes de desinstalar as máquinas virtuais. Se você especificar o comutador "Forçar", mesmo se os serviços de esvaziamento falharem, as máquinas virtuais serão desinstaladas. Este parâmetro é usado somente para desinstalar a versão atual em execução.  <br/> |
|Confirmar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Solicite confirmação do usuário para desinstalar as máquinas virtuais. O valor padrão é TRUE.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Uninstall-CcAppliance não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

