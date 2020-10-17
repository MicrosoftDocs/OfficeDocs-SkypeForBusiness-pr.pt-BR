---
title: 'Lync Server 2013: requisitos para roteamento de Location-Based para conferência'
description: 'Lync Server 2013: requisitos para roteamento de Location-Based para conferência.'
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
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542517"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Requisitos para Location-Based roteamento de conferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-19_

Estes são os requisitos necessários para a instalação e a configuração do aplicativo de conferência de roteamento de Location-Based:

  - A atualização cumulativa 2 do Lync Server 2013 deve ser implantada em todos os servidores ou pools da sua topologia.

<div>


> [!NOTE]  
> Se um Lync Server ou pool em sua topologia não tiver a atualização cumulativa 2 ou superior do Lync Server 2013 instalada, então a imposição de Location-Based roteamento de reuniões do Lync não poderá ser garantida.



</div>

  - Lync Server 2013 Location-Based o roteamento é um pré-requisito para Location-Based aplicativo de conferência de roteamento. Para obter mais informações sobre como configurar o roteamento Location-Based do Lync Server 2013, consulte [configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).

  - Os requisitos de Location-Based aplicativo de conferência de roteamento são os mesmos do Lync Server 2013 Location-Based roteamento. Para obter mais informações, consulte [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Servidores com suporte

O aplicativo de conferência de roteamento Location-Based requer que a atualização cumulativa 2 do Lync Server 2013 seja implantada em todos os pools de Front-End e servidores Standard Edition em sua topologia. Se o Lync Server 2013 atualização cumulativa 2 não estiver instalado em alguns servidores Lync em sua topologia, Location-Based restrições de roteamento não poderão ser totalmente impostas em reuniões do Lync e transferências de chamadas consultivas.

A tabela a seguir identifica a combinação de funções de servidor e versões que dão suporte ao roteamento Location-Based.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Front-End versão do pool</p></td>
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
<td><p>Qualquer</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Qualquer</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Qualquer</p></td>
<td><p>Não</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>Clientes com suporte

Os clientes do Lync que dão suporte Location-Based roteamento de reuniões do Lync são os mesmos clientes que dão suporte ao Lync Server 2013 Location-Based o roteamento. Para obter mais informações, consulte [suporte de cliente e servidor para roteamento Location-Based](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Requisitos do servidor de mediação para transferências de chamadas consultivas

O aplicativo de conferência de roteamento de Location-Based requer a implantação de servidores de mediação autônomos para impor restrições de roteamento Location-Based em transferências de chamadas consultivas.

Para impor Location-Based roteamento de transferências de chamadas consultivas, o servidor de mediação deve estar associado a apenas um ponto de servidor de mediação (ou seja, PBX, gateway SIP, etc.) em regiões de rede onde o roteamento de Location-Based é necessário. Se outros servidores de mediação estiverem implantados na mesma região de rede, o par do servidor de mediação deverá estar associado a um servidor de mediação diferente. Este requisito é detalhado da seguinte maneira:

  - Servidor de mediação único por vários pontos de servidor de mediação quando uma transferência de chamada consultiva é roteada para um ponto de servidor de mediação por meio de um servidor de mediação configurado com vários troncos SIP para vários pares (ou seja, PBXs e gateways), a transferência de chamadas consultivas é bloqueada para evitar troncos SIP, se a transferência de chamadas consultivas for
    
    Por exemplo, no caso de um único servidor de mediação servindo um ponto de servidor de mediação de gateway PSTN e um ponto de servidor de mediação PBX, o seguinte comportamento será observado:
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PSTN para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada para evitar o bypass de chamada PSTN.
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade de PBX no mesmo site (site 1) para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada mesmo que não se incorra em possíveis interurbanas PSTN.

  - Servidores de mediação separados por ponto de servidor de mediação
    
    Quando uma transferência consultiva é direcionada para um ponto de servidor de mediação, a transferência consultiva será avaliada em relação ao ponto único do servidor de mediação atendido pelo servidor de mediação. A chamada será desativada ou permitida com base em seu potencial de incorrer em desvio de interchamada PSTN, independentemente de todos os outros pares de servidores de mediação no site, conforme eles são atendidos por servidores de mediação separados.
    
    Por exemplo, no caso de um servidor de mediação separado servindo um ponto de servidor de mediação de gateway PSTN e um ponto de servidor de mediação PBX, o seguinte comportamento será observado:
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PSTN para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada para evitar o bypass de chamada PSTN.
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade de PBX no mesmo site (site 1) para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será permitida, pois ela não se incorrerá em um possível desvio de PSTN em potencial.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Recursos não suportados pelo aplicativo de conferência de roteamento Location-Based

Os seguintes recursos não são suportados pelo aplicativo de conferência de roteamento Location-Based:

  - Conferência discada. Location-Based roteamento não pode ser aplicado para conferência discada. Qualquer solicitação de discagem para uma determinada conferência não será restrita por Location-Based roteamento, mesmo que o organizador da conferência seja um usuário do Lync habilitado para o roteamento do Location-Based.

  - É recomendável não provisionar os números de acesso de conferência nas regiões onde Location-Based restrições de roteamento precisam ser impostas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

