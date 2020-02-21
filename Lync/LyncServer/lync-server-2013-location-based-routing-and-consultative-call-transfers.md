---
title: 'Lync Server 2013: roteamento baseado em local e transferências de chamadas consultivas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dff8b723889be65f26e2c04d7f6a594515bfd09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Roteamento baseado em local e transferências de chamadas consultivas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-31_

Além de aplicar o roteamento baseado em local às reuniões do Lync, o aplicativo de conferência de roteamento baseado em local impõe restrições de roteamento com base no local em transferências de chamadas consultivas que entram em pontos de extremidade PSTN. Uma transferência de chamada consultiva é estabelecida entre duas partes em que uma das partes transfere a chamada para um novo usuário. Por exemplo, um ponto de extremidade PSTN chama usuário A (Lync chamado). O usuário A determina que o usuário PSTN deve ser encaminhado para o usuário B (usuário do Lync). O usuário A coloca a chamada com o usuário PSTN em espera e chama o usuário B. o usuário B concorda em falar com o usuário PSTN. O usuário A transfere a chamada em espera para o usuário B.

**Fluxo de chamadas de transferência de chamadas consultivas**

![Roteamento baseado em local para o diagrama de conferência](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Roteamento baseado em local para o diagrama de conferência")

Quando um usuário habilitado para roteamento baseado em local inicia uma transferência de chamada consultiva de um ponto de extremidade PSTN (conforme mostrado na figura anterior), isso cria duas chamadas ativas, uma chamada entre o usuário PSTN e o usuário do Lync a e a outra entre o usuário do Lync e o usuário B do Lync. o comportamento a seguir é imposto pelo aplicativo de conferência de roteamento baseado em local:

  - Se o roteamento de tronco SIP, a chamada PSTN é autorizada a encaminhar novamente a chamada PSTN para o local de rede onde o usuário B do Lync (ou seja, destino da transferência) está localizado, a transferência de chamada será permitida; caso contrário, a transferência de chamadas consuldas será bloqueada. Essa autorização é executada com base no local da parte transferida que está no mesmo local de rede que o tronco SIP que está encaminhando a chamada ativa para o ponto de extremidade PSTN.

  - Se o tronco SIP de roteamento, a chamada PSTN de entrada não é autorizada a encaminhar chamadas para o local de rede onde a parte transferida (usuário B) está localizada ou a parte transferida está localizada em um site de rede desconhecido e, em seguida, a transferência de chamada consultiva para a PSTN o ponto de extremidade (ou seja, destino da transferência de chamada) será bloqueado.

A tabela a seguir descreve como as restrições de roteamento baseadas em local são aplicadas pelo aplicativo de conferência de roteamento baseado em local para transferências de chamadas consultivas. Embora os pontos de extremidade PBX não estejam diretamente associados a um site de rede, o tronco SIP ao qual o PBX está conectado pode ser atribuído a um local de rede. Portanto, o ponto de extremidade de PBX pode ser indiretamente associado a um site de rede.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Site de rede da parte transferida por chamada</p></td>
<td><p>Local de rede do destino da transferência de chamadas</p></td>
<td><p>Comportamento</p></td>
</tr>
<tr class="even">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>Usuário do Lync no mesmo local de rede (por exemplo, site 1)</p></td>
<td><p>A transferência consultiva será permitida</p></td>
</tr>
<tr class="odd">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>Usuário do Lync em diferentes sites de rede (por exemplo, site 2)</p></td>
<td><p>A transferência consultiva não será permitida</p></td>
</tr>
<tr class="even">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>Usuário do Lync em um site de rede desconhecido</p></td>
<td><p>A transferência consultiva não será permitida</p></td>
</tr>
<tr class="odd">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>Usuário do Lync federado</p></td>
<td><p>A transferência consultiva não será permitida</p></td>
</tr>
<tr class="even">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>Ponto de extremidade de PBX no mesmo site (ou seja, site 1)</p></td>
<td><p>A transferência consultiva será permitida</p></td>
</tr>
<tr class="odd">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>Ponto de extremidade de PBX em sites diferentes (por exemplo, site 2)</p></td>
<td><p>A transferência consultiva não será permitida</p></td>
</tr>
<tr class="even">
<td><p>Ponto de extremidade de PBX no mesmo site (ou seja, site 1)</p></td>
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>A transferência consultiva será permitida</p></td>
</tr>
<tr class="odd">
<td><p>Ponto de extremidade de PBX em um site diferente (ou seja, site 2)</p></td>
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>A transferência consultiva não será permitida</p></td>
</tr>
<tr class="even">
<td><p>Ponto de extremidade de PBX em qualquer site</p></td>
<td><p>Usuário do Lync no mesmo local de rede (por exemplo, site 1)</p></td>
<td><p>A transferência consultiva será permitida</p></td>
</tr>
<tr class="odd">
<td><p>Ponto de extremidade de PBX em qualquer site</p></td>
<td><p>Usuário do Lync em diferentes sites de rede (por exemplo, site 2)</p></td>
<td><p>A transferência consultiva será permitida</p></td>
</tr>
<tr class="even">
<td><p>Ponto de extremidade de PBX em qualquer site</p></td>
<td><p>Usuário do Lync em um site de rede desconhecido</p></td>
<td><p>A transferência consultiva será permitida</p></td>
</tr>
<tr class="odd">
<td><p>Ponto de extremidade de PBX em qualquer site</p></td>
<td><p>Usuário do Lync federado</p></td>
<td><p>A transferência consultiva será permitida</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

