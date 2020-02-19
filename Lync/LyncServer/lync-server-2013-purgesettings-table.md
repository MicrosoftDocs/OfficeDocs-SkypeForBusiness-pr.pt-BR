---
title: 'Lync Server 2013: tabela PurgeSettings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c44ad3541b4de3ac45169a01b14b2d571ed11b23
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Tabela PurgeSettings no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

A tabela PurgeSettings contém informações que especificam se (e quando) registros de detalhes de chamada desatualizadas serão automaticamente excluídos do banco de dados CDR. Observe que as informações relacionadas à limpeza também podem ser obtidas no Shell de gerenciamento do Microsoft Lync Server 2013 executando o seguinte comando:

    Get-CsCdrConfiguration

Os administradores devem tratar a tabela PurgeSettings como somente leitura: as alterações nas configurações de limpeza de detalhes da chamada devem ser feitas apenas usando os cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) ou [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

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
<th>Coluna</th>
<th>Tipo de dados</th>
<th>Chave/índice</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Id</strong></p></td>
<td><p>int</p></td>
<td><p>Primário</p></td>
<td><p>Identificador exclusivo da coleção de configurações de limpeza de CDR.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bits</p></td>
<td></td>
<td><p>Quando definido como true (1), o Microsoft Lync Server 2013 limpará periodicamente registros desatualizados do banco de dados CDR. A limpeza ocorrerá todos os dias na hora especificada pela configuração PurgeHour. Se definido como Falso (0), os registros não serão limpados automaticamente do banco de dados. O valor padrão é verdadeiro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica a idade dos registros de CDR (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros de CDR mais antigos do que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica a idade dos registros do relatório de erros (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros do relatório de erros mais antigos do que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica a hora local do dia em que a limpeza ocorrerá. A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00. Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido. O valor padrão é 2 (2:00).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

