---
title: 'Lync Server 2013: planejamento para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3068cae2545c0d3f1df3f04935914d21d032ffc2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522178"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Planejamento para acesso de usuário externo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-19_

Muitas das comunicações na sua organização provavelmente envolvem pessoas fora do firewall: funcionários que estão temporariamente ou permanentemente fora do escritório, funcionários de clientes ou de organizações parceiras, pessoas que usam IMs (serviços de mensagens instantâneas) e clientes em potencial que você convida para reuniões e apresentações. Nesta documentação, essas pessoas são coletivamente chamadas de *usuários externos*.

Com o Microsoft Lync Server 2013, os usuários da sua organização podem usar IM e presença para se comunicar com usuários externos e podem participar de conferência de áudio/vídeo (A/V) e conferência via Web com seus funcionários externos e outros tipos de usuários externos. Também é possível suportar acesso externo de dispositivos móveis e sobre o Enterprise Voice. Usuários externos que não são membros de sua organização podem participar de reuniões do Lync Server 2013, permitindo participantes anônimos.

Para dar suporte à comunicação no firewall da sua organização, implante o servidor de borda do Lync Server 2013 em sua rede de perímetro (também conhecida como DMZ, zona desmilitarizada e sub-rede filtrada). O servidor de borda controla como os usuários fora do firewall podem se conectar à sua implantação interna do Lync Server 2013. Também controla as comunicações com os usuários externos originários dentro do firewall.

Dependendo de seus requisitos, é possível implantar um ou mais Servidores de Borda em um ou mais locais. Esta seção descreve cenários para acesso de usuário externo no Lync Server 2013 e explica como planejar a topologia de borda e de proxy reverso.

<div>


> [!NOTE]  
> Embora você precise de um servidor de borda para dar suporte ao acesso de usuário externo e do Enterprise Voice, esta seção se concentra em suporte para IM, presença, conferência A/V, Federação, Webconferência e Lync Mobile. Para obter detalhes sobre o suporte para o Enterprise Voice, consulte <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice no Lync Server 2013</A> na documentação de planejamento.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Alterações no Lync Server 2013 que afetam o planejamento do servidor de borda](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Requisitos do sistema para componentes de acesso de usuário externo para o Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Visão geral do acesso de usuário externo no Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Compreendendo a descoberta automática no Lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Escolhendo uma topologia no Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Coleta de dados no Lync Server 2013](lync-server-2013-data-collection.md)

  - [Determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Determinar firewall A/V externo e requisitos de porta para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Planejar certificados de servidor de borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

