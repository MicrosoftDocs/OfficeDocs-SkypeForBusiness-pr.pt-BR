---
title: 'Lync Server 2013: tabela de registro'
description: 'Lync Server 2013: tabela de registro.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578517"
---
# <a name="registration-table-in-lync-server-2013"></a>Tabela de registro no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

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
<td><p><strong>Identificação_da_sessãotime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primário, Estrangeiro</p></td>
<td><p>Tempo da solicitação de sessão. Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, Estrangeiro</p></td>
<td><p>O número de ID para identificar a sessão. Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>A ID do usuário. Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endpointid</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Um GUID para identificar um ponto de extremidade de registro. Geralmente, o evento de registro do mesmo computador do mesmo usuário terá a mesma ID de ponto de extremidade. Máquinas diferentes possuem uma ID de ponto de extremidade diferente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ponteiro de fim</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>ID usado para diferenciar registros que envolvem o mesmo usuário e o mesmo ponto de extremidade.</p>
<p>Este campo foi introduzido no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Versão do cliente do usuário atual. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Registrador de registro</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>ID do Servidor Registrador usado para registro. Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Poolid</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>A ID do pool no qual a sessão foi capturada. Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Servidor de Borda pelo qual o registro está passando. Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Bits</p></td>
<td></td>
<td><p>Quer o usuário esteja conectado internamente ou não.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bits</p></td>
<td></td>
<td><p>Quer o UserService esteja disponível ou não.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bits</p></td>
<td></td>
<td><p>Quer registre-se no primeiro Registrador ou não.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>bits</p></td>
<td></td>
<td><p>Indica se o usuário é registrado com um Aparelho de Filial Persistente.</p>
<p>Este campo foi introduzido no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>Registertime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Período de registro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cancelar o Registrotime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Período de cancelamento de registro.</p></td>
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
<td><p>ID do diagnóstico da solicitação de registro, que indica o tipo de informação de diagnóstico.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>O dispositivo do qual a solicitação de registro está vindo. Consulte a <a href="lync-server-2013-devices-table.md">tabela de dispositivos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Estrangeira</p></td>
<td><p>O motivo do cancelamento do registro, como ‘iniciado pelo usuário’, ‘registro expirado’, ‘falha do cliente’ e mais. Consulte a <a href="lync-server-2013-deregistertype-table.md">tabela Canregistertype no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Iendereço de IP address do ponto da extremidade que o usuário é registrado. Pode ser um endereço IPv4 ou IPv6 address.</p>
<p>Este campo foi introduzido no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

