---
title: 'Lync Server 2013: Componentes e topologias para Arquivamento'
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
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Componentes e topologias para Arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-09_

Se você quiser arquivar o conteúdo de mensagens instantâneas e de conferência do Lync Server 2013, poderá implementar o arquivamento no Lync Server.

<div>

## <a name="archiving-components"></a>Arquivar componentes

O recurso de arquivamento inclui os seguintes componentes:

  - **Agentes de arquivamento**. Os agentes de arquivamento (também conhecidos como agentes de coleta de dados unificados) são instalados e ativados automaticamente em cada pool Front-end e servidor Standard Edition. Embora o arquivamento dos agentes seja ativado automaticamente, nenhuma mensagem é realmente capturada até que o arquivamento seja habilitado e configurado apropriadamente.

  - **Armazenamento de dados do arquivamento**. O armazenamento de dados do Lync Server 2013 pode ser um dos seguintes:
    
      - Armazenamento do Exchange 2013. Se você habilitar a opção de integração do Microsoft Exchange, as caixas de correio do usuário hospedadas no servidor Exchange 2013 usam o armazenamento do Exchange 2013 para dados arquivados, mas somente se as caixas de correio tiverem sido colocadas no bloqueio in-loco.
    
      - Armazenamento do SQL Server. Se você tiver usuários na sua implantação que são hospedados no Lync Server 2013, poderá configurar bancos de dados de arquivamento que executam uma versão do SQL Server com suporte para habilitar o arquivamento para esses usuários.

O arquivamento também requer armazenamento de arquivos, mas o arquivamento usa o mesmo armazenamento de arquivos que os servidores front-end ou o servidor Standard Edition.

Para obter uma lista dos requisitos de hardware e software para arquivamento, consulte suporte a [hardware com suporte para o Lync server 2013](lync-server-2013-supported-hardware.md) e [para software do servidor e infraestrutura no Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) na documentação de suporte.

</div>

<div>

## <a name="supported-topologies"></a>Topologias suportadas

Implante o arquivamento em cada pool que tenha usuários que exijam suporte para arquivamento. O arquivamento é executado em servidores front-end nos pools do Enterprise Edition e em servidores Standard Edition. O armazenamento de dados de arquivamento pode ser o seguinte:

  - Integrado ao armazenamento do Exchange 2013

  - Implantado usando bancos de dados SQL Server separados

Se sua implantação do Exchange 2013 não incluir todos os usuários em sua implantação do Lync Server, você deve usar a integração do Microsoft Exchange para os usuários cujas caixas de correio são domésticas em servidores do Exchange 2013 e você deve implantar bancos de dados SQL Server separados para todos os outros Usuários do Lync a serem usados para arquivamento.

</div>

<div>

## <a name="supported-collocation"></a>Colocação compatível

O Lync Server 2013 oferece suporte a uma variedade de cenários de colocação, permitindo que você economize em custos de hardware executando vários componentes em um servidor (se você tiver uma pequena organização) ou para executar componentes individuais em servidores diferentes (se você tiver mais de um organização que precisa de escalabilidade e desempenho). Fatores de escalabilidade certamente devem ser considerados antes de você decidir se deseja posicionar componentes.

O arquivamento é implantado nos servidores front-end de um pool ou servidores Standard Edition. Para obter detalhes sobre os componentes que podem ser posicionados, consulte [colocação do servidor com suporte no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.

Se você usar bancos de dados individuais do SQL Server para arquivamento, em vez de ou além de integrar o armazenamento com o armazenamento do Exchange 2013, poderá posicionar o banco de dados de arquivamento com qualquer um dos seguintes:

  - Banco de dados de monitoramento

  - Banco de dados back-end de um pool de front-ends Enterprise Edition

<div>


> [!NOTE]  
> O servidor que estiver hospedando o banco de dados de arquivamento pode hospedar outros bancos de dados. No entanto, ao considerar colocar o banco de dados de arquivamento com outros bancos de dados, saiba que se você estiver arquivando as mensagens de muitos usuários, o espaço em disco necessário para o banco de dados de arquivamento poderá aumentar bastante. Por essa razão, não recomendamos a colocação do banco de dados de arquivamento no banco de dados back-end.



</div>

Se você colocar o banco de dados de arquivamento com o banco de dados de monitoramento, banco de dados back-end ou ambos, você pode usar uma única instância SQL para qualquer ou todos os bancos de dados ou pode usar uma instância SQL separada para cada banco de dados, com o seguinte Mas

  - Cada instância SQL pode conter apenas um único banco de dados back-end, um único banco de dados de monitoramento e um banco de dados de arquivamento único.

Para obter detalhes sobre a colocação de todas as funções de servidor e bancos de dados, consulte [colocação de servidor com suporte no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

