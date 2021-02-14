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
description: Saiba como atualizar sua implantação do Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359287"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Atualizar para uma nova versão do Cloud Connector

> [!Important]
> O Cloud Connector Edition será destivado em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização atualizou para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)
 
Saiba como atualizar sua implantação do Cloud Connector Edition.
  
Se você tiver definido uma conta de locatário de gerenciamento online e habilitado as atualizações automáticas, sua implantação existente do Skype for Business Cloud Connector Edition será atualizada para a versão mais recente automaticamente, de acordo com a configuração da janela de tempo de atualização automática. Você também pode executar uma atualização manual. 
  
As versões 1.4.1 e posteriores do Cloud Connector Edition executam atualizações automáticas por padrão. Se você quiser atualizar para a versão mais recente (2.1) manualmente, consulte Atualizar um único [site](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) para uma nova versão posteriormente neste tópico.
  
A atualização automática requer que o serviço do Cloud Connector seja executado. As etapas a seguir descrevem o processo de atualizações automáticas:
  
- O processo de atualização automática será executado de acordo com o agendamento configurado para atualizações automáticas.
    
- Tarefas de atualização do sistema operacional
    
  - Verifique e baixe as atualizações do sistema operacional para todas as VMs do Cloud Connector. 
    
  - Instale e atualize todas as VMs do Cloud Connector uma por uma e reinicie.
    
  - Após a reinicialização das VMs do Cloud Connector, verifique se outra reinicialização é necessária.
    
  - Depois que as VMs do Cloud Connector foram corrigidas com êxito, repita o processo para o computador host do Cloud Connector.
    
  - Depois que a máquina host do Cloud Connector for inicializada com êxito, todas as tarefas pendentes de atualização do sistema operacional serão concluídas.
    
- Tarefas de atualização do Cloud Connector
    
  - Baixe e verifique o arquivo de versão do site de download.
    
  - Baixe o arquivo .msi da nova versão. 
    
  - Desinstale o arquivo msi antigo; instale o novo arquivo msi.
    
  - Baixe a nova versão dos bits do Skype for Business.
    
  - Registre o dispositivo chamando Register-CcAppliance.
    
  - Instale a nova versão do Cloud Connector.
    
  - Esvazia o dispositivo antigo e alterna a conexão de rede para o novo dispositivo.
    
> [!NOTE]
>  Quando o Cloud Connector é atualizado para um novo build, os cmdlets do Cloud Connector podem não ser atualizados. Isso pode acontecer, por exemplo, se uma janela do PowerShell for deixada aberta enquanto a atualização automática ocorrer. Para carregar os cmdlets atualizados, você pode executar uma das seguintes etapas: > fechar o PowerShell no dispositivo do Cloud Connector e reabrir o PowerShell.> Ou pode executar o Import-Module CloudConnector -Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Atualizar um único site para uma nova versão
<a name="BKMK_Upgrade"> </a>

Se houver apenas um dispositivo no site que você deseja atualizar, faça o seguinte:
  
1. Desinstale a versão existente do Cloud Connector em Programas e Recursos do Painel de **\> \> Controle.**
    
2. Instale a nova versão do CloudConnector.msi a partir de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .
    
3. Confirme se você tem o arquivo CloudConnector.ini para a versão que está instalando e se atualizou todos os valores necessários para seu ambiente. Você não pode usar o arquivo .ini de uma versão anterior. Se você estiver atualizando o Cloud Connector, consulte o tópico Preparar seu dispositivo do [Cloud Connector](prepare-your-cloud-connector-appliance.md) e certifique-se de que SiteName e EnableReferSupport estão definidos com o valor correto no arquivo CloudConnector.ini.
    
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

Se houver mais de um dispositivo no site, siga as etapas anteriores para atualizar cada dispositivo um a um.
  
Se você deseja atualizar o administrador de domínio, o administrador da máquina virtual, o administrador do Modo de Segurança e as credenciais de administrador do locatário, pode executar o cmdlet com o parâmetro  _UpdateAllCredentials_ para redefinir todas as credenciais:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Em seguida, quando você começar a atualizar para uma nova versão, será promovido a inserir as novas credenciais. 
  
Se você só quiser redefinir suas credenciais de administrador de locatários, execute o seguinte cmdlet:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Atualizar vários sites para uma nova versão
<a name="BKMK_Upgrade"> </a>

Siga as etapas para atualizar um único site, atualizando um site por vez para cada site em sua implantação. Certifique-se de [validar a implantação do Cloud Connector](validate-your-cloud-connector-deployment.md) depois de atualizar cada site.
  

