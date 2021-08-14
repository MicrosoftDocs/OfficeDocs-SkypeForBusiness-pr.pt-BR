---
title: Install-CcAppliance
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
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: O Install-CcAppliance cmdlet instala o dispositivo Skype for Business Cloud Connector Edition, incluindo o AD, o Armazenamento de Gerenciamento Central, o Servidor de Mediação e as máquinas virtuais do Servidor de Borda no servidor host.
ms.openlocfilehash: b88b869e3c30783a69bc16ab690a258506ebcc90e849eb474a17859140485e8d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343175"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
O Install-CcAppliance cmdlet instala o dispositivo Skype for Business Cloud Connector Edition, incluindo o AD, o Armazenamento de Gerenciamento Central, o Servidor de Mediação e as máquinas virtuais do Servidor de Borda no servidor host. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir instala um novo dispositivo do Cloud Connector no servidor host:
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Exemplo 2

O exemplo a seguir atualiza o Cloud Connector para a versão mais recente:
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Exemplo 3

O exemplo a seguir remove todas as credenciais do Cloud Connector armazenadas em cache no servidor host, solicita que o usuário especifique todas as informações de credencial novamente e instala o Cloud Connector:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Exemplo 4

O exemplo a seguir exibe todas as etapas de implantação no console do PowerShell:
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

O parâmetro -ShowStepsOnly é apenas para solução de problemas.
  
### <a name="example-5"></a>Exemplo 5

O exemplo a seguir gera arquivos de configuração para cada etapa de implantação no servidor host. Os arquivos de configuração são salvos na \<ApplianceRoot\> pasta \Instances \\<Version \> -default\ExportedConfig no servidor host:
  
```powershell
Install-CcAppliance -PrepareOnly
```

Para determinar a raiz do dispositivo, execute o Get-CcApplianceDirectory cmdlet. 
  
### <a name="example-6"></a>Exemplo 6

No exemplo a seguir, o Cloud Connector executa as etapas de implantação 1, 2 e 3 para criar comutadores virtuais, criar uma máquina virtual do AD e instalar o serviço de domínio no servidor AD. Ele ignora a etapa se a etapa já tiver sido executada:
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

O parâmetro SkipExistingObjects deve ser usado em conjunto com o parâmetro Steps.
  
> [!NOTE]
> O parâmetro Steps é apenas para fins de solução de problemas. Não use esse parâmetro para implantar um dispositivo ou para atualizar um dispositivo que está em serviço. 
  
Para determinar as etapas da implantação, execute o seguinte comando:
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O Install-CcAppliance cmdlet é usado para implantar o Cloud Connector em um novo dispositivo ou para atualizar um dispositivo existente para a versão mais recente.
  
Se você tiver um novo dispositivo, leia Prepare your environment for Cloud Connector primeiro, execute o cmdlet Register-CcAppliance para registrar o dispositivo e execute o cmdlet Install-CcAppliance. Para obter mais informações, [consulte Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and Deploy multiple sites in Cloud [Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
Se você tiver uma implantação existente do Cloud Connector e quiser atualizar, siga as instruções em Atualizar para uma nova [versão do Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Required**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> | Gere arquivos de configuração para cada etapa de implantação. Este parâmetro é apenas para solução de problemas. <br/> |
|ShowStepsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Exibir apenas nomes de etapa de implantação. Este parâmetro é apenas para solução de problemas.  <br/> |
|SkipExistingObjects  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Esse parâmetro deve ser usado em conjunto com o parâmetro Steps. Este parâmetro é apenas para solução de problemas.  <br/> |
|Etapas  <br/> |Opcional  <br/> |System.Array  <br/> |Execute as etapas de implantação. Este parâmetro é apenas para solução de problemas.  <br/> |
|Atualizar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Atualize o Cloud Connector existente para a versão mais recente.  <br/> |
|UpdateAllCredentials  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Remova todas as credenciais do Cloud Connector no cache. Solicitar que o usuário especifique novas informações de credencial para a instalação.  <br/> |
   
## <a name="input-types"></a>Tipos de Entrada
<a name="InputTypes"> </a>

Nenhum. O Install-CcAppliance cmdlet não aceita entrada canalada.
  
## <a name="return-types"></a>Tipos de Retorno
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Confira também
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

