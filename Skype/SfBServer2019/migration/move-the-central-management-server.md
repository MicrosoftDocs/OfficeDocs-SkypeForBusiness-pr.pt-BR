---
title: Mover o Servidor de Gerenciamento Central
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
description: Depois de migrar para o Skype for Business Server 2019, você precisará mover o Servidor de Gerenciamento Central para o Pool ou Servidor de Front End do Skype for Business Server 2019, antes de poder remover o servidor herdado.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752463"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Mover o Servidor de Gerenciamento Central herdada para o Skype for Business Server 2019

Depois de migrar para o Skype for Business Server 2019 e antes de remover o servidor herdado, você precisa mover o Servidor de Gerenciamento Central para o Pool ou Servidor de Front End do Skype for Business Server 2019. 
  
O Servidor de Gerenciamento Central é um único sistema mestre/com várias réplicas, onde a cópia de leitura/gravação do banco de dados é mantida pelo Servidor front-end que contém o Servidor de Gerenciamento Central. Cada computador na topologia, incluindo o Servidor #A0 que contém o Servidor de Gerenciamento Central, tem uma cópia somente leitura dos dados do armazenamento de Gerenciamento Central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e implantação. O banco de dados local recebe atualizações de réplica por meio do Agente Replicador de Réplicas do Skype for Business Server que é executado como um serviço em todos os computadores. O nome do banco de dados real no Servidor de Gerenciamento Central e a réplica local é XDS, que é feito dos arquivos xds.mdf e xds.ldf. O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos Serviços de Domínio Active Directory. Todas as ferramentas que usam o Servidor de Gerenciamento Central para gerenciar e configurar o Skype for Business Server usam o SCP para localizar o armazenamento de Gerenciamento Central.
  
Depois de ter movido com êxito o Servidor de Gerenciamento Central, remova os bancos de dados do Servidor de Gerenciamento Central do Servidor front-end original. Para obter informações sobre como remover os bancos de dados do Servidor de Gerenciamento Central, consulte Remover o banco de dados [do SQL Server para um pool de Front-End.](remove-the-sql-server-database-for-a-front-end-pool.md)
  
Use o cmdlet do Windows PowerShell **Move-CsManagementServer** no Shell de Gerenciamento do Skype for Business Server para mover o banco de dados do banco de dados de instalação herdado do SQL Server para o banco de dados do SQL Server 2019 e atualize o SCP para apontar para o local do Servidor de Gerenciamento Central do Skype for Business Server 2019. 
  
Use os procedimentos nesta seção para preparar os Servidores front-end do Skype for Business Server 2019 antes de mover o Servidor de Gerenciamento Central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Para preparar um pool de front-end do Enterprise Edition

1. No pool de front-end do Skype for Business Server 2019 Enterprise Edition em que você deseja realocar o Servidor de Gerenciamento Central, faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins.** Você também deve ter direitos e permissões de usuário sysadmin do banco de dados do SQL Server no banco de dados em que deseja instalar o armazenamento de Gerenciamento Central. 
    
2. Abra o Shell de Gerenciamento do Skype for Business Server.
    
3. Para criar o novo armazenamento de Gerenciamento Central no banco de dados do SQL Server do Skype for Business Server 2019, no Shell de Gerenciamento do Skype for Business Server, digite:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirme se o status do **serviço front-end** do Skype for Business Server foi **iniciado.**
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar um servidor front-end Standard Edition

1. No Servidor front-end do Skype for Business Server 2019 Standard Edition em que você deseja realocar o Servidor de Gerenciamento Central, faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins.** 
    
2. Abra o Assistente de Implantação do Skype for Business Server.
    
3. No Assistente de Implantação do Skype for Business Server, clique em **Preparar primeiro servidor Standard Edition.**
    
4. Na página **Executando Comandos,** o SQL Server Express é instalado como o Servidor de Gerenciamento Central. Regras de firewall necessárias são criadas. Quando a instalação do banco de dados e software de pré-requisito estiver concluída, clique em **Finalizar**.
    
    > [!NOTE]
    > A instalação inicial pode levar algum tempo sem nenhuma atualização visível na tela de resumo de saída do comando. Isso ocorre devido à instalação do SQL Server Express. Se você precisa monitorar a instalação do banco de dados, use o Gerenciador de Tarefas para monitorar a configuração. 
  
5. Para criar o novo armazenamento de Gerenciamento Central no Servidor front-end do Skype for Business Server 2019 Standard Edition, no Shell de Gerenciamento do Skype for Business Server, digite: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirme se o status do **serviço front-end** do Skype for Business Server foi **iniciado.**
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Para mover as instalações herdada do Servidor de Gerenciamento Central para o Skype for Business Server 2019

1. No servidor do Skype for Business Server 2019 que será o Servidor de Gerenciamento Central, faça logoff no computador em que o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins.** Você também deve ter direitos e permissões do usuário administrador do banco de dados do SQL Server. 
    
2. Abra o Shell de Gerenciamento do Skype for Business Server (executado como administrador).
    
3. No Shell de Gerenciamento do Skype for Business Server, digite: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Se `Enable-CsTopology` não tiver êxito, resolva o problema impedindo que o comando seja concluído antes de continuar. Se **Enable-CsTopology** não for bem-sucedido, a movimentação falhará e poderá deixar sua topologia em um estado onde não há nenhum armazenamento de Gerenciamento Central. 
  
4. No servidor front-end ou pool de front-end do Skype for Business Server 2019, no Shell de Gerenciamento do Skype for Business Server, digite: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. O Shell de Gerenciamento do Skype for Business Server exibe os servidores, os armazenamentos de arquivos, os armazenamentos de banco de dados e os pontos de conexão de serviço do Estado Atual e do Estado Proposto. Leia as informações cuidadosamente e confirme que esta é a origem e o destino pretendido. Digite **Y** para continuar ou **N** para parar a movimentação. 
    
6. Revise qualquer aviso ou erro gerado pelo comando **Move-CsManagementServer** e resolva-os. 
    
7. No servidor do Skype for Business Server 2019, abra o Assistente de Implantação do Skype for Business Server. 
    
8. In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click Step **2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**. 
    
9. No servidor de instalação herddo, abra o Assistente de Implantação. 
    
10. In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click Step **2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**. 
    
11. Reinicialize o servidor do Skype for Business Server 2019. Isso é necessário devido a uma alteração de associação de grupo para acessar o banco de dados do Servidor de Gerenciamento Central.
    
12. Para confirmar que a replicação com o novo armazenamento de Gerenciamento Central está ocorrendo, no Shell de Gerenciamento do Skype for Business Server, digite: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > A replicação pode levar algum tempo para atualizar todas as réplicas atuais. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Para remover arquivos do armazenamento de Gerenciamento Central de instalação herdado após uma movimentação

1. No servidor de instalação herdado, faça logoff no computador em que o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo **RTCUniversalServerAdmins.** Você também deve ter direitos e permissões do usuário administrador do banco de dados do SQL Server. 
    
2. Abra o Shell de Gerenciamento do Skype for Business Server
    
    > [!CAUTION]
    > Não continue com a remoção dos arquivos do banco de dados anteriores até que a replicação esteja concluída e estável. Se você remover os arquivos antes de concluir a replicação, interromperá o processo de replicação e deixará o Servidor de Gerenciamento Central recém-movido em um estado desconhecido. Use o cmdlet **Get-CsManagementStoreReplicationStatus** para confirmar o status da replicação. 
  
3. Para remover os arquivos de banco de dados do armazenamento de Gerenciamento Central do Servidor de Gerenciamento Central de instalação herdado, digite:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Por exemplo:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Onde está o Servidor back-end de instalação herdado em uma implantação Enterprise Edition ou o  _\<FQDN of SQL Server\>_ FQDN do servidor Standard Edition. 
    

