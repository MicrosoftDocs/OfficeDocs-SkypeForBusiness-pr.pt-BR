---
title: Implantar um grupo de disponibilidade sempre ativada em um servidor de Back-End no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Implante um sempre no grupo de disponibilidade na sua Skype (instalação) para o Business Server deployment.
ms.openlocfilehash: fcdae233e81f7c2dde3f1bdb4a79f06c95f640d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225529"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Implantar um grupo de disponibilidade sempre ativada em um servidor de Back-End no Skype para Business Server
 
Implante um sempre na disponibilidade grupo (AG) no seu Skype (instalação) para o Business Server deployment.
  
Como você implanta uma AG depende se você estiver implantando em um novo pool, um pool existente que usa espelhamento ou um pool existente que tem atualmente sem alta disponibilidade para o banco de dados de Back-End.
  
> [!NOTE]
> Usar uma AG com uma função de servidor de Chat persistente não é suportado. 
  
- [Implantar um sempre no grupo de disponibilidade em um novo pool de Front-End](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Implantar um sempre no grupo de disponibilidade em um pool existente que usa o espelhamento de banco de dados](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Implantar um sempre no grupo de disponibilidade em um pool existente que não usa o espelhamento de banco de dados](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Implantar um sempre no grupo de disponibilidade em um novo pool de Front-End
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Habilite o recurso de cluster de Failover em todos os servidores de banco de dados que farão parte da AG. Em cada servidor, faça o seguinte:
    
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
    
3. Crie o Cluster de Failover do Windows Server (WSFC).
    
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
    
5. Em cada servidor do cluster, habilite o recurso de AG no SQL Server Configuration Manager.
    
   - Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server.  
    
   - Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.
   
6. Use o construtor de topologias para criar o pool de Front-End, conforme explicado em [criar e publicar a nova topologia no Skype para Business Server](../../deploy/install/create-and-publish-new-topology.md). Quando você fizer isso, especifique a AG como o repositório SQL para o pool.
    
7. Criar o grupo de disponibilidade.
    
   - Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.
    
   - No Object Explorer, expanda a pasta de **Sempre na alta disponibilidade** . Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.
    
   - Se a página **Introdução** for exibida, clique em **Avançar**.
    
   - Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.
    
   - Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade do AlwaysOn. Then click **Next**.
    
     Não inclua o **ReportServer**, **ReportServerTempDB**ou bancos de dados de Chat persistente no grupo de disponibilidade do AlwaysOn, como eles não são suportados neste cenário. Você pode incluir todos os outro Skype para bancos de dados do servidor de negócios no grupo de disponibilidade do AlwaysOn.
    
   - Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.
    
   - Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.
    
   - Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.
    
   - Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).
    
   - Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.
    
   - Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.
    
     Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.
    
   - Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.
    
   - Na página **Resumo**, verifique todas as configurações e clique em Concluir.
      
8. Após o pool e o AG são implantados, realize algumas etapas finais para certificar-se de que os logons do SQL estão em cada uma das réplicas no grupo de disponibilidade do AlwaysOn. 
    
   - Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.
    
   - Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**. Clique com o botão o repositório SQL do novo grupo de disponibilidade do AlwaysOn e clique em **Editar propriedades**.
    
     - Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.
    
   - Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.
    
   - Abra o SQL Server Management Studio e navegue até a AG. Faça failover para uma réplica secundária.
    
   - Abra o Skype do Shell de gerenciamento do servidor de negócios e digite o seguinte cmdlet para criar logons do SQL nesta réplica:
    
   ```
   Install-CsDatabase -Update
   ```

   - Repita as duas etapas anteriores (failover no grupo para uma réplica secundária e, em seguida, usar `Install-CsDatabase -Update`) para cada réplica no grupo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Implantar um sempre no grupo de disponibilidade em um pool existente que usa o espelhamento de banco de dados
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se o pool que você estiver atualizando para uma AG hospedar o repositório de gerenciamento Central para sua organização, você deve primeiro mover o CMS para outro pool antes de atualizar este pool. Use o cmdlet Move-CsManagementServer para mover o pool. Se você não tiver outro pool em sua organização, você pode implantar um servidor Standard Edition temporariamente e mover o CMS para esse servidor antes de atualizar seu pool para a AG. 
  
1. Failover de todos os dados do espelho para o nó principal abrindo Skype do Shell de gerenciamento do servidor de negócios e digitando o seguinte cmdlet.
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Repita esse cmdlet para cada tipo de banco de dados no pool. Você pode utilizar o seguinte cmdlet para localizar todos os tipos de bancos de dados armazenados neste pool.
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Use o construtor de topologias para remover o espelhamento de banco de dados do pool.
    
   - Abra o construtor de topologia. Em sua topologia, expanda **Pools de Front-Ends Enterprise Edition**, clique com o botão direito do mouse no nome do pool e clique em **Editar Propriedades**.
    
   - Para cada tipo de repositório SQL no pool, desmarque a caixa de seleção **Habilitar Espelhamento do Repositório SQL**.
    
3. Publique a topologia alterada. No menu **Ação**, clique em **Topologia** e, em seguida, em **Publicar**. Na página de confirmação, clique em **Avançar**
    
4. Usar o SQL Server Management Studio para quebrar o espelho.
    
   - Abra o SQL Server Management Studio, navegue até seus bancos de dados, clique com o botão direito do mouse em **Tarefas** e clique em **Espelho**. Clique em **Remover Espelhamento** e clique em **OK**.
    
   - Repita esse procedimento para todos os bancos de dados do pool que será convertida em uma AG.
    
5. Configure o recurso de cluster de Failover em todos os servidores de banco de dados que farão parte da AG. Em cada servidor, faça o seguinte:
    
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
    
7. Crie o Cluster de Failover do Windows Server.
    
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
    
9. Em cada servidor do cluster, habilite o recurso de AG no SQL Server Configuration Manager.
    
   - Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server.  
    
   - Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.
    
10. Criar o grupo de disponibilidade.
    
    - Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.
    
    - No Object Explorer, expanda a pasta de **Sempre na alta disponibilidade** . Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.
    
    - Se a página **Introdução** for exibida, clique em **Avançar**.
    
    - Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.
    
    - Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir no grupo de disponibilidade do AlwaysOn. Then click **Next**.
    
    Não inclua o **ReportServer**, **ReportServerTempDB**ou bancos de dados de Chat persistente no grupo de disponibilidade do AlwaysOn, como eles não são suportados neste cenário. Você pode incluir todos os outro Skype para bancos de dados do servidor de negócios no grupo de disponibilidade do AlwaysOn.
    
    - Na página **Especificar Réplicas**, clique na guia **Réplicas**. Clique no botão **Adicionar Réplicas** e conecte-se às outras instâncias do SQL que você incluiu como nós do Clustering de Failover do Windows Server.
    
    - Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.
    
    - Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.
    
      - Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).
    
    - Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.
    
    - Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.
    
    Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.
    
    - Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.
    
    - Na página **Resumo**, verifique todas as configurações e clique em Concluir.
    
11. Crie um novo repositório especificando o ouvinte AG e especificando a entidade de segurança do espelho antigo como o nó principal da AG.
    
    - Abra o construtor de topologia. Em sua topologia, expanda **Componentes Compartilhados**, clique com o botão direito do mouse em **Repositórios do SQL Server** e clique em **Novo Repositório do SQL Server**.
    
    - Na página **Definir Novo Repositório SQL**, primeiro marque a caixa de seleção **Configurações de Alta Disponibilidade** e, em seguida, certifique-se de que a opção Grupos de Disponibilidade AlwaysOn do SQL aparece na caixa suspensa.
    
    - Na caixa **FQDN do Ouvinte de Disponibilidade do SQL Server**, digite o FQDN do ouvinte que criou quando criou o grupo de disponibilidade.
    
    - Na caixa **FQDN do SQL Server** , digite o FQDN do nó principal do AG e clique em **Okey**. Ele deve ser a entidade de segurança do espelho antigo para esse repositório.
    
12. Associe a nova AG com o pool de Front-End.
    
    - No construtor de topologia, clique com botão direito do pool para associar a AG e clique em **Editar propriedades**.
    
    - Em **associações**, na caixa **Repositório do SQL Server** , selecione a AG. Selecione o grupo mesmo para outros bancos de dados no qual você deseja mover para a AG pool.
    
    - Quando tiver certeza de que todos os bancos de dados necessários são definidos como a AG, clique em **Okey**.
    
13. Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**.
    
14. Execute algumas etapas finais para certificar-se de que os logons do SQL estão em cada uma das réplicas no grupo de disponibilidade do AlwaysOn.
    
    - Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.
    
    - Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**. Com o botão direito o repositório SQL da AG novo e clique em **Editar propriedades**.
    
    - Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.
    
    - Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.
    
    - Abra o SQL Server Management Studio e navegue até a AG. Faça failover para uma réplica secundária.
    
    - Abra o Skype do Shell de gerenciamento do servidor de negócios e digite o seguinte cmdlet para criar logons do SQL nesta réplica:
    
    ```
    Install-CsDatabase -Update
    ```

    - Repita as duas etapas anteriores (failover no grupo para uma réplica secundária e, em seguida, usar `Install-CsDatabase -Update`) para cada réplica no grupo.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Implantar um sempre no grupo de disponibilidade em um pool existente que não usa o espelhamento de banco de dados
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Se o pool que você estiver atualizando para uma AG hospedar o repositório de gerenciamento Central para sua organização, você deve primeiro mover o CMS para outro pool antes de atualizar este pool. Use o cmdlet Move-CsManagementServer para mover o pool. Se você não tiver outro pool em sua organização, você pode implantar um servidor Standard Edition temporariamente e mover o CMS para esse servidor antes de atualizar seu pool para a AG. 
  
1. Configure o recurso de cluster de Failover em todos os servidores de banco de dados que farão parte da AG. Em cada servidor, faça o seguinte:
    
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
    
3. Crie o Cluster de Failover do Windows Server (WSFC).
    
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
    
5. Em cada servidor do cluster, habilite AG no SQL Server Configuration Manager.
    
   - Abra o SQL Server Configuration Manager. Na árvore no lado esquerdo da tela, clique em **Serviços do SQL Server** e, em seguida, clique duas vezes no serviço SQL Server.  
    
   - Na caixa **Propriedades**, selecione a guia **Alta Disponibilidade AlwaysOn**. Marque a caixa de seleção **Habilitar Grupos de Disponibilidade AlwaysOn**. Reinicie o serviço SQL Server quando solicitado.
    
6. Criar o grupo de disponibilidade.
    
   - Abra o SQL Server Management Studio e conecte-se à instância do SQL Server.
    
   - No Object Explorer, expanda a pasta de **Sempre na alta disponibilidade** . Clique com o botão direito do mouse na pasta **Grupos de Disponibilidade** e clique em **Assistente para Novo Grupo de Disponibilidade**.
    
   - Se a página **Introdução** for exibida, clique em **Avançar**.
    
   - Na página **Especificar Nome do Grupo de Disponibilidade**, digite o nome do Grupo de disponibilidade e clique em **Avançar**.
    
   - Na página Selecionar bancos de dados, selecione os bancos de dados que você deseja incluir na AG. Then click **Next**.
    
     Não inclua o **ReportServer**, **ReportServerTempDB**ou bancos de dados de Chat persistente no AG, como eles não são suportados neste cenário. Você pode incluir todos os outro Skype para bancos de dados do servidor de negócios na AG.
    
   - Na página **Especificar réplicas** , clique na guia de **réplicas** . Em seguida, clique no botão **Adicionar réplicas** e conecte-se para as outras instâncias do SQL que você ingressou como nós o WSFC.
    
   - Para cada instância, selecione as opções **Failover Automático** e **Confirmação Síncrona**. Não selecione a opção **Secundária Legível**.
    
   - Clique na guia **Pontos de Extremidade** e verifique se o **Número da Porta** está definido como 5022.
    
   - Clique na guia **Ouvinte** e selecione a opção **Criar um ouvinte de grupo de disponibilidade**. Nesta opção, digite um nome para o ouvinte e defina a **Porta** como 1433 (outras portas não são suportadas para esta opção).
    
   - Clique em **Adicionar** e, na caixa **Endereço IPv4**, forneça o endereço IP virtual de sua preferência e clique em **OK**.
    
   - Na página **Selecionar Sincronização de Dados Inicial**, selecione Completo, especifique uma pasta que possa ser acessada pelas réplicas e para a qual a conta do serviço SQL Server usada por ambas as réplicas tenha permissões de Gravação. Clique em **Avançar**.
    
     Este compartilhamento de arquivos será usado temporariamente quando você inicializar os bancos de dados. Se você usar bancos de dados grandes, recomendamos que você os inicie manualmente caso a largura de banda de sua rede não possa acomodar o tamanho dos bancos de dados de backup.
    
     - Na página Validação, confira se as verificações de validação foram bem-sucedidas e, em seguida, clique em **Avançar**.
    
   - Na página **Resumo**, verifique todas as configurações e clique em Concluir.
    
7. Crie um novo repositório especificando o ouvinte AG.
    
   - Abra o construtor de topologia. Em sua topologia, expanda **Componentes Compartilhados**, clique com o botão direito do mouse em **Repositórios do SQL Server** e clique em **Novo Repositório do SQL Server**.
    
   - Na página **Definir Novo Repositório SQL**, primeiro marque a caixa de seleção **Configurações de Alta Disponibilidade** e, em seguida, certifique-se de que a opção Grupos de Disponibilidade AlwaysOn do SQL aparece na caixa suspensa.
    
   - Na caixa **FQDN do Ouvinte de Disponibilidade do SQL Server**, digite o FQDN do ouvinte que criou quando criou o grupo de disponibilidade.
    
   - Na caixa **FQDN do SQL Server** , digite o FQDN do nó principal do AG e clique em **Okey**.
    
8. Associe o novo sempre no grupo de disponibilidade com o pool de Front-End.
    
   - No construtor de topologia, clique com botão direito do pool para associar a AG e clique em **Editar propriedades**.
    
   - Em **associações**, na caixa **Repositório do SQL Server** , selecione a AG. Selecione o grupo mesmo para outros bancos de dados no qual você deseja mover para a AG pool.
    
   - Quando tiver certeza de que todos os bancos de dados necessários são definidos como a AG, clique em **Okey**.
    
9. Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**.
    
10. Execute algumas etapas finais para certificar-se de que os logons do SQL estão em cada uma das réplicas na AG.
    
    - Abra o construtor de topologia, selecione **Baixar topologia da implantação existente**e clique em **Okey**.
    
    - Expanda o Skype for Business Server, expanda sua topologia e expanda **Repositórios do SQL Server**. Com o botão direito o repositório SQL da AG novo e clique em **Editar propriedades**.
    
    - Na parte inferior da página, na caixa **FQDN do SQL Server** , altere o valor para o FQDN do ouvinte da AG.
    
    - Publique a topologia. No menu **Ação**, clique em **Topologia** e, em seguida, **Publicar**. Na página de confirmação, clique em **Avançar**. Aguarde alguns minutos para a nova topologia ser replicada.
    
    - Abra o SQL Server Management Studio e navegue até a AG. Faça failover para uma réplica secundária.
    
    - Abra o Skype do Shell de gerenciamento do servidor de negócios e digite o seguinte cmdlet para criar logons do SQL nesta réplica:
    
      ```
      Install-CsDatabase -Update
      ```

      - Repita as duas etapas anteriores (failover no grupo para uma réplica secundária e, em seguida, usar `Install-CsDatabase -Update`) para cada réplica no grupo.
