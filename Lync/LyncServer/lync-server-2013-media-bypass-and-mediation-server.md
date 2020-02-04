---
title: 'Lync Server 2013: Bypass de mídia e Servidor de Mediação'
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
ms.openlocfilehash: bf57bd94925ef5337656afc1b7cf4aa1ebc8ab17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Bypass de mídia e Servidor de Mediação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

O bypass de mídia é um recurso do Lync Server que permite que um administrador configure o roteamento de chamadas para fluir diretamente entre o ponto de extremidade do usuário e o gateway PSTN (rede telefônica pública comutada) sem atravessar o servidor de mediação. O bypass de mídia melhora a qualidade da chamada reduzindo a latência, a tradução desnecessária, a possibilidade de perda de pacotes e a quantidade de pontos de falha em potencial. Quando um site remoto sem um servidor de mediação está conectado a um site central por um ou mais links de WAN com largura de banda restrita, o bypass de mídia reduz a necessidade de largura de banda habilitando a mídia de um cliente em um site remoto para fluir diretamente para seu gateway local sem Primeiro, é necessário fluir pelo link de WAN para um servidor de mediação no site central e para trás. Essa redução no processamento de mídia também complementa a capacidade do servidor de mediação de controlar vários gateways.

O bypass de mídia e o CAC (controle de admissão de chamadas) são mutuamente exclusivos. Se o bypass de mídia for empregado para uma chamada, o CAC não será executado para essa chamada. Presume-se que não haja links com largura de banda restrita envolvidos na chamada.

<div>

## <a name="see-also"></a>Confira também


[Controle de admissão de chamada e Servidor de Mediação no Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Planejamento de bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

