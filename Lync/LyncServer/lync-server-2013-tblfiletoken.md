---
title: 'Lync Server 2013: tblFileToken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e3d80b1a326140a94b840c212fc8577a73e468f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a>tblFileToken no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-12_

tblFileToken inclui tokens temporários para fins de transferência de arquivos.

### <a name="columns"></a>Colunas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Tipo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>token de</p></td>
<td><p>nvarchar (50), not null</p></td>
<td><p>Token exclusivo (uma GUID).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenUserID</p></td>
<td><p>int, not null</p></td>
<td><p>ID da entidade de segurança que está transferindo o arquivo.</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenChannelID</p></td>
<td><p>GUID, não vazio</p></td>
<td><p>GUID do nó da sala de chat.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenExpireDate</p></td>
<td><p>datetime, not null</p></td>
<td><p>Tempo de expiração. (Tokens expiram após 30 minutos, a menos que fixado (consultar as descrições a seguir nesta coluna).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceFileUrl</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URL do arquivo transferido (para uso do serviço de Conformidade).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceThumbnailUrl</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URL da miniatura para o arquivo transferido (para uso do serviço de Conformidade).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceTime</p></td>
<td><p>datetime2</p></td>
<td><p>Carimbo de data e hora para a operação de transferência de arquivo atual (para uso do serviço de Conformidade).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceIsUpload</p></td>
<td><p>bits</p></td>
<td><p>Verdadeiro em caso de upload; Falso se download (para uso do serviço de Conformidade).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenCompliancePinned</p></td>
<td><p>bit, não vazio</p></td>
<td><p>Verdadeiro se fixado. É utilizado para manter o token na tabela até que o serviço de Conformidade tenha uma chance de recuperar os campos dele.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Chaves

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>token de</p></td>
<td><p>Chave primária.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenChannelID</p></td>
<td><p>Chave estrangeira com pesquisa na tabela tblNode.nodeGuid.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

