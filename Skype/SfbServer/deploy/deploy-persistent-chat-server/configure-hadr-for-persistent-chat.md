---
title: Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumo: Leia este tópico para saber como configurar a alta disponibilidade e a recuperação de desastres para o servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: e9e313cf83fd784e94efe98fe7a49bbbb800f83f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239832"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como configurar a alta disponibilidade e a recuperação de desastres para o servidor de chat persistente no Skype for Business Server 2015.
  
O Skype for Business Server oferece suporte a vários modos de alta disponibilidade para seus servidores back-end, incluindo o espelhamento de banco de dados. Para obter mais informações, veja [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Os grupos de disponibilidade AlwaysOn não são compatíveis com servidores de chat persistentes. 

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.
  
Antes de configurar a implantação de chat persistente para alta disponibilidade e recuperação de desastres, certifique-se de que você esteja familiarizado com os conceitos do [plano para alta disponibilidade e recuperação de desastres para servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md). A solução de recuperação de desastres para servidor de chat persistente descrito nestes tópicos foi criada em um pool de servidores de chat persistentes ampliados. O conteúdo de planejamento descreve os requisitos do recurso e a topologia de pool ampliada que permite alta disponibilidade e recuperação de desastre para o servidor de chat persistente, incluindo o uso do espelhamento do SQL Server para alta disponibilidade e envio de log do SQL Server para recuperação de desastres.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Uso do Construtor de Topologias para configurar alta disponibilidade e recuperação de desastre

No Construtor de Topologias, execute as seguintes etapas para configurar alta disponibilidade e recuperação de desastre para Servidor de Chat Persistente.
  
1. Adicione os bancos de dados espelho e os repositórios secundários do banco de dados do SQL Server de envio de log.
    
2. Edite as propriedades do serviço do servidor de chat persistente para:
    
    a. Ativar o espelhamento do banco de dados primário.
    
    b. Adicione a loja principal do SQL Server do espelho.
    
    c. Habilite o banco de dados de envio de log do SQL Server.
    
    d. Adicione o repositório do SQL Server secundário de envio de logs do SQL Server.
    
    vocálico. Adicione o espelho do SQL Server Store para o banco de dados secundário.
    
    letra. Publique a topologia.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configuração do envio de logs do SQL Server para o banco de dados primário do Servidor de Chat Persistente

Usando o SQL Server Management Studio, conecte-se à instância do banco de dados de envio de log secundário do servidor de chat persistente e certifique-se de que o agente do SQL Server esteja em execução. Em seguida, conecte-se à instância do banco de dados primário de chat persistente e execute as seguintes etapas:
  
1. Clique com o botão direito do mouse no banco de dados mgc e, em seguida, clique em **Propriedades**.
    
2. Em **Selecionar uma página**, clique em **Envio de Logs de Transação**.
    
3. Marque a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs**.
    
4. Em **Backups de log de transação**, clique em **Configurações de Backup**.
    
5. Na caixa **Caminho de rede para a pasta de backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup de log de transação.
    
6. Se a pasta de backup estiver localizada no servidor primário, digite o caminho local até a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c:\backup)**. (Se a pasta de backup não estiver no servidor primário, deixe essa caixa em branco.)
    
    > [!IMPORTANT]
    > Se a conta de serviço do SQL Server em seu servidor primário for executada na conta do sistema local, você deverá criar a pasta de backup no servidor primário e especificar um caminho local para essa pasta. 
  
7. Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.
    
8. Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**. Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server conforme necessário.
    
9. Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.
    
10. Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.
    
11. Clique em **conectar** e conecte-se à instância do SQL Server que você configurou como seu servidor secundário.
    
12. Na caixa **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.
    
13. Na guia **Inicializar Banco de Dados Secundário**, escolha a opção **Sim, gerar um backup completo do banco de dados primário e restaurá-lo no banco de dados secundário (e criar o banco de dados secundário caso ele não exista)**.
    
14. Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiados. Normalmente, essa pasta está localizada no servidor secundário.
    
15. Observe a agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**. Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server conforme necessário. Essa agenda deve ser praticamente igual à agenda de backup.
    
16. Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.
    
17. Em **Atrasar restauração de backups pelo menos:**, selecione **0 minuto**.
    
18. Escolha um limite de alerta em **Alertar se nenhuma restauração ocorrer em**.
    
19. Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**. Para personalizar o cronograma da instalação, clique em **agendar**, ajuste o cronograma do agente do SQL Server conforme necessário e clique em **OK**. Essa agenda deve ser praticamente igual à agenda de backup.
    
20. Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configuração do envio de logs do SQL Server entre o espelho primário e o banco de dados secundário

Execute as etapas a seguir para envio de log para continuar se o banco de dados de chat persistente principal tiver falhado em seu banco de dados de espelho.
  
1. Failover manual do banco de dados persistente de chat primário para o espelho. Isso é feito usando o Shell de gerenciamento do Skype for Business Server e o cmdlet **Invoke-CsDatabaseFailover** .
    
2. Usando o SQL Server Management Studio, conecte-se à instância principal do espelho do servidor de chat persistente.
    
3. Certifique-se de que o agente do SQL Server esteja em execução.
    
4. Clique com o botão direito do mouse no banco de dados mgc e, em seguida, clique em **Propriedades**.
    
5. Em **Selecionar uma página**, clique em **Envio de Logs de Transação**.
    
6. Marque a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs**.
    
7. Em **Backups de log de transação**, clique em **Configurações de Backup**.
    
8. Na caixa **Caminho de rede para a pasta de backup**, digite o caminho de rede para compartilhamento que você criou para a pasta de backup de log de transação.
    
9. Se a pasta de backup estiver no servidor primário, digite o caminho local para a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta**. (Se a pasta de backup não estiver no servidor primário, você pode deixar essa caixa de diálogo em branco.)
    
    > [!IMPORTANT]
    > Se a conta de serviço do SQL Server em seu servidor primário for executada na conta do sistema local, você deverá criar a pasta de backup no servidor primário e especificar um caminho local para essa pasta. 
  
10. Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.
    
11. Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**. Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server, conforme necessário.
    
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
    
20. Selecione e execute a primeira metade da consulta (consulte a etapa 18) até a linha:-- \* \* \* \* \* \* end: script a ser \* \* \* \* \* \*executado no principal:.
    
    > [!IMPORTANT]
    > Executar manualmente esse script é necessário porque o SQL Server Management Studio não oferece suporte a vários bancos de dados principais em uma configuração de envio de logs do SQL Server. 
  
21. Selecione **Cancelar** para fechar o painel de configuração de envio do arquivo de log e para estabelecer uma configuração de trabalho que implemente corretamente o envio do arquivo de log para os bancos de dados primário e espelhado (no caso de failover). 
    
22. Faça o failback manual do banco de dados de chat persistente principal para o principal. Isso é feito usando o Shell de gerenciamento do Skype for Business Server, e o cmdlet **Invoke-CsDatabaseFailover** .
    

