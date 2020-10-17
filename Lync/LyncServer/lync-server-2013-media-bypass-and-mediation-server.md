---
title: 'Lync Server 2013: bypass de mídia e servidor de mediação'
description: 'Lync Server 2013: bypass de mídia e servidor de mediação.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb005d3d52fa9e5a38fdf56a65dfcbd73616d87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556427"
---
# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Bypass de mídia e servidor de mediação no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

O bypass de mídia é um recurso do Lync Server que permite que um administrador configure o roteamento de chamadas para fluir diretamente entre o ponto de extremidade do usuário e o gateway PSTN (rede telefônica pública comutada) sem atravessar o servidor de mediação. O bypass de mídia melhora a qualidade da chamada reduzindo a latência, a tradução desnecessária, a possibilidade de perda de pacotes e o número de possíveis pontos de falha. Quando um site remoto sem um servidor de mediação estiver conectado a um site central por um ou mais links WAN com largura de banda restrita, o bypass de mídia reduzirá a necessidade de largura de banda habilitando a mídia de um cliente em um local remoto para fluir diretamente para seu gateway local, sem antes ter que fluir pelo link WAN para um servidor de mediação no site central Essa redução no processamento de mídia também complementa a capacidade do servidor de mediação de controlar vários gateways.

O bypass de mídia e o CAC (controle de admissão de chamadas) são mutuamente exclusivos. Se o bypass de mídia for empregado para uma chamada, o CAC não será executado para essa chamada. A pressuposição é que não há links com largura de banda restrita envolvida na chamada.

<div>

## <a name="see-also"></a>Confira também


[Controle de admissão de chamadas e servidor de mediação no Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Planejamento de bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

