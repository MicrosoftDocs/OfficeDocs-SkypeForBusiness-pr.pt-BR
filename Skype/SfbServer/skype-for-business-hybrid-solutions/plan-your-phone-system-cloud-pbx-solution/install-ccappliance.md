---
title: Install-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 'O cmdlet Install-CcAppliance instala o dispositivo do Skype for Business Cloud Connector Edition — incluindo as máquinas virtuais do AD, do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda — no servidor host. '
ms.openlocfilehash: a3717e510ccadaa930d50573f067888780f7dce5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
O cmdlet Install-CcAppliance instala o dispositivo do Skype for Business Cloud Connector Edition — incluindo as máquinas virtuais do AD, do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda — no servidor host.  
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]

```

## <a name="examples"></a>Exemplos
<a name="Examples"> </a>

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir instala um novo dispositivo de conector de nuvem no servidor host:
  
```
Install-CcAppliance
```

### <a name="example-2"></a>Exemplo 2

O exemplo a seguir atualiza o conector de nuvem para a versão mais recente:
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Exemplo 3

O exemplo a seguir remove todas as credenciais de nuvem conector armazenados em cache no servidor host, solicita ao usuário para especificar todas as informações de credencial novamente e em seguida, instala o conector de nuvem:
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Exemplo 4

O seguinte exemplo exibe todas as etapas de implantação no console do PowerShell:
  
```
Install-CcAppliance -ShowStepsOnly
```

O parâmetro -ShowStepsOnly é apenas para solução de problemas.
  
### <a name="example-5"></a>Exemplo 5

O exemplo seguinte gera arquivos de configuração para cada etapa de implantação no servidor host. Arquivos de configuração são salvas o \<ApplianceRoot\>\Instances\\< versão\>-default\ExportedConfig pasta no servidor host:
  
```
Install-CcAppliance -PrepareOnly
```

Para determinar a raiz do dispositivo, execute o cmdlet Get-CcApplianceDirectory.  
  
### <a name="example-6"></a>Exemplo 6

No exemplo seguinte, o Cloud Connector executa as etapas de implantação 1, 2 e 3 para criar comutadores virtuais, criar uma máquina virtual do AD e instalar o serviço do domínio no servidor AD. Ele pula a etapa se ela já tiver sido executada:
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

O parâmetro SkipExistingObjects deve ser usado em conjunto com o parâmetro Steps.
  
> [!NOTE]
> O parâmetro Steps é apenas para solução de problemas. Não use este parâmetro para implantar um dispositivo ou para atualizar um dispositivo que está em serviço. 
  
Para determinar as etapas da implantação, execute o seguinte comando:
  
Install-CcAppliance - ShowStepsOnly
  
## <a name="detailed-description"></a>Descrição detalhada
<a name="DetailedDescription"> </a>

O cmdlet Install-CcAppliance é usado para implantar o conector de nuvem para um novo aparelho ou atualizar um aparelho existente para a versão mais recente.
  
Se você tiver um novo aplicativo, certifique-se de ler o tópico Preparar seu ambiente para o Cloud Connector primeiro, executar o cmdlet Register-CcAppliance para registrar o dispositivo e depois executar o cmdlet Install-CcAppliance. Para obter mais informações, consulte [implantar um único site no conector de nuvem](deploy-a-single-site-in-cloud-connector.md) e [implantar vários sites em nuvem de conector](deploy-multiple-sites-in-cloud-connector.md). 
  
Se você tiver uma implantação existente do conector de nuvem e você deseja atualizar, siga as instruções [de atualização para uma nova versão do conector de nuvem](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Parâmetros
<a name="DetailedDescription"> </a>

|**Parâmetro**|**Obrigatório**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |  Gerar arquivos de configuração para cada etapa da implantação. Este parâmetro tem a finalidade exclusiva de solução de problemas.  <br/> |
|ShowStepsOnly  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Exibir apenas os nomes das etapas de implantação. Este parâmetro tem a finalidade exclusiva de solução de problemas.  <br/> |
|SkipExistingObjects  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Este parâmetro deve ser usado em conjunto com o parâmetro Steps. Este parâmetro tem a finalidade exclusiva de solução de problemas.  <br/> |
|Etapas  <br/> |Opcional  <br/> |System. Array  <br/> |Executar as etapas de implantação. Este parâmetro tem a finalidade exclusiva de solução de problemas.  <br/> |
|Atualizar  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Atualizar o Cloud Connector existente para a versão mais recente.  <br/> |
|UpdateAllCredentials  <br/> |Opcional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Remova todas as credenciais de nuvem conector no cache. Pedir para o usuário especificar as informações das novas credenciais para a instalação.  <br/> |
   
## <a name="input-types"></a>Tipos de entrada
<a name="InputTypes"> </a>

Nenhum. O cmdlet Install-CcAppliance não aceita a entrada por pipeline.
  
## <a name="return-types"></a>Tipos de retorno
<a name="ReturnTypes"> </a>

Nenhum
  
## <a name="see-also"></a>Consulte também
<a name="ReturnTypes"> </a>

[Publicar-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Cancelar o registro de CcAppliance](unregister-ccappliance.md)
  
[Desinstalar-CcAppliance](uninstall-ccappliance.md)
  

