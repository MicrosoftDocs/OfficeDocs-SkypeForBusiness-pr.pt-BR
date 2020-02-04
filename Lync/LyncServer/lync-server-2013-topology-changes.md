---
title: 'Lync Server 2013: Alterações de topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4453a9b5b8a5fcd60eaad1e437fd4800caddfba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Alterações de topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

Os requisitos de topologia e as considerações para o Lync Server 2013 são diferentes dos requisitos para versões anteriores, conforme descrito nesta seção.

<div>

## <a name="new-front-end-pools-architecture"></a>Nova arquitetura de grupos de front-end

No Lync Server 2013, a arquitetura dos pools de front-end do Enterprise Edition foi alterada para uma arquitetura de sistema distribuído.

Com essa nova arquitetura, o banco de dados back-end não é mais o repositório de dados em tempo real em um pool. As informações sobre um determinado usuário são mantidas em três servidores front-end no pool. Para cada usuário, um servidor front-end atua como mestre para as informações do usuário e outros dois servidores front-end servem como réplicas. Se um servidor front-end for desligado, outro servidor front-end que seja servido como réplica será automaticamente promovido para Master.

Isso acontece nos bastidores, e os administradores não precisam saber quais servidores de front-end são os mestres para os quais os usuários. Essa distribuição de armazenamento de dados melhora o desempenho e a escalabilidade dentro do pool e elimina o único ponto de falha de um único servidor back-end.

O servidor back-end funciona como armazenamento de backup para dados de usuários e de conferências e também é o armazenamento principal para outros bancos de dados, como o banco de dados do grupo de resposta.

Esses aprimoramentos também significam que há alterações na maneira como você planeja e mantém seus pools. Recomendamos que todos os seus pools do front-end do Enterprise Edition incluam pelo menos três servidores front end para fornecer o número total de réplicas para as quais a arquitetura do pool de front-end foi desenvolvida. Além disso, você deve seguir determinados procedimentos ao adicionar servidores a um pool de front-end, remover servidores dele ou atualizar servidores. Para obter mais informações, consulte [topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

<div>

## <a name="server-role-topology-changes"></a>Alterações de topologia de função de servidor

Algumas funções de servidor executadas anteriormente em servidores separados agora são consolidadas na função de servidor front-end, permitindo que você economize em custos de hardware

  - No Lync Server 2013, o servidor de conferência A/V sempre é posicionado com o servidor front-end.

  - Os front-ends para monitoramento e arquivamento agora são sempre posicionados com o servidor front-end. Monitorar e arquivar cada um ainda exige um banco de dados back-end separado, que pode ser posicionado no mesmo servidor que o banco de dados back-end do pool de front-end, ou pode ser hospedado em servidores back-end separados.

  - O servidor de chat persistente agora é uma função de servidor. No Microsoft Lync Server 2010, o servidor de chat de grupo era um aplicativo confiável de terceiros para o Microsoft Lync Server 2010. No Lync Server 2013, a funcionalidade do servidor de chat persistente é implementada usando três novas funções de servidor:
    
      - **PersistentChatService:** Principais serviços de servidor de chat persistentes implementados como uma função de front-end
    
      - **PersistentChatStore:** Função de servidor back-end
    
      - **PersistentChatComplianceStore:** Função de servidor back-end para conformidade com o chat persistente

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

