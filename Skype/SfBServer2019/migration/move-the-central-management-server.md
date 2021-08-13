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
description: Depois de migrar para o Skype for Business Server 2019, você precisará mover o Servidor de Gerenciamento Central para o servidor ou pool de front-end do Skype for Business Server 2019, antes de poder remover o servidor herdado.
ms.openlocfilehash: 0c5ee756a52d61008498e50df5d3bf64fbe20f8c4ef1ee96e4e7528c2a3bd820
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300597"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Mover o Servidor de Gerenciamento Central herdado para Skype for Business Server 2019

Depois de migrar para o Skype for Business Server 2019 e antes de poder remover o servidor herdado, você precisa mover o Servidor de Gerenciamento Central para o servidor ou pool do Skype for Business Server 2019. 
  
O Servidor de Gerenciamento Central é um único sistema mestre/réplica múltipla, onde a cópia de leitura/gravação do banco de dados é mantida pelo Servidor de Front-End que contém o Servidor de Gerenciamento Central. Cada computador na topologia, incluindo o Servidor front-end que contém o Servidor de Gerenciamento Central, tem uma cópia somente leitura dos dados do armazenamento do Gerenciamento Central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e implantação. O banco de dados local recebe atualizações de réplica por meio do Skype for Business Server Replica ReplicaDor que é executado como um serviço em todos os computadores. O nome do banco de dados real no Servidor de Gerenciamento Central e a réplica local é XDS, que é feito dos arquivos xds.mdf e xds.ldf. O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos Serviços de Domínio do Active Directory. Todas as ferramentas que usam o Servidor de Gerenciamento Central para gerenciar e configurar Skype for Business Server usar o SCP para localizar o armazenamento de Gerenciamento Central.
  
Depois de ter movido com êxito o Servidor de Gerenciamento Central, remova os bancos de dados do Servidor de Gerenciamento Central do Servidor Front-End original. Para obter informações sobre como remover os bancos de dados do Servidor de Gerenciamento Central, consulte [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Você usa o cmdlet **move-CsManagementServer** do Windows PowerShell no Shell de Gerenciamento do Skype for Business Server para mover o banco de dados do banco de dados de instalação herdada do SQL Server para o banco de dados SQL Server do Skype for Business Server 2019 e atualizar o SCP para apontar para o local do Servidor de Gerenciamento Central do Skype for Business Server 2019. 
  
Use os procedimentos nesta seção para preparar os servidores front-end Skype for Business Server 2019 antes de mover o Servidor de Gerenciamento Central.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Para preparar um pool Edição Enterprise front-end

1. No pool de front-end do Skype for Business Server 2019 Edição Enterprise onde você deseja realocar o Servidor de Gerenciamento Central, faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do **grupo RTCUniversalServerAdmins.** Você também deve ter SQL Server de usuário sysadmin de banco de dados e permissões no banco de dados onde deseja instalar o armazenamento de Gerenciamento Central. 
    
2. Abra o Shell Skype for Business Server Gerenciamento.
    
3. Para criar o novo armazenamento de Gerenciamento Central no banco de dados Skype for Business Server 2019 SQL Server 2019, no Shell de Gerenciamento Skype for Business Server, digite:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Confirme se o status do serviço **Skype for Business Server Front-End** é **Iniciado**.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar um servidor Edição Standard front-end

1. No servidor de front-end do Skype for Business Server 2019 Edição Standard 2019 onde você deseja realocar o Servidor de Gerenciamento Central, faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do **grupo RTCUniversalServerAdmins.** 
    
2. Abra o Assistente Skype for Business Server implantação.
    
3. No Assistente Skype for Business Server implantação, clique em **Preparar o primeiro Edição Standard servidor**.
    
4. Na página **Comandos de** Execução, SQL Server Express é instalado como o Servidor de Gerenciamento Central. Regras de firewall necessárias são criadas. Quando a instalação do banco de dados e software de pré-requisito estiver concluída, clique em **Finalizar**.
    
    > [!NOTE]
    > A instalação inicial pode levar algum tempo sem nenhuma atualização visível na tela de resumo de saída do comando. Isso ocorre devido à instalação de SQL Server Express. Se você precisa monitorar a instalação do banco de dados, use o Gerenciador de Tarefas para monitorar a configuração. 
  
5. Para criar o novo armazenamento de Gerenciamento Central no Skype for Business Server 2019 Edição Standard Servidor Front-End, no Shell de Gerenciamento Skype for Business Server, digite: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Confirme se o status do serviço **Skype for Business Server Front-End** é **Iniciado**.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Para mover o servidor de gerenciamento central herdado para Skype for Business Server 2019

1. No servidor Skype for Business Server 2019 que será o Servidor de Gerenciamento Central, faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do **grupo RTCUniversalServerAdmins.** Você também deve ter direitos e permissões do usuário administrador do banco de dados do SQL Server. 
    
2. Abra Skype for Business Server Shell de Gerenciamento (executado como administrador).
    
3. No Shell Skype for Business Server Gerenciamento, digite: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Se `Enable-CsTopology` não tiver êxito, resolva o problema que impede que o comando seja concluído antes de continuar. Se **Enable-CsTopology** não for bem-sucedido, a movimentação falhará e poderá deixar sua topologia em um estado em que não há nenhum armazenamento de Gerenciamento Central. 
  
4. No pool Skype for Business Server 2019 ou servidor front-end, no Shell de Gerenciamento Skype for Business Server, digite: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype for Business Server O Shell de Gerenciamento exibe os servidores, os armazenamentos de arquivos, os armazenamentos de banco de dados e os pontos de conexão de serviço do Estado Atual e do Estado Proposto. Leia as informações cuidadosamente e confirme que esta é a origem e o destino pretendido. Digite **Y** para continuar ou **N** para parar a movimentação. 
    
6. Revise qualquer aviso ou erro gerado pelo comando **Move-CsManagementServer** e resolva-os. 
    
7. No servidor Skype for Business Server 2019, abra o Assistente Skype for Business Server implantação. 
    
8. No Skype for Business Server Assistente de Implantação, clique em Instalar ou Atualizar Skype for Business Server **Sistema,** clique em Etapa **2:** Instalação ou Remover componentes Skype for Business Server, clique em **Próximo**, revise o resumo e clique em **Concluir**. 
    
9. No servidor de instalação herddo, abra o Assistente de Implantação. 
    
10. No Skype for Business Server Assistente de Implantação, clique em Instalar ou Atualizar Skype for Business Server **Sistema,** clique em Etapa **2:** Instalação ou Remover componentes Skype for Business Server, clique em **Próximo**, revise o resumo e clique em **Concluir**. 
    
11. Reinicie o Skype for Business Server 2019. Isso é necessário devido a uma alteração de associação de grupo para acessar o banco de dados do Servidor de Gerenciamento Central.
    
12. Para confirmar que a replicação com o novo armazenamento de Gerenciamento Central está ocorrendo, no Shell de Gerenciamento Skype for Business Server, digite: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > A replicação pode levar algum tempo para atualizar todas as réplicas atuais. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Para remover arquivos de armazenamento de Gerenciamento Central de instalação herdados após uma movimentação

1. No servidor de instalação herdado, faça logoff no computador onde o Shell de Gerenciamento Skype for Business Server está instalado como membro do **grupo RTCUniversalServerAdmins.** Você também deve ter direitos e permissões do usuário administrador do banco de dados do SQL Server. 
    
2. Abrir Skype for Business Server Shell de Gerenciamento
    
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

    Onde o é o servidor back-end de instalação herdado em uma implantação Edição Enterprise _\<FQDN of SQL Server\>_ ou o FQDN do servidor Edição Standard. 
    

