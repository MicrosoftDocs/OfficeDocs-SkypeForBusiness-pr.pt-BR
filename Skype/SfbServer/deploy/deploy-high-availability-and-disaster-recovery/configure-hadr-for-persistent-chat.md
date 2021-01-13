---
title: Configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumo: Leia este tópico para saber como configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 0b58f820c1157da8ff36f8dcc68d9e08465bcddc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830621"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015.
  
O Skype for Business Server oferece suporte a vários modos de alta disponibilidade para seus Servidores Back-End, incluindo espelhamento de banco de dados. Para obter mais informações, [consulte Plan for high availability and disaster recovery in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
> [!NOTE]
> Os Grupos de Disponibilidade AlwaysOn não são suportados com Servidores de Chat Persistente. 
  
Antes de configurar sua implantação de Chat Persistente para alta disponibilidade e recuperação de desastre, certifique-se de estar familiarizado com os conceitos em Planejar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no [Skype for Business Server 2015.](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) A solução de recuperação de desastre para o Servidor de Chat Persistente descrito nestes tópicos é criada em um pool estendido de Servidor de Chat Persistente. O conteúdo de planejamento descreve os requisitos de recursos e a topologia de pool estendido que permite alta disponibilidade e recuperação de desastres para o Servidor de Chat Persistente, incluindo o uso do espelhamento do SQL Server para alta disponibilidade e envio de log do SQL Server para recuperação de desastres.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Usar o Construtor de Topologias para configurar alta disponibilidade e recuperação de desastre

No Construtor de Topologias, execute as seguintes etapas para configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente.
  
1. Adicione os bancos de dados espelho e os armazenamentos do SQL Server do banco de dados secundário de envio de log.
    
2. Edite as propriedades do serviço do Servidor de Chat Persistente para:
    
    a. Ativar espelhamento do banco de dados primário.
    
    b. Adicione o armazenamento principal do SQL Server espelho.
    
    c. Habilita o banco de dados de Envio de Log do SQL Server.
    
    d. Adicione o armazenamento secundário do SQL Server envio de log do SQL Server.
    
    e. Adicione o espelho do armazenamento do SQL Server ao banco de dados secundário.
    
    f. Publique a topologia.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configurar o envio de log do SQL Server para o banco de dados primário do Servidor de Chat Persistente

Usando o SQL Server Management Studio, conecte-se à instância secundária do banco de dados de Envio de Log do Servidor de Chat Persistente e certifique-se de que o SQL Server Agent está em execução. Em seguida, conecte-se à instância do banco de dados primário de Chat Persistente e execute as seguintes etapas:
  
1. Clique com o botão direito no banco de dados mgc e, em seguida, clique em **Propriedades**.
    
2. Em **Selecionar uma página**, clique em **Envio de Logs de Transações**.
    
3. Selecione a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de log**.
    
4. Em **Backups do log de transação**, clique em **Configurações de Backup**.
    
5. Na caixa **Caminho de rede para a pasta Backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup do log de transação.
    
6. Se a pasta de backup estiver localizada no servidor primário, digite o caminho local até a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c:\backup)**. (Se a pasta backup não estiver no servidor primário, deixa essa caixa em branco.)
    
    > [!IMPORTANT]
    > Se a conta de serviço do SQL Server em seu servidor primário for executado sob a conta do sistema local, você deverá criar sua pasta de backup no servidor primário e especificar um caminho local para essa pasta. 
  
7. Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.
    
8. Observe a agenda de backup listada na caixa de diálogo **Agendar** em **Trabalho de backup**. Para personalizar a agenda da instalação, clique em **Agendar** e ajuste a agenda do SQL Server Agent conforme necessário.
    
9. Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.
    
10. Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.
    
11. Clique **em** Conectar e conecte-se à instância do SQL Server que você configurou como seu servidor secundário.
    
12. Na caixa de diálogo **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.
    
13. Na guia **Inicializar** banco de dados secundário, escolha a opção Sim, gere um backup completo do banco de dados primário e restaure-o no banco de dados secundário (e crie o banco de dados secundário se ele não **existir).**
    
14. Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiadas. Normalmente, essa pasta está localizada no servidor secundário.
    
15. Observe agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**. Para personalizar a agenda da instalação, clique em **Agendar** e ajuste a agenda do SQL Server Agent conforme necessário. Essa agenda deve ser quase a mesma que a agenda de backup.
    
16. Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.
    
17. Em **Atrasar restauração de backups pelo menos:**, selecione **0 minutos**.
    
18. Escolha um limite de alerta sob **Alertar se nenhuma restauração ocorrer em**.
    
19. Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**. Para personalizar a agenda da instalação, clique **em** Agendar, ajuste a agenda do SQL Server Agent conforme necessário e clique em **OK.** Essa agenda deve ser quase a mesma que a agenda de backup.
    
20. Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configurar o envio de log do SQL Server entre o espelho primário e o banco de dados secundário

Execute as etapas a seguir para que o envio de log continue se o banco de dados de Chat Persistente primário for failed over para seu banco de dados espelho.
  
1. Fail over the primary Persistent Chat database to the mirror. Isso é feito usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Invoke-CsDatabaseFailover.**
    
2. Usando o SQL Server Management Studio, conecte-se à instância de espelho principal do Servidor de Chat Persistente.
    
3. Certifique-se de que o SQL Server Agent está em execução.
    
4. Clique com o botão direito no banco de dados mgc e, em seguida, clique em **Propriedades**.
    
5. Em **Selecionar uma página**, clique em **Envio de Logs de Transações**.
    
6. Selecione a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de log**.
    
7. Em **Backups de log de transações**, clique em **Configurações de Backup**.
    
8. Na caixa de diálogo **Caminho de rede para a pasta Backup**, digite o caminho de rede para compartilhamento que você criou para a pasta backup de log de transação.
    
9. Se a pasta de backup estiver no servidor primário, digite o caminho local na pasta de backup na caixa de diálogo **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta**. (Se a pasta de backup não estiver o servidor primário, você pode deixa essa caixa de diálogo vazia.)
    
    > [!IMPORTANT]
    > Se a conta de serviço do SQL Server em seu servidor primário for executado sob a conta do sistema local, você deverá criar sua pasta de backup no servidor primário e especificar um caminho local para essa pasta. 
  
10. Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.
    
11. Observe a agenda de backup listada na caixa de diálogo **Agendar** em **Trabalho de backup**. Para personalizar a agenda da instalação, clique em **Agendar** e ajuste a agenda do SQL Server Agent, conforme necessário.
    
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
    
20. Selecione e execute a primeira metade da consulta (veja a etapa 18) até a linha: -- Fim: script a ser executado \* \* \* \* \* \* no Primário: \* \* \* \* \* \* .
    
    > [!IMPORTANT]
    > A execução manual desse script é necessária porque o SQL Server Management Studio não dá suporte a vários bancos de dados primários em uma configuração de Envio de Log do SQL Server. 
  
21. Selecione **Cancelar** para fechar o painel de configuração de envio do Arquivo de Log e para estabelecer uma configuração de trabalho que implemente corretamente o envio do arquivo de log para os bancos de dados primário e espelhado (no case de failover).
    
22. Fail back manual do banco de dados de Chat Persistente primário para o primário. Isso é feito usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Invoke-CsDatabaseFailover.**
    

