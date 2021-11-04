---
title: Configurar alta disponibilidade e recuperação de desastres para o Servidor de Chat Persistente Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumo: leia este tópico para saber como configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: b4377d2151adfccd591bb7c59d7d8854f03e453b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755630"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurar alta disponibilidade e recuperação de desastres para o Servidor de Chat Persistente Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente Skype for Business Server 2015.
  
Skype for Business Server oferece suporte a vários modos de alta disponibilidade para seus Servidores Back-End, incluindo espelhamento de banco de dados. Para obter mais informações, [consulte Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Os Grupos de Disponibilidade AlwaysOn não são suportados com Servidores de Chat Persistente. 

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015.
  
Antes de configurar sua implantação de Chat Persistente para alta disponibilidade e recuperação de desastres, certifique-se de que você está familiarizado com os conceitos em Plan for high availability and [disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md). A solução de recuperação de desastres para o Servidor de Chat Persistente descrito nestes tópicos é construída em um pool de Servidor de Chat Persistente estendido. O conteúdo de planejamento descreve os requisitos de recursos e a topologia de pool estendido que permite alta disponibilidade e recuperação de desastres para o Servidor de Chat Persistente, incluindo o uso de espelhamento SQL Server para alta disponibilidade e envio de log SQL Server para recuperação de desastres.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Usar o Construtor de Topologias para configurar a alta disponibilidade e a recuperação de desastres

No Construtor de Topologias, execute as etapas a seguir para configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente.
  
1. Adicione os bancos de dados espelho e o banco de dados secundário de envio de log SQL Server armazenamentos.
    
2. Edite as propriedades de serviço do Servidor de Chat Persistente para:
    
    a. Ativar espelhamento do banco de dados primário.
    
    b. Adicione o espelho principal SQL Server store.
    
    c. Habilita o SQL Server de Envio de Log.
    
    d. Adicione o SQL Server de Envio de Log secundário SQL Server armazenamento.
    
    e. Adicione o SQL Server de armazenamento do banco de dados secundário.
    
    f. Publique a topologia.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configurar o SQL Server de log para o banco de dados primário do Servidor de Chat Persistente

Usando SQL Server Management Studio, conecte-se à instância de banco de dados de Envio de Log do Servidor de Chat Persistente e certifique-se de que SQL Server Agente está em execução. Em seguida, conecte-se à instância de banco de dados principal de Chat Persistente e execute as seguintes etapas:
  
1. Clique com o botão direito no banco de dados mgc e, em seguida, clique em **Propriedades**.
    
2. Em **Selecionar uma página**, clique em **Envio de Logs de Transações**.
    
3. Selecione a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de log**.
    
4. Em **Backups do log de transação**, clique em **Configurações de Backup**.
    
5. Na caixa **Caminho de rede para a pasta Backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup do log de transação.
    
6. Se a pasta de backup estiver localizada no servidor primário, digite o caminho local até a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c:\backup)**. (Se a pasta backup não estiver no servidor primário, deixa essa caixa em branco.)
    
    > [!IMPORTANT]
    > Se a SQL Server de serviço no servidor primário for executado na conta do sistema local, você deverá criar sua pasta de backup no servidor principal e especificar um caminho local para essa pasta. 
  
7. Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.
    
8. Observe a agenda de backup listada na caixa de diálogo **Agendar** em **Trabalho de backup**. Para personalizar a agenda da instalação, clique em **Agendar** e ajustar a agenda SQL Server agente conforme necessário.
    
9. Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.
    
10. Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.
    
11. Clique **Conexão** e conecte-se à instância de SQL Server que você configurou como seu servidor secundário.
    
12. Na caixa de diálogo **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.
    
13. Na guia **Inicializar** banco de dados secundário, escolha a opção Sim, gere um backup completo do banco de dados principal e restaure-o no banco de dados secundário (e crie o banco de dados secundário se ele não **existir)**.
    
14. Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiadas. Normalmente, essa pasta está localizada no servidor secundário.
    
15. Observe agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**. Para personalizar a agenda da instalação, clique em **Agendar** e ajustar a agenda SQL Server agente conforme necessário. Essa agenda deve ser quase a mesma que a agenda de backup.
    
16. Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.
    
17. Em **Atrasar restauração de backups pelo menos:**, selecione **0 minutos**.
    
18. Escolha um limite de alerta sob **Alertar se nenhuma restauração ocorrer em**.
    
19. Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**. Para personalizar a agenda da instalação, clique em **Agendar**, ajustar a agenda SQL Server agente conforme necessário e clique em **OK**. Essa agenda deve ser quase a mesma que a agenda de backup.
    
20. Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configurar o SQL Server de log entre o espelho principal e o banco de dados secundário

Execute as etapas a seguir para que o envio de log continue se o banco de dados de Chat Persistente principal falhar no banco de dados espelho.
  
1. Falha manualmente no banco de dados de Chat Persistente principal no espelho. Isso é feito usando o Shell de Gerenciamento Skype for Business Server e o cmdlet **Invoke-CsDatabaseFailover.**
    
2. Usando a SQL Server Management Studio, conecte-se à instância de espelho principal do Servidor de Chat Persistente.
    
3. Certifique-se de que o SQL Server agente está em execução.
    
4. Clique com o botão direito no banco de dados mgc e, em seguida, clique em **Propriedades**.
    
5. Em **Selecionar uma página**, clique em **Envio de Logs de Transações**.
    
6. Selecione a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de log**.
    
7. Em **Backups de log de transações**, clique em **Configurações de Backup**.
    
8. Na caixa de diálogo **Caminho de rede para a pasta Backup**, digite o caminho de rede para compartilhamento que você criou para a pasta backup de log de transação.
    
9. Se a pasta de backup estiver no servidor primário, digite o caminho local na pasta de backup na caixa de diálogo **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta**. (Se a pasta de backup não estiver o servidor primário, você pode deixa essa caixa de diálogo vazia.)
    
    > [!IMPORTANT]
    > Se a SQL Server de serviço no servidor primário for executado na conta do sistema local, você deverá criar sua pasta de backup no servidor principal e especificar um caminho local para essa pasta. 
  
10. Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.
    
11. Observe a agenda de backup listada na caixa de diálogo **Agendar** em **Trabalho de backup**. Para personalizar a agenda da instalação, clique em **Agendar** e ajustar a agenda SQL Server agente, conforme necessário.
    
    > [!IMPORTANT]
    > Use as mesmas configurações que você usou para o banco de dados primário. 
  
12. Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.
    
13. Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.
    
14. Clique **Conectar** e conecte-se na instância do SQL Server que você configurou como servidor secundário.
    
15. Na caixa de diálogo **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.
    
16. Na guia **Inicializar Banco de Dados Secundário**, selecione a opção **Não, o banco de dados secundário é inicializado**.
    
17. Na guia **Copiar Arquivos**, em **Pasta de destino dos arquivos copiados**, digite o caminho da pasta à qual a o backup de logs de transação deveriam ser copiados e clique em **OK**. Essa pasta normalmente se encontra no servidor secundário.
    
18. Abra a lista suspensa **Configuração do Script** e selecione **Configuração de Script na Janela Nova Consulta**.
    
19. Na nova janela de consulta, em **Propriedades do Banco de Dados**, clique em **OK** para iniciar o processo de configuração.
    
20. Selecione e execute a primeira metade da consulta (consulte a etapa 18) até a linha: -- Fim: Script a ser executado \* \* \* \* \* \* no Primário: \* \* \* \* \* \* .
    
    > [!IMPORTANT]
    > A execução manual desse script é necessária porque SQL Server Management Studio não dá suporte a vários bancos de dados principais em uma configuração SQL Server Envio de Log. 
  
21. Selecione **Cancelar** para fechar o painel de configuração de envio do Arquivo de Log e para estabelecer uma configuração de trabalho que implemente corretamente o envio do arquivo de log para os bancos de dados primário e espelhado (no case de failover).
    
22. Retornar manualmente o banco de dados de Chat Persistente principal para o principal. Isso é feito usando o Shell de Gerenciamento Skype for Business Server e o cmdlet **Invoke-CsDatabaseFailover.**
    

