---
title: 'Lync Server 2013: tronco SIP do site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 161964bc7a183672323ac277eae4f3a7ce0d2b82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Tronco SIP do site de filial no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Em alguns casos, talvez seja necessário implementar o tronco SIP distribuído em sites de filial selecionados. Para determinar se um tronco SIP é necessário para um site de filial, revise as informações em [como implementar o tronco SIP no Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Para obter detalhes sobre as opções de topologia suportadas para implantação de troncos SIP em sites de filial, consulte [Branch-site resiliência Solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Análise de requisitos do tronco SIP do exemplo de site de filial

Quando você decidir implantar um tronco SIP de site de filial, precisará executar uma análise de custo específica do site. Por exemplo, uma empresa que tenha um site central em Redmond, Washington e um site de filial em Nova York, deve fazer uma análise para determinar se deve implementar um tronco SIP do site de Nova York para um provedor de serviços local.

Para determinar se um tronco SIP distribuído em Nova Iorque é uma opção com bom custo benefício, identifique quais números DID usarão o tronco SIP e analise o número de chamadas feitas de Nova Iorque para áreas diferentes de Redmond (425). Você pode ter cancelamento para o site de filial no site central. Por exemplo, o site central Redmond pode hospedar números para o site de filial de Nova York. Se o custo da implementação de um tronco SIP distribuído for menor do que o custo dessas chamadas, considere a implementação de um tronco SIP no site de filial de Nova York.

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>Outros requisitos de tronco SIP do site de filial

A opção entre uma implantação de um tronco SIP em vez de um gateway tem base na diferença entre as cobranças de PSTN de longa distância de cada opção. Se você implantar um tronco SIP de site de filial, também precisará determinar os requisitos de resiliência e largura de banda. Se o link entre seu site de filial e o site central for resistente e tiver largura de banda suficiente, você poderá implantar um tronco SIP ou um gateway. Não é necessário implantar um aparelho de filial persistente no site de filial. Se o link entre o seu site de filial e o site central não for resistente, implante um aparelho de filial persistente ou implante um servidor de filial persistente com um gateway ou tronco SIP no site de filial.

</div>

</div>

<span> </span>

</div>

</div>

</div>

