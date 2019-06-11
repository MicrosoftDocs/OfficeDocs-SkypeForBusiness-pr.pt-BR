---
title: 'Lync Server 2013: Configuração do Envio de Logs do Servidor SQL entre o espelho primário e o banco de dados secundário de Envio de Logs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a>Configuração do Envio de Logs do Servidor SQL entre o espelho primário e o banco de dados secundário de Envio de Logs no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Execute as etapas a seguir para envio de log para continuar se o banco de dados de chat persistente principal tiver falhado em seu banco de dados de espelho.

1.  Failover manual do banco de dados persistente de chat primário para o espelho. Isso é feito por meio do Shell de gerenciamento do Lync Server e do cmdlet **Invoke-CsDatabaseFailover** . Para obter detalhes, consulte "usando cmdlets do Shell de gerenciamento do Lync Server" em Implantando [SQL Mirroring para back-end Server High Availability no Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

2.  Usando o SQL Server Management Studio, conecte-se à instância principal do espelho do servidor de chat persistente.

3.  Certifique-se de que o agente do SQL Server esteja em execução.

4.  Clique com o botão direito do mouse no banco de dados mgc e, em seguida, clique em **Propriedades**.

5.  Em **Selecionar uma página**, clique em **Envio de Logs de Transação**.

6.  Marque a caixa de seleção **Habilitar como banco de dados primário em uma configuração de envio de logs**.

7.  Em **Backups de log de transação**, clique em **Configurações de Backup**.

8.  Na caixa **Caminho de rede para a pasta de backup**, digite o caminho de rede para compartilhamento que você criou para a pasta de backup de log de transação.

9.  Se a pasta de backup estiver no servidor primário, digite o caminho local para a pasta de backup na caixa **Se a pasta de backup estiver localizada no servidor primário, digite um caminho local para a pasta**. (Se a pasta de backup não estiver no servidor primário, você pode deixar essa caixa de diálogo em branco.)
    
    <div>
    

    > [!IMPORTANT]  
    > Se a conta de serviço do SQL Server em seu servidor primário for executada na conta do sistema local, você deverá criar a pasta de backup no servidor primário e especificar um caminho local para essa pasta.

    
    </div>

10. Configure os parâmetros **Excluir arquivos com mais de** e **Alertar se nenhum backup ocorrer em**.

11. Observe a agenda de backup listada na caixa **Agenda** em **Trabalho de backup**. Para personalizar o cronograma da instalação, clique em **agendar**e ajuste o cronograma do agente do SQL Server, conforme necessário.
    
    <div>
    

    > [!IMPORTANT]  
    > Use as mesmas configurações que você usou para o banco de dados primário.

    
    </div>

12. Em **Compactação**, selecione **Usar a configuração padrão do servidor** e clique em **OK**.

13. Em **Instâncias e bancos de dados do servidor secundário**, clique em **Adicionar**.

14. Clique em **Conectar** e conecte-se à instância do SQL Server que você configurou como servidor secundário.

15. Na caixa **Banco de dados secundário**, selecione o banco de dados **mgc** da lista.

16. Na guia **Inicializar Banco de Dados Secundário**, selecione a opção **Não, o banco de dados secundário é inicializado**.

17. Na guia **Copiar Arquivos**, em **Pasta de destino dos arquivos copiados**, digite o caminho da pasta à qual os backups de logs de transação devem ser copiados e clique em **OK**. Essa pasta normalmente se encontra no servidor secundário.

18. Abra a lista suspensa **Configuração de Script** e selecione **Configuração de Script para a janela Nova Consulta**.

19. Na janela Nova Consulta, em **Propriedades do Banco de Dados**, clique em **OK** para iniciar o processo de configuração.

20. Selecione e execute a primeira metade da consulta (consulte a etapa 18) até a linha:-- \* \* \* \* \* \* end: script a ser \* \* \* \* \* \*executado no principal:.
    
    <div>
    

    > [!IMPORTANT]  
    > Executar manualmente esse script é necessário porque o SQL Server Management Studio não oferece suporte a vários bancos de dados principais em uma configuração de envio de logs do SQL Server.

    
    </div>

21. Selecione **Cancelar** para fechar o painel de configuração de envio do arquivo de log e para estabelecer uma configuração de trabalho que implemente corretamente o envio do arquivo de log para os bancos de dados primário e espelhado (no caso de failover). 

22. Faça o failback manual do banco de dados de chat persistente principal para o principal. Isso é feito usando o Shell de gerenciamento do Lync Server e o cmdlet **Invoke-CsDatabaseFailover** . Para obter detalhes, consulte "usando cmdlets do Shell de gerenciamento do Lync Server" em Implantando [SQL Mirroring para back-end Server High Availability no Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

<div>

## <a name="see-also"></a>Confira também


[Implantando espelhamento SQL para alta disponibilidade de Servidor Back-End no Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[Implantando espelhamento SQL para alta disponibilidade de Servidor Back-End no Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

