---
title: 'Lync Server 2013: Visão geral do tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e2c79261923456575e208aa472daae4aaab5f55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Visão geral do tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

A implantação de troncos SIP pode ser um grande passo para a simplificação das telecomunicações da sua organização e a preparação para as melhorias atuais nas comunicações em tempo real. Umas das principais vantagens do tronco SIP é que você pode consolidar as conexões da sua organização com a PSTN (Rede Telefônica Pública Comutada) em um local central, ao contrário de seu predecessor, o tronco TDM, que normalmente requer um tronco separado de cada filial.

<div>

## <a name="sip-trunking-in-lync-server"></a>Entroncamento SIP no Lync Server

Os recursos de entroncamento SIP do Lync Server 2013 permitem o seguinte:

  - Um usuário empresarial, dentro ou fora do firewall corporativo, pode fazer uma chamada local ou uma chamada de longa distância especificada por um número em conformidade com o E. 164 que é encerrado na PSTN como um serviço do provedor de serviços correspondente.

  - Qualquer assinante PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo, discando um número do Direct Inward Dialing (DID) associado a esse usuário da empresa.

</div>

<div>

## <a name="cost-savings"></a>Redução de custo

As reduções de custo associadas ao tronco SIP podem ser substanciais:

  - Geralmente, as chamadas de longa distância custam menos através de um tronco SIP.

  - Você pode cortar os custos de gerenciamento e reduzir a complexidade da implementação.

  - A interface de tarifa básica (BRI) e a interface de tarifa primária (PRI) podem ser eliminadas se você conectar um tronco SIP diretamente ao ITSP, por um custo significativamente inferior. Nos troncos TDM, os provedores de serviço cobram as chamadas por minuto. O custo do tronco SIP pode ser baseado no uso da largura de banda, e você pode comprar incrementos menores e mais econômicos. (O custo real depende do modelo de serviço do que você escolhe).

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Tronco SIP vs. hospedagem de um gateway PSTN ou IP-PBX

Uma vez que os troncos SIP se conectam diretamente ao provedor de serviço, você pode eliminar os seus gateways PSTN e seu custo de gerenciamento e complexidade. O uso de um tronco SIP pode levar a cortes substanciais no custo, através da manutenção e administração reduzida.

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>Serviços de VoIP expandidos

Os recursos de voz são frequentemente a principal motivação para implantar o tronco SIP, mas o suporte de voz é apenas a primeira etapa. Com o entroncamento SIP, você pode estender os recursos de VoIP e habilitar o Lync Server 2013 para fornecer um conjunto mais rico de serviços. Por exemplo:

  - A detecção de presença avançada para dispositivos que não estão executando o Lync Server 2013 pode oferecer uma melhor integração com telefones celulares, permitindo que você veja quando um usuário está em uma chamada de celular.

  - As chamadas de emergência E9-1-1 permitem que as autoridades que atendem às chamadas 911 determinem o local do chamador a partir do número de telefone.

<div>


> [!NOTE]  
> Consulte o ITSP para obter uma lista de serviços que eles suportam e podem habilitar para sua organização.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

