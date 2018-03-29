---
title: Desinstalar-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'O cmdlet Uninstall-CcAppliance cancela a instalação do dispositivo  em execução do Skype for Business Cloud Connector Edition no servidor host. '
ms.openlocfilehash: 325e21d28ef87f9d27e87721452bc3d67d197169
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="uninstall-ccappliance"></a>Desinstalar-CcAppliance
 
O cmdlet Uninstall-CcAppliance cancela a instalação do dispositivo  em execução do Skype for Business Cloud Connector Edition no servidor host.  
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir descarrega e desinstala o aparelho de conector de nuvem de servidor host:
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a>Exemplo 2

O próximo exemplo descarrega e obrigatoriamente desinstala o aparelho de conector de nuvem em execução no servidor host, mesmo se o processo de drenagem falhou:
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Exemplo 3

O próximo exemplo desinstala uma versão de backup do conector de nuvem sem confirmação do usuário:
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

Se você estiver desinstalando a versão atual de execução do conector de nuvem, serviços de drenagem inicialmente são executados no servidor de mediação e no servidor de borda para permitir que chamadas simultâneas concluir antes de desinstalar as máquinas virtuais. Se você estiver desinstalando uma versão do backup, os esvaziamento não será executado.
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
| Versão <br/> | Opcional <br/> |System. String  <br/> | A versão do conector de nuvem que será desinstalado do servidor host. Se não for especificado, desinstale a versão atual em execução. <br/> |
|Forçar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se você estiver desinstalando a versão atual em execução, tente esvaziar os servidores no Servidor de Mediação e do Servidor de Borda antes de desinstalar as máquinas virtuais. Se você especificar o comutador "Forçar", mesmo se os serviços de esvaziamento falharem, as máquinas virtuais serão desinstaladas. Este parâmetro é usado somente para desinstalar a versão atual em execução.  <br/> |
|Confirmar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Pedir a confirmação do usuário para desinstalar as máquinas virtuais. O valor padrão é TRUE.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Uninstall-CcAppliance não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publicar-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Cancelar o registro de CcAppliance](unregister-ccappliance.md)
  

