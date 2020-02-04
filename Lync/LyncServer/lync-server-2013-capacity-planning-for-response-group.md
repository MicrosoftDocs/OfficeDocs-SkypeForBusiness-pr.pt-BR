---
title: 'Lync Server 2013: Planejamento de capacidade para Grupo de Resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efb1b928ce7b4bafbbff20ad31872fe12735fe0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Planejamento de capacidade para Grupo de Resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

<div id="sectionSection0" class="section">

A tabela a seguir descreve o modelo de usuário do grupo de resposta que você pode usar como base para requisitos de planejamento de capacidade.

<div>


> [!NOTE]  
> Os números na tabela a seguir pressupõem que você use arquivos Wave de 16 bits (. wav) de 16 bits para todos os arquivos de áudio do grupo de resposta. Se você usar outros formatos de arquivo, como o áudio do Windows Media (. WMA), os números podem variar.



</div>

<div>


> [!IMPORTANT]  
> Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de manipular as cargas de trabalho para todos os grupos de resposta em ambos os pools.



</div>

### <a name="response-group-user-model"></a>Modelo de usuário do grupo de resposta

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Indicador</th>
<th>Por pool de edição para empresas (com 8 servidores front end)</th>
<th>Por servidor padrão da edição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas recebidas por segundo</p></td>
<td><p>16</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Chamadas simultâneas conectadas ao IVR ou MoH</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Sessões anônimas simultâneas (sem mensagens instantâneas)</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>Sessões anônimas simultâneas (com mensagens instantâneas)</p></td>
<td><p>64</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>Agentes ativos (formais e informais)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>Número de grupos de busca</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>Número de grupos IVR (usar reconhecimento de fala)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

