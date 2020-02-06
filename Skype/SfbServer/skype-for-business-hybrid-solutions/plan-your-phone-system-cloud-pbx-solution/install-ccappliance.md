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
description: 'O cmdlet Install-CcAppliance instala o dispositivo do Skype for Business Cloud Connector Edition — incluindo as máquinas virtuais do AD, do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda — no servidor host. '
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799871"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
O cmdlet Install-CcAppliance instala o dispositivo do Skype for Business Cloud Connector Edition — incluindo as máquinas virtuais do AD, do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda — no servidor host.  
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir instala um novo dispositivo de conector de nuvem no servidor host:
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Exemplo 2

O exemplo a seguir atualiza o conector de nuvem para a versão mais recente:
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Exemplo 3

O exemplo a seguir remove todas as credenciais do conector de nuvem armazenadas em cache no servidor host, solicita que o usuário especifique todas as informações de credenciais novamente e, em seguida, instale o Cloud Connector:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Exemplo 4

O seguinte exemplo exibe todas as etapas de implantação no console do PowerShell:
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

O parâmetro -ShowStepsOnly é apenas para solução de problemas.
  
### <a name="example-5"></a>Exemplo 5

O exemplo seguinte gera arquivos de configuração para cada etapa de implantação no servidor host. Os arquivos de configuração são salvos \<na\>pasta\\ ApplianceRoot \Instances\><versão-default\ExportedConfig no servidor host:
  
```powershell
Install-CcAppliance -PrepareOnly
```

Para determinar a raiz do dispositivo, execute o cmdlet Get-CcApplianceDirectory.  
  
### <a name="example-6"></a>Exemplo 6

No exemplo seguinte, o Cloud Connector executa as etapas de implantação 1, 2 e 3 para criar comutadores virtuais, criar uma máquina virtual do AD e instalar o serviço do domínio no servidor AD. Ele pula a etapa se ela já tiver sido executada:
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

O parâmetro SkipExistingObjects deve ser usado em conjunto com o parâmetro Steps.
  
> [!NOTE]
> O parâmetro Steps é apenas para solução de problemas. Não use este parâmetro para implantar um dispositivo ou para atualizar um dispositivo que está em serviço. 
  
Para determinar as etapas da implantação, execute o seguinte comando:
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Install-CcAppliance é usado para implantar o conector de nuvem em um novo dispositivo ou para atualizar um aparelho existente para a versão mais recente.
  
Se você tiver um novo aplicativo, certifique-se de ler o tópico Preparar seu ambiente para o Cloud Connector primeiro, executar o cmdlet Register-CcAppliance para registrar o dispositivo e depois executar o cmdlet Install-CcAppliance. Para obter mais informações, consulte [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
Se você tiver uma implantação existente do conector de nuvem e quiser atualizar, siga as instruções em [atualizar para uma nova versão do Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |  Gerar arquivos de configuração para cada etapa da implantação. Este parâmetro tem a finalidade exclusiva de solução de problemas.  <br/> |
|ShowStepsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Exibir apenas os nomes das etapas de implantação. Este parâmetro tem a finalidade exclusiva de solução de problemas.  <br/> |
|SkipExistingObjects  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Este parâmetro deve ser usado em conjunto com o parâmetro Steps. Este parâmetro tem a finalidade exclusiva de solução de problemas.  <br/> |
|Etapas  <br/> |Opcional  <br/> |System.Array  <br/> |Executar as etapas de implantação. Este parâmetro tem a finalidade exclusiva de solução de problemas.  <br/> |
|Atualizar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Atualizar o Cloud Connector existente para a versão mais recente.  <br/> |
|UpdateAllCredentials  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Remova todas as credenciais do conector de nuvem no cache. Pedir para o usuário especificar as informações das novas credenciais para a instalação.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Install-CcAppliance não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte Também
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

