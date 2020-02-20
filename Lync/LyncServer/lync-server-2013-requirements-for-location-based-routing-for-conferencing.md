---
title: 'Lync Server 2013: requisitos para roteamento baseado em local para conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ce41a338f3185f6f051da3df41e91c6b287af20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Requisitos para roteamento baseado em local para conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-19_

Estes são os requisitos necessários para a instalação e configuração do aplicativo de conferência de roteamento baseado em local:

  - A atualização cumulativa 2 do Lync Server 2013 deve ser implantada em todos os servidores ou pools da sua topologia.

<div>


> [!NOTE]  
> Se um servidor ou pool do Lync em sua topologia não tiver a atualização cumulativa 2 ou superior do Lync Server 2013 instalada, então a imposição do roteamento baseado em local das reuniões do Lync não poderá ser garantida.



</div>

  - Lync Server 2013 o roteamento baseado em local é um pré-requisito para aplicativo de conferência de roteamento baseado em local. Para obter mais informações sobre como configurar o roteamento baseado em local do Lync Server 2013, confira [Configurando o roteamento baseado em local](lync-server-2013-configuring-location-based-routing.md).

  - Os requisitos do aplicativo de conferência de roteamento baseado em local são os mesmos que os requisitos para o roteamento baseado em local do Lync Server 2013. Para obter mais informações, consulte [planejando o roteamento baseado em local](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Servidores com suporte

O aplicativo de conferência de roteamento baseado em local exige que a atualização cumulativa 2 do Lync Server 2013 seja implantada em todos os pools de front-end e servidores Standard Edition em sua topologia. Se o Lync Server 2013 atualização cumulativa 2 não estiver instalado em alguns servidores do Lync em sua topologia, as restrições de roteamento baseadas em local não poderão ser totalmente impostas em reuniões do Lync e transferências de chamadas consultivas.

A tabela a seguir identifica a combinação de funções de servidor e versões que dão suporte ao roteamento baseado em local.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Versão do pool de front-end</p></td>
<td><p>Versão do servidor de mediação</p></td>
<td><p>Com suporte</p></td>
</tr>
<tr class="even">
<td><p>Atualização cumulativa 2 do Lync Server 2013</p></td>
<td><p>Atualização cumulativa 2 do Lync Server 2013</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="odd">
<td><p>Atualização cumulativa 2 do Lync Server 2013</p></td>
<td><p>Atualização cumulativa 1 do Lync Server 2013</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Atualização cumulativa 2 do Lync Server 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Atualização cumulativa 2 do Lync Server 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Atualização cumulativa 1 do Lync Server 2013</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Não</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>Clientes com suporte

Os clientes do Lync que dão suporte ao roteamento baseado em local de reuniões do Lync são os mesmos clientes que dão suporte ao roteamento baseado em local do Lync Server 2013. Para obter mais informações, consulte [suporte de cliente e servidor para roteamento baseado em local](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Requisitos do servidor de mediação para transferências de chamadas consultivas

O aplicativo de conferência de roteamento baseado em local requer a implantação de servidores de mediação autônomos para impor restrições de roteamento com base no local em transferências de chamadas consultivas.

Para impor o roteamento baseado em local das transferências de chamadas consultivas, o servidor de mediação deve estar associado a apenas um ponto de servidor de mediação (ou seja, PBX, gateway SIP, etc.) em regiões de rede onde o roteamento baseado em local é necessário. Se outros servidores de mediação estiverem implantados na mesma região de rede, o par do servidor de mediação deverá estar associado a um servidor de mediação diferente. Este requisito é detalhado da seguinte maneira:

  - Servidor de mediação único por vários pontos de servidor de mediação quando uma transferência de chamada consultiva é roteada para um ponto de servidor de mediação por meio de um servidor de mediação configurado com vários troncos SIP para vários pares (ou seja, PBXs e gateways), o consultion a transferência de chamada é bloqueada para evitar o bypass de chamadas PSTN se a transferência de chamada consultiva é permitida por meio de alguns troncos SIP, mas não é permitida através de outros troncos SIP.
    
    Por exemplo, no caso de um único servidor de mediação servindo um ponto de servidor de mediação de gateway PSTN e um ponto de servidor de mediação PBX, o seguinte comportamento será observado:
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PSTN para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada para evitar o bypass de chamada PSTN.
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PBX no mesmo site (site 1) para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada mesmo que não se incorra em possíveis Tol PSTN l ignorando.

  - Servidores de mediação separados por ponto de servidor de mediação
    
    Quando uma transferência consultiva é direcionada para um ponto de servidor de mediação, a transferência consultiva será avaliada em relação ao ponto único do servidor de mediação atendido pelo servidor de mediação. A chamada será desativada ou permitida com base em seu potencial de incorrer em desvio de interchamada PSTN, independentemente de todos os outros pares de servidores de mediação no site, conforme eles são atendidos por servidores de mediação separados.
    
    Por exemplo, no caso de um servidor de mediação separado servindo um ponto de servidor de mediação de gateway PSTN e um ponto de servidor de mediação PBX, o seguinte comportamento será observado:
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PSTN para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada para evitar o bypass de chamada PSTN.
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PBX no mesmo site (site 1) para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será permitida, pois ela não incorrerá em um possível desvio de PSTN em potencial tendo.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Recursos não suportados pelo aplicativo de conferência de roteamento baseado em local

Os seguintes recursos não são suportados pelo aplicativo de conferência de roteamento baseado em local:

  - Conferência discada. O roteamento baseado em local não pode ser imposto para conferência discada. Qualquer solicitação de discagem para uma determinada conferência não será restringida pelo roteamento baseado em local, mesmo se o organizador da conferência for um usuário do Lync habilitado para roteamento baseado em local.

  - É recomendável não provisionar os números de acesso de conferência nas regiões onde as restrições de roteamento baseadas em local precisam ser impostas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

