---
title: 'Lync Server 2013: visão geral do roteamento baseado em local para conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 863cd213fb28d3adeedc04a5d46e4310ea4cd83b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Visão geral do roteamento baseado em local para conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-19_

O aplicativo de conferência de roteamento baseado em local oferece ao Lync conferências um mecanismo para a prevenção de desvio de chamada PSTN. O aplicativo monitora conferências ativas e impõe restrições de roteamento com base no local com base no local dos usuários do Lync participando.

O aplicativo de conferência de roteamento baseado em local determina se o roteamento baseado em local deve ser aplicado em uma reunião do Lync se os seguintes critérios forem atendidos:

  - O organizador da reunião está habilitado para roteamento baseado em local. As restrições de roteamento com base no local serão aplicadas somente a conferências organizadas por usuários habilitados para roteamento baseado em local.

  - Pelo menos um participante de reunião é um ponto de extremidade PSTN. As restrições de roteamento com base no local são aplicáveis apenas para conferências que incluem pontos de extremidade PSTN.

  - O local de rede onde o gateway PSTN usado para fazer a ponte da conferência para o PSTN está localizado, bem como os sites de rede onde os organizadores e participantes estão se conectando.

O aplicativo de conferência de roteamento baseado em local impede a participação de usuários do Lync e pontos de extremidade PSTN de diferentes sites de rede para a mesma conferência. Se o organizador de uma reunião estiver habilitado para roteamento baseado em local, o aplicativo de conferência imporá as seguintes restrições:

  - Os pontos de extremidade que podem ingressar em uma reunião do Lync dependem dos pontos de extremidade que já ingressaram na conferência, e essa restrição é ajustada conforme os pontos de extremidade associados deixam e novos pontos de extremidade ingressam na conferência. Se os organizadores e participantes estiverem participando de uma reunião do Lync do mesmo local de rede, então um ponto de extremidade PSTN, outro participante do mesmo local de rede, outro participante de um site de rede diferente ou um participante de um site de rede desconhecido tem permissão para ingressar.

  - Se os organizadores e participantes estiverem participando da reunião de sites de rede diferentes ou desconhecidos, um ponto de extremidade PSTN não terá permissão para ingressar na reunião se a chamada PSTN ingresses de um tronco SIP habilitado para roteamento baseado em local.

  - Se os organizadores e participantes estiverem participando da reunião do mesmo local de rede e se houver participantes participando da mesma reunião da PSTN, um ponto de extremidade do Lync de um site de rede diferente não tem permissão para participar da reunião.

Essas restrições de roteamento com base no local de conferência são resumidas na tabela a seguir.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Usuário (s) em uma conferência em um determinado ponto</p></td>
<td><p>Usuário (s) com permissão para ingressar na conferência</p></td>
<td><p>Usuário (s) não autorizados a ingressar na conferência</p></td>
</tr>
<tr class="even">
<td><p>Usuário (s) do cliente VoIP do Lync de um único site de rede</p></td>
<td><p>Usuário de cliente VoIP do Lync do mesmo local de rede</p>
<p>Usuário de cliente VoIP do Lync de um site de rede diferente</p>
<p>Usuário de cliente VoIP do Lync de um site de rede desconhecido</p>
<p>Usuário do cliente do Lync VoIP federado</p>
<p>Usuário ingressando a partir de um ponto de extremidade PSTN</p></td>
<td><p>Nenhum</p></td>
</tr>
<tr class="odd">
<td><p>Usuário (s) do cliente VoIP do Lync de um site de rede desconhecido</p></td>
<td><p>Usuário de cliente VoIP do Lync de qualquer site</p>
<p>Usuário de cliente VoIP do Lync de um site desconhecido</p>
<p>Usuário do cliente do Lync VoIP federado</p></td>
<td><p>Ingresso de usuário por meio de um ponto de extremidade PSTN</p></td>
</tr>
<tr class="even">
<td><p>Usuários de cliente do Lync VoIP de diferentes locais de rede</p></td>
<td><p>Usuário de cliente VoIP do Lync de qualquer site de rede</p>
<p>Usuário de cliente VoIP do Lync de um site de rede desconhecido</p>
<p>Usuário do cliente do Lync VoIP federado</p></td>
<td><p>Ingresso de usuário por meio de um ponto de extremidade PSTN</p></td>
</tr>
<tr class="odd">
<td><p>Usuário (s) do cliente VoIP do Lync de um único site de rede e usuários ingressando de um ponto de extremidade PSTN</p></td>
<td><p>Usuário de cliente VoIP do Lync do mesmo local de rede</p></td>
<td><p>Usuário de cliente VoIP do Lync de um site de rede diferente</p>
<p>Usuário de cliente VoIP do Lync de um site de rede desconhecido</p>
<p>Usuário do cliente do Lync VoIP federado</p></td>
</tr>
</tbody>
</table>


Veja a seguir as características adicionais do aplicativo de conferência de roteamento baseado em local:

  - Quando um usuário não tem permissão para ingressar em uma conferência determinada por restrições de roteamento baseado em local, a chamada de usuários para a conferência será rejeitada e seu cliente do Lync relatará que a chamada não foi concluída ou terminou.

  - Um ponto de extremidade PSTN ingressando em uma conferência com enforces de roteamento baseado em local não será restrito a ingressar na conferência independentemente de seu estado se o ponto de extremidade ingressar por meio de um tronco que não está habilitado para roteamento baseado em local.

  - Um sistema PBX conectado a um servidor de mediação por meio de um tronco SIP que não faz chamadas de egresso à PSTN terá as mesmas impostas que os usuários do Lync localizados no mesmo local de rede onde o tronco SIP está definido. Por exemplo, um ponto de extremidade PSTN poderá ingressar em uma conferência com um usuário PBX e um usuário do Lync se eles estiverem localizados no mesmo local de rede; caso contrário, o ponto de extremidade PSTN não terá permissão para ingressar na conferência se o usuário do PBX estiver em um local de rede diferente do usuário do Lync.

</div>

<span> </span>

</div>

</div>

</div>

