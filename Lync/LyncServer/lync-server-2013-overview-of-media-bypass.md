---
title: 'Lync Server 2013: visão geral do bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84c70cae521deebecf30e7c8ec6505b18e9842fa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Visão geral do bypass de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

O bypass de mídia é útil quando você deseja minimizar o número de servidores de mediação implantados. Geralmente, um pool de servidores de mediação será implantado em um site central, e ele controlará os gateways em sites de filiais. Habilitar o bypass de mídia permite que a mídia para chamadas PSTN de clientes em sites locais flua diretamente pelos gateways para estes sites. Os roteamentos de chamadas de saída do Lync Server 2013 e as políticas de voz corporativa devem ser configurados corretamente para que chamadas PSTN de clientes em um site de filial sejam roteadas para o gateway apropriado.

As redes Wi-Fi geralmente enfrentam uma maior perda de pacotes do que as redes com fio. A recuperação desta perda de pacotes não é algo que geralmente possa ser acomodado por gateways. Assim, recomendamos a avaliação da qualidade da rede Wi-Fi antes de determinar se o bypass deve estar habilitado para uma sub-rede sem fio. Há uma compensação na redução da latência contra a recuperação da perda de pacotes a considerar. RTAudio, um codec disponível para chamadas que não ignorem o Servidor de Mediação, é mais adequado para tratar da perda de pacotes.

Depois que a estrutura da sua empresa estiver no lugar certo, é simples planejar o bypass de mídia.

  - Se você possui uma topologia centralizada sem links WAN para sites de filiais, é possível habilitar o bypass de mídia global, pois é necessário um ajuste refinado.

  - Se você não tem uma topologia distribuída que consiste em uma ou mais regiões de rede e seus sites de filiais associados, determine o seguinte:
    
      - Se os seus colegas do Servidor de Mediação oferecem suporte aos recursos necessários para o bypass de mídia.
    
      - Quais sites em cada região de rede estão bem conectados.
    
      - Qual combinação de bypass de mídia e controle de admissão de chamada é adequada para sua rede.

Quando o bypass de mídia é habilitado, uma ID de bypass exclusiva é gerado automaticamente para uma região de rede e para todos os sites de rede sem limites de largura de banda nessa região. Os sites com limites de largura de banda na região e os sites conectados à região por links WAN com limites de largura de banda obtêm suas próprias IDs de bypass exclusivas.

Quando um usuário faz uma chamada para a PSTN, o servidor de mediação compara a ID de bypass da sub-rede do cliente com a ID de bypass da sub-rede do gateway. Se as duas IDs de bypass forem correspondentes, o bypass de mídia será usado na chamada. Se as IDs de bypass não corresponderem, a mídia para a chamada deve fluir pelo servidor de mediação.

Quando um usuário recebe uma chamada do PSTN, o cliente do usuário compara seu ID de bypass com aquele do gateway PSTN. Se as duas IDs de bypass corresponderem, a mídia fluirá diretamente do gateway para o cliente, ignorando o servidor de mediação.

Somente os clientes ou dispositivos do Lync 2010 ou posterior dão suporte a interações de bypass de mídia com um servidor de mediação.

<div>


> [!IMPORTANT]  
> Além de habilitar o bypass de mídia globalmente, é necessário habilitar o bypass de mídia individualmente em cada tronco PSTN. Se o bypass estiver habilitado globalmente, mas não estiver habilitado para um determinado tronco PSTN, o bypass de mídia não será invocado para qualquer chamada envolvendo aquele tronco PSTN. Além disso, quando o bypass de mídia é definido para <STRONG>Use Site and Region Information</STRONG> (Usar informações do site e da região) é necessário associar todas as sub-redes roteáveis com os sites nos quais estão localizadas. Se há sub-redes roteáveis dentro de um site no qual o bypass não é desejado, estas sub-redes devem ser agrupadas dentro de um novo site antes de habilitar o bypass de mídia. Fazer isso garantirá que as sub-redes não roteáveis sejam atribuídas com uma ID de bypass diferente.



</div>

<div>

## <a name="see-also"></a>Confira também


[Modos de bypass de mídia no Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Bypass de mídia e controle de admissão de chamadas no Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Requisitos técnicos para bypass de mídia no Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

