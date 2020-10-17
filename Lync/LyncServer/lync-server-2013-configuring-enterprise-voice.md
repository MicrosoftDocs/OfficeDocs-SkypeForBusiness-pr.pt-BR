---
title: 'Lync Server 2013: Configurando o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca998a723e4ef84fc1c203d6eddc5f9016f28739
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532548"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Configurando o Enterprise Voice no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-12_

Para implantar o Enterprise Voice, você precisará configurar o seguinte:

  - Criar um tronco

  - Definir uma política de voz

  - Definir uma rota de voz

  - Habilitar usuários para o Enterprise Voice

<div>

## <a name="create-a-trunk"></a>Criar um tronco

Você deve definir troncos em sua implantação do Enterprise Voice. Para Location-Based roteamento, você deve criar uma configuração de tronco por tronco. Use o construtor de topologias do Lync Server para definir seus troncos e use o comando do Lync Server Windows PowerShell, New-CsTrunkConfiguration ou o painel de controle do Lync Server para definir as configurações de tronco correspondentes. É possível encontrar mais informações sobre como habilitar o roteamento de Location-Based nas configurações de tronco na seção, habilitar Location-Based roteamento para troncos, no tópico, [habilitando Location-Based roteamento no Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). Neste exemplo, a tabela a seguir ilustra os troncos usados neste cenário.

Para obter mais informações, consulte [definir troncos adicionais no construtor de topologias no Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome do tronco</th>
<th>Tipo de sistema</th>
<th>Nome</th>
<th>Local</th>
<th>Servidor de Mediação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tronco 1 DEL-GW</p></td>
<td><p>Gateway PSTN</p></td>
<td><p>DEL-GW</p></td>
<td><p>Déli</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Tronco 2 HYD-GW</p></td>
<td><p>Gateway PSTN</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Tronco 3 DEL-PBX</p></td>
<td><p>RESPECTIVA</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Déli</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Tronco 4 HYD-PBX</p></td>
<td><p>RESPECTIVA</p></td>
<td><p>HYD-PBX</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>Define políticas de voz

Você deve definir políticas de voz para a implantação do Enterprise Voice. Defina uma política de voz para impor restrições de roteamento Location-Based a um subconjunto de usuários se apenas um subconjunto deles for necessário para usar o roteamento Location-Based. Neste exemplo, a tabela a seguir ilustra as políticas de voz usadas neste cenário. Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.

Para saber mais, confira [Configurando políticas de voz e registros de uso de PSTN para autorizar recursos e privilégios de chamada no Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Política de voz 1</th>
<th>Política de voz 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID da política de voz</p></td>
<td><p>Política de voz de Delhi</p></td>
<td><p>Política de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de PSTN</p></td>
<td><p>Uso de Delhi, uso de PBX, uso do PBX Hyd</p></td>
<td><p>Uso do Hyderabad, uso do PBX Hyd, uso do PBX</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>Falso</p></td>
<td><p>Falso</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>Definir rotas de voz

Você deve definir rotas de voz para sua implantação do Enterprise Voice. Neste exemplo, a tabela a seguir ilustra as rotas de voz usadas neste cenário. Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.

Para obter mais informações, consulte [Configurando rotas de voz para chamadas de saída no Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Rota de voz 1</th>
<th>Rota de voz 2</th>
<th>Rota de voz 3</th>
<th>Rota de voz 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome</p></td>
<td><p>Rota de Déli</p></td>
<td><p>Rota Hyderabad</p></td>
<td><p>Rota de del do PBX</p></td>
<td><p>Rota de Hyd PBX</p></td>
</tr>
<tr class="even">
<td><p>Usos de PSTN</p></td>
<td><p>Uso de Delhi</p></td>
<td><p>Uso do Hyderabad</p></td>
<td><p>Uso do PBX del</p></td>
<td><p>Uso do Hyd PBX</p></td>
</tr>
<tr class="odd">
<td><p>Trunk</p></td>
<td><p>Tronco 1 DEL-GW</p></td>
<td><p>Tronco 2 HYD-GW</p></td>
<td><p>Tronco 3 DEL-PBX</p></td>
<td><p>Tronco 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Habilitar usuários para o Enterprise Voice

Habilite usuários para o Enterprise Voice e atribua a eles uma política de voz que você tenha definido anteriormente. Neste exemplo, a tabela a seguir ilustra a atribuição usada neste cenário. Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.

Para obter mais informações, consulte [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Usuários localizados em Delhi</th>
<th>Usuários localizados no Hyderabad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Política de voz associada</p></td>
<td><p>Política de voz de Delhi</p></td>
<td><p>Política de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usuários de exemplo</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando o roteamento de Location-Based no Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

