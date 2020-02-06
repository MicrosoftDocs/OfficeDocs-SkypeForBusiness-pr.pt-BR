---
title: Mover o servidor central de gerenciamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Depois de migrar para o Skype for Business Server 2019, você precisa mover o servidor de gerenciamento central para o servidor ou pool de front-end do Skype for Business Server 2019 para poder remover o servidor herdado.
ms.openlocfilehash: 6f78a242ce42a3dca56cc1e4e1f2fa604611d68c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813239"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Mover o servidor de gerenciamento central herdado para o Skype for Business Server 2019

Depois de migrar para o Skype for Business Server 2019 e antes de remover o servidor herdado, você precisará mover o servidor de gerenciamento central para o servidor ou o pool de front-end do Skype for Business Server 2019. 
  
O servidor de gerenciamento central é um único sistema de réplica mestra/múltipla, em que a cópia de leitura/gravação do banco de dados é mantida pelo servidor front-end que contém o servidor de gerenciamento central. Cada computador na topologia, incluindo o servidor front-end que contém o servidor de gerenciamento central, tem uma cópia somente leitura dos dados do repositório de gerenciamento central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalados no computador durante a instalação e implementação. O banco de dados local recebe atualizações de réplica por meio do agente duplicador de réplica do servidor do Skype for Business que é executado como um serviço em todos os computadores. O nome do banco de dados real no servidor de gerenciamento central e na réplica local é XDS, que é composto pelos arquivos XDS. MDF e XDS. ldf. O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio Active Directory. Todas as ferramentas que usam o servidor de gerenciamento central para gerenciar e configurar o Skype for Business Server usam o SCP para localizar o repositório de gerenciamento central.
  
Depois de mover com êxito o servidor de gerenciamento central, você deve remover os bancos de dados do servidor de gerenciamento central do servidor front-end original. Para obter informações sobre como remover os bancos de dados do servidor de gerenciamento central, consulte [remover o banco de dados do SQL Server de um pool de front-ends](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Você usa o cmdlet **move-CsManagementServer** do Windows PowerShell no Shell de gerenciamento do Skype for Business Server para mover o banco de dados do banco de dados do SQL Server de instalação herdado para o banco de dados do SQL Server do Skype for business Server 2019 e, em seguida, atualizar o scp para apontar para o local do servidor do Skype for business Server 2019 central Management Server. 
  
Use os procedimentos desta seção para preparar os servidores front-end do Skype for Business Server 2019 antes de mover o servidor de gerenciamento central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Para preparar um pool de front-end do Enterprise Edition

1. No pool de front-ends do Skype for Business Server 2019 Enterprise Edition onde você deseja realocar o servidor de gerenciamento central, faça logon no computador onde o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins** . Você também deve ter direitos de usuário e permissões do banco de dados do SQL Server sysadmin no banco de dados onde deseja instalar o repositório de gerenciamento central. 
    
2. Abra o Shell de gerenciamento do Skype for Business Server.
    
3. Para criar o novo repositório de gerenciamento central no banco de dados do Skype for Business Server 2019 do SQL Server, no Shell de gerenciamento do Skype for Business Server, digite:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirme se o status do serviço de **front-end do Skype for Business Server** foi **iniciado**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar um servidor front-end padrão da edição

1. No servidor front-end do Skype for Business Server 2019 Standard Edition onde você deseja realocar o servidor de gerenciamento central, faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins** . 
    
2. Abra o assistente de implantação do Skype for Business Server.
    
3. No assistente de implantação do Skype for Business Server, clique em **preparar primeiro servidor Standard Edition**.
    
4. Na página **comandos em execução** , o SQL Server Express é instalado como o servidor de gerenciamento central. Regras de firewall necessárias são criadas. Quando a instalação do banco de dados e do software de pré-requisito estiver concluída, clique em **concluir**.
    
    > [!NOTE]
    > A instalação inicial pode levar algum tempo sem atualizações visíveis para a tela Resumo da saída do comando. Isso se deve à instalação do SQL Server Express. Se você precisar monitorar a instalação do banco de dados, use o Gerenciador de tarefas para monitorar a configuração. 
  
5. Para criar o novo repositório de gerenciamento central no servidor front-end do Skype for Business Server 2019 Standard Edition, no Shell de gerenciamento do Skype for Business Server, digite: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirme se o status do serviço de **front-end do Skype for Business Server** foi **iniciado**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Para mover o herdado instala o servidor central de gerenciamento para o Skype for Business Server 2019

1. No servidor do Skype for Business Server 2019 que será o servidor de gerenciamento central, faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins** . Você também deve ter direitos de usuário e permissões de administrador de banco de dados do SQL Server. 
    
2. Abrir o Shell de gerenciamento do Skype for Business Server (executar como administrador).
    
3. No Shell de gerenciamento do Skype for Business Server, digite: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Se `Enable-CsTopology` o problema não for bem-sucedido, resolva o problema para impedir que o comando seja concluído antes de continuar. Se **Enable-CsTopology** não for bem-sucedido, a mudança falhará e poderá deixar a sua topologia em um estado em que não haja repositório de gerenciamento central. 
  
4. No servidor front-end do Skype for Business Server 2019 ou no pool de front-end do Shell de gerenciamento do Skype for Business Server, digite: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Shell de gerenciamento do Skype for Business Server exibe os servidores, armazenamentos de arquivos, armazenamentos de banco de dados e os pontos de conexão de serviço do estado atual e o Estado proposto. Leia as informações com atenção e confirme se essa é a origem e o destino pretendidos. Digite **Y** para continuar ou **N** para interromper a movimentação. 
    
6. Revise todos os avisos ou erros gerados pelo comando **mover-CsManagementServer** e resolva-os. 
    
7. No servidor do Skype for Business Server 2019, abra o assistente de implantação do Skype for Business Server. 
    
8. No assistente de implantação do Skype for Business Server, clique em **instalar ou atualizar o sistema do Skype for Business Server**, clique em **etapa 2: configurar ou remover componentes do Skype for Business Server**, clique em **Avançar**, revise o resumo e clique em **concluir**. 
    
9. No servidor de instalação herdado, abra o assistente de implantação. 
    
10. No assistente de implantação do Skype for Business Server, clique em **instalar ou atualizar o sistema do Skype for Business Server**, clique em **etapa 2: configurar ou remover componentes do Skype for Business Server**, clique em **Avançar**, revise o resumo e clique em **concluir**. 
    
11. Reinicie o servidor do Skype for Business Server 2019. Isso é necessário devido a uma alteração de associação do grupo para acessar o banco de dados do servidor de gerenciamento central.
    
12. Para confirmar se a replicação com o novo repositório de gerenciamento central está ocorrendo, no Shell de gerenciamento do Skype for Business Server, digite: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > A replicação pode levar algum tempo para atualizar todas as réplicas atuais. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Para remover arquivos do repositório de gerenciamento central de instalação herdada após uma mudança

1. No servidor de instalação herdado, faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins** . Você também deve ter direitos de usuário e permissões de administrador de banco de dados do SQL Server. 
    
2. Abrir o Shell de gerenciamento do Skype for Business Server
    
    > [!CAUTION]
    > Não prossiga com a remoção dos arquivos de banco de dados anteriores até que a replicação seja concluída e seja estável. Se você remover os arquivos antes de concluir a replicação, irá interromper o processo de replicação e deixar o servidor de gerenciamento central recentemente movido em um estado desconhecido. Use o cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar o status de replicação. 
  
3. Para remover os arquivos de banco de dados do repositório de gerenciamento central do servidor de gerenciamento central de instalação herdada, digite:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Por exemplo:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Onde o _ \<FQDN do SQL Server\> _ é o servidor back-end de instalação herdada em uma implantação do Enterprise Edition ou o FQDN do servidor Standard Edition. 
    

