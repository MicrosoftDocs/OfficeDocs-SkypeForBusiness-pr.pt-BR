---
title: 'Lync Server 2013: atribuir políticas de presença por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Como atribuir políticas de presença por usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-11_

Uma política de presença é um conjunto de limites e restrições que afetam a presença. A tabela a seguir descreve as configurações de política de presença disponíveis no Lync Server 2013.

### <a name="presence-policy-settings"></a>Configurações da política de presença

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
<th>Nome XML</th>
<th>Nome para exibição</th>
<th>Descrição</th>
<th>Tipo</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>Número máximo de assinaturas de categoria de assinante</p></td>
<td><p>Limita o número de assinaturas de categoria do Assinante. Por exemplo, quando o Communicator assina a presença de um usuário, ele obtém uma assinatura de categoria para cada um dos cartões de visita, dados de calendário, observações, serviços e categorias de estado.</p>
<p>Uma configuração de 0 significa que o objeto de contato ou usuário não pode ser inscrito por outras pessoas.</p>
<div>

> [!NOTE]  
> Essa configuração pode ter um impacto significativo no desempenho se estiver definida como um número alto, e o usuário médio tiver um grande número de usuários assinando sua presença.


</div></td>
<td><p>Positivo</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>Número máximo de alertas de assinatura de presença em fila</p></td>
<td><p>Limita o número de entradas na tabela de assinantes solicitados. Essa configuração determina o número máximo de solicitações que podem ser enfileiradas para um determinado usuário. Por exemplo, quando o usuário assina a presença do usuário B, o usuário B recebe uma solicitação que o usuário A já está inscrito para o usuário B, e um prompt de confirmação é criado na tabela de assinantes solicitados do usuário B. Depois que o usuário B aceita, ou reconhece, a assinatura, o prompt de confirmação é removido da tabela de assinantes solicitados do usuário B.</p>
<p>Uma configuração 0 significa que o usuário não é avisado quando alguém assina sua presença.</p></td>
<td><p>Número inteiro ou token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


Por padrão, a **política** e o **serviço padrão:** as políticas de presença média são instaladas quando você implanta o Lync Server. A tabela a seguir descreve as configurações específicas das duas políticas de presença.

### <a name="presence-policies"></a>Políticas de presença

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome da política</th>
<th>Descrição</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Política padrão</p></td>
<td><p>Política para usuários típicos. Esta é a política de presença padrão.</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>Serviço: médio</p></td>
<td><p>Política para aplicativos que exigem que mais usuários assinem a presença do objeto.</p></td>
<td><p>1000</p></td>
<td><p>0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

