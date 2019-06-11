---
title: 'Lync Server 2013: tabela PurgeSettings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b9fc0aa03596677cb73641ed46e86ea133f308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Tabela PurgeSettings no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

A tabela PurgeSettings contém informações que especificam se (e quando) registros de detalhes de chamadas desatualizados serão automaticamente excluídos do banco de dados CDR. Observe que as informações relacionadas à remoção também podem ser obtidas dentro do Shell de gerenciamento do Microsoft Lync Server 2013 executando o seguinte comando:

    Get-CsCdrConfiguration

Os administradores devem tratar a tabela PurgeSettings como somente leitura: as alterações nas configurações de limpeza de detalhes da chamada devem ser feitas somente usando cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) ou [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

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
<td><p><strong>%</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Identificador exclusivo da coleção de configurações de limpeza de CDR.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Quando definido como true (1), o Microsoft Lync Server 2013 limpará periodicamente registros desatualizados do banco de dados CDR. A limpeza ocorrerá a cada dia no Tomé especificado pela configuração PurgeHour. Se definido como falso (0), os registros não serão automaticamente limpos do banco de dados. O valor padrão é True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica a idade dos registros CDR (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros CDR mais antigos do que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica a idade dos registros de relatório de tempo (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros de relatório de erros anteriores a esse valor serão removidos do banco de dados. O valor padrão é 60 dias.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Especifica a hora local do dia em que a limpeza do banco de dados ocorrerá. O horário é especificado utilizando-se um relógio de 24 horas, onde 0 representa a meia-noite (00:00) e 23 representa 23 horas. Observe que você só pode especificar a hora do dia: é permitido um valor de 10 (indicando 10:00 AM), mas um valor de 10:30 de 10,5 (indicando 10:30 AM) não é permitido. O valor padrão é 2 (2:00).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

