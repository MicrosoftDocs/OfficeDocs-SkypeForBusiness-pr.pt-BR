---
title: 'Lync Server 2013: estimando o uso e o tráfego de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7723a67b4cefb75218f01dde3603a100b54d40b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a>Estimando o uso de voz e o tráfego do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-08-07_

A ferramenta de planejamento do Microsoft Lync Server 2013 usa a métrica a seguir para estimar o tráfego de usuários em cada local e o número de portas necessárias para dar suporte a esse tráfego.

  - <span></span>  
    Para **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta

  - <span></span>  
    Para **Tráfego médio**, (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta

  - <span></span>  
    Para **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta

O número de portas, por sua vez, determina o número de servidores de mediação e gateways que serão necessários. Os gateways PSTN (rede telefônica pública comutada) que a maioria das organizações consideram implantando intervalo em tamanho de duas portas para até 960 portas. (Há até gateways maiores, mas eles são usados principalmente por provedores de serviços de telefonia.)

Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.

</div>

<span> </span>

</div>

</div>

</div>

