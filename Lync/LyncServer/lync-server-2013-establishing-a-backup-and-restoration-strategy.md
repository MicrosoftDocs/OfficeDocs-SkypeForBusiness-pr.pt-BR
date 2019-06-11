---
title: 'Lync Server 2013: estabelecendo uma estratégia de backup e restauração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d378c66ae820ef0be7b7b3b0492b023863e977ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Como estabelecer uma estratégia de backup e restauração para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-26_

Antes de poder desenvolver um plano de backup e restauração para o Lync Server, você precisará desenvolver uma estratégia que se adapte às metas da sua organização. Para desenvolver uma estratégia eficaz de backup e restauração, será necessário:

  - Estabeleça prioridades de negócios.

  - Identifique os requisitos de backup e restauração.

<div>

## <a name="establishing-business-priorities"></a>Estabelecendo prioridades de negócios

Avaliar as prioridades comerciais da sua organização. Geralmente, as principais prioridades de negócios que afetam a estratégia de backup e restauração são as seguintes:

  - Requisitos de continuidade de negócios

  - Integridade dos dados

  - Criticalidade de dados

  - Requisitos de portabilidade

  - Restrições de custo

Necessidades comerciais, como estes ajudam a determinar os contratos de nível de serviço (SLAs) que você desenvolve com seus clientes. Contratos de nível de serviço influenciam bastante sua estratégia de backup e recuperação.

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>Identificar requisitos de backup e restauração

Suas prioridades de negócios e contratos de nível de serviço atuam para determinar os requisitos da sua organização para o backup e a restauração do Lync Server. Identifique e documente seus requisitos para o seguinte:

  - **Frequência de backups**   para obter detalhes sobre as práticas recomendadas para a frequência de backup, consulte [práticas recomendadas de backup e restauração do Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **As ferramentas**   de backup e restauração incluem quem deve usar as ferramentas e em quais computadores. Para obter detalhes sobre as ferramentas discutidas neste tópico e as permissões necessárias, consulte [requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Local de backup**   identifique se os backups são mantidos localmente ou remotamente, levando a segurança e acessibilidade em consideração. Especifique a mídia a ser usada para os backups.

  - **Os requisitos**   de hardware e software identificam e documentam seus requisitos específicos de hardware e software, incluindo o hardware para armazenamento de backup e restauração de componentes específicos e qualquer conectividade de software e rede necessária para suporte para backup e restauração. Ao desenvolver seus requisitos de hardware e software, tenha em mente os vários cenários de restauração que se seguem.

  - **Cenários de restauração**   aqui estão os processos de restauração dos seguintes cenários:
    
      - Um pool de servidores do Lync falha. Esse cenário requer a recriação de cada servidor no pool.
    
      - Um servidor Standard Edition falha. Esse cenário requer a recriação do servidor em um computador novo ou limpo e a restauração de bancos de dados.
    
      - Perda do repositório de gerenciamento central. No mínimo, esse cenário exige a restauração e a publicação do repositório de gerenciamento central.
    
      - Perda de um servidor back-end quando o repositório de gerenciamento central ainda estiver funcionando normalmente. Esse cenário requer a recriação do servidor em um computador novo ou limpo e a restauração de bancos de dados.
    
      - Um servidor que é membro de um pool do Lync Server falha. Esse cenário requer a recriação do servidor em um computador novo ou limpo.
    
      - Um repositório de arquivos falha. Esse cenário requer a restauração do servidor de arquivos ou do cluster de arquivos.
    
      - Falha em um banco de dados de arquivamento, monitoramento ou de chat persistente. Esse cenário exige a recriação de bancos de dados e, se os dados forem críticos para a sua organização, a restauração dos dados. O arquivamento, o monitoramento e os dados de chat persistentes não são necessários para ter backup e execução do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

