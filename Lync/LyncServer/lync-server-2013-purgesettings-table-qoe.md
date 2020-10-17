---
title: 'Lync Server 2013: tabela PurgeSettings (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac236e08f79adbe1ec7cbe92ea04405de46d0055
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512218"
---
# <a name="purgesettings-table-qoe-in-lync-server-2013"></a>Tabela PurgeSettings (QoE) no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

A tabela PurgeSettings contém informações que especificam se (e quando) os registros de qualidade de experiência defasados serão excluídos automaticamente do banco de dados de QoE. Observe que as informações relacionadas à limpeza também podem ser obtidas no Shell de gerenciamento do Microsoft Lync Server 2013 executando o seguinte comando:

    Get-CsQoEConfiguration

Esta tabela foi introduzida no Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Coluna</strong></th>
<th><strong>Tipo de dados</strong></th>
<th><strong>Chave/índice</strong></th>
<th><strong>Detalhes</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Primário</p></td>
<td><p>Identificador exclusivo do conjunto de configurações de limpeza de QoE.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bits</p></td>
<td></td>
<td><p>Quando definido como true (1), o Microsoft Lync Server 2013 limpará periodicamente registros desatualizados do banco de dados de QoE. A limpeza ocorrerá todos os dias na hora especificada pela configuração PurgeHour. Se definido como Falso (0), os registros não serão limpados automaticamente do banco de dados. O valor padrão é verdadeiro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica a idade dos registros de QoE (em dias) que serão limpados do banco de dados: se a limpeza estiver ativada, os registros de QoE mais antigos que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica a hora local do dia em que a limpeza ocorrerá. A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00. Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido. O valor padrão é 1 (1:00). Especifica a hora local do dia em que a limpeza do banco de dados ocorrerá. A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00. Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido. O valor padrão é 1 (1:00).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

