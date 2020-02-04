---
title: 'Lync Server 2013: Processo de implantação para Roteamento Baseado em Local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e09106bc9d96fbfab2935aec07f3c472f49d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Processo de implantação para Roteamento Baseado em Local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-09_

Este tópico fornece uma visão geral do processo envolvido na configuração de roteamento baseado em localização. Você deve implantar o Lync Server Enterprise Edition ou Standard Edition com o Enterprise Voice antes de configurar o roteamento baseado no local. Os componentes exigidos pelo roteamento baseado em local já estão instalados e habilitados quando você implanta o Enterprise Voice.

### <a name="location-based-routing-deployment-process"></a>Processo de implantação de roteamento baseado em localização

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Grupos e funções necessários</th>
<th>Documentação de Implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Implantar o Enterprise Voice</p></td>
<td><ul>
<li><p>Configurar troncos</p></li>
<li><p>Criar políticas de voz</p></li>
<li><p>Definir roteiros de voz</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Implantação do Enterprise Voice</p></td>
</tr>
<tr class="even">
<td><p>Verificar a implantação do Enterprise Voice</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Configurar regiões de rede, sites e sub-redes</p></td>
<td><ul>
<li><p>Criar regiões de rede</p></li>
<li><p>Criar sites de rede</p></li>
<li><p>Associa sub-redes a sites de rede</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Sobre regiões de rede, sites e sub-redes<br />
Criar ou modificar uma região de rede<br />
Criar ou modificar um site de rede<br />
Associar uma sub-rede a um site de rede</p></td>
</tr>
<tr class="even">
<td><p>Configurar o roteamento baseado no local</p></td>
<td><ul>
<li><p>Criar políticas de roteamento de voz</p></li>
<li><p>Definir configuração de tronco separada por tronco</p></li>
<li><p>Modificar políticas de voz</p></li>
<li><p>Habilitar a configuração de roteamento baseado em localização</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>Exemplo de implantação

A implantação a seguir é usada para ilustrar mais os mecanismos habilitados pelo roteamento baseado em local.

![e1bd2230-44da-4784-B359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-B359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>Chamadas PSTN recebidas

Um administrador pode habilitar o tronco definido para direcionar chamadas para "gateway do site 1" para roteamento baseado em local e associar o "gateway do site 1" ao site 1. Uma vez habilitada, as chamadas roteadas pelo "gateway do site 1" só serão roteadas para os usuários localizados no site 1. Todas as chamadas roteadas pelo tronco "gateway do site 1" destinados a usuários em um site diferente, como o site 2 serão bloqueadas para impedir o bypass de chamada PSTN.

Todas as chamadas PSTN de entrada por meio do "gateway do site 1" só poderão ser roteadas para pontos de extremidade localizados no site 1. Por exemplo, quando "usuário do Lync 1" viaja para o site 2, todas as chamadas PSTN de entrada por meio do "gateway do site 1" não serão roteadas para os pontos de extremidade "usuário do Lync 1" localizado no site 2. A mesma regra de roteamento se aplica se "usuário do Lync 1" viajar para um site de rede desconhecido onde a localização do usuário não pode ser determinada.

A tabela a seguir descreve a experiência do usuário do "usuário do Lync 1" nesse contexto.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Pontos de extremidade de usuário 1 do Lync localizados no site de rede 1</th>
<th>Pontos de extremidade de usuário 1 do Lync localizados no site de rede 2</th>
<th>Pontos de extremidade de usuário 1 do Lync localizados em um site de rede desconhecido</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas PSTN de entrada para o usuário 1 do Lync</p></td>
<td><p>As chamadas são roteadas para pontos de extremidade neste local</p></td>
<td><p>As chamadas não são roteadas para pontos de extremidade neste local</p></td>
<td><p>As chamadas não são roteadas para pontos de extremidade neste local</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>Chamadas PSTN de saída

As rotas de voz são referenciadas em políticas de voz atribuídas diretamente a usuários e políticas de roteamento de voz atribuídas a sites de rede. Ambas as políticas contêm referências a rotas, que podem ser usadas para direcionar uma chamada de maneira diferente. Por exemplo, um administrador pode definir uma política de roteamento de voz para todos os usuários localizados no site 1 de rede para direcionar todas as chamadas feitas por meio do "gateway do site 1" enquanto a política de voz de alguns usuários define uma rota para todas as chamadas feitas por meio do "gateway 2 do site". Enquanto esses usuários estão localizados no site da rede 1, suas chamadas de saída serão roteadas pelo "gateway do site 1".

Quando um usuário está localizado em um site de rede configurado para roteamento baseado em local, a rota da política de roteamento de voz do site da rede substitui a rota de política de voz do usuário. Essa regra é particularmente útil para os usuários que se movem temporariamente para um site diferente. Nesse caso específico, um usuário sempre usará um gateway local para o seu local; Se o "usuário do Lync 3" estiver localizado em "site 2", todas as suas chamadas serão roteadas pelo "gateway do site 2", mas se ele viajar para o site 1, todas as suas chamadas feitas durante o site 1 serão roteadas pelo "gateway do site 1".

A tabela a seguir ilustra a experiência do usuário do Lync usuário 1 fazendo uma chamada de saída dos seguintes sites de rede.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Site de rede 1</th>
<th>Site de rede 2</th>
<th>Site de rede desconhecido ou não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorização de chamadas de saída</p></td>
<td><p>Política de voz do usuário 1 do Lync</p></td>
<td><p>Política de voz do usuário 1 do Lync</p></td>
<td><p>Política de voz do usuário 1 do Lync</p></td>
</tr>
<tr class="even">
<td><p>Roteamento de chamadas de saída</p></td>
<td><p>Política de roteamento de voz do site 1</p></td>
<td><p>Política de roteamento de voz do site 2</p></td>
<td><p>Política de voz do usuário e somente para sistemas não habilitados para roteamento baseado em local</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>Transferências de chamadas e encaminhamentos

Quando as chamadas são transferidas ou encaminhadas, o roteamento de chamadas é afetado pelo roteamento baseado em local.

A tabela a seguir descreve o usuário do Lync 1 transferindo ou encaminhando uma chamada PSTN para outro usuário do Lync.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Usuário Iniciando transferência ou encaminhamento de chamadas</th>
<th>Usuário do Lync 2</th>
<th>Usuário do Lync 4</th>
<th>Usuário do Lync no site de rede não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuário 1 do Lync</p></td>
<td><p>Encaminhamento ou transferência de chamada permitido</p></td>
<td><p>Encaminhamento ou transferência de chamada não permitido</p></td>
<td><p>Encaminhamento ou transferência de chamada não permitido</p></td>
</tr>
</tbody>
</table>

  
A tabela a seguir ilustra como o roteamento baseado em localização afeta a forma como a chamada é roteada com base no local do usuário do Lync que está sendo transferido (usuário do Lync 2, usuário do Lync 4 etc) para um ponto de extremidade PSTN


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ponto de extremidade onde a chamada é transferida ou encaminhada para</th>
<th>Usuário do Lync 2</th>
<th>Usuário do Lync 4</th>
<th>Usuário do Lync no site de rede não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>Encaminhamento de chamadas ou transferência é roteada pela política de roteamento de voz do site 1 e egresso pelo gateway do site 1</p></td>
<td><p>Encaminhamento de chamadas ou transferência é roteada pela política de roteamento de voz do site 2 e egresso via gateway do site 2</p></td>
<td><p>Encaminhamento de chamadas ou transferência é roteada pela política de voz do usuário do Lync e egresso por meio de um gateway não habilitado para roteamento baseado em local (se disponível)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>Toque simultâneo

Quando o roteamento baseado em local está configurado na topologia de exemplo, as seguintes interações são impostas.

A tabela a seguir ilustra se o roteamento baseado em localização permite o toque simultâneo para diferentes usuários do Lync (ou seja, usuário do Lync 2, usuário do Lync 4, etc).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino da chamada PSTN de entrada</th>
<th>Usuário do Lync 2</th>
<th>Usuário do Lync 4</th>
<th>Usuário do Lync no site de rede não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuário 1 do Lync</p></td>
<td><p>O toque simultâneo é permitido</p></td>
<td><p>O toque simultâneo não é permitido</p></td>
<td><p>O toque simultâneo não é permitido</p></td>
</tr>
</tbody>
</table>

  
A tabela a seguir ilustra se o roteamento baseado em localização permite o toque simultâneo para um ponto de extremidade PSTN de diferentes usuários do Lync (ou seja, usuário do Lync 2, usuário do Lync 4, etc).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de toque simultâneo</th>
<th>Usuário do Lync 2</th>
<th>Usuário do Lync 4</th>
<th>Usuário do Lync no site de rede não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Telefone celular usuário 1 do Lync (ponto de extremidade PSTN)</p></td>
<td><p>Chamada roteada pela política de roteamento de voz do site 1 e egresso por meio do gateway do site 1</p></td>
<td><p>Chamada roteada pela política de roteamento de voz do site 2 da rede e egresso via gateway do site 2</p></td>
<td><p>Chamada roteada pela política de voz do chamador e será egresso por meio de um gateway PSTN não habilitado para roteamento baseado em local</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de Roteamento Baseado em Local no Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

