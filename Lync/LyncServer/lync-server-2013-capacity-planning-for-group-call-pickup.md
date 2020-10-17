---
title: 'Lync Server 2013: planejamento de capacidade para recebimento de chamadas em grupo'
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
ms.openlocfilehash: c073ea360e00b196e6cf30b6bb6f204d37532ae0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512808"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Planejamento de capacidade para recebimento de chamadas em grupo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-12_

<div id="sectionSection0" class="section">

A tabela a seguir descreve o modelo de usuário de recebimento de chamadas de grupo que você pode usar como base para os requisitos de planejamento de capacidade.

<div>


> [!IMPORTANT]  
> O recebimento de chamadas em grupo é baseado no aplicativo de estacionamento de chamada. Tenha em mente que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de lidar com as cargas de trabalho para serviços de estacionamento de chamadas, incluindo o recebimento de chamadas em grupo, em ambos os pools.



</div>

### <a name="group-call-pickup-user-model"></a>Modelo de usuário de recebimento de chamada de grupo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Indicador</th>
<th>Por pool de front-ends (com 8 servidores front-end)</th>
<th>Por servidor Standard Edition</th>
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
<td><p>Número máximo de usuários por pool habilitado para recebimento de chamadas em grupo</p></td>
<td><p>25.000</p></td>
<td><p>3.000</p></td>
</tr>
<tr class="even">
<td><p>Taxa máxima de chamadas de entrada para usuários total habilitados para retirada de chamada de grupo por pool por minuto</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Taxa máxima de chamadas recuperadas por usuários com retirada de chamada de grupo por pool por minuto</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Para pools de front-ends com menos de oito servidores front-end, calcule as métricas linearmente. Por exemplo, se o seu pool de front-ends tiver um servidor front-end, calcule a carga máxima como 1/8 dos valores mostrados na tabela.</P>
> <LI>
> <P>Você pode aumentar ou diminuir o número recomendado de usuários por grupo e número de grupos, desde que não exceda o número máximo de usuários por pool. Por exemplo, seu servidor Standard Edition pode ter 120 grupos com 25 usuários por grupo porque o número de usuários habilitados para o recebimento de chamadas de grupo ainda está dentro do modelo de usuário máximo (ou seja, 120 grupos de 25 usuários é 3.000 usuários habilitados para o recebimento de chamadas de grupo).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

