---
title: 'Lync Server 2013: acessando dados de monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aee3b01eaefa08bfa35ba7355debe347bc07ff0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a>Acessar dados de monitoramento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-05_

Os dados de monitoramento são armazenados em um par de bancos de dados SQL Server databases: LcsCdr para registro de detalhes das chamadas e QoEMetrics para dados sobre a qualidade da experiência. Não há nada de especial nesses dois bancos de dados, o que significa que os dados armazenados neles podem ser acessados por meio das ferramentas que você usa normalmente para acessar e analisar dados do SQL Server.

Uma ferramenta que você deve considerar para acessar e analisar dados de monitoramento são os relatórios de monitoramento do Lync Server. Os Relatórios de monitoramento são um conjunto de relatórios padrão publicados pelo Microsoft SQL Server Reporting Service. Esses relatórios, que podem ser acessados por meio de navegadores, fornecem informações de uso, diagnóstico de camada e qualidade de mídia, todos com base em registros de detalhes das chamadas call detail recording (CDR) e qualidade da experiência (QoE) armazenados nos bancos de dados de CDR e QoE. Os relatórios de monitoramento são fornecidos com o Lync Server 2013 e podem ser instalados a partir do assistente de implantação do Lync Server depois que o Lync Server tiver sido instalado e o monitoramento tiver sido configurado.

Os Relatórios de monitoreamente requerem o uso do SQL Server Reporting Service. O SQL Server Reporting Service pode ser instalado ao mesmo tempo que o SQL Server é instalado ou a qualquer momento após a instalação do próprio SQL Server.

Para obter mais informações, consulte o tópico [instalando os relatórios de monitoramento do Lync server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) no guia de implantação do lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

