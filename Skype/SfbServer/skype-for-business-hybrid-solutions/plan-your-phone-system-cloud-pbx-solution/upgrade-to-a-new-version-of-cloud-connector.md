---
title: Atualizar para uma nova versão do Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Saiba como atualizar sua implantação do Cloud Connector Edition.
ms.openlocfilehash: 5b3ca4b216bc376c9e23424fb978b5cd83e4aa41
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240659"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Upgrade to a new version of Cloud Connector
 
Saiba como atualizar sua implantação do Cloud Connector Edition.
  
Se você tiver configurado uma conta de locatário de gerenciamento e habilitado as atualizações automáticas, sua implantação existente do Skype for Business Cloud Connector Edition será atualizada para a versão mais recente automaticamente, conforme sua configuração de frequência de atualização automática. Você também poderá executar uma atualização manual.  
  
Versões de conector Edition 1.4.1 em nuvem e posteriormente executar atualizações automáticas por padrão. Se você deseja atualizar para a versão mais recente (2.1) manualmente, consulte [atualizar um único site para uma nova versão](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) , mais adiante neste tópico.
  
Atualização automática requer que o serviço de nuvem conector está funcionando. As seguintes etapas escrevem o processo para as atualizações automáticas:
  
- O processo de atualização automática será executado de acordo com a programação que você configurou para as atualizações automáticas.
    
- Tarefas de atualização do sistema operacional
    
  - Verifique e baixar atualizações de sistema operacional para todas as máquinas virtuais de conector de nuvem. 
    
  - Instalar e atualizar todas as VMs de conector de nuvem uma e reiniciar.
    
  - Após reiniciar a nuvem conector VMs, verifique se outra reinicialização é necessária.
    
  - Após a nuvem conector VMs receberam com êxito o patch, repita o processo para a máquina host de conector de nuvem.
    
  - Depois que a máquina host de conector de nuvem inicializa com êxito, qualquer excelente do sistema operacional atualizar tarefas podem ser concluídas.
    
- Tarefas de atualização do conector na nuvem
    
  - Baixe e verifique o arquivo de versão do site de download.
    
  - Baixe a nova versão do arquivo .msi.  
    
  - Desinstalar o arquivo msi antigo; Instale o novo arquivo msi.
    
  - Baixe a nova versão do Skype para bits de negócios.
    
  - Registre o dispositivo chamando o Register-CcAppliance.
    
  - Instale a nova versão do conector de nuvem.
    
  - Esvazie o dispositivo antigo e alterne a conexão da rede para o novo dispositivo.
    
> [!NOTE]
>  Quando o conector de nuvem atualiza para uma nova compilação, cmdlets de conector de nuvem não pode ser atualizados. Isso pode acontecer, por exemplo, se uma janela do PowerShell permanecerá aberta durante a atualização automática. Para carregar os cmdlets atualizados, você pode fazer um das seguintes etapas: gt _ PowerShell Close no dispositivo do conector de nuvem e reabra PowerShell.> ou, você pode executar Import-Module CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Atualizar um único site para uma nova versão
<a name="BKMK_Upgrade"> </a>

Se existir somente um dispositivo no site que você deseja atualizar, faça o seguinte:
  
1. Desinstalar a versão existente do conector de nuvem em **Painel de controle \> programas \> programas e recursos**.
    
2. Instalar a nova versão do CloudConnector.msi do [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).
    
3. Confirme se você tem o arquivo CloudConnector.ini para a versão que está instalando e se atualizou todos os valores necessários para seu ambiente. Você não pode usar o arquivo .ini de uma versão anterior. Se você estiver atualizando o conector de nuvem, consulte o tópico [Prepare seu aparelho de conector de nuvem](prepare-your-cloud-connector-appliance.md) e certificar-se de que SiteName e EnableReferSupport estão definidos para o valor correto no arquivo CloudConnector.ini.
    
4. Inicie um console do PowerShell como administrador e execute o seguinte cmdlet para registrar o dispositivo atual:
    
   ```
   Register-CcAppliance
   ```

5. Execute o seguinte cmdlet para baixar a versão mais recente:
    
   ```
   Start-CcDownload
   ```

6. Execute o seguinte cmdlet para iniciar a instalação: 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. Execute o seguinte cmdlet para ativar a nova implantação e desativar a versão anterior.
    
   ```
   Switch-CcVersion
   ```

Se existir mais de um dispositivo no site, siga as etapas anteriores para atualizar cada dispositivo individualmente.
  
Se você deseja atualizar o administrador de domínio, o administrador da máquina Virtual, o administrador do modo de segurança e credenciais de administrador de locatário, você pode executar o cmdlet com o parâmetro _UpdateAllCredentials_ para redefinir todas as credenciais:
  
```
Install-CcAppliance -UpdateAllCredentials
```

Posteriormente, quando você iniciar a atualização para uma nova versão, o programa solicitará a entrada das novas credenciais.  
  
Para apenas redefinir as credenciais do administrador de locatários, execute o seguinte cmdlet:
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Atualizar vários sites para uma nova versão
<a name="BKMK_Upgrade"> </a>

Siga as etapas para a atualização de um único site, atualizando um site de cada vez de sua implantação. Certifique-se de [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) após atualizar cada site.
  

