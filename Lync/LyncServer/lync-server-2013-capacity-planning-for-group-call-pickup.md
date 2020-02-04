---
title: 'Lync Server 2013: planejamento de capacidade para retirada de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d694b20d026d83b4cef37c713e38ab8066e22f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Planejamento de capacidade para retirada de chamadas em grupo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-12_

<div id="sectionSection0" class="section">

A tabela a seguir descreve o modelo de usuário de retirada de chamada de grupo que você pode usar como base para requisitos de planejamento de capacidade.

<div>


> [!IMPORTANT]  
> O recebimento de chamadas em grupo é baseado no aplicativo parque de chamadas. Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de manipular as cargas de trabalho para serviços de Call Park, incluindo o recebimento de chamadas em grupo, em ambos os pools.



</div>

### <a name="group-call-pickup-user-model"></a>Modelo de usuário de retirada de chamadas em grupo

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
<td><p>Número recomendado de usuários por grupo</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Número recomendado de grupos</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Número máximo de usuários por pool ativado para Recebimento de chamada de grupo</p></td>
<td><p>25.000</p></td>
<td><p>3.000</p></td>
</tr>
<tr class="even">
<td><p>Taxa máxima de chamadas recebidas para o total de usuários habilitados para Recebimento de chamada de grupo por pool por minuto</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Taxa máxima de chamadas recuperadas por usuários com Recebimento de chamada de grupo por pool por minuto</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Para pools front-ends com menos de oito servidores front-end, calcule as métricas linearmente. Por exemplo, se o seu pool de front-ends tiver um servidor front-end, calcule a carga máxima como 1/8 dos valores mostrados na tabela.</P>
> <LI>
> <P>Você pode aumentar ou diminuir o número recomendado de usuários por grupo e número de grupos desde que você não exceda o número máximo de usuários por pool. Por exemplo, seu servidor Standard Edition pode ter 120 grupos com 25 usuários por grupo porque o número de usuários habilitados para o recebimento de chamadas em grupo ainda está dentro do modelo de usuário máximo (ou seja, o 120 grupos em que 25 usuários tem 3.000 usuários habilitados para o recebimento de chamadas em grupo).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

