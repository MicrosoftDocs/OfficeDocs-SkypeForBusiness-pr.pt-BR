---
title: Controle de admissão de chamada com um gateway de PSTN de terceiros ou PBX
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09aae207844fed12c840918a533fb181ca36634e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>Controle de admissão de chamada no Lync Server 2013 com um gateway de PSTN de terceiros ou PBX

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

Este tópico descreve exemplos de como o controle de admissão de chamada (CAC) pode ser implantado no link entre a interface do gateway do Servidor de Mediação e um gateway PSTN ou PBX de terceiros.

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Caso 1: CAC entre o Servidor de Mediação e um gateway PSTN

O CAC pode ser implantado no link WAN da interface do gateway do Servidor de Mediação para um PBX de terceiros ou gateway PSTN.

**Caso 1: CAC entre o Servidor de Mediação e um gateway PSTN**

![Caso 1: CAC entre o gateway PSTN do servidor de mediação](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Caso 1: CAC entre o gateway PSTN do servidor de mediação")

Neste exemplo, o CAC é aplicado entre o servidor de mediação e um gateway PSTN. Se um usuário do cliente do Lync no site da rede 1 colocar uma chamada PSTN por meio do gateway PSTN no site de rede 2, a mídia fluirá pelo link de WAN. Portanto, duas verificações CAC são executadas para cada sessão PSTN:

  - Entre o aplicativo cliente do Lync e o servidor de mediação

  - Entre o servidor de mediação e o gateway PSTN

Isto funciona para as chamadas PSTN de entrada para um cliente no Local de Rede 1 e para chamadas PSTN de saída provenientes de um aplicativo cliente no Local de Rede 1.

<div>


> [!NOTE]
> Certifique-se de que a sub-rede do IP ao qual o gateway PSTN pertence está configurada e associada ao Local de Rede 2.<BR>Verifique se a sub-rede IP à qual as duas interfaces do servidor de mediação pertence está configurada e associada ao local de rede 1.<BR>Para obter detalhes, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associar uma sub-rede a um site de rede no Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Caso 2: CAC entre o servidor de mediação e um PBX de terceiros com ponto de terminação de mídia

Esta configuração é similar ao Caso 1. Nos dois casos, o servidor de mediação sabe qual dispositivo termina a mídia na extremidade oposta do link de WAN, e o endereço IP do gateway PSTN ou PBX com ponto de terminação de mídia (MTP) está configurado no servidor de mediação como o próximo nó.

**Caso 2: CAC entre o Servidor de Mediação e um PBX de terceiros com MTP**

![Caso 2: CAC entre o PBX do servidor de mediação com MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Caso 2: CAC entre o PBX do servidor de mediação com MTP")

Neste exemplo, o CAC é aplicado entre o servidor de mediação e o PBX/MTP. Se um usuário cliente do Lync no site de rede 1 colocar uma chamada PSTN por meio do PBX/MTP localizado no site de rede 2, a mídia fluirá pelo link de WAN. Portanto, para cada sessão PSTN duas verificações CAC são executadas:

  - Entre o aplicativo cliente do Lync e o servidor de mediação

  - Entre o servidor de mediação e o PBX/MTP

Isto funciona para ambas, chamadas PSTN de entrada para um cliente no Local de Rede 1 e chamadas PSTN de saída provenientes de um cliente no Local de Rede 1.

<div>


> [!NOTE]
> Certifique-se de que a sub-rede do IP à qual o MTP pertence está configurada e associada ao Local de Rede 2.<BR>Verifique se a sub-rede IP à qual as duas interfaces do servidor de mediação pertence está configurada e associada ao local de rede 1.<BR>Para obter detalhes, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associar uma sub-rede a um site de rede no Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Caso 3: CAC entre o servidor de mediação e um PBX de terceiros sem um ponto de terminação de mídia

O Caso 3 é um ligeiramente diferente dos dois primeiros. Se não houver MTP no PBX de terceiros, para uma solicitação de sessão de saída para o PBX de terceiros, o servidor de mediação não saberá onde a mídia será encerrada no limite do PBX. Nesse caso, a mídia flui diretamente entre o servidor de mediação e o dispositivo de ponto de extremidade de terceiros.

**Caso 3: CAC entre o Servidor de Mediação e um PBX de terceiros sem MTP**

![Caso 3: CAC entre o PBX do servidor de mediação sem MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Caso 3: CAC entre o PBX do servidor de mediação sem MTP")

Neste exemplo, se um usuário cliente do Lync no site da rede 1 colocar uma chamada para um usuário por meio do PBX, o servidor de mediação poderá executar o CAC verifica somente no trecho do proxy (entre o aplicativo cliente do Lync e o servidor de mediação). Como o servidor de mediação não tem informações sobre o dispositivo de ponto de extremidade enquanto a sessão está sendo solicitada, as verificações de CAC não podem ser executadas no link de WAN (entre o servidor de mediação e o ponto de extremidade de terceiros) antes do estabelecimento da chamada. No entanto, depois que a sessão for estabelecida, o servidor de mediação facilitará a contabilidade para a largura de banda usada no tronco.

Para chamadas originadas no ponto de extremidade de terceiros, as informações sobre esse dispositivo de ponto de extremidade estão disponíveis no momento da solicitação de sessão, e a verificação de CAC pode ser executada nos dois lados do servidor de mediação.

<div>


> [!NOTE]
> Certifique-se de que a sub-rede do IP à qual os dispositivos de ponto de extremidade pertencem está configurada e associada ao Local de Rede 2.<BR>Verifique se a sub-rede IP à qual as duas interfaces do servidor de mediação pertence está configurada e associada ao local de rede 1.<BR>Para obter detalhes, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associar uma sub-rede a um site de rede no Lync Server 2013</A>.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

