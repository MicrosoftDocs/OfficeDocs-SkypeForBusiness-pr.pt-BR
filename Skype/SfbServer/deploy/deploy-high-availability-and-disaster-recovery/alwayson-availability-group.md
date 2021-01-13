---
title: Implantar um grupo de disponibilidade Always On em um servidor back-end no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implante (instale) um Grupo de Disponibilidade Always On em sua implantação do Skype for Business Server.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830651"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Implantar um grupo de disponibilidade Always On em um servidor back-end no Skype for Business Server
 
Implante (instale) um Grupo de Disponibilidade Always On (AG) em sua implantação do Skype for Business Server.
  
A maneira como você implanta um AG depende se você o está implantando em um novo pool, em um pool existente que usa espelhamento ou em um pool existente que atualmente não tem alta disponibilidade para o banco de dados back-end.
  
> [!NOTE]
> O uso de uma AG com uma função de Servidor de Chat Persistente não é suportado. 
  
- [Implantar um Grupo de Disponibilidade Always On em um novo pool de Front-End](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Implantar um Grupo de Disponibilidade Always On em um pool existente que usa espelhamento de banco de dados](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Implantar um Grupo de Disponibilidade Always On em um pool existente que não usa espelhamento de banco de dados](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Implantar um Grupo de Disponibilidade Always On em um novo pool de Front-End
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Habilita o recurso de Clustering de Failover em todos os servidores de banco de dados que fazem parte do AG. Em cada servidor, faça o seguinte
    
   - Abra o Gerenciador do Servidor e clique **em Adicionar funções e recursos.**
    
   - Clique **em Próximo** até chegar à caixa Selecionar **recursos.** Aqui, marque a caixa **de seleção Clustering de Failover.**
    
   - Na caixa **Adicionar recursos necessários para Clustering de Failover,** clique em **Adicionar Recursos.**
    
   - Clique em **Instalar**.
    
2. Valide a configuração do cluster.
    
   - No Gerenciador do Servidor, clique no menu **Ferramentas** e clique em **Gerenciador de Cluster de Failover.**
    
   - Em **Ações** no lado direito da tela, clique em **Validar Configuração.**
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Selecione os servidores para adicionar ao cluster e clique em **Executar todos os testes.**
    
   - Na caixa **Resumo,** verifique os erros que o assistente relata. Em **seguida, clique em** Concluir para concluir a validação.
    
     O assistente provavelmente relatará vários avisos, especialmente se você não estiver usando o armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma **mensagem de** erro, deverá corrigir esses problemas antes de continuar.
    
3. Crie o Cluster de Failover do Windows Server (WSFC).
    
   - No assistente **de Gerenciamento de Cluster de Failover,** clique com o botão direito do mouse em Gerenciamento de Cluster de **Failover** e clique **em Criar Cluster.**
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Adicione o nome do cluster e o endereço IP. Quando as configurações são validadas, clique em **Próximo**.
    
   - Na página Confirmação, clique em **Avançar**.
    
   - Depois que o cluster for criado, clique em **Concluir.**
    
4. Recomendamos que você configure as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para fazer isso, use estas etapas:
    
   - Clique com o botão direito do mouse no nome do cluster, clique em **Mais** Ações e clique em **Definir Configurações de Quorum do Cluster.**
    
   - Na página **Selecionar Opção de Configuração de Quorum,** clique **em Selecionar a testemunha de quórum.**
    
   - Na página **Selecionar Testemunha de Quorum,** clique em **Configurar uma testemunha de compartilhamento de arquivos.**
    
   - Na página **Configurar Testemunha de Compartilhamento de** Arquivos, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Próximo.**
    
   - Na página **Confirmação**, clique em **Avançar**.
    
5. Em cada servidor no cluster, habilita o recurso AG no SQL Server Configuration Manager.
    
   - Abra o Gerente de configuração do SQL Server. Na árvore no lado esquerdo da tela, clique em **SQL Server Services** e, em seguida, clique duas vezes no serviço do SQL Server. 
    
   - Na caixa **Propriedades,** selecione a **guia Alta Disponibilidade AlwaysOn.** Marque a caixa **de seleção Habilitar Grupos de Disponibilidade AlwaysOn.** Reinicie o serviço do SQL Server quando solicitado.
   
6. Use o Construtor de Topologias para criar o pool de Front-End, conforme explicado em Criar e publicar nova [topologia no Skype for Business Server.](../../deploy/install/create-and-publish-new-topology.md) Ao fazer isso, especifique o AG como o armazenamento SQL para o pool.
    
7. Crie o grupo de disponibilidade.
    
   - Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.
    
   - No Explorador de Objetos, expanda **a pasta Alta Disponibilidade Always On.** Clique com o botão direito do mouse na pasta **Grupos de** Disponibilidade e clique em Assistente para Novo Grupo **de Disponibilidade.**
    
   - Se a **página introdução** aparecer, clique em **Próximo**.
    
   - Na página **Especificar Nome do Grupo de Disponibilidade,** digite o nome do grupo de Disponibilidade e clique em **Próximo.**
    
   - Na página Selecionar Bancos de Dados, selecione os bancos de dados que você deseja incluir no Grupo de Disponibilidade AlwaysOn. Em seguida, clique em **Avançar**.
    
     Não inclua os bancos de dados **ReportServer**, **ReportServerTempDB** ou Chat Persistente no Grupo de Disponibilidade AlwaysOn, pois eles não são suportados neste cenário. Você pode incluir todos os outros bancos de dados do Skype for Business Server no Grupo de Disponibilidade AlwaysOn.
    
   - Na página **Especificar Réplicas,** clique na **guia Réplicas.** Em **seguida, clique** no botão Adicionar Réplicas e conecte-se às outras instâncias SQL que você adicionou como nós do Cluster de Failover do Windows Server.
    
   - Para cada instância, selecione as **opções de Failover Automático** e Confirmação **Síncrona.** Não selecione a **opção Secundária Aceitável.**
    
   - Clique na **guia Pontos de Extremidade e** verifique se o Número **da** Porta está definido como 5022.
    
   - Clique na **guia Ouvinte** e selecione a opção Criar um ouvinte do **grupo de** disponibilidade. Nessa opção, digite um nome para o  ouvinte e de definir a porta como 1433 (outras portas não são suportadas para essa opção).
    
   - Clique **em** Adicionar e, em seguida, na caixa **endereço IPv4,** forneça seu endereço IP virtual preferencial e clique em **OK.**
    
   - Na  página Selecionar Sincronização de Dados Inicial, selecione Completo, especifique uma pasta acessível para as réplicas e para a qual a conta de serviço do SQL Server usada por ambas as réplicas tenha permissões de Gravação. Em seguida, clique em **Avançar**.
    
     Esse compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você estiver lidando com bancos de dados grandes, recomendamos que você os inicialize manualmente caso sua largura de banda de rede não possa acomodar o tamanho dos backups de banco de dados.
    
   - Na página Validação, verifique se todas as verificações de validação foram bem-sucedidas e clique em **Próximo.**
    
   - Na página **Resumo,** verifique todas as configurações e clique em Concluir.
      
8. Depois que o pool e o AG são implantados, execute algumas etapas finais para garantir que os logons do SQL estão em cada uma das réplicas no Grupo de Disponibilidade AlwaysOn. 
    
   - Abra o Construtor de Topologias, **selecione Baixar topologia da implantação existente** e clique em **OK.**
    
   - Expanda o Skype for Business Server, expanda sua topologia e expanda os **Armazenamentos do SQL Server.** Clique com o botão direito do mouse no armazenamento SQL do novo Grupo de Disponibilidade AlwaysOn e clique em **Editar Propriedades.**
    
     - Na parte inferior da página, na caixa **FQDN** do SQL Server, altere o valor para o FQDN do Ouvinte do AG.
    
   - Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique.** Em seguida, na página de confirmação, clique em **Próximo**. Aguarde alguns minutos para que a nova topologia seja replicada.
    
   - Abra o SQL Server Management Studio e navegue até AG. Fail it over to a secondary replica.
    
   - Abra o Shell de Gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Repita as duas etapas anteriores (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update` ) for each replica in the group.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Implantar um Grupo de Disponibilidade Always On em um pool existente que usa espelhamento de banco de dados
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se o pool que você está atualizando para um AG hospeda o armazenamento de Gerenciamento Central da sua organização, primeiro você deve mover o CMS para outro pool antes de atualizar esse pool. Use o Move-CsManagementServer cmdlet para mover o pool. Se você não tiver outro pool em sua organização, poderá implantar um servidor Standard Edition temporariamente e mover o CMS para este servidor antes de atualizar seu pool para o AG. 
  
1. Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Repita esse cmdlet para cada tipo de banco de dados no pool. Você pode usar o cmdlet a seguir para encontrar todos os tipos de banco de dados armazenados neste pool.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Use o Construtor de Topologias para remover o espelhamento de banco de dados do pool.
    
   - Abra o Construtor de Topologia. Em sua topologia, **expanda pools de front-end** do Enterprise Edition , clique com o botão direito do mouse no nome do pool e clique em **Editar Propriedades**.
    
   - Para cada tipo de armazenamento SQL no pool, des clear the **Enable SQL Store Mirroring** check box.
    
3. Publique a topologia alterada. No menu **Ação,** clique **em Topologia** e **publique.** Em seguida, na página de confirmação, clique em **Próximo**
    
4. Use o SQL Server Management Studio para quebrar o espelho.
    
   - Abra o SQL Server Management Studio, navegue até seus bancos de dados, clique com o botão direito do mouse **em Tarefas** e clique em **Espelho.** Em **seguida, clique em Remover Espelhamento** e clique em **OK.**
    
   - Repita isso para todos os bancos de dados no pool que serão convertidos em um AG.
    
5. Configurar o recurso de Clustering de Failover em todos os servidores de banco de dados que serão parte do AG. Em cada servidor, faça o seguinte
    
   - Abra o Gerenciador do Servidor e clique **em Adicionar funções e recursos.**
    
   - Clique **em Próximo** até chegar à caixa Selecionar **recursos.** Aqui, marque a caixa **de seleção Clustering de Failover.**
    
   - Na caixa **Adicionar recursos necessários para Clustering de Failover,** clique em **Adicionar Recursos.**
    
   - Clique em **Instalar**.
    
6. Valide a configuração do cluster.
    
   - No Gerenciador do Servidor, clique no menu **Ferramentas** e clique em **Gerenciador de Cluster de Failover.**
    
   - Em **Ações** no lado direito da tela, clique em **Validar Configuração.**
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Selecione os servidores para adicionar ao cluster e clique em **Executar todos os testes.**
    
   - Na caixa **Resumo,** verifique os erros que o assistente relata. Em **seguida, clique em** Concluir para concluir a validação.
    
     O assistente provavelmente relatará vários avisos, especialmente se você não estiver usando o armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma **mensagem de** erro, deverá corrigir esses problemas antes de continuar.
    
7. Crie o Cluster de Failover do Windows Server.
    
   - No assistente **de Gerenciamento de Cluster de Failover,** clique com o botão direito do mouse em Gerenciamento de Cluster de **Failover** e clique **em Criar Cluster.**
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Adicione o nome do cluster e o endereço IP. Quando as configurações são validadas, clique em **Próximo**.
    
   - Na página Confirmação, clique em **Avançar**.
    
   - Depois que o cluster for criado, clique em **Concluir.**
    
8. Recomendamos que você configure as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para fazer isso, use estas etapas:
    
   - Clique com o botão direito do mouse no nome do cluster, clique em **Mais** Ações e clique em **Definir Configurações de Quorum do Cluster.**
    
   - Na página **Selecionar Opção de Configuração de Quorum,** clique **em Selecionar a testemunha de quórum.**
    
   - Na página **Selecionar Testemunha de Quorum,** clique em **Configurar uma testemunha de compartilhamento de arquivos.**
    
   - Na página **Configurar Testemunha de Compartilhamento de** Arquivos, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Próximo.**
    
   - Na página **Confirmação**, clique em **Avançar**.
    
9. Em cada servidor no cluster, habilita o recurso AG no SQL Server Configuration Manager.
    
   - Abra o Gerente de configuração do SQL Server. Na árvore no lado esquerdo da tela, clique em **SQL Server Services** e, em seguida, clique duas vezes no serviço do SQL Server. 
    
   - Na caixa **Propriedades,** selecione a **guia Alta Disponibilidade AlwaysOn.** Marque a caixa **de seleção Habilitar Grupos de Disponibilidade AlwaysOn.** Reinicie o serviço do SQL Server quando solicitado.
    
10. Crie o grupo de disponibilidade.
    
    - Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.
    
    - No Explorador de Objetos, expanda **a pasta Alta Disponibilidade Always On.** Clique com o botão direito do mouse na pasta **Grupos de** Disponibilidade e clique em Assistente para Novo Grupo **de Disponibilidade.**
    
    - Se a **página introdução** aparecer, clique em **Próximo**.
    
    - Na página **Especificar Nome do Grupo de Disponibilidade,** digite o nome do grupo de Disponibilidade e clique em **Próximo.**
    
    - Na página Selecionar Bancos de Dados, selecione os bancos de dados que você deseja incluir no Grupo de Disponibilidade AlwaysOn. Em seguida, clique em **Avançar**.
    
    Não inclua os bancos de dados **ReportServer**, **ReportServerTempDB** ou Chat Persistente no Grupo de Disponibilidade AlwaysOn, pois eles não são suportados neste cenário. Você pode incluir todos os outros bancos de dados do Skype for Business Server no Grupo de Disponibilidade AlwaysOn.
    
    - Na página **Especificar Réplicas,** clique na **guia Réplicas.** Em **seguida, clique** no botão Adicionar Réplicas e conecte-se às outras instâncias SQL que você adicionou como nós do Cluster de Failover do Windows Server.
    
    - Para cada instância, selecione as **opções de Failover Automático** e Confirmação **Síncrona.** Não selecione a **opção Secundária Aceitável.**
    
    - Clique na **guia Pontos de Extremidade e** verifique se o Número **da** Porta está definido como 5022.
    
      - Clique na **guia Ouvinte** e selecione a opção Criar um ouvinte do **grupo de** disponibilidade. Nessa opção, digite um nome para o  ouvinte e de definir a porta como 1433 (outras portas não são suportadas para essa opção).
    
    - Clique **em** Adicionar e, em seguida, na caixa **endereço IPv4,** forneça seu endereço IP virtual preferencial e clique em **OK.**
    
    - Na  página Selecionar Sincronização de Dados Inicial, selecione Completo, especifique uma pasta acessível para as réplicas e para a qual a conta de serviço do SQL Server usada por ambas as réplicas tenha permissões de Gravação. Em seguida, clique em **Avançar**.
    
    Esse compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você estiver lidando com bancos de dados grandes, recomendamos que você os inicialize manualmente caso sua largura de banda de rede não possa acomodar o tamanho dos backups de banco de dados.
    
    - Na página Validação, verifique se todas as verificações de validação foram bem-sucedidas e clique em **Próximo.**
    
    - Na página **Resumo,** verifique todas as configurações e clique em Concluir.
    
11. Crie um novo armazenamento especificando o ouvinte AG e especificando a entidade de entidade do espelho antigo como o nó principal do AG.
    
    - Abra o Construtor de Topologia. Em sua topologia, **expanda Os Componentes** **Compartilhados,** clique com o botão direito do mouse em Sql Server Store e clique em **Novo Armazenamento do SQL Server.**
    
    - Na página **Definir Novo Armazenamento SQL,** marque primeiro a caixa de seleção Configurações de Alta Disponibilidade e, em seguida, verifique se os Grupos de Disponibilidade AlwaysOn do SQL aparecem na caixa de lista. 
    
    - Na caixa **FQDN** do Ouvinte de Disponibilidade do SQL Server, digite o FQDN do ouvinte que você criou ao criar o grupo de disponibilidade.
    
    - Na caixa **FQDN** do SQL Server, digite o FQDN do nó principal do AG e clique em **OK.** Esse deve ser o principal do espelho antigo para esse armazenamento.
    
12. Associe o novo AG ao pool de Front-End.
    
    - No Construtor de Topologias, clique com o botão direito do mouse no pool a ser associado ao AG e clique em **Editar Propriedades.**
    
    - Em **Associações,** na **caixa Sql Server Store,** selecione AG. Selecione o mesmo grupo para quaisquer outros bancos de dados no pool que você deseja mover para o AG.
    
    - Quando você tem certeza de que todos os bancos de dados necessários estão definidos para o AG, clique em **OK.**
    
13. Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique.** Em seguida, na página de confirmação, clique em **Próximo**.
    
14. Execute algumas etapas finais para garantir que os logons do SQL estão em cada uma das réplicas no Grupo de Disponibilidade AlwaysOn.
    
    - Abra o Construtor de Topologias, **selecione Baixar topologia da implantação existente** e clique em **OK.**
    
    - Expanda o Skype for Business Server, expanda sua topologia e expanda os **Armazenamentos do SQL Server.** Clique com o botão direito do mouse no armazenamento SQL do novo AG e clique em **Editar Propriedades.**
    
    - Na parte inferior da página, na caixa **FQDN** do SQL Server, altere o valor para o FQDN do Ouvinte do AG.
    
    - Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique.** Em seguida, na página de confirmação, clique em **Próximo**. Aguarde alguns minutos para que a nova topologia seja replicada.
    
    - Abra o SQL Server Management Studio e navegue até AG. Fail it over to a secondary replica.
    
    - Abra o Shell de Gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Repita as duas etapas anteriores (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update` ) for each replica in the group.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Implantar um Grupo de Disponibilidade Always On em um pool existente que não usa espelhamento de banco de dados
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se o pool que você está atualizando para um AG hospeda o armazenamento de Gerenciamento Central da sua organização, primeiro você deve mover o CMS para outro pool antes de atualizar esse pool. Use o Move-CsManagementServer cmdlet para mover o pool. Se você não tiver outro pool em sua organização, poderá implantar um servidor Standard Edition temporariamente e mover o CMS para este servidor antes de atualizar seu pool para o AG. 
  
1. Configurar o recurso de Clustering de Failover em todos os servidores de banco de dados que serão parte do AG. Em cada servidor, faça o seguinte
    
   - Abra o Gerenciador do Servidor e clique **em Adicionar funções e recursos.**
    
   - Clique **em Próximo** até chegar à caixa Selecionar **recursos.** Aqui, marque a caixa **de seleção Clustering de Failover.**
    
   - Na caixa **Adicionar recursos necessários para Clustering de Failover,** clique em **Adicionar Recursos.**
    
   - Clique em **Instalar**.
    
2. Valide a configuração do cluster.
    
   - No Gerenciador do Servidor, clique no menu **Ferramentas** e clique em **Gerenciador de Cluster de Failover.**
    
   - Em **Ações** no lado direito da tela, clique em **Validar Configuração.**
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Selecione os servidores para adicionar ao cluster e clique em **Executar todos os testes.**
    
   - Na caixa **Resumo,** verifique os erros que o assistente relata. Em **seguida, clique em** Concluir para concluir a validação.
    
     O assistente provavelmente relatará vários avisos, especialmente se você não estiver usando o armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma **mensagem de** erro, deverá corrigir esses problemas antes de continuar.
    
3. Crie o Cluster de Failover do Windows Server (WSFC).
    
   - No assistente **de Gerenciamento de Cluster de Failover,** clique com o botão direito do mouse em Gerenciamento de Cluster de **Failover** e clique **em Criar Cluster.**
    
   - Na página **Antes de começar**, clique em **Seguinte**.
    
   - Adicione o nome do cluster e o endereço IP. Quando as configurações são validadas, clique em **Próximo**.
    
   - Na página Confirmação, clique em **Avançar**.
    
   - Depois que o cluster for criado, clique em **Concluir.**
    
4. Recomendamos que você configure as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para fazer isso, use estas etapas:
    
   - Clique com o botão direito do mouse no nome do cluster, clique em **Mais** Ações e clique em **Definir Configurações de Quorum do Cluster.**
    
   - Na página **Selecionar Opção de Configuração de Quorum,** clique **em Selecionar a testemunha de quórum.**
    
   - Na página **Selecionar Testemunha de Quorum,** clique em **Configurar uma testemunha de compartilhamento de arquivos.**
    
   - Na página **Configurar Testemunha de Compartilhamento de** Arquivos, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Próximo.**
    
   - Na página **Confirmação**, clique em **Avançar**.
    
5. Em cada servidor do cluster, habilita o AG no SQL Server Configuration Manager.
    
   - Abra o Gerente de configuração do SQL Server. Na árvore no lado esquerdo da tela, clique em **SQL Server Services** e, em seguida, clique duas vezes no serviço do SQL Server. 
    
   - Na caixa **Propriedades,** selecione a **guia Alta Disponibilidade AlwaysOn.** Marque a caixa **de seleção Habilitar Grupos de Disponibilidade AlwaysOn.** Reinicie o serviço do SQL Server quando solicitado.
    
6. Crie o grupo de disponibilidade.
    
   - Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.
    
   - No Explorador de Objetos, expanda **a pasta Alta Disponibilidade Always On.** Clique com o botão direito do mouse na pasta **Grupos de** Disponibilidade e clique em Assistente para Novo Grupo **de Disponibilidade.**
    
   - Se a **página introdução** aparecer, clique em **Próximo**.
    
   - Na página **Especificar Nome do Grupo de Disponibilidade,** digite o nome do grupo de Disponibilidade e clique em **Próximo.**
    
   - Na página Selecionar Bancos de Dados, selecione os bancos de dados que você deseja incluir no AG. Em seguida, clique em **Avançar**.
    
     Não inclua os bancos de dados **ReportServer**, **ReportServerTempDB** ou Chat Persistente no AG, pois eles não são suportados neste cenário. Você pode incluir todos os outros bancos de dados do Skype for Business Server no AG.
    
   - Na página **Especificar Réplicas,** clique na **guia Réplicas.** Em **seguida, clique** no botão Adicionar Réplicas e conecte-se às outras instâncias SQL que você adicionou como nós do WSFC.
    
   - Para cada instância, selecione as **opções de Failover Automático** e Confirmação **Síncrona.** Não selecione a **opção Secundária Aceitável.**
    
   - Clique na **guia Pontos de Extremidade e** verifique se o Número **da** Porta está definido como 5022.
    
   - Clique na **guia Ouvinte** e selecione a opção Criar um ouvinte do **grupo de** disponibilidade. Nessa opção, digite um nome para o  ouvinte e de definir a porta como 1433 (outras portas não são suportadas para essa opção).
    
   - Clique **em** Adicionar e, em seguida, na caixa **endereço IPv4,** forneça seu endereço IP virtual preferencial e clique em **OK.**
    
   - Na  página Selecionar Sincronização de Dados Inicial, selecione Completo, especifique uma pasta acessível para as réplicas e para a qual a conta de serviço do SQL Server usada por ambas as réplicas tenha permissões de Gravação. Em seguida, clique em **Avançar**.
    
     Esse compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você estiver lidando com bancos de dados grandes, recomendamos que você os inicialize manualmente caso sua largura de banda de rede não possa acomodar o tamanho dos backups de banco de dados.
    
     - Na página Validação, verifique se todas as verificações de validação foram bem-sucedidas e clique em **Próximo.**
    
   - Na página **Resumo,** verifique todas as configurações e clique em Concluir.
    
7. Crie um novo armazenamento especificando o ouvinte AG.
    
   - Abra o Construtor de Topologia. Em sua topologia, **expanda Os Componentes** **Compartilhados,** clique com o botão direito do mouse em Sql Server Store e clique em **Novo Armazenamento do SQL Server.**
    
   - Na página **Definir Novo Armazenamento SQL,** marque primeiro a caixa de seleção Configurações de Alta Disponibilidade e, em seguida, verifique se os Grupos de Disponibilidade AlwaysOn do SQL aparecem na caixa de lista. 
    
   - Na caixa **FQDN** do Ouvinte de Disponibilidade do SQL Server, digite o FQDN do ouvinte que você criou ao criar o grupo de disponibilidade.
    
   - Na caixa **FQDN** do SQL Server, digite o FQDN do nó principal do AG e clique em **OK.**
    
8. Associe o novo Grupo de Disponibilidade Always On ao pool de Front-End.
    
   - No Construtor de Topologias, clique com o botão direito do mouse no pool a ser associado ao AG e clique em **Editar Propriedades.**
    
   - Em **Associações,** na **caixa Sql Server Store,** selecione AG. Selecione o mesmo grupo para quaisquer outros bancos de dados no pool que você deseja mover para o AG.
    
   - Quando você tem certeza de que todos os bancos de dados necessários estão definidos para o AG, clique em **OK.**
    
9. Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique.** Em seguida, na página de confirmação, clique em **Próximo**.
    
10. Execute algumas etapas finais para garantir que os logons do SQL estão em cada uma das réplicas no AG.
    
    - Abra o Construtor de Topologias, **selecione Baixar topologia da implantação existente** e clique em **OK.**
    
    - Expanda o Skype for Business Server, expanda sua topologia e expanda os **Armazenamentos do SQL Server.** Clique com o botão direito do mouse no armazenamento SQL do novo AG e clique em **Editar Propriedades.**
    
    - Na parte inferior da página, na caixa **FQDN** do SQL Server, altere o valor para o FQDN do Ouvinte do AG.
    
    - Publique a topologia. No menu **Ação,** clique **em Topologia** e **publique.** Em seguida, na página de confirmação, clique em **Próximo**. Aguarde alguns minutos para que a nova topologia seja replicada.
    
    - Abra o SQL Server Management Studio e navegue até AG. Fail it over to a secondary replica.
    
    - Abra o Shell de Gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Repita as duas etapas anteriores (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update` ) for each replica in the group.
