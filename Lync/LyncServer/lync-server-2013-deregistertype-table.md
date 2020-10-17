---
title: 'Lync Server 2013: tabela de cancelamento de registro'
description: 'Lync Server 2013: tabela de cancelamento de Registrotype.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afad63c2abeba3e91565e07dac75d0ac6c96ca3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555347"
---
# <a name="deregistertype-table-in-lync-server-2013"></a>Tabela deregistertype no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de cancelamento de registro de usuário, como "cliente iniciado", "registro vencido" ou "cliente não responde".


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
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primário</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Valores permitidos:</p>
<ul>
<li><p>0 -- Desconhecido</p></li>
<li><p>Iniciado o cancelamento do registro pelo cliente</p></li>
<li><p>2 -- Registro expirado</p></li>
<li><p>3 – Client crashed</p></li>
<li><p>Atributos do usuário mudaram</p></li>
<li><p>5 - Registrador preferido mudou</p></li>
<li><p>6 -- Cliente herdado em Modo de sobrevivência</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

