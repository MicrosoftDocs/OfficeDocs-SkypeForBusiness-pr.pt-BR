---
title: Mover o servidor de gerenciamento central
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Após a migração para o Skype for Business Server 2019, você precisa mover o servidor de gerenciamento central para o servidor de front-end ou pool do Skype for Business Server 2019, antes de poder remover o servidor herdado.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752463"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Mover o servidor de gerenciamento central herdado para o Skype for Business Server 2019

Após migrar para o Skype for Business Server 2019 e antes de remover o servidor herdado, você precisará mover o servidor de gerenciamento central para o servidor front-end ou pool do Skype for Business Server 2019. 
  
O servidor de gerenciamento central é um único sistema de réplicas/mestres, onde a cópia de leitura/gravação do banco de dados é mantida pelo servidor de front-end que contém o servidor de gerenciamento central. Cada computador na topologia, incluindo o servidor front-end que contém o servidor de gerenciamento central, tem uma cópia somente leitura do repositório de gerenciamento central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e implantação. O banco de dados local recebe atualizações de réplica por meio do agente replicador de réplica do Skype for Business Server que é executado como um serviço em todos os computadores. O nome do banco de dados real no servidor de gerenciamento central e na réplica local é XDS, que é composto pelos arquivos XDS. MDF e XDS. ldf. O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio do Active Directory. Todas as ferramentas que usam o servidor de gerenciamento central para gerenciar e configurar o Skype for Business Server usam o SCP para localizar o repositório de gerenciamento central.
  
Depois de mover com êxito o servidor de gerenciamento central, você deve remover os bancos de dados do servidor de gerenciamento central do servidor front-end original. Para obter informações sobre como remover os bancos de dados do servidor de gerenciamento central, consulte [remover o banco de dados do SQL Server para um pool de front-ends](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Você usa o cmdlet **move-CsManagementServer** do Windows PowerShell no Shell de gerenciamento do Skype for Business Server para mover o banco de dados do banco de dados do SQL Server herdado para o banco de dados do sql Server 2019 do Skype for Business Server e, em seguida, atualizar o scp para apontar para o local do servidor de gerenciamento central do Skype for business Server 2019. 
  
Use os procedimentos desta seção para preparar os servidores front-end do Skype for Business Server 2019 antes de mover o servidor de gerenciamento central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Para preparar um pool de front-ends Enterprise Edition

1. No pool de front-ends do Skype for Business Server 2019 Enterprise Edition onde você deseja realocar o servidor de gerenciamento central, faça logon no computador onde o Shell de gerenciamento do Skype for Business Server está instalado como um membro do grupo **RTCUniversalServerAdmins** . Você também deve ter direitos e permissões de usuário sysadmin do SQL Server no banco de dados onde você deseja instalar o repositório de gerenciamento central. 
    
2. Abra o Shell de gerenciamento do Skype for Business Server.
    
3. Para criar o novo repositório de gerenciamento central no banco de dados do SQL Server 2019 do Skype for Business Server, no Shell de gerenciamento do Skype for Business Server, digite:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirme se o status do serviço **front-end do Skype for Business Server** foi **iniciado**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar um servidor front-end Standard Edition

1. No servidor front-end do Skype for Business Server 2019 Standard Edition onde você deseja realocar o servidor de gerenciamento central, faça logon no computador onde o Shell de gerenciamento do Skype for Business Server está instalado como um membro do grupo **RTCUniversalServerAdmins** . 
    
2. Abra o assistente de implantação do Skype for Business Server.
    
3. No assistente de implantação do Skype for Business Server, clique em **preparar primeiro servidor Standard Edition**.
    
4. Na página **executando comandos** , o SQL Server Express é instalado como o servidor de gerenciamento central. Regras de firewall necessárias são criadas. Quando a instalação do banco de dados e software de pré-requisito estiver concluída, clique em **Finalizar**.
    
    > [!NOTE]
    > A instalação inicial pode levar algum tempo sem nenhuma atualização visível na tela de resumo de saída do comando. Isso ocorre devido à instalação do SQL Server Express. Se você precisa monitorar a instalação do banco de dados, use o Gerenciador de Tarefas para monitorar a configuração. 
  
5. Para criar o novo repositório de gerenciamento central no servidor front-end do Skype for Business Server 2019 Standard Edition, no Shell de gerenciamento do Skype for Business Server, digite: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirme se o status do serviço **front-end do Skype for Business Server** foi **iniciado**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Para mover o herdado instala o servidor de gerenciamento central para o Skype for Business Server 2019

1. No servidor do Skype for Business Server 2019 que será o servidor de gerenciamento central, faça logon no computador onde o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins** . Você também deve ter direitos e permissões do usuário administrador do banco de dados do SQL Server. 
    
2. Abra o Shell de gerenciamento do Skype for Business Server (executar como administrador).
    
3. No Shell de gerenciamento do Skype for Business Server, digite: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Se `Enable-CsTopology` o não for bem-sucedido, resolva o problema que impede o comando de concluir antes de continuar. Se **Enable-CsTopology** não for bem-sucedido, a movimentação falhará e poderá deixar sua topologia em um estado em que não haja repositório de gerenciamento central. 
  
4. No servidor front-end do Skype for Business Server 2019 ou no pool de front-ends, no Shell de gerenciamento do Skype for Business Server, digite: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. O Shell de gerenciamento do Skype for Business Server exibe os servidores, repositórios de arquivos, repositórios de bancos de dados e os pontos de conexão de serviço do estado atual e o Estado proposto. Leia as informações cuidadosamente e confirme que esta é a origem e o destino pretendido. Digite **Y** para continuar ou **N** para parar a movimentação. 
    
6. Revise qualquer aviso ou erro gerado pelo comando **Move-CsManagementServer** e resolva-os. 
    
7. No servidor do Skype for Business Server 2019, abra o assistente de implantação do Skype for Business Server. 
    
8. No assistente de implantação do Skype for Business Server, clique em **instalar ou atualizar o sistema do Skype for Business Server**, clique em **etapa 2: configurar ou remover componentes do Skype for Business Server**, clique em **Avançar**, revise o resumo e clique em **concluir**. 
    
9. No servidor de instalação herdado, abra o assistente de implantação. 
    
10. No assistente de implantação do Skype for Business Server, clique em **instalar ou atualizar o sistema do Skype for Business Server**, clique em **etapa 2: configurar ou remover componentes do Skype for Business Server**, clique em **Avançar**, revise o resumo e clique em **concluir**. 
    
11. Reinicialize o servidor do Skype for Business Server 2019. Isso é necessário devido a uma alteração na associação de grupo para acessar o banco de dados do servidor de gerenciamento central.
    
12. Para confirmar se a replicação com o novo repositório de gerenciamento central está ocorrendo, no Shell de gerenciamento do Skype for Business Server, digite: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > A replicação pode levar algum tempo para atualizar todas as réplicas atuais. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Para remover arquivos de repositório de gerenciamento central de instalação herdados após uma movimentação

1. No servidor de instalação herdado, faça logon no computador onde o Shell de gerenciamento do Skype for Business Server está instalado como um membro do grupo **RTCUniversalServerAdmins** . Você também deve ter direitos e permissões do usuário administrador do banco de dados do SQL Server. 
    
2. Abrir o Shell de gerenciamento do Skype for Business Server
    
    > [!CAUTION]
    > Não continue com a remoção dos arquivos do banco de dados anteriores até que a replicação esteja concluída e estável. Se você remover os arquivos antes de concluir a replicação, interromperá o processo de replicação e deixará o servidor de gerenciamento central recentemente movido em um estado desconhecido. Use o cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar o status da replicação. 
  
3. Para remover os arquivos do banco de dados do repositório de gerenciamento central do servidor de gerenciamento central de instalação herdado, digite:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Por exemplo:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Em que o _\<FQDN of SQL Server\>_ é o servidor back-end de instalação herdado em uma implantação Enterprise Edition ou o FQDN do servidor Standard Edition. 
    

