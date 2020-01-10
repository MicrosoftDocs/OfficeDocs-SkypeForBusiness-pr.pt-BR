---
title: Atualizar para uma nova versão do Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Saiba como atualizar sua implantação do Cloud Connector Edition.
ms.openlocfilehash: c340b7325c95d25212c9c1f77f9379a25708cea8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002041"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Upgrade to a new version of Cloud Connector
 
Saiba como atualizar sua implantação do Cloud Connector Edition.
  
Se você tiver configurado uma conta de locatário de gerenciamento e habilitado as atualizações automáticas, sua implantação existente do Skype for Business Cloud Connector Edition será atualizada para a versão mais recente automaticamente, conforme sua configuração de frequência de atualização automática. Você também poderá executar uma atualização manual.  
  
O Cloud Connector Edition versões 1.4.1 e posteriores executam atualizações automáticas por padrão. Se você deseja atualizar para a versão mais recente (2,1) manualmente, confira [atualizar um único site para uma nova versão](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) posteriormente neste tópico.
  
A atualização automática requer que o serviço do conector de nuvem esteja em execução. As seguintes etapas escrevem o processo para as atualizações automáticas:
  
- O processo de atualização automática será executado de acordo com a programação que você configurou para as atualizações automáticas.
    
- Tarefas de atualização do sistema operacional
    
  - Verifique e baixe atualizações do sistema operacional para todas as VMs do conector de nuvem. 
    
  - Instale e atualize todas as VMs do conector de nuvem uma a uma e reinicie.
    
  - Após a reinicialização das VMs do conector de nuvem, verifique se outra reinicialização é necessária.
    
  - Após a aplicação bem-sucedida das VMs do conector de nuvem, repita o processo para a máquina host do conector da nuvem.
    
  - Depois que o computador host do conector de nuvem inicializar com êxito, todas as tarefas pendentes de atualização do sistema operacional serão concluídas.
    
- Tarefas de atualização do conector de nuvem
    
  - Baixe e verifique o arquivo de versão do site de download.
    
  - Baixe a nova versão do arquivo .msi.  
    
  - Desinstale o arquivo MSI antigo; Instale o novo arquivo MSI.
    
  - Baixe a nova versão dos bits do Skype for Business.
    
  - Registre o dispositivo chamando o Register-CcAppliance.
    
  - Instale a nova versão do conector de nuvem.
    
  - Esvazie o dispositivo antigo e alterne a conexão da rede para o novo dispositivo.
    
> [!NOTE]
>  Quando atualizações do Cloud Connector para um novo Build, cmdlets do conector de nuvem podem não ser atualizados. Isso pode acontecer, por exemplo, se uma janela do PowerShell for deixada aberta enquanto ocorre a atualização automática. Para carregar os cmdlets atualizados, você pode executar uma das seguintes etapas: > fechar o PowerShell no aparelho do Cloud Connector e, em seguida, abrir novamente o PowerShell. > ou, você pode executar Import-Module CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Atualizar um único site para uma nova versão
<a name="BKMK_Upgrade"> </a>

Se existir somente um dispositivo no site que você deseja atualizar, faça o seguinte:
  
1. Desinstale a versão do conector de nuvem existente nos ** \> \> programas e recursos do painel de controle**.
    
2. Instale a nova versão do CloudConnector. msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).
    
3. Confirme se você tem o arquivo CloudConnector.ini para a versão que está instalando e se atualizou todos os valores necessários para seu ambiente. Você não pode usar o arquivo .ini de uma versão anterior. Se você estiver atualizando o conector de nuvem, consulte o tópico [preparar seu aparelho de conector de nuvem](prepare-your-cloud-connector-appliance.md) e verifique se SiteName e EnableReferSupport estão definidos com o valor correto no arquivo CloudConnector. ini.
    
4. Inicie um console do PowerShell como administrador e execute o seguinte cmdlet para registrar o dispositivo atual:
    
   ```powershell
   Register-CcAppliance
   ```

5. Execute o seguinte cmdlet para baixar a versão mais recente:
    
   ```powershell
   Start-CcDownload
   ```

6. Execute o seguinte cmdlet para iniciar a instalação: 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. Execute o seguinte cmdlet para ativar a nova implantação e desativar a versão anterior.
    
   ```powershell
   Switch-CcVersion
   ```

Se existir mais de um dispositivo no site, siga as etapas anteriores para atualizar cada dispositivo individualmente.
  
Se quiser atualizar o administrador do domínio, o administrador da máquina virtual, o administrador do modo de segurança e as credenciais de administrador do locatário, você pode executar o cmdlet com o parâmetro _UpdateAllCredentials_ para redefinir todas as credenciais:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Posteriormente, quando você iniciar a atualização para uma nova versão, o programa solicitará a entrada das novas credenciais.  
  
Para apenas redefinir as credenciais do administrador de locatários, execute o seguinte cmdlet:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Atualizar vários sites para uma nova versão
<a name="BKMK_Upgrade"> </a>

Siga as etapas para a atualização de um único site, atualizando um site de cada vez de sua implantação. Certifique-se de [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) após atualizar cada site.
  

