---
title: 'Lync Server 2013: visão geral de tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbf29b02af831f82050e9a032a35f0fa57c1eb1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Visão geral do tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

A implantação de troncos SIP pode ser um grande passo para a simplificação das telecomunicações da sua organização e a preparação para os últimos aperfeiçoamentos nas comunicações em tempo real. Umas das principais vantagens de troncos SIP é que você pode consolidar as conexões da sua organização com a PSTN em um local central, ao contrário do seu anterior, o tronco TDM, que normalmente exige um tronco separado de cada local.

<div>

## <a name="sip-trunking-in-lync-server"></a>Tronco SIP no Lync Server

Os recursos de tronco SIP do Lync Server 2013 habilitam o seguinte:

  - Um usuário corporativo, dentro ou fora do firewall corporativo, pode fazer uma chamada local ou de longa distância especificada por um número compatível com o E.164 que seja terminado no PSTN como um serviço do provedor correspondente.

  - Qualquer assinante do PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo ao discar um número DID (Discagem Direta Interna) associado àquele usuário da empresa.

</div>

<div>

## <a name="cost-savings"></a>Redução de custo

As reduções de custo associadas ao tronco SIP podem ser substanciais:

  - Geralmente, as chamadas de longa distância custam menos através de um tronco SIP.

  - Você pode cortar os custos de gerenciamento e reduzir a complexidade da implementação.

  - A interface de tarifa básica (BRI) e a interface de tarifa primária (PRI) podem ser eliminadas se você conectar um tronco SIP diretamente ao ITSP, por um custo significativamente inferior. Nos troncos TDM, os provedores de serviço cobram as chamadas por minuto. O custo do tronco SIP pode ser baseado no uso da largura de banda, e você pode comprar incrementos menores e mais econômicos. (O custo real depende do modelo de serviço do que você escolhe).

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Tronco SIP versus hospedagem de um gateway PSTN ou IP-PBX

Uma vez que os troncos SIP se conectam diretamente ao provedor de serviço, você pode eliminar os seus gateways PSTN e seu custo de gerenciamento e complexidade. O uso de um tronco SIP pode levar a cortes substanciais no custo, através da manutenção e administração reduzida.

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>Serviços de VoIP expandidos

Os recursos de voz são frequentemente o principal motivo para implantar o tronco SIP, mas o suporte de voz é apenas a primeira etapa. Com o tronco SIP, você pode estender os recursos de VoIP e habilitar o Lync Server 2013 para fornecer um conjunto de serviços mais avançado. Por exemplo:

  - A detecção de presença avançada para dispositivos que não estão executando o Lync Server 2013 pode fornecer uma melhor integração com telefones celulares, permitindo que você veja quando um usuário está em uma chamada de telefone celular.

  - As chamadas de emergência E9-1-1 permitem que as autoridades que atendem ao 911 determinem a localização do chamador a partir do número do telefone.

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

