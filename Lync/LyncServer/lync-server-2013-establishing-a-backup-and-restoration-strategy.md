---
title: 'Lync Server 2013: estabelecendo uma estratégia de backup e restauração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcdfbb6b51a966149451e8f396b345b0383947e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Estabelecendo uma estratégia de backup e restauração para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-26_

Antes de poder desenvolver um plano de backup e restauração para o Lync Server, você precisa desenvolver uma estratégia que se ajuste às metas da sua organização. Para desenvolver uma estratégia de backup e restauração eficaz, você precisará:

  - Estabelecer prioridades de negócios.

  - Identificar os requisitos de backup e restauração.

<div>

## <a name="establishing-business-priorities"></a>Estabelecer as prioridades comerciais

Avaliar as prioridades comerciais da sua organização. Geralmente, as prioridades comerciais primárias que afetam sua estratégia de backup e restauração são as seguintes:

  - Requisitos de continuidade comercial

  - Plenitude de dados

  - Criticidade de dados

  - Requisitos de portabilidade

  - Restrições de custo

Necessidades comerciais, como estas ajudam a determinar os contratos de nível de serviço (SLAs) que você desenvolve com seus clientes. Os contratos de nível de serviço influenciam muito sua estratégia de backup e recuperação.

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>Identificar os requisitos de backup e restauração

Suas prioridades de negócios e contratos de nível de serviço atuam na determinação dos requisitos de sua organização para o backup e a restauração do Lync Server. Identifique e documente seus requisitos para o seguinte:

  - **Frequência de backups**   para obter detalhes sobre as práticas recomendadas para frequência de backup, consulte [práticas recomendadas de backup e restauração para o Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **As ferramentas**   de backup e restauração incluem quem é usar as ferramentas e em quais computadores. Para obter detalhes sobre as ferramentas discutidas neste tópico e permissões necessárias, consulte [requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Local de backup**   identifique se os backups são mantidos local ou remotamente, levando a segurança e acessibilidade em consideração. Especifique a mídia a ser usada para os backups.

  - **Os requisitos**   de hardware e software identificam e documentam os requisitos específicos de hardware e software, incluindo o hardware para o armazenamento de backup e a restauração de componentes específicos e qualquer software e conectividade de rede necessários para dar suporte a backup e restauração. Conforme você desenvolve seus requisitos de hardware e software, lembre-se dos vários cenários de restauração a seguir.

  - **Cenários de restauração**   aqui estão os processos de restauração para os seguintes cenários:
    
      - Um pool do Lync Server falha. Este cenário exige a recompilação de cada servidor no pool.
    
      - Um servidor Standard Edition falha. Este cenário exige a recompilação do servidor em um computador novo ou limpo e a restauração dos bancos de dados.
    
      - Perda do repositório de gerenciamento central. No mínimo, esse cenário requer a restauração e publicação do repositório de gerenciamento central.
    
      - Perda de um servidor back-end quando o repositório de gerenciamento central ainda está funcionando normalmente. Este cenário exige a recompilação do servidor em um computador novo ou limpo e a restauração dos bancos de dados.
    
      - Um servidor que é membro de um pool do Lync Server falha. Este cenário exige a recompilação do servidor em um computador novo ou limpo.
    
      - Um repositório de arquivos falha. Este cenário exige a restauração do servidor de arquivos ou cluster de arquivos.
    
      - Um banco de dados de chat de arquivamento, monitoramento ou persistente falha. Este cenário exige a recriação dos bancos de dados e, se os dados são fundamentais para sua organização, restaurar os dados. Os dados de arquivamento, monitoramento e chat persistente não são necessários para fazer o backup e a execução do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

