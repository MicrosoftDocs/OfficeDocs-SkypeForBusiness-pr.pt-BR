---
title: Implantar um grupo de disponibilidade always on em um servidor back-end em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implantar (instalar) um Grupo de Disponibilidade Always On em sua Skype for Business Server implantação.
ms.openlocfilehash: c30a17ee0852cab3e8e61ee7751a6e8f5f5a6bd1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829465"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Implantar um grupo de disponibilidade always on em um servidor back-end em Skype for Business Server
 
Implantar (instalar) um Grupo de Disponibilidade Always On (AG) em sua Skype for Business Server implantação.
  
A implantação de uma AG depende de você implantá-lo em um novo pool, em um pool existente que usa espelhamento ou em um pool existente que atualmente não tenha alta disponibilidade para o banco de dados back-end.
  
> [!NOTE]
> Não há suporte para o uso de uma ag com uma função de Servidor de Chat Persistente. 
  
- [Implantar um grupo de disponibilidade always on em um novo pool de front-end](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Implantar um Grupo de Disponibilidade Always On em um pool existente que usa espelhamento de banco de dados](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Implantar um Grupo de Disponibilidade Always On em um pool existente que não usa espelhamento de banco de dados](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Implantar um grupo de disponibilidade always on em um novo pool de front-end
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Habilita o recurso clustering de failover em todos os servidores de banco de dados que fará parte da AG. Em cada servidor, faça o seguinte
    
   - Abra o Gerenciador de Servidores e clique **em Adicionar funções e recursos.**
    
   - Clique **em Próximo** até chegar à caixa Selecionar **recursos.** Aqui, marque a caixa **de seleção Clustering de Failover.**
    
   - Na caixa **Adicionar recursos necessários para Cluster de Failover?** clique em **Adicionar Recursos**.
    
   - Clique em **Instalar**.
    
2. Valide a configuração do cluster.
    
   - No Gerenciador de Servidores, clique no menu **Ferramentas** e clique em **Gerenciador de Cluster de Failover.**
    
   - Em **Ações** no lado direito da tela, clique em **Validar Configuração**.
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Selecione os servidores a adicionar ao cluster e clique em **Executar todos os testes**.
    
   - Na caixa **Resumo,** verifique os erros que o assistente relata. Em **seguida, clique em** Concluir para concluir a validação.
    
     O assistente provavelmente relatará vários avisos, especialmente se você não estiver usando o armazenamento compartilhado. Não é necessário usar armazenamento compartilhado. No entanto, se você vir qualquer **mensagem de** erro, deverá corrigir esses problemas antes de continuar.
    
3. Crie o Windows de Failover do Servidor (WSFC).
    
   - No assistente **de Gerenciamento de Cluster de Failover,** clique com o botão direito do mouse em Gerenciamento de Cluster de **Failover** e clique **em Criar Cluster**.
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Adicione o nome do cluster e o endereço IP. Quando as configurações são validadas, clique em **Próximo**.
    
   - Na página Confirmação, clique em **Avançar**.
    
   - Depois que o cluster for criado, clique em **Concluir**.
    
4. Recomendamos que você configure as configurações de quórum de cluster para usar uma testemunha de compartilhamento de arquivos. Para fazer isso, use estas etapas:
    
   - Clique com o botão direito do mouse no nome do cluster, clique em **Mais Ações** e clique em **Configurar Quorum de Cluster Configurações**.
    
   - Na página **Selecionar Opção de Configuração de Quórum,** clique **em Selecionar a testemunha de quórum**.
    
   - Na página **Selecionar Testemunha de Quórum,** clique em **Configurar uma testemunha de compartilhamento de arquivo**.
    
   - Na página **Configurar Testemunha de Compartilhamento** de Arquivos, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Próximo**.
    
   - Na página **Confirmação**, clique em **Avançar**.
    
5. Em cada servidor no cluster, habilita o recurso AG no SQL Server Configuration Manager.
    
   - Abra o Gerente de configuração do SQL Server. Na árvore no lado esquerdo da tela, clique em serviços SQL Server **e** clique duas vezes no serviço SQL Server. 
    
   - Na caixa **Propriedades,** selecione a guia **Alta Disponibilidade AlwaysOn.** Marque a **caixa de seleção Habilitar Grupos de Disponibilidade AlwaysOn.** Reinicie o SQL Server quando solicitado.
   
6. Use o Construtor de Topologias para criar o pool de Front-End, conforme explicado em [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md). Ao fazer isso, especifique o AG como o SQL do pool.
    
7. Crie o grupo de disponibilidade.
    
   - Abra SQL Server Management Studio e conecte-se à instância SQL Server.
    
   - No Explorador de Objetos, expanda **a pasta Always On High Availability.** Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em Novo Assistente de Grupo de **Disponibilidade.**
    
   - Se a **página Introdução** for exibida, clique em **Próximo**.
    
   - Na página **Especificar Nome do Grupo de Disponibilidade,** digite o nome do grupo Disponibilidade e clique em **Próximo**.
    
   - Na página Selecionar Bancos de Dados, selecione os bancos de dados que você deseja incluir no Grupo de Disponibilidade AlwaysOn. Depois, clique em **Avançar**.
    
     Não inclua os bancos de dados **ReportServer,** **ReportServerTempDB** ou Chat Persistente no Grupo de Disponibilidade AlwaysOn, pois eles não têm suporte neste cenário. Você pode incluir todos os outros Skype for Business Server de dados no Grupo de Disponibilidade AlwaysOn.
    
   - Na página **Especificar Réplicas,** clique na **guia Réplicas.** Em seguida, clique no botão Adicionar **Réplicas** e conecte-se às outras instâncias SQL que você ingressou como nós do cluster de Failover do Windows Server.
    
   - Para cada instância, selecione as **opções Failover Automático** e **Confirmação Síncrona.** Não selecione a **opção Secundário Acessível.**
    
   - Clique na **guia Pontos de** Extremidade e verifique se o Número da **Porta** está definido como 5022.
    
   - Clique na **guia Ouvinte** e selecione a opção Criar um ouvinte de **grupo de** disponibilidade. Nessa opção, digite um nome para o ouvinte e de definir a **Porta** como 1433 (outras portas não são suportadas para essa opção).
    
   - Clique **em** Adicionar e, em seguida, na caixa **Endereço IPv4,** forneça seu endereço IP virtual preferencial e clique em **OK**.
    
   - Na página **Selecionar** Sincronização Inicial de Dados, selecione Completo e especifique uma pasta acessível às réplicas e que a conta de serviço SQL Server usada por ambas as réplicas tenha permissões de gravação. Depois, clique em **Avançar**.
    
     Esse compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você estiver lidando com bancos de dados grandes, recomendamos que você os inicialize manualmente caso sua largura de banda de rede não possa acomodar o tamanho dos backups do banco de dados.
    
   - Na página Validação, verifique se todas as verificações de validação são bem-sucedidas e clique em **Próximo**.
    
   - Na página **Resumo,** verifique todas as configurações e clique em Concluir.
      
8. Depois que o pool e a AG são implantados, execute algumas etapas finais para certificar-se de que os logons SQL estão em cada uma das réplicas no Grupo de Disponibilidade AlwaysOn. 
    
   - Abra o Construtor de Topologias, selecione **Baixar topologia da** implantação existente e clique em **OK**.
    
   - Expanda Skype for Business Server, expanda sua topologia e **expanda SQL Server Stores.** Clique com o botão direito do SQL do novo Grupo de Disponibilidade AlwaysOn e clique em **Editar Propriedades.**
    
     - Na parte inferior da página, na caixa **SQL Server FQDN,** altere o valor para o FQDN do Ouvinte da AG.
    
   - Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique**. Em seguida, na página de confirmação, clique **em Próximo**. Em seguida, aguarde alguns minutos para que a nova topologia seja replicada.
    
   - Abra SQL Server Management Studio e navegue até a AG. Fail it over to a secondary replica.
    
   - Abra Skype for Business Server Shell de Gerenciamento e digite o seguinte cmdlet para criar SQL logon nesta réplica:
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Repita as duas etapas anteriores (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update` ) for each replica in the group.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Implantar um Grupo de Disponibilidade Always On em um pool existente que usa espelhamento de banco de dados
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se o pool que você está atualizando para uma AG hospeda o armazenamento de Gerenciamento Central da sua organização, primeiro você deve mover o CMS para outro pool antes de atualizar esse pool. Use o Move-CsManagementServer para mover o pool. Se você não tiver outro pool em sua organização, poderá implantar um servidor de Edição Standard temporariamente e mover o CMS para esse servidor antes de atualizar seu pool para a AG. 
  
1. Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Repita este cmdlet para cada tipo de banco de dados no pool. Você pode usar o cmdlet a seguir para encontrar todos os tipos de banco de dados armazenados neste pool.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Use o Construtor de Topologias para remover o espelhamento de banco de dados do pool.
    
   - Abra o Construtor de Topologia. Em sua topologia, **expanda Edição Enterprise Pools front-end,** clique com o botão direito do mouse no nome do pool e clique em **Editar Propriedades**.
    
   - Para cada tipo de SQL no pool, desative a caixa de seleção Habilitar SQL **Espelhamento da Loja.**
    
3. Publique a topologia alterada. No menu **Ação,** clique **em Topologia** e **publique**. Em seguida, na página de confirmação, clique em **Próximo**
    
4. Use SQL Server Management Studio para quebrar o espelho.
    
   - Abra SQL Server Management Studio, navegue até seus bancos de dados, clique com o botão direito do mouse em **Tarefas** e clique em **Espelho**. Em **seguida, clique em Remover Espelhamento** e clique em **OK**.
    
   - Repita isso para todos os bancos de dados no pool que serão convertidos em um AG.
    
5. Configurar o recurso Clustering de Failover em todos os servidores de banco de dados que fará parte da AG. Em cada servidor, faça o seguinte
    
   - Abra o Gerenciador de Servidores e clique **em Adicionar funções e recursos.**
    
   - Clique **em Próximo** até chegar à caixa Selecionar **recursos.** Aqui, marque a caixa **de seleção Clustering de Failover.**
    
   - Na caixa **Adicionar recursos necessários para Cluster de Failover?** clique em **Adicionar Recursos**.
    
   - Clique em **Instalar**.
    
6. Valide a configuração do cluster.
    
   - No Gerenciador de Servidores, clique no menu **Ferramentas** e clique em **Gerenciador de Cluster de Failover.**
    
   - Em **Ações** no lado direito da tela, clique em **Validar Configuração**.
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Selecione os servidores a adicionar ao cluster e clique em **Executar todos os testes**.
    
   - Na caixa **Resumo,** verifique os erros que o assistente relata. Em **seguida, clique em** Concluir para concluir a validação.
    
     O assistente provavelmente relatará vários avisos, especialmente se você não estiver usando o armazenamento compartilhado. Não é necessário usar armazenamento compartilhado. No entanto, se você vir qualquer **mensagem de** erro, deverá corrigir esses problemas antes de continuar.
    
7. Crie o Windows Cluster de Failover do Servidor.
    
   - No assistente **de Gerenciamento de Cluster de Failover,** clique com o botão direito do mouse em Gerenciamento de Cluster de **Failover** e clique **em Criar Cluster**.
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Adicione o nome do cluster e o endereço IP. Quando as configurações são validadas, clique em **Próximo**.
    
   - Na página Confirmação, clique em **Avançar**.
    
   - Depois que o cluster for criado, clique em **Concluir**.
    
8. Recomendamos que você configure as configurações de quórum de cluster para usar uma testemunha de compartilhamento de arquivos. Para fazer isso, use estas etapas:
    
   - Clique com o botão direito do mouse no nome do cluster, clique em **Mais Ações** e clique em **Configurar Quorum de Cluster Configurações**.
    
   - Na página **Selecionar Opção de Configuração de Quórum,** clique **em Selecionar a testemunha de quórum**.
    
   - Na página **Selecionar Testemunha de Quórum,** clique em **Configurar uma testemunha de compartilhamento de arquivo**.
    
   - Na página **Configurar Testemunha de Compartilhamento** de Arquivos, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Próximo**.
    
   - Na página **Confirmação**, clique em **Avançar**.
    
9. Em cada servidor no cluster, habilita o recurso AG no SQL Server Configuration Manager.
    
   - Abra o Gerente de configuração do SQL Server. Na árvore no lado esquerdo da tela, clique em serviços SQL Server **e** clique duas vezes no serviço SQL Server. 
    
   - Na caixa **Propriedades,** selecione a guia **Alta Disponibilidade AlwaysOn.** Marque a **caixa de seleção Habilitar Grupos de Disponibilidade AlwaysOn.** Reinicie o SQL Server quando solicitado.
    
10. Crie o grupo de disponibilidade.
    
    - Abra SQL Server Management Studio e conecte-se à instância SQL Server.
    
    - No Explorador de Objetos, expanda **a pasta Always On High Availability.** Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em Novo Assistente de Grupo de **Disponibilidade.**
    
    - Se a **página Introdução** for exibida, clique em **Próximo**.
    
    - Na página **Especificar Nome do Grupo de Disponibilidade,** digite o nome do grupo Disponibilidade e clique em **Próximo**.
    
    - Na página Selecionar Bancos de Dados, selecione os bancos de dados que você deseja incluir no Grupo de Disponibilidade AlwaysOn. Depois, clique em **Avançar**.
    
    Não inclua os bancos de dados **ReportServer,** **ReportServerTempDB** ou Chat Persistente no Grupo de Disponibilidade AlwaysOn, pois eles não têm suporte neste cenário. Você pode incluir todos os outros Skype for Business Server de dados no Grupo de Disponibilidade AlwaysOn.
    
    - Na página **Especificar Réplicas,** clique na **guia Réplicas.** Em seguida, clique no botão Adicionar **Réplicas** e conecte-se às outras instâncias SQL que você ingressou como nós do cluster de Failover do Windows Server.
    
    - Para cada instância, selecione as **opções Failover Automático** e **Confirmação Síncrona.** Não selecione a **opção Secundário Acessível.**
    
    - Clique na **guia Pontos de** Extremidade e verifique se o Número da **Porta** está definido como 5022.
    
      - Clique na **guia Ouvinte** e selecione a opção Criar um ouvinte de **grupo de** disponibilidade. Nessa opção, digite um nome para o ouvinte e de definir a **Porta** como 1433 (outras portas não são suportadas para essa opção).
    
    - Clique **em** Adicionar e, em seguida, na caixa **Endereço IPv4,** forneça seu endereço IP virtual preferencial e clique em **OK**.
    
    - Na página **Selecionar** Sincronização Inicial de Dados, selecione Completo e especifique uma pasta acessível às réplicas e que a conta de serviço SQL Server usada por ambas as réplicas tenha permissões de gravação. Depois, clique em **Avançar**.
    
    Esse compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você estiver lidando com bancos de dados grandes, recomendamos que você os inicialize manualmente caso sua largura de banda de rede não possa acomodar o tamanho dos backups do banco de dados.
    
    - Na página Validação, verifique se todas as verificações de validação são bem-sucedidas e clique em **Próximo**.
    
    - Na página **Resumo,** verifique todas as configurações e clique em Concluir.
    
11. Crie um novo armazenamento especificando o ouvinte AG e especificando a entidade principal do espelho antigo como o nó principal da AG.
    
    - Abra o Construtor de Topologia. Em sua topologia, **expanda Componentes** **Compartilhados,** clique com o botão direito do mouse SQL Server Store e clique em **Novo SQL Server Store**.
    
    - Na página Definir Novo SQL **Store,** selecione primeiro **a** caixa de seleção Configurações alta disponibilidade e verifique se os grupos de disponibilidade alwayson SQL aparecerão na caixa de seleção.
    
    - Na caixa **SQL Server FQDN** do Ouvinte de Disponibilidade, digite o FQDN do ouvinte criado ao criar o grupo de disponibilidade.
    
    - Na caixa **SQL Server FQDN,** digite o FQDN do nó principal da AG e clique em **OK**. Essa deve ser a principal do espelho antigo para esse armazenamento.
    
12. Associe a nova AG ao pool de Front-End.
    
    - No Construtor de Topologias, clique com o botão direito do mouse no pool para associar à AG e clique **em Editar Propriedades**.
    
    - Em **Associações**, na caixa **SQL Server Store,** selecione AG. Selecione o mesmo grupo para quaisquer outros bancos de dados no pool que você deseja mover para a AG.
    
    - Quando você tem certeza de que todos os bancos de dados necessários estão definidos para a AG, clique em **OK**.
    
13. Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique**. Em seguida, na página de confirmação, clique **em Próximo**.
    
14. Execute algumas etapas finais para garantir que os SQL de logon estão em cada uma das réplicas no Grupo de Disponibilidade AlwaysOn.
    
    - Abra o Construtor de Topologias, selecione **Baixar topologia da** implantação existente e clique em **OK**.
    
    - Expanda Skype for Business Server, expanda sua topologia e **expanda SQL Server Stores.** Clique com o botão direito do SQL da nova AG e clique em **Editar Propriedades**.
    
    - Na parte inferior da página, na caixa **SQL Server FQDN,** altere o valor para o FQDN do Ouvinte da AG.
    
    - Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique**. Em seguida, na página de confirmação, clique **em Próximo**. Em seguida, aguarde alguns minutos para que a nova topologia seja replicada.
    
    - Abra SQL Server Management Studio e navegue até a AG. Fail it over to a secondary replica.
    
    - Abra Skype for Business Server Shell de Gerenciamento e digite o seguinte cmdlet para criar SQL logon nesta réplica:
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Repita as duas etapas anteriores (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update` ) for each replica in the group.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Implantar um Grupo de Disponibilidade Always On em um pool existente que não usa espelhamento de banco de dados
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se o pool que você está atualizando para uma AG hospeda o armazenamento de Gerenciamento Central da sua organização, primeiro você deve mover o CMS para outro pool antes de atualizar esse pool. Use o Move-CsManagementServer para mover o pool. Se você não tiver outro pool em sua organização, poderá implantar um servidor de Edição Standard temporariamente e mover o CMS para esse servidor antes de atualizar seu pool para a AG. 
  
1. Configurar o recurso Clustering de Failover em todos os servidores de banco de dados que fará parte da AG. Em cada servidor, faça o seguinte
    
   - Abra o Gerenciador de Servidores e clique **em Adicionar funções e recursos.**
    
   - Clique **em Próximo** até chegar à caixa Selecionar **recursos.** Aqui, marque a caixa **de seleção Clustering de Failover.**
    
   - Na caixa **Adicionar recursos necessários para Cluster de Failover?** clique em **Adicionar Recursos**.
    
   - Clique em **Instalar**.
    
2. Valide a configuração do cluster.
    
   - No Gerenciador de Servidores, clique no menu **Ferramentas** e clique em **Gerenciador de Cluster de Failover.**
    
   - Em **Ações** no lado direito da tela, clique em **Validar Configuração**.
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Selecione os servidores a adicionar ao cluster e clique em **Executar todos os testes**.
    
   - Na caixa **Resumo,** verifique os erros que o assistente relata. Em **seguida, clique em** Concluir para concluir a validação.
    
     O assistente provavelmente relatará vários avisos, especialmente se você não estiver usando o armazenamento compartilhado. Não é necessário usar armazenamento compartilhado. No entanto, se você vir qualquer **mensagem de** erro, deverá corrigir esses problemas antes de continuar.
    
3. Crie o Windows de Failover do Servidor (WSFC).
    
   - No assistente **de Gerenciamento de Cluster de Failover,** clique com o botão direito do mouse em Gerenciamento de Cluster de **Failover** e clique **em Criar Cluster**.
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Adicione o nome do cluster e o endereço IP. Quando as configurações são validadas, clique em **Próximo**.
    
   - Na página Confirmação, clique em **Avançar**.
    
   - Depois que o cluster for criado, clique em **Concluir**.
    
4. Recomendamos que você configure as configurações de quórum de cluster para usar uma testemunha de compartilhamento de arquivos. Para fazer isso, use estas etapas:
    
   - Clique com o botão direito do mouse no nome do cluster, clique em **Mais Ações** e clique em **Configurar Quorum de Cluster Configurações**.
    
   - Na página **Selecionar Opção de Configuração de Quórum,** clique **em Selecionar a testemunha de quórum**.
    
   - Na página **Selecionar Testemunha de Quórum,** clique em **Configurar uma testemunha de compartilhamento de arquivo**.
    
   - Na página **Configurar Testemunha de Compartilhamento** de Arquivos, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Próximo**.
    
   - Na página **Confirmação**, clique em **Avançar**.
    
5. Em cada servidor no cluster, habilita a AG SQL Server Configuration Manager.
    
   - Abra o Gerente de configuração do SQL Server. Na árvore no lado esquerdo da tela, clique em serviços SQL Server **e** clique duas vezes no serviço SQL Server. 
    
   - Na caixa **Propriedades,** selecione a guia **Alta Disponibilidade AlwaysOn.** Marque a **caixa de seleção Habilitar Grupos de Disponibilidade AlwaysOn.** Reinicie o SQL Server quando solicitado.
    
6. Crie o grupo de disponibilidade.
    
   - Abra SQL Server Management Studio e conecte-se à instância SQL Server.
    
   - No Explorador de Objetos, expanda **a pasta Always On High Availability.** Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em Novo Assistente de Grupo de **Disponibilidade.**
    
   - Se a **página Introdução** for exibida, clique em **Próximo**.
    
   - Na página **Especificar Nome do Grupo de Disponibilidade,** digite o nome do grupo Disponibilidade e clique em **Próximo**.
    
   - Na página Selecionar Bancos de Dados, selecione os bancos de dados que você deseja incluir na AG. Depois, clique em **Avançar**.
    
     Não inclua os bancos de dados **ReportServer,** **ReportServerTempDB** ou Chat Persistente na AG, pois eles não são suportados neste cenário. Você pode incluir todos os outros Skype for Business Server de dados na AG.
    
   - Na página **Especificar Réplicas,** clique na **guia Réplicas.** Em seguida, clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias SQL que você ingressou como nós do WSFC.
    
   - Para cada instância, selecione as **opções Failover Automático** e **Confirmação Síncrona.** Não selecione a **opção Secundário Acessível.**
    
   - Clique na **guia Pontos de** Extremidade e verifique se o Número da **Porta** está definido como 5022.
    
   - Clique na **guia Ouvinte** e selecione a opção Criar um ouvinte de **grupo de** disponibilidade. Nessa opção, digite um nome para o ouvinte e de definir a **Porta** como 1433 (outras portas não são suportadas para essa opção).
    
   - Clique **em** Adicionar e, em seguida, na caixa **Endereço IPv4,** forneça seu endereço IP virtual preferencial e clique em **OK**.
    
   - Na página **Selecionar** Sincronização Inicial de Dados, selecione Completo e especifique uma pasta acessível às réplicas e que a conta de serviço SQL Server usada por ambas as réplicas tenha permissões de gravação. Depois, clique em **Avançar**.
    
     Esse compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você estiver lidando com bancos de dados grandes, recomendamos que você os inicialize manualmente caso sua largura de banda de rede não possa acomodar o tamanho dos backups do banco de dados.
    
     - Na página Validação, verifique se todas as verificações de validação são bem-sucedidas e clique em **Próximo**.
    
   - Na página **Resumo,** verifique todas as configurações e clique em Concluir.
    
7. Crie um novo armazenamento especificando o ouvinte AG.
    
   - Abra o Construtor de Topologia. Em sua topologia, **expanda Componentes** **Compartilhados,** clique com o botão direito do mouse SQL Server Store e clique em **Novo SQL Server Store**.
    
   - Na página Definir Novo SQL **Store,** selecione primeiro **a** caixa de seleção Configurações alta disponibilidade e verifique se os grupos de disponibilidade alwayson SQL aparecerão na caixa de seleção.
    
   - Na caixa **SQL Server FQDN** do Ouvinte de Disponibilidade, digite o FQDN do ouvinte criado ao criar o grupo de disponibilidade.
    
   - Na caixa **SQL Server FQDN,** digite o FQDN do nó principal da AG e clique em **OK**.
    
8. Associe o novo Grupo de Disponibilidade Always On ao pool de Front-End.
    
   - No Construtor de Topologias, clique com o botão direito do mouse no pool para associar à AG e clique **em Editar Propriedades**.
    
   - Em **Associações**, na caixa **SQL Server Store,** selecione AG. Selecione o mesmo grupo para quaisquer outros bancos de dados no pool que você deseja mover para a AG.
    
   - Quando você tem certeza de que todos os bancos de dados necessários estão definidos para a AG, clique em **OK**.
    
9. Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique**. Em seguida, na página de confirmação, clique **em Próximo**.
    
10. Execute algumas etapas finais para garantir que os SQL de logon estão em cada uma das réplicas na AG.
    
    - Abra o Construtor de Topologias, selecione **Baixar topologia da** implantação existente e clique em **OK**.
    
    - Expanda Skype for Business Server, expanda sua topologia e **expanda SQL Server Stores.** Clique com o botão direito do SQL da nova AG e clique em **Editar Propriedades**.
    
    - Na parte inferior da página, na caixa **SQL Server FQDN,** altere o valor para o FQDN do Ouvinte da AG.
    
    - Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique**. Em seguida, na página de confirmação, clique **em Próximo**. Em seguida, aguarde alguns minutos para que a nova topologia seja replicada.
    
    - Abra SQL Server Management Studio e navegue até a AG. Fail it over to a secondary replica.
    
    - Abra Skype for Business Server Shell de Gerenciamento e digite o seguinte cmdlet para criar SQL logon nesta réplica:
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Repita as duas etapas anteriores (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update` ) for each replica in the group.
