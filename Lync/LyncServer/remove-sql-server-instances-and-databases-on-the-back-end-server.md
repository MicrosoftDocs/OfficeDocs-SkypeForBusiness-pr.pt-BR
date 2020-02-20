---
title: Remover instâncias e bancos de dados do SQL Server no servidor back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02aa65c631e62d7ffb699d85d982858164848c2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Remover instâncias e bancos de dados do SQL Server no servidor back-end

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Você remove os bancos de dados e instâncias do Microsoft SQL Server após remover os servidores que executam o Lync Server 2010 que são dependentes deles ou após a reconfiguração dos servidores que executam o Lync Server 2010 para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando você desativa o SQL Server atual ou reconfigura o servidor atual executando o Lync Server 2010 de forma que ele processe os bancos de dados obsoletos ou indisponíveis.

Para remover os bancos de dados ou instâncias do servidor de arquivamento ou do Monitoring Server, primeiro você deve remover a função de servidor. Da mesma forma, para remover as instâncias ou os bancos de dados do pool de front-ends, primeiro você deve remover ou reconfigurar a função de servidor dependente. Esses procedimentos não fazem distinção entre bancos de dados colocados ou instâncias separadas. Os procedimentos não são afetados pela colocação do banco de dados.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Remover o banco de dados do SQL Server para um pool de front-ends](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Remover o banco de dados do SQL Server de um servidor de monitoramento](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Remover o banco de dados do SQL Server para um servidor de arquivamento](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

