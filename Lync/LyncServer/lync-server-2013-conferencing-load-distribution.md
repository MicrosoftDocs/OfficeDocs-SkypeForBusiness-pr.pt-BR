---
title: Distribuição de carga de conferência do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baa8230470fc765bbda7c3b2bf49e6962b3db22f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Distribuição de carga de conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Ao contrário de outras soluções de conferência dedicadas, a arquitetura do Lync Server é um modelo de hardware compartilhado. Isso significa que o mesmo hardware é compartilhado por muitos componentes de software, cada um com suporte a diferentes comunicações em tempo real. Cada tipo de comunicação em tempo real coloca cargas específicas nos servidores. Por exemplo, o servidor front-end pode executar os componentes de roteamento do protocolo SIP, aplicativos Web (como a pesquisa no catálogo de endereços), serviço de webconferência, serviço de conferência A/V, aplicativos Enterprise Voice (por exemplo, aplicativo atendedor de conferência e aplicativo de grupo de resposta) e servidor de mediação. Um conjunto de bancos de dados no servidor front-end também fornece armazenamento e processamento para dados de usuário, contato, presença, conferência e roteamento de voz. Com esse recurso, o compartilhamento, os componentes, os serviços e os processos de hardware compete pelos recursos de CPU e de memória, as cargas de trabalho de não conferência têm um impacto direto no dimensionamento do servidor.

Em comparação com outras soluções de conferência baseadas em portas de hardware, a arquitetura de conferência do Lync Server é um modelo sem reserva. Quando um usuário agenda uma reunião, o Lync Server cria um registro no banco de dados de conferência, que armazena dados de conferência, mas não reserva nenhum recurso de hardware para a reunião agendada antes do tempo. Em vez disso, o Lync Server tem lógica de balanceamento de carga interna para alocar dinamicamente recursos de conferência em servidores front-end, de forma que distribua cargas igualmente em todos os servidores de front-end do pool. Isso efetivamente provisiona e utiliza recursos de hardware, mas torna difícil dar suporte a reuniões muito grandes (especialmente sem planejamento apropriado). Por exemplo, quando um pool do Lync Server 2013 está sendo executado próximo à sua capacidade máxima, cada servidor front-end pode hospedar aproximadamente 10 reuniões de tamanho médio de 125. Adicionar outra reunião pequena não seria problema, mas adicionar uma reunião para 1.000 usuários, sim, pois os Servidores Front-End provavelmente não seriam compatíveis com tal reunião grande ao mesmo tempo que as outras 125 reuniões.

</div>

<span> </span>

</div>

</div>

</div>

