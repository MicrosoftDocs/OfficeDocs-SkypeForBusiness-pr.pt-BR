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
ms.openlocfilehash: ac57a32476d80ab1aca5d2ad0928e2862a4c8558
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Requisitos para roteamento baseado em local para conferências no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-19_

Veja a seguir os requisitos necessários para a instalação e a configuração do aplicativo de conferência de roteamento baseado em localização:

  - A atualização cumulativa 2 do Lync Server 2013 deve ser implantada em todos os servidores ou pools na sua topologia.

<div>


> [!NOTE]  
> Se um servidor ou pool do Lync na sua topologia não tiver a atualização cumulativa 2 do Lync Server 2013 ou posterior instalada, a aplicação de roteamento baseado em local de reuniões do Lync não poderá ser garantida.



</div>

  - O roteamento baseado em localização do Lync Server 2013 é um pré-requisito para o aplicativo de conferência de roteamento baseado em localização. Para obter mais informações sobre como configurar o roteamento baseado em localização do Lync Server 2013, consulte [Configurando o roteamento baseado em local](lync-server-2013-configuring-location-based-routing.md).

  - Os requisitos do aplicativo de conferência de roteamento baseado em local são os mesmos que os requisitos para roteamento baseado em localização do Lync Server 2013. Para obter mais informações, consulte [planejando o roteamento baseado em local](lync-server-2013-planning-for-location-based-routing.md).

<div>

## <a name="supported-servers"></a>Servidores com suporte

O aplicativo de conferência de roteamento baseado em localização requer que a atualização cumulativa 2 do Lync Server 2013 seja implantada em todos os pools front-end e servidores Standard Edition na sua topologia. Se a atualização cumulativa 2 do Lync Server 2013 não estiver instalada em alguns servidores do Lync na topologia, as restrições de roteamento baseadas em local não poderão ser totalmente impostas em reuniões do Lync e transferências de chamadas consultivas.

A tabela a seguir identifica a combinação de funções de servidor e versões que dão suporte ao roteamento baseado em localização.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Versão do Pool de Front-End</p></td>
<td><p>Versão do Servidor de Mediação</p></td>
<td><p>Com suporte</p></td>
</tr>
<tr class="even">
<td><p>Atualização Cumulativa 2 do Lync Server 2013</p></td>
<td><p>Atualização Cumulativa 2 do Lync Server 2013</p></td>
<td><p>Sim</p></td>
</tr>
<tr class="odd">
<td><p>Atualização Cumulativa 2 do Lync Server 2013</p></td>
<td><p>Atualização Cumulativa 1 do Lync Server 2013</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Atualização Cumulativa 2 do Lync Server 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Atualização Cumulativa 2 do Lync Server 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Atualização Cumulativa 1 do Lync Server 2013</p></td>
<td><p>Qualquer um</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Qualquer um</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Qualquer um</p></td>
<td><p>Não</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>Clientes com suporte

Os clientes do Lync que dão suporte ao roteamento baseado em localização de reuniões do Lync são os mesmos clientes que dão suporte ao roteamento baseado em localização do Lync Server 2013. Para obter mais informações, consulte [suporte do cliente e do servidor para roteamento baseado em local](lync-server-2013-client-and-server-support-for-location-based-routing.md).

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>Requisitos do servidor de mediação para transferências de chamadas consultivas

O aplicativo de conferência de roteamento baseado em localização exige a implantação de servidores de mediação autônomos para impor restrições de roteamento baseado em localização em transferências de chamadas consultivas.

Para impor o roteamento baseado em local das transferências de chamadas consultivas, o servidor de mediação deve estar associado a apenas um par de servidor de mediação (isto é, PBX, gateway SIP etc.) nas regiões de rede onde o roteamento baseado em localização é necessário. Se os pares do servidor de mediação adicionais estiverem implantados na mesma região de rede, o par do servidor de mediação deve estar associado a um servidor de mediação diferente. Este requisito é detalhado da seguinte maneira:

  - Servidor de mediação único por vários pares de servidores de mediação quando uma transferência de chamadas consuldas é roteada para um servidor de mediação ponto a ponto por meio de um servidor de mediação configurado com vários troncos SIP para vários pares (ou seja, PBXs e gateways), consultoria a transferência de chamadas está bloqueada para evitar a interligação PSTN se a transferência de chamadas consuldas for permitida por meio de alguns troncos SIP, mas não por meio de outros troncos SIP.
    
    Por exemplo, no caso de um único servidor de mediação servindo um peer do servidor de mediação PSTN e um peer do servidor de mediação do PBX, o seguinte comportamento será observado:
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PSTN para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada para impedir que a chamada em PSTN seja ignorada.
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade do PBX no mesmo site 1 (site 1) para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada mesmo que não se incorra em uma possível PSTN Tol l ignorando.

  - Servidores de mediação separados por peer do servidor de mediação
    
    Quando uma transferência consultiva for direcionada a um peer do servidor de mediação, a transferência consultiva será avaliada em relação ao serviço de servidor de mediação único do servidor de mediação. A chamada será desautorizada ou permitida com base em seu potencial de incorrer em uma interligação de PSTN, independentemente de todas as outras mediações do servidor de mediação do site, pois elas são atendidas por servidores de mediação separados.
    
    Por exemplo, no caso de um servidor de mediação separado servindo um peer do servidor de mediação de gateway PSTN e um peer do servidor de mediação do PBX, o seguinte comportamento será observado:
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PSTN para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada para impedir que a chamada em PSTN seja ignorada.
    
      - Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade do PBX no mesmo site 1 (site 1) para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será permitida, pois ela não se incorrerá em uma possível bypass de chamada PSTN ndo.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Recursos que não são compatíveis com o aplicativo de conferência de roteamento baseado em localização

Os seguintes recursos não são compatíveis com o aplicativo de conferência de roteamento baseado em localização:

  - Conferência discada. O roteamento baseado em local não pode ser imposto para conferência discada. Qualquer solicitação de discagem para uma determinada conferência não será restringida por roteamento baseado em local, mesmo que o organizador de conferências seja um usuário do Lync habilitado para roteamento baseado em local.

  - Não é recomendável fornecer números de acesso à conferência nas regiões em que as restrições de roteamento baseadas em localização precisam ser impostas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

