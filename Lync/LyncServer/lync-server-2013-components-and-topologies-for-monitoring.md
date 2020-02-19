---
title: 'Lync Server 2013: componentes e topologias para monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d93920040ff18d623748b375849f5639a831772a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Componentes e topologias para monitoramento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-05_

Como os agentes de coleta de dados unificados são instalados e ativados automaticamente em cada servidor de front-end, não é necessário configurar um servidor para atuar como o servidor de monitoramento; cada servidor de front-end já funciona como um servidor de monitoramento. No entanto, será necessário instalar e configurar um banco de dados para atuar como o armazenamento de dados de backend para seus dados de monitoramento. O Microsoft Lync Server 2013 pode usar qualquer um dos seguintes bancos de dados como o armazenamento de backend para monitoramento:

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Observe que você deve usar as edições de 64 bits desses bancos de dados; as versões de 32 bits do SQL Server não podem ser usadas como o armazenamento de backend para monitoramento. Da mesma forma, o Lync Server 2013 não é compatível com as edições Express do SQL Server 2008 ou SQL Server 2012. Para obter mais informações sobre os requisitos de banco de dados para o Lync Server 2013, consulte o tópico [suporte a software de banco de dados no Lync server 2013](lync-server-2013-database-software-support.md) no guia de suporte do lync Server 2013.

Tenha em mente que o SQL Server deve ser instalado e configurado antes de implantar e configurar o monitoramento. No entanto, você só precisa implantar o SQL Server em si; Você não precisa configurar os bancos de dados de monitoramento com antecedência. Em vez disso, esses bancos de dados serão criados automaticamente quando você publicar sua topologia do Lync Server.

Os dados de monitoramento podem compartilhar uma instância do SQL Server com outros tipos de dados. Normalmente, o banco de dados de registro de detalhes da chamada (LcsCdr) e o banco de dados de qualidade da experiência (QoEMetrics) compartilham a mesma instância do SQL; também é comum que os dois bancos de dados de monitoramento estejam na mesma instância SQL que o banco de dados de arquivamento (LcsLog). Sobre o único requisito real com instâncias do SQL Server é que qualquer instância do SQL Server está limitada à seguinte:

  - Uma instância do banco de dados de backend do Lync Server 2013. (Como regra geral, não é recomendável que seu banco de dados de monitoramento seja colocado na mesma instância SQL ou mesmo no mesmo computador, como banco de dados de back-end. Embora tecnicamente possível, você corre o risco de o banco de dados de monitoramento usar espaço em disco necessário para o banco de dados de back-end.

  - Uma instância do banco de dados de registro de detalhes das chamadas.

  - Uma instância do banco de dados de qualidade da experiência.

  - Uma instância do banco de dados de arquivamento.

Em outras palavras, não é possível ter duas instâncias do banco de dados LcsCdr na mesma instância do SQL Server. Se você precisar de várias instâncias do banco de dados do LcsCdr, será necessário configurar várias instâncias do SQL Server.

<div>

## <a name="see-also"></a>Confira também


[Implantando o monitoramento no Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

