---
title: Remover instâncias SQL Server e bancos de dados no Servidor Back-End
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
ms.openlocfilehash: 11439dd9fd339c3620b3e6288526459f45a2a542
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Remover instâncias SQL Server e bancos de dados no Servidor Back-End

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Você remove os bancos de dados e instâncias do Microsoft SQL Server após remover os servidores que executam o Lync Server 2010 que sejam dependentes deles ou após a reconfiguração dos servidores que executam o Lync Server 2010 para usar outro banco de dados. Você precisa executar o procedimento neste tópico quando desativar o SQL Server atual ou reconfigurar o servidor atual que executa o Lync Server 2010 de forma que ele processe os bancos de dados obsoletos ou indisponíveis.

Para remover os bancos de dados ou instâncias do servidor de arquivamento ou Monitoring Server, primeiro você deve remover a função de servidor. Da mesma forma, para remover as instâncias ou os bancos de dados do pool de front-end, você deve primeiro remover ou reconfigurar a função de servidor dependente. Esses procedimentos não fazem distinção entre bancos de dados posicionados ou instâncias separadas para servidores. Os procedimentos não são afetados pela colocação de bancos de dados.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Remover o banco de dados do Servidor SQL para um pool Front-End](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Remover banco de dados do SQL Server de um servidor de Monitoramento](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Remover o banco de dados do Servidor SQL de um servidor de Arquivamento](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

