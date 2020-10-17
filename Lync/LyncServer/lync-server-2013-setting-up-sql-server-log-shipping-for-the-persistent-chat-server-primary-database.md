---
title: 'Lync Server 2013: Configurando o envio de logs do SQL Server para o banco de dados de servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ff5f403329c430e18767d9b334982ecccc3898b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521798"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>Configurando o envio de logs do SQL Server no Lync Server 2013 para o banco de dados primário do servidor de chat persistente

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-12_

Usando o SQL Server Management Studio, conecte-se à instância do banco de dados de envio de logs do servidor de chat persistente secundário e certifique-se de que o SQL Server Agent esteja em execução.

Usando o SQL Server Management Studio conectado à instância de banco de dados principal de chat persistente, execute as seguintes etapas:

1.  Certifique-se de que o SQL Server Agent esteja em execução.

2.  Clique com o botão direito no banco de dados mgc e, em seguida, clique em **Propriedades**.

3.  Em **Selecionar uma página**, clique em **Envio de Logs de Transações**.

4.  Selecione a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de log**.

5.  Em **Backups do log de transação**, clique em **Configurações de Backup**.

6.  Na caixa **Caminho de rede para a pasta Backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup do log de transação.

7.  Se a pasta de backup estiver localizada no servidor primário, digite o caminho local para a pasta de backup na caixa **se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c: \\ backup)** . (Se a pasta de backup não estiver o servidor primário, você pode deixa essa caixa de diálogo vazia.)
    
    <div>
    

    > [!IMPORTANT]  
    > Se a conta de serviço do SQL Server em seu servidor principal é executada sob a conta do sistema local, você deve criar sua pasta de backup no servidor primário e especificar um caminho local para essa pasta.

    
    </div>

8.  Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.

9.  Observe a agenda de backup listada na caixa de diálogo **Agendar** em **Trabalho de backup**. Para personalizar a agenda da instalação, clique em **agenda**e ajuste a agenda do SQL Server Agent conforme necessário.

10. Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.

11. Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.

12. Clique em **conectar** e conecte-se à instância do SQL Server que você configurou como servidor secundário.

13. Na caixa de diálogo **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.

14. Na guia **inicializar banco de dados secundário** , escolha a opção **Sim, gere um backup completo do banco de dados primário e restaure-o no banco de dados secundário (e crie o banco de dados secundário, caso não exista)**.

15. Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiadas. Normalmente, essa pasta está localizada no servidor secundário.

16. Observe agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**. Para personalizar a agenda da instalação, clique em **agenda**e ajuste a agenda do SQL Server Agent conforme necessário. Essa agenda deve ser quase a mesma que a agenda de backup.

17. Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.

18. Em **Atrasar restauração de backups pelo menos:**, selecione **0 minutos**.

19. Escolha um limite de alerta sob **Alertar se nenhuma restauração ocorrer em**.

20. Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**. Para personalizar a agenda da instalação, clique em **agenda**, ajuste a agenda do SQL Server Agent conforme necessário e clique em **OK**. Essa agenda deve ser quase a mesma que a agenda de backup.

21. Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.

</div>

<span> </span>

</div>

</div>

</div>

