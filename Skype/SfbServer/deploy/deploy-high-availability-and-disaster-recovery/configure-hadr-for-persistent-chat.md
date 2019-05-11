---
title: Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumo: Leia este tópico para saber como configurar alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015.'
ms.openlocfilehash: 0d2dcd4650c842dad58d85f9f2d9d67ad74ef667
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894476"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como configurar alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015.
  
Skype para Business Server suporta vários modos de alta disponibilidade para seus servidores Back-End, incluindo o espelhamento de banco de dados. Para obter mais informações, veja [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Não há suporte para grupos de disponibilidade do AlwaysOn com servidores de Chat persistente. 
  
Antes de configurar a implantação do Chat persistente para alta disponibilidade e recuperação de desastres, certifique-se de que você está familiarizado com os conceitos apresentados no [plano de alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md). A solução de recuperação de desastres para o servidor de Chat persistente descritas nestes tópicos baseia-se em um pool do servidor de Chat persistente ampliado. O conteúdo de planejamento descreve os requisitos de recursos e a topologia de pool ampliado que permite alta disponibilidade e recuperação de desastres para o servidor de Chat persistente, incluindo o uso de espelhamento do SQL Server para alta disponibilidade e o envio de logs do SQL Server recuperação de desastres.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Uso do Construtor de Topologias para configurar alta disponibilidade e recuperação de desastre

No Construtor de Topologias, execute as seguintes etapas para configurar alta disponibilidade e recuperação de desastre para Servidor de Chat Persistente.
  
1. Adicione os bancos de dados de espelho e o log envio banco de dados secundário que armazena do SQL Server.
    
2. Edite as propriedades do serviço do servidor de Chat persistente para:
    
    a. Ativar o espelhamento do banco de dados primário.
    
    b. Adicione o repositório do SQL Server espelho primário.
    
    c. Habilite o banco de dados de envio de Log do SQL Server.
    
    d. Adicione o envio de Log do SQL Server secundário SQL Server store.
    
    f. Adicione o espelho do repositório do SQL Server para o banco de dados secundário.
    
    f. Publique a topologia.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configuração do envio de logs do SQL Server para o banco de dados primário do Servidor de Chat Persistente

Usando o SQL Server Management Studio, conecte-se para os instância de banco de dados de envio de Log secundária Persistent Chat Server e certifique-se de que o SQL Server Agent esteja em execução. Em seguida, conecte-se à instância de banco de dados primário do Chat persistente e execute as seguintes etapas:
  
1. Clique com o botão direito do mouse no banco de dados mgc e, em seguida, clique em **Propriedades**.
    
2. Em **Selecionar uma página**, clique em **Envio de Logs de Transação**.
    
3. Marque a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs**.
    
4. Em **Backups de log de transação**, clique em **Configurações de Backup**.
    
5. Na caixa **Caminho de rede para a pasta de backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup de log de transação.
    
6. Se a pasta de backup estiver localizada no servidor primário, digite o caminho local até a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c:\backup)**. (Se a pasta de backup não estiver no servidor primário, deixe essa caixa em branco.)
    
    > [!IMPORTANT]
    > Se a conta de serviço do SQL Server no seu servidor principal é executado sob a conta do sistema local, você deve criar sua pasta de backup no servidor principal e especificar um caminho local para essa pasta. 
  
7. Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.
    
8. Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**. Para personalizar o agendamento para sua instalação, clique em **Agendar**e ajuste a agenda do SQL Server Agent conforme necessário.
    
9. Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.
    
10. Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.
    
11. Clique em **Conectar** e conecte-se à instância do SQL Server que você configurou como servidor secundário.
    
12. Na caixa **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.
    
13. Na guia **Inicializar Banco de Dados Secundário**, escolha a opção **Sim, gerar um backup completo do banco de dados primário e restaurá-lo no banco de dados secundário (e criar o banco de dados secundário caso ele não exista)**.
    
14. Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiados. Normalmente, essa pasta está localizada no servidor secundário.
    
15. Observe a agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**. Para personalizar o agendamento para sua instalação, clique em **Agendar**e ajuste a agenda do SQL Server Agent conforme necessário. Essa agenda deve ser praticamente igual à agenda de backup.
    
16. Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.
    
17. Em **Atrasar restauração de backups pelo menos:**, selecione **0 minuto**.
    
18. Escolha um limite de alerta em **Alertar se nenhuma restauração ocorrer em**.
    
19. Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**. Para personalizar o agendamento para sua instalação, clique em **Agendar**, ajuste a agenda do SQL Server Agent conforme necessário e clique em **Okey**. Essa agenda deve ser praticamente igual à agenda de backup.
    
20. Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configuração do envio de logs do SQL Server entre o espelho primário e o banco de dados secundário

Execute as etapas a seguir para envio de log continue se o banco de dados primário do Chat persistente realizou um failover ao seu banco de dados de espelho.
  
1. Failover manualmente o banco de dados de bate-papo persistente principal para o espelho. Isso é feito usando o Skype para o Shell de gerenciamento de servidor de negócios e o cmdlet **Invoke-CsDatabaseFailover** .
    
2. Usando o SQL Server Management Studio, conecte-se à instância de espelho primária do servidor de Chat persistente.
    
3. Certifique-se de que o SQL Server Agent esteja em execução.
    
4. Clique com o botão direito do mouse no banco de dados mgc e, em seguida, clique em **Propriedades**.
    
5. Em **Selecionar uma página**, clique em **Envio de Logs de Transação**.
    
6. Marque a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs**.
    
7. Em **Backups de log de transação**, clique em **Configurações de Backup**.
    
8. Na caixa **Caminho de rede para a pasta de backup**, digite o caminho de rede para compartilhamento que você criou para a pasta de backup de log de transação.
    
9. Se a pasta de backup estiver no servidor primário, digite o caminho local para a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta**. (Se a pasta de backup não estiver no servidor primário, você pode deixar essa caixa de diálogo em branco.)
    
    > [!IMPORTANT]
    > Se a conta de serviço do SQL Server no seu servidor principal é executado sob a conta do sistema local, você deve criar sua pasta de backup no servidor principal e especificar um caminho local para essa pasta. 
  
10. Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.
    
11. Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**. Para personalizar o agendamento para sua instalação, clique em **Agendar**e ajuste a agenda do SQL Server Agent, conforme necessário.
    
    > [!IMPORTANT]
    > Use as mesmas configurações que você usou para o banco de dados primário. 
  
12. Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.
    
13. Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.
    
14. Clique em **Conectar** e conecte-se à instância do SQL Server que você configurou como servidor secundário.
    
15. Na caixa **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.
    
16. Na guia **Inicializar Banco de Dados Secundário**, selecione a opção **Não, o banco de dados secundário é inicializado**.
    
17. Na guia **Copiar Arquivos**, em **Pasta de destino dos arquivos copiados**, digite o caminho da pasta à qual os backups de logs de transação devem ser copiados e clique em **OK**. Essa pasta normalmente se encontra no servidor secundário.
    
18. Abra a lista suspensa **Configuração de Script** e selecione **Configuração de Script para a janela Nova Consulta**.
    
19. Na janela Nova Consulta, em **Propriedades do Banco de Dados**, clique em **OK** para iniciar o processo de configuração.
    
20. Selecione e execute a primeira metade da consulta (veja etapa 18) para cima na linha:- \* \* \* \* \* \* fim: Script a ser executado no primário: \* \* \* \* \* \*.
    
    > [!IMPORTANT]
    > Execução manual desse script é necessária porque o SQL Server Management Studio não suporta vários bancos de dados primários em uma configuração de envio de Log do SQL Server. 
  
21. Selecione **Cancelar** para fechar o painel de configuração de envio do arquivo de log e para estabelecer uma configuração de trabalho que implemente corretamente o envio do arquivo de log para os bancos de dados primário e espelhado (no caso de failover). 
    
22. Manualmente failback Chat persistente banco de dados primário para o principal. Isso é feito usando o Skype para Business Server Management Shell e o cmdlet **Invoke-CsDatabaseFailover** .
    

