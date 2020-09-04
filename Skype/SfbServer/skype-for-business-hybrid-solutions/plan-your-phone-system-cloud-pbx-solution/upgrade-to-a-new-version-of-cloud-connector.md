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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Saiba mais sobre como atualizar sua implantação do Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359287"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Atualizar para uma nova versão do Cloud Connector

> [!Important]
> O Cloud Connector Edition vai retirar 31 de julho de 2021 junto com o Skype for Business online. Depois que sua organização tiver atualizado para o Microsoft Teams, saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
 
Saiba mais sobre como atualizar sua implantação do Cloud Connector Edition.
  
Se você configurou uma conta de locatário de gerenciamento online e habilitou atualizações automáticas, sua implantação existente do Skype for Business Cloud Connector Edition será atualizada para a versão mais recente automaticamente, de acordo com a configuração da janela de tempo de atualização automática. Você também pode executar uma atualização manual. 
  
As versões do Cloud Connector Edition 1.4.1 e posteriores realizam atualizações automáticas por padrão. Se você deseja atualizar para a versão mais recente (2,1) manualmente, consulte [atualizar um único site para uma nova versão](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) posteriormente neste tópico.
  
A atualização automática requer que o serviço do Cloud Connector esteja em execução. As etapas a seguir descrevem o processo de atualizações automáticas:
  
- O processo de atualização automática será executado de acordo com a agenda que você configurou para as atualizações automáticas.
    
- Tarefas de atualização do sistema operacional
    
  - Verifique e baixe as atualizações do sistema operacional para todas as VMs do Cloud Connector. 
    
  - Instale e atualize todas as VMs do Cloud Connector um por um e reinicie o.
    
  - Após a reinicialização das VMs do Cloud Connector, verifique se outra reinicialização é necessária.
    
  - Depois que as VMs do Cloud Connector tiverem sido corrigidas com êxito, repita o processo para a máquina host do Cloud Connector.
    
  - Após a inicialização bem-sucedida da máquina host do Cloud Connector, todas as tarefas pendentes de atualização do sistema operacional serão concluídas.
    
- Tarefas de atualização do Cloud Connector
    
  - Baixe e verifique o arquivo de versão do site de download.
    
  - Baixe o novo arquivo Version. msi. 
    
  - Desinstale o arquivo MSI antigo; Instale o novo arquivo MSI.
    
  - Baixe a nova versão dos bits do Skype for Business.
    
  - Registre o dispositivo chamando Register-CcAppliance.
    
  - Instale a nova versão do Cloud Connector.
    
  - Dissipe o dispositivo antigo e mude a conexão de rede para o novo dispositivo.
    
> [!NOTE]
>  Quando as atualizações do Cloud Connector para uma nova compilação, os cmdlets do Cloud Connector podem não ser atualizados. Isso pode acontecer, por exemplo, se uma janela do PowerShell for deixada aberta enquanto a atualização automática ocorre. Para carregar os cmdlets atualizados, você pode fazer uma das seguintes etapas: > fechar o PowerShell no aparelho do Cloud Connector e, em seguida, reabrir o PowerShell. > ou, você pode executar Import-Module CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Atualizar um único site para uma nova versão
<a name="BKMK_Upgrade"> </a>

Se houver apenas um dispositivo no site que você deseja atualizar, faça o seguinte:
  
1. Desinstale a versão existente do Cloud Connector no **painel de controle programas \> \> e recursos**.
    
2. Instalar a nova versão do CloudConnector.msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .
    
3. Confirme se você tem o arquivo de CloudConnector.ini da versão que está instalando e se você atualizou todos os valores necessários para o seu ambiente. Não é possível usar o arquivo. ini de uma versão anterior. Se você estiver atualizando o Cloud Connector, confira o tópico [Prepare Your Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md) e certifique-se de que SiteName e EnableReferSupport estão definidos com o valor correto no arquivo CloudConnector.ini.
    
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

7. Execute o seguinte cmdlet para ativar a nova implantação e desativar a versão anterior:
    
   ```powershell
   Switch-CcVersion
   ```

Se houver mais de um dispositivo no site, siga as etapas anteriores para atualizar cada dispositivo um por um.
  
Se você deseja atualizar o administrador de domínio, administrador de máquina virtual, administrador de modo de segurança e credenciais de administrador de locatário, você pode executar o cmdlet com o parâmetro  _UpdateAllCredentials_ para redefinir todas as credenciais:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Em seguida, ao iniciar a atualização para uma nova versão, você será promovido para inserir as novas credenciais. 
  
Se você quiser redefinir suas credenciais de administrador de locatários, execute o seguinte cmdlet:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Atualizar vários sites para uma nova versão
<a name="BKMK_Upgrade"> </a>

Siga as etapas para atualizar um único site, atualizando um site de cada vez para cada site em sua implantação. Certifique-se de [validar sua implantação do Cloud Connector](validate-your-cloud-connector-deployment.md) após atualizar cada site.
  

