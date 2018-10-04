---
title: Mover o servidor de gerenciamento Central
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após migrar para o Skype para Business Server 2019, você precisa mover o servidor de gerenciamento Central para o Skype para Business Server 2019 servidor Front-End ou pool, antes de poder remover o servidor herdado.
ms.openlocfilehash: 6a358b11d7d319d5dafbb82f4391cdc3d0ae1562
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373440"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Mover o servidor de gerenciamento Central herdado para Skype para Business Server 2019

Após migrar para o Skype para Business Server 2019 e antes de poder remover o servidor herdado, você precisa mover o servidor de gerenciamento Central para o Skype para Business Server 2019 servidor Front-End ou pool. 
  
O servidor de gerenciamento Central é um sistema de única réplica mestre/múltiplo, onde a cópia de leitura/gravação do banco de dados é mantida por servidor Front-End que contém o servidor de gerenciamento Central. Cada computador na topologia, incluindo o servidor Front-End que contém o servidor de gerenciamento Central, tem uma cópia somente leitura dos dados do repositório de gerenciamento Central em dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e implantação. O banco de dados local recebe atualizações de réplica por meio do Skype para agente replicador de réplica de servidor de negócios que é executado como um serviço em todos os computadores. O nome do banco de dados real no servidor de gerenciamento Central e da réplica local é XDS, que é composta dos arquivos XDS. mdf e xds.ldf. O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio Active Directory. Todas as ferramentas que usam o servidor de gerenciamento Central para gerenciar e configurar o Skype para Business Server usam o SCP para localizar o repositório de gerenciamento Central.
  
Após você moveu com êxito o servidor de gerenciamento Central, você deve remover os bancos de dados do servidor de gerenciamento Central do servidor Front-End original. Para obter informações sobre como remover os bancos de dados do servidor de gerenciamento Central, consulte [Remover o banco de dados do SQL Server para um pool de Front-End](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Você usa o cmdlet **Move-CsManagementServer** no Skype para Business Server Management Shell mover o banco de dados do banco de dados de SQL Server instalar herdado para o Skype para banco de dados de negócios Server 2019 SQL Server e atualizar do Windows PowerShell a SCP para apontar para o Skype para o local do servidor de gerenciamento Central do Business Server 2019. 
  
Use os procedimentos nesta seção para preparar o Skype Business Server 2019 servidores Front-End antes de mover o servidor de gerenciamento Central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Para preparar um pool de Front End do Enterprise Edition

1. Em Skype para pool de negócios 2019 Enterprise Edition Front-End Server onde você deseja realocar o servidor de gerenciamento Central, faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do **RTCUniversalServerAdmins **grupo. Você também deve ter permissões e direitos de usuário de sysadmin do SQL Server banco de dados no banco de dados onde você deseja instalar o repositório de gerenciamento Central. 
    
2. Abra o Skype do Shell de gerenciamento do servidor de negócios.
    
3. Para criar o novo repositório de gerenciamento Central no Skype para banco de dados corporativos Server 2019 SQL Server, no Skype do Shell de gerenciamento do servidor de negócios, digite:
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirme se o status do serviço do **Skype para Business Server front-end** é **iniciado**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar um Standard Edition servidor Front-End

1. Em Skype para Business Server 2019 servidor Standard Edition Front End onde você deseja realocar o servidor de gerenciamento Central, faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do **RTCUniversalServerAdmins **grupo. 
    
2. Abra o Skype do Assistente de implantação de servidor de negócios.
    
3. Na Skype para o Assistente de implantação do Business Server, clique em **Preparar primeiro servidor Standard Edition**.
    
4. Na página **Executando comandos** , o SQL Server Express está instalado como o servidor de gerenciamento Central. Regras de firewall necessárias são criadas. Quando a instalação do banco de dados e o software de pré-requisito for concluída, clique em **Concluir**.
    
    > [!NOTE]
    > A instalação inicial pode levar algum tempo com nenhuma atualização visível na tela de resumo de saída do comando. Isso acontece devido à instalação do SQL Server Express. Se você precisa monitorar a instalação do banco de dados, use o Gerenciador de tarefas para monitorar a instalação. 
  
5. Para criar o novo repositório de gerenciamento Central no Skype para Business Server 2019 Standard Edition servidor Front-End no Skype do Shell de gerenciamento do servidor de negócios, digite: 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirme se o status do serviço do **Skype para Business Server front-end** é **iniciado**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Para mover o antigo instala o servidor de gerenciamento Central Skype para Business Server 2019

1. Sobre o Skype para servidor de Business Server 2019 que será o servidor de gerenciamento Central, faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo **RTCUniversalServerAdmins** . Você também deve ter as permissões e direitos de usuário de administrador de banco de dados do SQL Server. 
    
2. Abra o Skype do Shell de gerenciamento do servidor de negócios.
    
3. Em Skype do Shell de gerenciamento do servidor de negócios, digite: 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Se `Enable-CsTopology` não for bem-sucedida, resolver o problema, impedindo que o comando concluir antes de continuar. Se **Enable-CsTopology** não for bem-sucedida, a movimentação falhará e ele poderá deixar a sua topologia em um estado onde não há nenhum repositório de gerenciamento Central. 
  
4. Sobre o Skype para pool Business Server 2019 servidor Front-End ou Front-End, no Skype do Shell de gerenciamento do servidor de negócios, digite: 
    
   ```
   Move-CsManagementServer
   ```

5. Skype do Shell de gerenciamento do servidor de negócios exibe os pontos de conexão de serviço do estado atual e o estado de proposto, repositórios de arquivos, repositórios de banco de dados e os servidores. Leia as informações cuidadosamente e confirme que este é pretendido de origem e de destino. Digite **Y** para continuar ou **N** para interromper a movimentação. 
    
6. Revise quaisquer avisos ou erros gerados pelo comando **Move-CsManagementServer** e resolva-os. 
    
7. No Skype para Business Server 2019 server, abra o Skype para o Assistente de implantação de servidor de negócios. 
    
8. No Skype para o Assistente de implantação do Business Server, clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**, clique em **etapa 2: instalar ou remover Skype para componentes de servidor de negócios**, clique em **Avançar**, revise o resumo e clique em **Concluir **. 
    
9. No antigo servidor instalado, abra o Assistente para implantação. 
    
10. No Skype para o Assistente de implantação do Business Server, clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**, clique em **etapa 2: instalar ou remover Skype para componentes de servidor de negócios**, clique em **Avançar**, revise o resumo e clique em **Concluir **. 
    
11. Reinicialize o Skype para Business Server 2019 server. Isso é necessário devido a uma alteração de associação de grupo para acessar o banco de dados do servidor de gerenciamento Central.
    
12. Para confirmar que a replicação com o novo repositório está ocorrendo, além de gerenciamento Central do Skype do Shell de gerenciamento do servidor de negócios, digite: 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > A replicação pode levar algum tempo para atualizar todas as réplicas atuais. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Para remover o legacy instalar arquivos do repositório de gerenciamento Central após uma movimentação

1. Sobre o antigo instalar o servidor, faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo **RTCUniversalServerAdmins** . Você também deve ter as permissões e direitos de usuário de administrador de banco de dados do SQL Server. 
    
2. Abra o Skype do Shell de gerenciamento do servidor de negócios
    
    > [!CAUTION]
    > Não prossiga com a remoção dos arquivos de banco de dados anterior até que a replicação seja concluída e esteja estável. Se você remover os arquivos antes de concluir a replicação, você irá interromper o processo de replicação e deixar o recém movido servidor de gerenciamento Central em um estado desconhecido. Use o cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar o status da replicação. 
  
3. Para remover os arquivos de banco de dados do repositório de gerenciamento Central da herdado instalar servidor de gerenciamento Central, digite:
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Por exemplo:
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Onde o _ \<FQDN do SQL Server\> _ é o legados instalar o servidor Back-End em uma implantação do Enterprise Edition ou o FQDN do servidor do Standard Edition. 
    

