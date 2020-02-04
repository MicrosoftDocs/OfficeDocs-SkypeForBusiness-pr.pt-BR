---
title: 'Lync Server 2013: Configurando o envio de logs do SQL Server ao banco de dados primário do servidor de chat persistente'
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
ms.openlocfilehash: ae44d410ef165cdd4f77b877afcfb9349dd0ec00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>Configurando o envio de logs do SQL Server no Lync Server 2013 ao banco de dados primário do servidor de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-12_

Usando o SQL Server Management Studio, conecte-se à instância do banco de dados de envio de log secundário do servidor de chat persistente e certifique-se de que o agente do SQL Server esteja em execução.

Usando o SQL Server Management Studio conectado à instância do banco de dados primário de chat persistente, execute as seguintes etapas:

1.  Certifique-se de que o agente do SQL Server esteja em execução.

2.  Clique com o botão direito do mouse no banco de dados mgc e, em seguida, clique em **Propriedades**.

3.  Em **Selecionar uma página**, clique em **Envio de Logs de Transação**.

4.  Marque a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs**.

5.  Em **Backups de log de transação**, clique em **Configurações de Backup**.

6.  Na caixa **Caminho de rede para a pasta de backup**, digite o caminho de rede até o compartilhamento criado para a pasta de backup de log de transação.

7.  Se a pasta de backup estiver localizada no servidor primário, digite o caminho local para a pasta de backup na caixa **se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta (exemplo: c\\: backup)** . (Se a pasta de backup não estiver no servidor primário, você pode deixar essa caixa de diálogo em branco.)
    
    <div>
    

    > [!IMPORTANT]  
    > Se a conta de serviço do SQL Server em seu servidor primário for executada na conta do sistema local, você deverá criar a pasta de backup no servidor primário e especificar um caminho local para essa pasta.

    
    </div>

8.  Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.

9.  Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**. Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server conforme necessário.

10. Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.

11. Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.

12. Clique em **conectar** e conecte-se à instância do SQL Server que você configurou como seu servidor secundário.

13. Na caixa **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.

14. Na guia **Inicializar Banco de Dados Secundário**, escolha a opção **Sim, gerar um backup completo do banco de dados primário e restaurá-lo no banco de dados secundário (e criar o banco de dados secundário caso ele não exista)**.

15. Na guia **Copiar Arquivos**, na caixa **Pasta de destino dos arquivos copiados**, digite o caminho da pasta na qual os backups de logs de transação devem ser copiados. Normalmente, essa pasta está localizada no servidor secundário.

16. Observe a agenda de cópia listada na caixa **Agenda** em **Trabalho de cópia**. Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server conforme necessário. Essa agenda deve ser praticamente igual à agenda de backup.

17. Na guia **Restauração**, em **Estado do banco de dados ao restaurar backups**, escolha a opção **Nenhum modo de recuperação**.

18. Em **Atrasar restauração de backups pelo menos:**, selecione **0 minuto**.

19. Escolha um limite de alerta em **Alertar se nenhuma restauração ocorrer em**.

20. Observe a agenda de restauração listada na caixa **Agenda** em **Trabalho de restauração**. Para personalizar o cronograma da instalação, clique em **agendar**, ajuste o cronograma do agente do SQL Server conforme necessário e clique em **OK**. Essa agenda deve ser praticamente igual à agenda de backup.

21. Na caixa de diálogo **Propriedades do Banco de Dados**, clique em **OK** para começar o processo de configuração.

</div>

<span> </span>

</div>

</div>

</div>

