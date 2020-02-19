---
title: 'Lync Server 2013: permissões de implantação para o SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a6697fdb4910b16592ace53e08dcc754cdb2446
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Permissões de implantação para o SQL Server no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

O Microsoft SQL Server 2012 tem requisitos específicos ao instalar e implantar o Lync Server 2013. Como o Windows e o SQL Server definem sua segurança de forma diferente, fazer logon como administrador no domínio do Active Directory não concede implicitamente permissões para o SQL Server. Você também deve ser membro da entidade sysadmin no servidor baseado no SQL Server que está configurando.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Permissões necessárias para a instalação do banco de dados e do Lync Server

As opções a seguir detalham três associações de associação de grupo e permissões para instalação de arquivos do Lync Server 2013 e bancos de dados do SQL Server. Escolha o cenário que melhor atenda às necessidades de sua organização.

### <a name="permissions-and-group-membership-associations"></a>Permissões e associações de membros do grupo

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função do SQL Server ou do Lync Server 2013</th>
<th>Permissões e membros de grupo típicos de função do SQL Server</th>
<th>Função-permissões típicas do Lync Server 2013 e Associação de grupo</th>
<th>Resultado de permissões</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Administrador do Lync Server 2013</p></td>
<td><p>Deve ser concedido a membros do grupo de segurança sysadmins do SQL Server e a membros do grupo Administradores local do SQL Server</p></td>
<td><p>Deve ser um membro do grupo RTCUniversalServerAdmins</p></td>
<td><p>Lync Server 2013 o administrador tem as permissões adequadas para instalar os bancos de dados do Lync Server 2013 e do SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Administrador do SQL Server</p></td>
<td><p>Membro do grupo sysadmin do SQL Server (ou equivalente) e membro do grupo Administradores local do SQL Server</p></td>
<td><p>Deve ser um membro do grupo RTCUniversalServerReadOnly</p></td>
<td><p>O administrador do SQL Server tem as permissões adequadas para instalar os bancos de dados do Lync Server 2013 e do SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Os dois administradores compartilham as tarefas de instalação</p></td>
<td><p>O administrador do SQL Server é membro do grupo de sysadmins (ou equivalente) e membro do grupo Administradores local do SQL Server</p></td>
<td><p>Lync Server 2013 o administrador é membro de RTCUniversalServerAdmins</p></td>
<td><p>O administrador do Lync Server 2013 pode instalar o Lync Server 2013, mas não pode instalar os bancos de dados. O administrador do SQL Server usa o Shell de gerenciamento do Lync Server e os cmdlets do Windows PowerShell fornecidos pelo administrador do Lync Server 2013 para instalar os bancos de dados. O Shell de gerenciamento do Lync Server 2013 usado pelo administrador do SQL Server é instalado no servidor front-end. Isso elimina a necessidade de instalar as ferramentas administrativas do Lync Server 2013 no servidor baseado no SQL Server.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

