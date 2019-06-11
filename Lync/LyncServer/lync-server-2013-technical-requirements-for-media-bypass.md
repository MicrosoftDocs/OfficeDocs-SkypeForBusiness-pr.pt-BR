---
title: 'Lync Server 2013: Requisitos técnicos para bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f59e0c025935ca8c2cd341549cdb58a44e7dbb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Requisitos técnicos para bypass de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Para cada chamada à PSTN, o servidor de mediação determina se a mídia do ponto de extremidade do Lync da origem pode ser enviada diretamente para um ponto do servidor de mediação sem percorrer o servidor de mediação. O par pode ser um gateway PSTN, um IP-PBX ou um SBC (Controlador de Borda de Sessão) em um ITSP (provedor de serviços de telefonia da Internet) associado ao tronco entre o Servidor de Mediação para o qual a chamada é roteada.

O bypass de mídia pode ser empregado quando os seguintes requisitos são atendidos:

  - Um peer do servidor de mediação deve dar suporte aos recursos necessários para o bypass de mídia, o mais importante é a capacidade de manipular várias respostas bifurcadas (conhecidas como "primeiras caixas de diálogo"). Contate o fabricante do seu gateway ou PBX ou seu ITSP para obter o valor do número máximo de caixas de diálogo iniciais que o gateway, o PBX ou o SBC pode aceitar.

  - O par do servidor de mediação deve aceitar o tráfego de mídia diretamente dos pontos de extremidade do Lync. Muitos ITSPs permitem que o SBC receba tráfego somente do servidor de mediação. Entre em contato com seu ITSP para determinar se o seu SBC aceita tráfego de mídia diretamente dos pontos de extremidade do Lync.

  - Os clientes do Lync e um peer do servidor de mediação devem ser bem conectados, o que significa que eles estão localizados na mesma região de rede ou em sites de rede que se conectam à região em links de WAN que não têm restrições de largura de banda

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

