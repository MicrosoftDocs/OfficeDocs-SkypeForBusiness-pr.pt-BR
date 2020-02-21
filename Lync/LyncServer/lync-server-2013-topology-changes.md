---
title: Alterações de topologia do Lync Server 2013
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
ms.openlocfilehash: ac7cf9fe1bdabcba4b0b5fc1134f1835407041a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Alterações de topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Os requisitos e as considerações de topologia para o Lync Server 2013 são diferentes das versões anteriores, conforme descrito nesta seção.

<div>

## <a name="new-front-end-pools-architecture"></a>Nova arquitetura de pools de front end

No Lync Server 2013, a arquitetura dos pools de front-ends Enterprise Edition foi alterada para uma arquitetura de sistemas distribuídos.

Com essa nova arquitetura, o banco de dados de backend não é mais o armazenamento de dados em tempo real no pool. Informações sobre um usuário específico são mantidas em três servidores de front end no pool. Para cada usuário, um servidor de front end age como o mestre das informações desse usuário, e os outros dois servidores de front end servem como réplicas. Se um servidor de front end cair, outro servidor de front end que servia como réplica será automaticamente promovido a mestre.

Isso acontece nos bastidores e os administradores não precisam saber quais servidores de front end são os mestres para quais usuários. Essa distribuição de armazenamento de dados melhora o desempenho e a escalabilidade dentro do pool e elimina o ponto único de falha de um único servidor back-end.

O servidor de back end serve como armazenamento de back up do usuário e dados de conferência, e também é o armazenamento principal de outros bancos de dados, como o banco de dados do Grupo de Resposta.

Essas melhorias também significam que há mudanças em como planejar e manter seus pools. Recomendamos que todos os pools de front-ends Enterprise Edition incluam pelo menos três servidores front-end, para fornecer o número total de réplicas para as quais a arquitetura do pool de front-ends foi projetada. Além disso, você deve seguir determinados procedimentos ao adicionar servidores a um pool de front-ends, remover servidores dele ou atualizar servidores. Para obter mais informações, consulte [topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

<div>

## <a name="server-role-topology-changes"></a>Alterações na topologia de função do servidor

Algumas funções de servidor que eram executadas antes em servidores separados são agora consolidadas na função de servidor de front end, permitindo economizar em custos de hardware

  - No Lync Server 2013, o servidor de conferência A/V é sempre colocado com o servidor front-end.

  - Os servidores de front end de Monitoramento e arquivamento são sempre colocados com o servidor de front end. O Monitoramento e arquivamento exigem, cada um deles, um banco de dados de backend separado, que pode ser colocado no mesmo servidor do banco de dados de backend do pool de front end, ou pode ser hospedado em servidores de backend separados.

  - O servidor de chat persistente agora é uma função de servidor. No Microsoft Lync Server 2010, o servidor de chat de grupo era um aplicativo confiável de terceiros para o Microsoft Lync Server 2010. No Lync Server 2013, a funcionalidade do servidor de chat persistente é implementada usando três novas funções de servidor:
    
      - **PersistentChatService:** Principais serviços do servidor de chat persistente implementados como função de front-end
    
      - **PersistentChatStore:** Função de servidor back-end
    
      - **PersistentChatComplianceStore:** Função de servidor back-end para conformidade de chat persistente

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

