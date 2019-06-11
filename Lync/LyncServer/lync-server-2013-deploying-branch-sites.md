---
title: 'Lync Server 2013: Implantando sites de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c96a8c99b6f80e7e70f3129e502d33b93a73f42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>Implantando sites de filial no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Os usuários do site de filiais obtêm a maioria da funcionalidade do Lync Server 2013 do servidor no site central ao qual o site de filial está associado. Cada site de filial está associado a um site central de exatamente. Para fornecer chamadas de e para a rede telefônica pública comutada (PSTN), um site de filial pode conter qualquer um dos seguintes:

  - Um gateway PSTN e, possivelmente, um servidor meditação

  - Um tronco SIP

  - Uma infraestrutura de voz existente com um PBX (Private Branch Exchange)

  - Um aparelho de ramificação sobreviventes

  - Um servidor de ramificação sobreviventes

Os sites de filiais com um aparelho de ramificação sobreviventes ou um servidor de filiais sobreviventes são mais resistentes em tempo de falhas de rede de longa distância ou de locais centrais do que os sites de filiais sem uma dessas soluções. Por exemplo, em um site com um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes implantado, os usuários ainda poderão fazer e receber chamadas PSTN se a rede que conecta o site de filial ao site central estiver inativa. Outra maneira de obter resiliência de site de filial é usar um gateway PSTN ou um tronco SIP com uma implantação completa do Lync Server no site da filial.

Para obter detalhes sobre qual implantação de site de filial é ideal para sua organização, incluindo pré-requisitos e outras considerações de planejamento, consulte [planejando a conectividade PSTN no Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) e [planejando a resiliência de voz no site de filial no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) na documentação de planejamento.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Fornecendo conectividade de PSTN ao site da filial no Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Implantando Aplicativo ou Servidor de Filial Persistente com Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

