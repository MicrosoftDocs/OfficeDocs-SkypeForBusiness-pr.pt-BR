---
title: 'Lync Server 2013: requisitos técnicos para bypass de mídia'
description: 'Lync Server 2013: requisitos técnicos para bypass de mídia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee594139031966342fcec2bc1296a603055b4cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559437"
---
# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Requisitos técnicos para bypass de mídia no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Para cada chamada à PSTN, o servidor de mediação determina se a mídia do ponto de origem do Lync pode ser enviada diretamente para um ponto de servidor de mediação sem atravessar o servidor de mediação. O par pode ser um gateway PSTN, um IP-PBX ou um SBC (Controlador de Borda de Sessão) em um ITSP (provedor de serviços de telefonia da Internet) associado ao tronco entre o Servidor de Mediação para o qual a chamada é encaminhada.

O desvio de mídia pode ser empregado quando os seguintes requisitos são atendidos:

  - Um ponto de servidor de mediação deve suportar os recursos necessários para o bypass de mídia, o mais importante é a capacidade de lidar com várias respostas bifurcadas (conhecidas como "caixas de diálogo iniciais"). Contate o fabricante do seu gateway ou PBX ou seu ITSP para obter o valor do número máximo de caixas de diálogo iniciais que o gateway, o PBX ou o SBC pode aceitar.

  - O ponto do servidor de mediação deve aceitar o tráfego de mídia diretamente dos pontos de extremidade do Lync. Muitos ITSPs permitem que o SBC receba tráfego apenas do servidor de mediação. Entre em contato com seu ITSP para determinar se o SBC aceita tráfego de mídia diretamente dos pontos de extremidade do Lync.

  - Os clientes do Lync e um par de servidor de mediação devem estar bem conectados, o que significa que eles estão localizados na mesma região de rede ou em sites de rede que se conectam à região em links WAN que não têm restrições de largura de banda

<div>

## <a name="see-also"></a>Confira também


[Modos de bypass de mídia no Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Bypass de mídia e controle de admissão de chamadas no Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

