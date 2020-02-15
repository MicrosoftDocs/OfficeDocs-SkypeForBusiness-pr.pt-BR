---
title: Remover o banco de dados do SQL Server para um pool de front-ends
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a6aba3f084be6c40d5019af5da37f1a682f6eb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Remover o banco de dados do SQL Server para um pool de front-ends

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

Após remover um pool de front-ends do Microsoft Lync Server 2010 ou reconfigurar o pool para usar um banco de dados diferente, você pode remover os bancos de dados do SQL Server que hospedam os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para remover o banco de dados do SQL Server usando o construtor de topologia

1.  No servidor front-end do Lync Server 2013, abra o construtor de topologias e baixe a topologia existente.

2.  No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, **repositórios do SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao pool de front-ends removido ou reconfigurado e clique em **excluir**.

3.  Publique a topologia e verifique o status da replicação.

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Para remover os bancos de dados de usuário e de aplicativo do SQL Server

1.  Para remover os bancos de dados do SQL Server, você deve ser um membro do grupo SQL Server sysadmins do SQL Server do qual está removendo os arquivos de banco de dados.

2.  Abrir o Shell de gerenciamento do Lync Server

3.  Para remover o banco de dados do repositório de usuários do pool, digite:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Onde \<FQDN\> é o FQDN (nome de domínio totalmente qualificado) do servidor de banco de \<dados\> e instância é a instância de banco de dados nomeada (isto é, se houver uma definida).

4.  Para remover o banco de dados do repositório de aplicativos do pool, digite:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Onde \<FQDN\> é o FQDN do servidor de banco de dados \<e\> instância é a instância do banco de dados nomeado (ou seja, se houver uma definida).

5.  Quando o cmdlet **Uninstall-CsDataBase** solicitar que você confirme as ações, leia as informações e pressione **Y** (ou Enter) para continuar ou pressione **N** e em seguida Enter se desejar interromper o cmdlet (em caso de erros).

</div>

</div>

<span> </span>

</div>

</div>

</div>

