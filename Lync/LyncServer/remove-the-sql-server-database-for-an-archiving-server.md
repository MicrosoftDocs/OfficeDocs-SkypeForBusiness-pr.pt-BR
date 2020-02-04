---
title: Remover o banco de dados do Servidor SQL de um servidor de Arquivamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a820780b7ca3646ba9fa6cc5d02a3c5022db9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Remover o banco de dados do Servidor SQL de um servidor de Arquivamento

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

Depois de remover um servidor de arquivamento do Microsoft Lync Server 2010, você pode remover os bancos de dados do SQL Server que hospedavam os dados do pool. Use os procedimentos a seguir para remover as definições do construtor de topologias e, em seguida, remover os arquivos de banco de dados e de log do servidor de banco de dados.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para remover o banco de dados do SQL Server usando o construtor de topologias

1.  No servidor front-end do Lync Server 2013, abra o construtor de topologias.

2.  No construtor de topologias, navegue até **componentes compartilhados** e, em seguida, **repositórios do SQL Server**, clique com o botão direito do mouse na instância do SQL Server associada ao servidor de arquivamento removido ou reconfigurado e clique em **excluir**.

3.  Publique a topologia e, em seguida, verifique o status de replicação.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para remover os arquivos de banco de dados do SQL Server

1.  Para remover os bancos de dados no SQL Server, você deve ser membro do grupo Administradores do SQL Server do SQL Server no qual está removendo os arquivos de banco de dados.

2.  Abra o Shell de gerenciamento do Lync Server.

3.  Na linha de comando, digite o seguinte:
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Onde \<FQDN\> é o nome de domínio totalmente qualificado (FQDN) do servidor de banco de \<dados\> e a instância é a instância do banco de dados nomeado (ou seja, se foi definida uma).

4.  Quando o cmdlet **Uninstall-CsDataBase** solicita que você confirme ações, leia as informações e, em seguida, pressione **Y** (ou pressione Enter) para continuar, ou pressione **N** e, em seguida, insira se você deseja parar o cmdlet (ou seja, em caso de erros).

</div>

</div>

<span> </span>

</div>

</div>

</div>

