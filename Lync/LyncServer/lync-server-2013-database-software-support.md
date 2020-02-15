---
title: Suporte para software de banco de dados do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da1ffd79ccfb652c0f853cb027577d477a14d33e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Suporte a software de banco de dados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-12-01_

O Lync Server 2013 oferece suporte aos seguintes sistemas de gerenciamento de banco de dados:

  - **Banco de dados back-end de um pool Front-end, banco de dados de arquivamento, banco de dados de monitoramento, banco de dados de chat persistente e banco de dados de conformidade**
    
      - Software de banco de dados corporativo do Microsoft SQL Server 2008 R2 (64-bit Edition). É recomendável executar adicionalmente o Service Pack mais recente.
    
      - Microsoft SQL Server 2008 R2 Standard (64-bit Edition). É recomendável executar adicionalmente o Service Pack mais recente.
    
      - Microsoft SQL Server 2012 Enterprise (64-bit Edition). É recomendável executar adicionalmente o Service Pack mais recente.
    
      - Microsoft SQL Server 2012 Standard (edição de 64 bits). É recomendável executar adicionalmente o Service Pack mais recente.

  - **Bancos de dados do servidor do Standard Edition e do servidor front-end**
    
      - Microsoft SQL Server 2012 Express (64-bit Edition). É recomendável executar adicionalmente o Service Pack mais recente.
        
        Oferecemos suporte para a aplicação de patch e atualização do Microsoft SQL Server em servidores front-end e servidores Standard Edition. No entanto, ao fazer qualquer tipo de atualização ou patch em servidores front-end, você deve considerar os requisitos de quorum. Para obter mais informações, consulte [atualizar ou atualizar servidores front-end no Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) e [topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > O Microsoft SQL Server 2012 Express (64-bit Edition) é instalado automaticamente pelo Lync Server 2013 em cada servidor Standard Edition e cada servidor de servidor front-end.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>O Lync Server 2013 não dá suporte à edição de 32 bits do SQL Server. Você deve usar a edição de 64 bits.</P>
> <LI>
> <P>O SQL Server Web Edition e o SQL Server Workgroup Edition não têm suporte. Você não pode usá-los com o Lync Server 2013.</P>
> <LI>
> <P>O Lync Server 2013 oferece suporte a espelhamento de banco de dados nativo.</P>
> <LI>
> <P>Para usar a função de servidor de monitoramento, você deve instalar o SQL Server Reporting Services.</P></LI></UL>



</div>

Em um pool de front-ends, o banco de dados back-end pode ser um único computador do SQL Server.

<div>


> [!IMPORTANT]  
> Se você colocar os bancos de dados do Lync Server com outros bancos de dados, é altamente recomendável avaliar todos os fatores que podem afetar a disponibilidade e o desempenho, além de garantir que, se um nó falhar, o nó restante poderá lidar com a carga. Para verificar os recursos de failover, é recomendável testar todos os cenários de failover.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Usando o espelhamento do SQL e o cluster SQL

O Lync Server 2013 oferece suporte ao uso de espelhamento de SQL ou de SQL para cada banco de dados do Lync Server. Você pode configurar facilmente o espelhamento do SQL com a ferramenta Construtor de topologia no Lync Server 2013. Para o cluster de failover do SQL, você deve usar o SQL Server para configuração.

O Lync Server 2013 oferece suporte a topologias de espelhamento do SQL e de cluster SQL para todas as implantações, incluindo implantações e organizações do Greenfield que tenham sido atualizadas de versões anteriores do Lync Server.

O suporte a clusters do SQL é para uma configuração ativa/passiva. Por motivos de desempenho, o nó passivo não deve ser compartilhado por nenhuma outra instância do SQL.

O suporte a seguir está incluído:

  - Clustering de failover de dois nós para o seguinte:
    
      - Microsoft SQL Server 2012 Standard (edição de 64 bits). É recomendável executar adicionalmente o Service Pack mais recente.
    
      - Microsoft SQL Server 2008 R2 Standard (64-bit Edition). É recomendável executar adicionalmente o Service Pack mais recente.

  - Clustering de failover de até dezesseis nós para o seguinte:
    
      - Microsoft SQL Server 2012 Enterprise (64-bit Edition). É recomendável executar adicionalmente o Service Pack mais recente.
    
      - Software de banco de dados corporativo do Microsoft SQL Server 2008 R2 (64-bit Edition). É recomendável executar adicionalmente o Service Pack mais recente.

Para obter mais informações sobre o espelhamento do SQL, consulte [back end Server High Availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md). Para obter detalhes sobre como implantar o cluster SQL, consulte [Configure SQL Server clustering for Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).

Para obter mais informações e práticas recomendadas para clustering de failover no SQL Server <http://technet.microsoft.com/library/hh231721.aspx>2012, consulte. Para clustering de failover no SQL Server 2008, <http://technet.microsoft.com/library/ms189134(v=sql.105).aspx>consulte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

