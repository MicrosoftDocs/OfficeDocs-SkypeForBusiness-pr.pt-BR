---
title: 'Lync Server 2013: Suporte a software de banco de dados'
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
ms.openlocfilehash: d4c39a51f742266c12f618f687c23c645977ffdb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Suporte a software de banco de dados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-12-01_

O Lync Server 2013 é compatível com os seguintes sistemas de gerenciamento de banco de dados:

  - **Banco de dados Back-end de um pool de Front-End, banco de dados de Arquivamento, banco de dados de Monitoramento, banco de dados de chat persistente e banco de dados de conformidade do chat persistente**
    
      - Software do banco de dados do Microsoft SQL Server 2008 R2 Enterprise (edição de 64 bits). Além disso, executar o service pack mais atual é recomendado.
    
      - Microsoft SQL Server 2008 R2 Standard (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.
    
      - Microsoft SQL Server 2012 Enterprise (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.
    
      - Microsoft SQL Server 2012 Standard (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.

  - **Bancos de dados do servidor do servidor de front-end do Standard Edition**
    
      - Microsoft SQL Server 2012 Express (edição de 64 bits). A execução adicional do service pack mais recente é recomendada
        
        Oferecemos suporte para o patch e a atualização do Microsoft SQL Server em servidores front-end e servidores Standard Edition. No entanto, ao fazer qualquer tipo de atualização ou patch em servidores front end, você deve considerar os requisitos de quorum. Para mais informações, veja [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) e [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > O Microsoft SQL Server 2012 Express (64-bit Edition) é instalado automaticamente pelo Lync Server 2013 em cada servidor Standard Edition e cada servidor de servidor front-end.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>O Lync Server 2013 não é compatível com a edição de 32 bits do SQL Server. Você deve usar a edição de 64 bits.</P>
> <LI>
> <P>Não há suporte para SQL Server Web Edition e SQL Server Workgroup Edition. Você não pode usá-los com o Lync Server 2013.</P>
> <LI>
> <P>O Lync Server 2013 suporta o espelhamento de banco de dados nativo.</P>
> <LI>
> <P>Para usar a função de servidor de monitoramento, você deve instalar o SQL Server Reporting Services.</P></LI></UL>



</div>

Em um pool de front-ends, o banco de dados back-end pode ser um único computador SQL Server.

<div>


> [!IMPORTANT]  
> Se você colocar bancos de dados do Lync Server com outros bancos de dados, é altamente recomendável avaliar todos os fatores que podem afetar a disponibilidade e o desempenho, além de garantir que, se um nó falhar, o nó restante pode manipular a carga. Para verificar as capacidades de failover, recomendamos o teste de todos os cenários de failover.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Usando o espelhamento SQL e o cluster SQL

O Lync Server 2013 oferece suporte ao uso do SQL Mirroring ou do SQL clustering para cada banco de dados do Lync Server. Você pode configurar facilmente o espelhamento do SQL com a ferramenta Construtor de topologias no Lync Server 2013. Para o cluster de failover SQK, você deve usar o SQL Server para a configuração.

O Lync Server 2013 oferece suporte ao espelhamento do SQL e às topologias de cluster do SQL para todas as implantações, incluindo implantações e organizações do Greenfield que foram atualizadas a partir de versões anteriores do Lync Server.

O suporte do cluster SQL é para uma configuração ativa/passiva. Por motivos de desempenho, o nó passivo não deve ser compartilhado por nenhuma outra instância SQL.

O suporte a seguir é incluído:

  - Cluster de failover com dois nós para o seguinte:
    
      - Microsoft SQL Server 2012 Standard (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.
    
      - Microsoft SQL Server 2008 R2 Standard (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.

  - Cluster de failover com até 16 nós para o seguinte:
    
      - Microsoft SQL Server 2012 Enterprise (edição de 64 bits). Além disso, executar o service pack mais recente é recomendado.
    
      - Software do banco de dados do Microsoft SQL Server 2008 R2 Enterprise (edição de 64 bits). Além disso, executar o service pack mais atual é recomendado.

Para obter mais informações sobre o espelhamento do SQL, consulte [back-end Server High Availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md). Para obter detalhes sobre como implantar o SQL clustering, consulte [Configurar o cluster do SQL Server para o Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

Para obter mais informações e práticas recomendadas para cluster de failover no SQL Server 2012 <http://technet.microsoft.com/en-us/library/hh231721.aspx>, consulte. Para o cluster de failover no SQL Server 2008, <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>consulte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

