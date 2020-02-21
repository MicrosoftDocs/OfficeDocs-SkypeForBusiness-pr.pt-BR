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
ms.openlocfilehash: 66cfdab2f59ca29022435a1f7863e8fce79075e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Distribuição de carga de conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Diferentemente de outras soluções de conferência dedicadas, a arquitetura do Lync Server é um modelo de hardware compartilhado. Isto significa que o mesmo hardware é compartilhado por muitos componentes de software, cada um dos quais suporta diferentes comunicações em tempo real. Cada tipo de comunicações em tempo real coloca cargas específicas sobre os servidores. Por exemplo, o servidor front-end pode executar os componentes de roteamento do protocolo SIP, aplicativos Web (como pesquisa do catálogo de endereços), serviço de webconferência, serviço de conferência A/V, aplicativos do Enterprise Voice (por exemplo, aplicativo de atendedor de conferência e aplicativo de grupo de resposta) e servidor de mediação. Um conjunto de bancos de dados no servidor front-end também fornece armazenamento e processamento para o usuário, contato, presença, conferência e dados de roteamento de voz. Com esse compartilhamento de hardware, os componentes, os serviços e os processos competem com os recursos de CPU e memória, dessa forma, as cargas de trabalho que não sejam de conferência não têm um impacto direto sobre a escala do servidor..

Em comparação com outras soluções de conferência baseadas em portas de hardware, a arquitetura de conferência do Lync Server é um modelo sem reserva. Quando um usuário agenda uma reunião, o Lync Server cria um registro no banco de dados de conferência, que armazena dados de conferência, mas não reserva nenhum recurso de hardware para a reunião agendada antes do tempo. Em vez disso, o Lync Server tem lógica de balanceamento de carga interna para alocar dinamicamente recursos de conferência em servidores front-end, de forma que distribua cargas igualmente entre todos os servidores front-end do pool. Isso provisiona e utiliza de forma eficaz os recursos de hardware, mas dificulta o fornecimento de suporte para as reuniões muito grandes (especialmente sem um planejamento adequado). Por exemplo, quando um pool do Lync Server 2013 está sendo executado próximo à sua capacidade máxima, cada servidor de front-end pode hospedar aproximadamente 125 reuniões de tamanho médio. Adicionar outra pequena reunião não seria um problema, mas adicionar uma reunião para 1000 os usuários seria um problema, pois os servidores de front-end provavelmente não seriam capazes de oferecer suporte a uma reunião grande, ao mesmo tempo que as outras reuniões de 125.

</div>

<span> </span>

</div>

</div>

</div>

