---
title: Implantar um grupo de disponibilidade AlwaysOn em um servidor back-end no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implantar (instalar) um grupo de disponibilidade AlwaysOn na implantação do Skype for Business Server.
ms.openlocfilehash: eadf3c67f5d2618d7070c2a3540c2a9ad08b5942
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002911"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Implantar um grupo de disponibilidade AlwaysOn em um servidor back-end no Skype for Business Server
 
Implantar (instalar) um AG (grupo de disponibilidade contínua) na implantação do Skype for Business Server.
  
A maneira como você implanta uma AG depende se você a está implantando em um novo pool, um pool existente que usa espelhamento ou um pool existente que atualmente não tem alta disponibilidade para o banco de dados back-end.
  
> [!NOTE]
> Não há suporte para o uso de uma AG com uma função de servidor de chat persistente. 
  
- [Implantar um grupo de disponibilidade AlwaysOn em um novo pool de front-end](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Implantar um grupo de disponibilidade AlwaysOn em um pool existente que usa o espelhamento de banco de dados](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Implantar um grupo de disponibilidade AlwaysOn em um pool existente que não usa o espelhamento de banco de dados](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Implantar um grupo de disponibilidade AlwaysOn em um novo pool de front-end
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Habilite o recurso de cluster de failover em todos os servidores de banco de dados que farão parte da AG. Em cada servidor, faça o seguinte:
    
   - Abra o Server Manager e clique em **Adicionar funções e recurso**.
    
   - Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.
    
   - Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.
    
   - Clique em **Instalar**.
    
2. Validar a configuração de cluster.
    
   - No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.
    
   - Em **Ações** no lado direito da tela, clique em **Validar Configuração**.
    
   - Na página **Antes de começar**, clique em **Avançar**.
    
   - Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.
    
   - Na caixa **Resumo**, verifique os erros relatados pelo assistente. Clique em **Concluir** para concluir a validação.
    
     O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.
    
3. Crie o WSFC (cluster de failover do Windows Server).
    
   - No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.
    
   - Na página **Antes de começar**, clique em **Avançar**.
    
   - Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.
    
   - Na página Confirmação, clique em **Avançar**.
    
   - Depois que o cluster for criado, clique em **Concluir**.
    
4. Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:
    
   - Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.
    
   - Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.
    
   - Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.
    
   - Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.
    
   - Na página **Confirmação**, clique em **Avançar**.
    
5. Em cada servidor do cluster, habilite o recurso AG no Gerenciador de configuração do SQL Server.
    
   - Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server.  
    
   - Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.
   
6. Use o construtor de topologias para criar o pool de front-end, conforme explicado em [criar e publicar nova topologia no Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md). Ao fazer isso, especifique AG como o repositório SQL do pool.
    
7. Criar o grupo de disponibilidade.
    
   - Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.
    
   - No explorador de objetos, expanda a pasta **sempre na alta disponibilidade** . Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.
    
   - Se a página **Introdução** for exibida, clique em **Avançar**.
    
   - Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.
    
   - Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade AlwaysOn. Then click **Next**.
    
     Não inclua os bancos de dados de chat **ReportServer**, **ReportServerTempDB**ou persistent no grupo de disponibilidade AlwaysOn, pois eles não têm suporte nesse cenário. Você pode incluir todos os outros bancos de dados do Skype for Business Server no grupo de disponibilidade AlwaysOn.
    
   - Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.
    
   - Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.
    
   - Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.
    
   - Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).
    
   - Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.
    
   - Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.
    
     Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.
    
   - Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.
    
   - Na página **Resumo**, verifique todas as configurações e clique em Concluir.
      
8. Após a implantação do pool e da AG, execute algumas etapas finais para garantir que os logons do SQL estejam em cada uma das réplicas do grupo disponibilidade AlwaysOn. 
    
   - Abra o construtor de topologias, selecione **baixar topologia de implantação existente**e clique em **OK**.
    
   - Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**. Clique com o botão direito do mouse no repositório SQL do novo grupo de disponibilidade AlwaysOn e clique em **Editar propriedades**.
    
     - Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.
    
   - Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.
    
   - Abra o SQL Server Management Studio e navegue até o AG. Faça failover para uma réplica secundária.
    
   - Abra o Shell de gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Repita as duas etapas anteriores (failover do grupo para uma réplica secundária e, em seguida `Install-CsDatabase -Update`, use) para cada réplica do grupo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Implantar um grupo de disponibilidade AlwaysOn em um pool existente que usa o espelhamento de banco de dados
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se o pool que você está atualizando para um AG hospeda o repositório central de gerenciamento para a sua organização, você deve primeiro mover o CMS para outro pool antes de atualizar este pool. Use o cmdlet Move-CsManagementServer para mover o pool. Se você não tiver outro pool em sua organização, poderá implantar um servidor Standard Edition temporariamente e mover o CMS para este servidor antes de atualizar o pool para a AG. 
  
1. Falhe em todos os dados do espelho para o nó principal abrindo o Shell de gerenciamento do Skype for Business Server e digitando o cmdlet a seguir.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Repita esse cmdlet para cada tipo de banco de dados no pool. Você pode utilizar o seguinte cmdlet para localizar todos os tipos de bancos de dados armazenados neste pool.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Use o construtor de topologias para remover o espelhamento de banco de dados do pool.
    
   - Abrir o construtor de topologias. Em sua topologia, expanda **Pools de Front-Ends Enterprise Edition**, clique com o botão direito do mouse no nome do pool e clique em **Editar Propriedades**.
    
   - Para cada tipo de repositório SQL no pool, desmarque a caixa de seleção **Habilitar Espelhamento do Repositório SQL**.
    
3. Publique a topologia alterada. No menu **Ação**, clique em **Topologia** e, em seguida, em **Publicar**. Na página de confirmação, clique em **Avançar**
    
4. Usar o SQL Server Management Studio para quebrar o espelho.
    
   - Abra o SQL Server Management Studio, navegue até seus bancos de dados, clique com o botão direito do mouse em **Tarefas** e clique em **Espelho**. Clique em **Remover Espelhamento** e clique em **OK**.
    
   - Repita esse procedimento para todos os bancos de dados no pool que serão convertidos em uma AG.
    
5. Configure o recurso de cluster de failover em todos os servidores de banco de dados que farão parte da AG. Em cada servidor, faça o seguinte:
    
   - Abra o Server Manager e clique em **Adicionar funções e recurso**.
    
   - Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.
    
   - Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.
    
   - Clique em **Instalar**.
    
6. Validar a configuração de cluster.
    
   - No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.
    
   - Em **Ações** no lado direito da tela, clique em **Validar Configuração**.
    
   - Na página **Antes de começar**, clique em **Avançar**.
    
   - Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.
    
   - Na caixa **Resumo**, verifique os erros relatados pelo assistente. Clique em **Concluir** para concluir a validação.
    
     O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.
    
7. Crie o cluster de failover do Windows Server.
    
   - No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.
    
   - Na página **Antes de começar**, clique em **Avançar**.
    
   - Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.
    
   - Na página Confirmação, clique em **Avançar**.
    
   - Depois que o cluster for criado, clique em **Concluir**.
    
8. Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:
    
   - Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.
    
   - Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.
    
   - Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.
    
   - Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.
    
   - Na página **Confirmação**, clique em **Avançar**.
    
9. Em cada servidor do cluster, habilite o recurso AG no Gerenciador de configuração do SQL Server.
    
   - Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server.  
    
   - Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.
    
10. Criar o grupo de disponibilidade.
    
    - Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.
    
    - No explorador de objetos, expanda a pasta **sempre na alta disponibilidade** . Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.
    
    - Se a página **Introdução** for exibida, clique em **Avançar**.
    
    - Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.
    
    - Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade AlwaysOn. Then click **Next**.
    
    Não inclua os bancos de dados de chat **ReportServer**, **ReportServerTempDB**ou persistent no grupo de disponibilidade AlwaysOn, pois eles não têm suporte nesse cenário. Você pode incluir todos os outros bancos de dados do Skype for Business Server no grupo de disponibilidade AlwaysOn.
    
    - Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.
    
    - Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.
    
    - Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.
    
      - Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).
    
    - Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.
    
    - Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.
    
    Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.
    
    - Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.
    
    - Na página **Resumo**, verifique todas as configurações e clique em Concluir.
    
11. Crie uma nova loja especificando o ouvinte AG e especificando a entidade de segurança do espelho antigo como o nó primário da AG.
    
    - Abrir o construtor de topologias. Em sua topologia, expanda **Componentes Compartilhados**, clique com o botão direito do mouse em **Repositórios do SQL Server** e clique em **Novo Repositório do SQL Server**.
    
    - Na página **Definir Novo Repositório SQL**, primeiro marque a caixa de seleção **Configurações de Alta Disponibilidade** e, em seguida, certifique-se de que a opção Grupos de Disponibilidade AlwaysOn do SQL aparece na caixa suspensa.
    
    - Na caixa **FQDN do Ouvinte de Disponibilidade do SQL Server**, digite o FQDN do ouvinte que criou quando criou o grupo de disponibilidade.
    
    - Na caixa **FQDN do SQL Server** , digite o FQDN do nó primário da AG e clique em **OK**. Ele deve ser a entidade de segurança do espelho antigo para esse repositório.
    
12. Associe o novo AG ao pool de front-end.
    
    - No construtor de topologias, clique com o botão direito do mouse no pool para associá-lo à AG e clique em **Editar propriedades**.
    
    - Em **associações**, na caixa da **loja do SQL Server** , selecione a AG. Selecione o mesmo grupo para qualquer outro banco de dados no pool que você deseja mover para a AG.
    
    - Quando tiver certeza de que todos os bancos de dados necessários estão definidos para a AG, clique em **OK**.
    
13. Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**.
    
14. Execute algumas etapas finais para garantir que os logons do SQL estejam em cada uma das réplicas do grupo de disponibilidade AlwaysOn.
    
    - Abra o construtor de topologias, selecione **baixar topologia de implantação existente**e clique em **OK**.
    
    - Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**. Clique com o botão direito do mouse na loja do SQL da nova AG e clique em **Editar propriedades**.
    
    - Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.
    
    - Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.
    
    - Abra o SQL Server Management Studio e navegue até o AG. Faça failover para uma réplica secundária.
    
    - Abra o Shell de gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Repita as duas etapas anteriores (failover do grupo para uma réplica secundária e, em seguida `Install-CsDatabase -Update`, use) para cada réplica do grupo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Implantar um grupo de disponibilidade AlwaysOn em um pool existente que não usa o espelhamento de banco de dados
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se o pool que você está atualizando para um AG hospeda o repositório central de gerenciamento para a sua organização, você deve primeiro mover o CMS para outro pool antes de atualizar este pool. Use o cmdlet Move-CsManagementServer para mover o pool. Se você não tiver outro pool em sua organização, poderá implantar um servidor Standard Edition temporariamente e mover o CMS para este servidor antes de atualizar o pool para a AG. 
  
1. Configure o recurso de cluster de failover em todos os servidores de banco de dados que farão parte da AG. Em cada servidor, faça o seguinte:
    
   - Abra o Server Manager e clique em **Adicionar funções e recurso**.
    
   - Clique em **Avançar** até chegar à caixa **Selecionar recursos**. Aqui, marque a caixa de seleção **Clustering de Failover**.
    
   - Na caixa **Adicionar recursos necessários para o Clustering de Failover?**, clique em **Adicionar Recursos**.
    
   - Clique em **Instalar**.
    
2. Validar a configuração de cluster.
    
   - No Server Manager, clique no menu **Ferramentas** e, em seguida, clique em **Gerenciador de Cluster de Failover**.
    
   - Em **Ações** no lado direito da tela, clique em **Validar Configuração**.
    
   - Na página **Antes de começar**, clique em **Avançar**.
    
   - Selecione os servidores a serem adicionados ao cluster e clique em **Executar todos os testes**.
    
   - Na caixa **Resumo**, verifique os erros relatados pelo assistente. Clique em **Concluir** para concluir a validação.
    
     O assistente provavelmente mostrará diversos avisos, especialmente se você não estiver usando armazenamento compartilhado. Não é necessário usar o armazenamento compartilhado. No entanto, se você vir alguma mensagem de **Erro**, deverá corrigir esses problemas antes de continuar.
    
3. Crie o WSFC (cluster de failover do Windows Server).
    
   - No assistente de **Gerenciamento de Cluster de Failover**, clique com o botão direito do mouse em **Gerenciamento de Cluster de Failover** e, em seguida, clique em **Criar Cluster**.
    
   - Na página **Antes de começar**, clique em **Avançar**.
    
   - Adicione o nome e o endereço IP do cluster. Quando as definições forem validadas, clique em **Avançar**.
    
   - Na página Confirmação, clique em **Avançar**.
    
   - Depois que o cluster for criado, clique em **Concluir**.
    
4. Recomendamos que você defina as configurações de quorum do cluster para usar uma testemunha de compartilhamento de arquivos. Para isso, siga estas instruções:
    
   - Clique com o botão direito do mouse no nome do cluster, em **Mais Ações** e, em seguida, em **Configurar Quorum do Cluster**.
    
   - Na página **Selecionar Opção de Configuração de Quorum**, clique em **Selecione a testemunha de Quorum**.
    
   - Na página **Selecione a testemunha de Quorum**, clique em **Configurar uma testemunha de compartilhamento de arquivos**.
    
   - Na página **Configurar Testemunha de Compartilhamento de Arquivo**, digite o caminho do compartilhamento de arquivos que você deseja usar e clique em **Avançar**.
    
   - Na página **Confirmação**, clique em **Avançar**.
    
5. Em cada servidor do cluster, habilite a AG no Gerenciador de configuração do SQL Server.
    
   - Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server.  
    
   - Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.
    
6. Criar o grupo de disponibilidade.
    
   - Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.
    
   - No explorador de objetos, expanda a pasta **sempre na alta disponibilidade** . Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.
    
   - Se a página **Introdução** for exibida, clique em **Avançar**.
    
   - Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.
    
   - Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir na AG. Then click **Next**.
    
     Não inclua os bancos de dados de chat **ReportServer**, **ReportServerTempDB**ou persistent na AG, pois eles não têm suporte nesse cenário. Você pode incluir todos os outros bancos de dados do Skype for Business Server na AG.
    
   - Na página **especificar réplicas** , clique na guia **réplicas** . Em seguida, clique no botão **Adicionar réplicas** e conecte-se às outras instâncias do SQL que você ingressou como nós do WSFC.
    
   - Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.
    
   - Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.
    
   - Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).
    
   - Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.
    
   - Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.
    
     Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.
    
     - Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.
    
   - Na página **Resumo**, verifique todas as configurações e clique em Concluir.
    
7. Crie uma nova loja especificando o ouvinte AG.
    
   - Abrir o construtor de topologias. Em sua topologia, expanda **Componentes Compartilhados**, clique com o botão direito do mouse em **Repositórios do SQL Server** e clique em **Novo Repositório do SQL Server**.
    
   - Na página **Definir Novo Repositório SQL**, primeiro marque a caixa de seleção **Configurações de Alta Disponibilidade** e, em seguida, certifique-se de que a opção Grupos de Disponibilidade AlwaysOn do SQL aparece na caixa suspensa.
    
   - Na caixa **FQDN do Ouvinte de Disponibilidade do SQL Server**, digite o FQDN do ouvinte que criou quando criou o grupo de disponibilidade.
    
   - Na caixa **FQDN do SQL Server** , digite o FQDN do nó primário da AG e clique em **OK**.
    
8. Associe o novo grupo de disponibilidade AlwaysOn ao pool de front-ends.
    
   - No construtor de topologias, clique com o botão direito do mouse no pool para associá-lo à AG e clique em **Editar propriedades**.
    
   - Em **associações**, na caixa da **loja do SQL Server** , selecione a AG. Selecione o mesmo grupo para qualquer outro banco de dados no pool que você deseja mover para a AG.
    
   - Quando tiver certeza de que todos os bancos de dados necessários estão definidos para a AG, clique em **OK**.
    
9. Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**.
    
10. Execute algumas etapas finais para garantir que os logons do SQL estejam em cada uma das réplicas da AG.
    
    - Abra o construtor de topologias, selecione **baixar topologia de implantação existente**e clique em **OK**.
    
    - Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**. Clique com o botão direito do mouse na loja do SQL da nova AG e clique em **Editar propriedades**.
    
    - Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.
    
    - Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.
    
    - Abra o SQL Server Management Studio e navegue até o AG. Faça failover para uma réplica secundária.
    
    - Abra o Shell de gerenciamento do Skype for Business Server e digite o seguinte cmdlet para criar os logons do SQL nesta réplica:
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Repita as duas etapas anteriores (failover do grupo para uma réplica secundária e, em seguida `Install-CsDatabase -Update`, use) para cada réplica do grupo.
