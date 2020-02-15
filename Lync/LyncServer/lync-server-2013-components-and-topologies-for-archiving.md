---
title: 'Lync Server 2013: componentes e topologias para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a762219ef6cbecab47dcaeda313ff49dba51ed0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Componentes e topologias para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

Se você deseja arquivar o conteúdo de IM e conferência do Lync Server 2013, é possível implementar o arquivamento no Lync Server.

<div>

## <a name="archiving-components"></a>Componentes de arquivamento

O recurso de arquivamento inclui os seguintes componentes:

  - **Operadores de arquivamento**. Os operadores de arquivamento (também conhecido como operadores de coleta de dados unificados) são instalados e ativados automaticamente em cada pool de Front-Ends e servidor Standard Edition. Embora os operadores de arquivamento sejam ativados automaticamente, nenhuma mensagem será realmente capturada até o arquivamento ser habilitado e configurado adequadamente.

  - **Armazenamento de dados de arquivamento**. O armazenamento de dados do Lync Server 2013 pode ser um dos seguintes:
    
      - Armazenamento 2013 do Exchange. Se você habilitar a opção de integração do Microsoft Exchange, as caixas de correio do usuário hospedadas no servidor Exchange 2013 usam o armazenamento do Exchange 2013 para dados arquivados, mas somente se as caixas de correio foram colocadas em retenção in-loco.
    
      - Armazenamento do SQL Server. Se você tiver usuários na sua implantação hospedados no Lync Server 2013, poderá configurar bancos de dados de arquivamento que executam uma versão com suporte do SQL Server para habilitar o arquivamento para esses usuários.

O arquivamento também requer armazenamento de arquivos, mas o arquivamento utiliza o mesmo armazenamento de arquivos como servidores Front-End ou servidor Standard Edition.

Para obter uma lista de requisitos de hardware e software para arquivamento, consulte [hardware suportado para o Lync Server 2013](lync-server-2013-supported-hardware.md) e [suporte a infraestrutura e software do servidor no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) na documentação de suporte.

</div>

<div>

## <a name="supported-topologies"></a>Topologias suportadas

Você implanta o arquivamento em cada pool que possui usuários que requerem suporte ao arquivamento. O arquivamento é executado em servidores front-end em pools do Enterprise Edition e em servidores Standard Edition. O armazenamento de dados de arquivamento pode ser o seguinte:

  - Integrado ao armazenamento do Exchange 2013

  - Implantado usando bancos de dados do SQL Server separados

Se sua implantação do Exchange 2013 não inclui todos os usuários em sua implantação do Lync Server, você deve usar a integração do Microsoft Exchange para os usuários cujas caixas de correio estão em casa nos servidores do Exchange 2013 e você deve implantar bancos de dados do SQL Server separados para todos os outros Usuários do Lync a serem usados para arquivamento.

</div>

<div>

## <a name="supported-collocation"></a>Colocação suportada

O Lync Server 2013 oferece suporte a uma variedade de cenários de colocação, permitindo que você tenha flexibilidade para salvar os custos de hardware executando vários componentes em um servidor (se você tiver uma organização pequena) ou para executar componentes individuais em servidores diferentes (se você tiver um maior organização que precisa de escalabilidade e desempenho). Os fatores de escalabilidade certamente devem ser considerados antes de você decidir se quer colocar componentes.

O arquivamento é implantado nos servidores front-end de um pool ou servidores Standard Edition. Para obter detalhes sobre os componentes que podem ser colocados no local, consulte [suporte à colocação de servidor no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.

Se você usar bancos de dados separados do SQL Server para arquivamento, em vez de ou além de integrar o armazenamento com o armazenamento do Exchange 2013, poderá colocar o banco de dados de arquivamento com qualquer um dos seguintes:

  - Banco de dados de monitoramento

  - Banco de dados back-end de um pool de Front-Ends Enterprise Edition

<div>


> [!NOTE]  
> O servidor que estiver hospedando o banco de dados de arquivamento pode hospedar outros bancos de dados. No entanto, ao considerar colocar o banco de dados de arquivamento com outros bancos de dados, saiba que se você estiver arquivando as mensagens de muitos usuários, o espaço em disco necessário para o banco de dados de arquivamento poderá aumentar bastante. Por essa razão, não recomendamos a colocação do banco de dados de arquivamento no banco de dados back-end.



</div>

Se você colocar o banco de dados de arquivamento com o banco de dados de monitoramento, banco de dados back-end ou ambos, é possível utilizar uma instância SQL exclusiva para qualquer ou todos os bancos de dados ou uma instância SQL separada para cada banco de dados, com a seguinte limitação:

  - Cada instância SQL pode conter somente um banco de dados back-end exclusivo, um banco de dados de monitoramento exclusivo e um banco de dados de arquivamento exclusivo.

Para obter detalhes sobre a colocação de todas as funções de servidor e bancos de dados, consulte [supported Server Coexistence no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

