---
title: 'Lync Server 2013: Tabela de registro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a>Tabela de registro no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Cada registro representa um evento de registro de usuário.


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
<td><p><strong>Id_da_sessãotime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Tempo de solicitação de sessão. Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Número de identificação para identificar a sessão. Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>A ID de usuário. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endpointid</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Um GUID para identificar um ponto de extremidade de registro. Geralmente, o evento Register do mesmo computador do mesmo usuário terá a mesma ID de ponto de extremidade. Máquinas diferentes têm uma ID de ponto de extremidade diferente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ponteiro de fim</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>ID usada para diferenciar os registros que envolvem o mesmo usuário e o mesmo ponto de extremidade.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Versão cliente do usuário atual. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Registrador de registro</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID do servidor de registrador usado para registro. Consulte a <a href="lync-server-2013-servers-table.md">tabela servidores no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Poolid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID do pool no qual a sessão foi capturada. Consulte a <a href="lync-server-2013-pools-table.md">tabela de grupos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Servidor de borda no qual o registro está indo. Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Se o usuário está conectado de Internal ou not.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Se o UserService está disponível ou não.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Se registrar ao registrador principal ou não.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica se o usuário está ou não registrado em um aparelho de ramificação sobreviventes.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Registertime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora do registro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cancelar registro</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora de cancelamento de registro.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Código de resposta da solicitação de registro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnosticid</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID do diagnóstico da solicitação de registro. Isso indica que o tipo de informações de diagnóstico.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>O dispositivo do qual a solicitação de registro provém. Consulte a <a href="lync-server-2013-devices-table.md">tabela de dispositivos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Exterior</p></td>
<td><p>O motivo do cancelamento de registro, como ' iniciado pelo usuário ', ' registro expirado ', ' falha do cliente ' e muito mais. Consulte a <a href="lync-server-2013-deregistertype-table.md">tabela Canregistertype no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Endereço IP do ponto de extremidade ao qual o usuário se cadastrou. Pode ser um endereço IPv4 ou um endereço IPv6.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

