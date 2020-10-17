---
title: 'Lync Server 2013: Implantando sites de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed57a78637639d5e6402f88b7909114f3aabce7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531288"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a>Implantando sites de filial no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Os usuários do site de filial obtêm a maior parte da funcionalidade do Lync Server 2013 do servidor no site central ao qual o site de filial está associado. Cada filial está associada a exatamente um local central. Para fazer chamadas de/para a PSTN (Rede Telefônica Pública Comutada), uma filial deve incluir qualquer um dos itens a seguir:

  - Um gateway PSTN e, possivelmente, um Servidor de Mediação

  - Um tronco SIP

  - Uma infraestrutura existente de voz com uma central privada de comutação telefônica (PBX)

  - Um aparelho de filial persistente

  - Um servidor de filial persistente

Os sites de filial com um aparelho de filial persistente ou servidor de filial persistente são mais resistentes em horários de falhas de rede de longa distância ou de site central do que os sites de filiais sem uma dessas soluções. Por exemplo, em um site com um aparelho de filial persistente ou um servidor de filial persistente implantado, os usuários ainda poderão fazer e receber chamadas PSTN se a rede que conecta o site de filial ao site central estiver desativada. Outra maneira de obter resiliência de site de filial é usar um gateway PSTN ou um tronco SIP com uma implantação do Lync Server em escala total no site de filial.

Para obter detalhes sobre qual implantação de site de filial é ideal para sua organização, incluindo pré-requisitos e outras considerações de planejamento, consulte [Planning for PSTN Connectivity in Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) e [Planning for Branch-site Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) na documentação de planejamento.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Fornecendo conectividade PSTN em um site de filial no Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

