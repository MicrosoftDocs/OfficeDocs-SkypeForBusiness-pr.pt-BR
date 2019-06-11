---
title: 'Lync Server 2013: Planejamento para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Planejamento para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-19_

As comunicações na maioria das organizações envolvem serviços e usuários que não estão dentro da sua rede interna. Esses serviços e usuários incluem funcionários que são temporários ou permanentemente externos, funcionários de organizações de clientes ou parceiros, pessoas que usam serviços de mensagens instantâneas (IM) públicas e clientes potenciais, parceiros e usuários anônimos convidados para reuniões e apresentações. Nesta documentação, essas pessoas são chamadas coletivamente como *usuários externos*.

Com o Microsoft Lync Server 2013, os usuários em sua organização podem usar mensagens instantâneas e presença para se comunicar com usuários externos, e podem participar de conferências de áudio/vídeo (A/V) e conferência via Web com seus funcionários externos e outros tipos de usuários externos. Você também pode dar suporte ao acesso externo de dispositivos móveis e do Enterprise Voice. Os usuários externos que não são membros da sua organização podem participar de reuniões do Lync Server 2013, permitindo participantes anônimos.

Para dar suporte à comunicação no firewall da sua organização, implante o servidor de borda do Lync Server 2013 na sua rede de perímetro (também conhecido como DMZ, zona desmilitarizada e sub-rede filtrada). O servidor de borda controla como os usuários de fora do firewall podem se conectar à sua implantação interna do Lync Server 2013. Ele também controla comunicações com usuários externos que se originam dentro do firewall.

Dependendo dos seus requisitos, você pode implantar um ou mais servidores de borda em um ou mais locais. Esta seção descreve os cenários de acesso de usuários externos no Lync Server 2013, e explica como planejar a topologia de borda e de proxy inversa.

<div>


> [!NOTE]  
> Embora você precise de um servidor de borda para dar suporte a acesso de usuário externo e de voz, esta seção enfoca o suporte para mensagens instantâneas, presença, conferência A/V, Federação, conferência via Web e Lync Mobile. Para obter detalhes sobre o suporte para Enterprise Voice, consulte <A href="lync-server-2013-planning-for-enterprise-voice.md">planejamento para Enterprise Voice no Lync Server 2013</A> na documentação de planejamento.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Alterações no Lync Server 2013 que afetam o planejamento do Servidor de Borda](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Requisitos do sistema para componentes de acesso de usuário externo para Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Visão geral de acesso de usuário externo no Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Compreendendo a descoberta automática no Lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Escolhendo uma topologia no Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Coleta de dados no Lync Server 2013](lync-server-2013-data-collection.md)

  - [Determinar requisitios de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Determinar firewall A/V externo e requisitos de porta para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Planejar certificados do Servidor de Borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Cenários de acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

