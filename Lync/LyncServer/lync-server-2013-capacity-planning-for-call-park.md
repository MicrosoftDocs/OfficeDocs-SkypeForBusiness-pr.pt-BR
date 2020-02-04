---
title: 'Lync Server 2013: Planejamento de capacidade para Estacionamento de Chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd4cc9d10a3a3562c035c7bc2f64f551b70cc5da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Planejamento de capacidade para Estacionamento de Chamada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-13_

<div id="sectionSection0" class="section">

A tabela a seguir descreve o modelo de usuário do parque de chamadas que você pode usar como base para requisitos de planejamento de capacidade.

<div>


> [!IMPORTANT]  
> Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de manipular as cargas de trabalho para serviços de estacionamento de chamadas em ambos os pools.



</div>

### <a name="call-park-user-model"></a>Modelo de usuário do estacionamento de chamada

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Indicador</th>
<th>Por pool de front-end (com 8 servidores front end)</th>
<th>Por servidor padrão da edição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Taxa de estacionamento</p></td>
<td><p>8 por minuto</p></td>
<td><p>1 por minuto</p></td>
</tr>
<tr class="even">
<td><p>Recuperar a taxa de chamada estacionada</p></td>
<td><p>8 por minuto</p></td>
<td><p>1 por minuto</p></td>
</tr>
<tr class="odd">
<td><p>Duração média do estacionamento</p></td>
<td><p>60 segundos</p></td>
<td><p>60 segundos</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

